---
title: "Creating a Batch Request in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Creating a Batch Request in C# #
This example shows how to create a batch request that can contain thousands of insert, get, and delete operations using C#. The example uses the CodeGrantFlow class shown in [Authenticating Microsoft Account Credentials in C#](../shopping-content/authentication-oauth-csharp.md) example.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.IO.Compression;
using System.Threading.Tasks;
using System.Net;
using Content.OAuth;
using Newtonsoft.Json;           // NuGet Json.NET

namespace Batch
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<CLIENTIDGOESHERE>";
        private static string clientSecret = "<CLIENTSECRETGOESHERE>";
        private static string storedRefreshToken = "<REFRESHTOKENGOESHERE OR NULL";
        private static CodeGrantOauth tokens = null;
        private static DateTime tokenExpiration;

        private static string devToken = "<DEVELOPERTOKENGOESHERE>";

        // URI templates used to get resources.

        public const string BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
        public static string BmcUri = BaseUri + "/bmc/{0}";
        public static string BatchUri = BmcUri + "/products/batch";

        // Query strings

        public static string queryString = "?bmc-catalog-id={1}&alt=json";

        // Replace with your store ID and catalog ID.

        public static long merchantId = <STOREIDGOESHERE>;
        public static long catalogId = <CATALOGIDGOESHERE>;

        // Used in example to store operation ids.
        
        public static List<string> ProductList = new List<string>();
        public static int batchOperationId = 0;

        // The maximum number of objects that you can specify depends upon
        // the number of product attributes that you specify and whether you 
        // compress the data. If you do not compress the data, 
        // you can specify about 2,000 objects; otherwise, you can specify 
        // about 12,000 objects.
 
        // For this example, limit the list to 5 products.

        public const int MAX_ENTRIES = 5;


        static void Main(string[] args)
        {
            try
            {
                var headers = GetCredentialHeaders();

                // Build URL with query string and store id.

                var url = string.Format(BatchUri + queryString, merchantId, catalogId);

                // A batch operation may include any operation (insert, get, delete);
                // however, because the operations may not act on the same product,
                // this example performs the batch operations separately.

                BatchInsert(url, headers);
                BatchGet(url, headers);
                BatchDelete(url, headers);
            }
            catch (WebException e)
            {
                Console.WriteLine("\n" + e.Message);

                HttpWebResponse response = (HttpWebResponse)e.Response;

                // If the request is bad, the API returns the errors in the 
                // body of the request. For cases where the path may be valid, but
                // the resource does not belong to the user, the API returns not found.

                if (response != null &&
                    (HttpStatusCode.BadRequest == response.StatusCode ||
                     HttpStatusCode.NotFound == response.StatusCode ||
                     HttpStatusCode.InternalServerError == response.StatusCode))
                {
                    using (Stream stream = response.GetResponseStream())
                    {
                        StreamReader reader = new StreamReader(stream);
                        string json = reader.ReadToEnd();
                        reader.Close();

                        try
                        {
                            var errors = JsonConvert.DeserializeObject<ContentError>(json);

                            PrintErrors(errors.Error.Errors);
                        }
                        catch (Exception deserializeError)
                        {
                            // This case occurs when the path is not valid.

                            if (HttpStatusCode.NotFound == response.StatusCode)
                            {
                                Console.WriteLine("Path not found: " + response.ResponseUri);
                            }
                            else
                            {
                                Console.WriteLine(deserializeError.Message);
                            }
                        }
                    }
                }
            }
            catch (Exception e)
            {
                Console.WriteLine("\n" + e.Message);
            }

        }

        // Use the BatchCollection object and POST operation to create multiple Content API operations.
        // This example uses compression.
        
        private static BatchCollection BatchRequest(string uri, WebHeaderCollection headers, BatchCollection batchCollection)
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "POST";
            request.Headers = headers;
            request.Headers.Add("Content-Encoding", "gzip");
            request.AutomaticDecompression = DecompressionMethods.GZip;
            request.ContentType = "application/json";

            var serializerSettings = new JsonSerializerSettings();
            serializerSettings.NullValueHandling = NullValueHandling.Ignore;

            var json = JsonConvert.SerializeObject(batchCollection, serializerSettings);

            using (Stream requestStream = request.GetRequestStream())
            {
                var buffer = Encoding.UTF8.GetBytes(json);

                using (GZipStream compressionStream = new GZipStream(requestStream, CompressionMode.Compress, true))
                {
                    compressionStream.Write(buffer, 0, buffer.Length);
                }
            }

            var response = (HttpWebResponse)request.GetResponse();
            BatchCollection batchOut = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                batchOut = JsonConvert.DeserializeObject<BatchCollection>(jsonOut);
            }

            return batchOut;
        }

        // Add 5 products to the catalog. Write the IDs to a list that's used in BatchGet
        // and BatchDelete.

        private static void BatchInsert(string url, WebHeaderCollection headers)
        {
            var batchCollection = new BatchCollection();
            batchCollection.Entries = new List<BatchEntry>();

            for (var i = 0; i < MAX_ENTRIES; i++)
            {
                var product = GetProduct();
                product.OfferId = i.ToString();
                var batchEntry = new BatchEntry(i, merchantId, "insert", null, product);
                batchCollection.Entries.Add(batchEntry);
            }

            // If you try to insert too many products, the call fails with status code 413.

            var batchOut = BatchRequest(url, headers, batchCollection);

            for (var i = 0; i < batchOut.Entries.Count; i++)
            {
                if (batchOut.Entries[i].Error != null)
                {
                    Console.WriteLine("Failed to insert product {0}.", 
                        batchCollection.Entries[(int)(batchOut.Entries[i].BatchId)].Product.OfferId);
                    PrintErrors(batchOut.Entries[i].Error.Errors);
                }
                else
                {
                    Console.WriteLine("Inserted product " + batchOut.Entries[i].Product.Id);
                    ProductList.Add(batchOut.Entries[i].Product.Id);
                }
            }
        }

        // Use GET operation on the products inserted by BatchInsert.

        private static void BatchGet(string url, WebHeaderCollection headers)
        {
            var batchCollection = new BatchCollection();
            batchCollection.Entries = new List<BatchEntry>();
            batchOperationId = 0;

            foreach (string productId in ProductList)
            {
                var batchEntry = new BatchEntry(batchOperationId++, merchantId, "get", productId, null);
                batchCollection.Entries.Add(batchEntry);
            }

            var batchOut = BatchRequest(url, headers, batchCollection);

            for (var i = 0; i < batchOut.Entries.Count; i++)
            {
                if (batchOut.Entries[i].Error != null)
                {
                    Console.WriteLine("Failed to get product {0}.", 
                        batchCollection.Entries[(int)(batchOut.Entries[i].BatchId)].ProductId);
                    PrintErrors(batchOut.Entries[i].Error.Errors);
                }
                else
                {
                    if (batchOut.Entries[i].Product == null)
                    {
                        Console.WriteLine("Product {0} was not found.",
                            batchCollection.Entries[(int)(batchOut.Entries[i].BatchId)].ProductId);
                    }
                    else
                    {
                        PrintProduct(batchOut.Entries[i].Product);
                        Console.WriteLine();
                    }
                }
            }
        }

        // Use DELETE operation on the products inserted in BatchInsert.

        private static void BatchDelete(string url, WebHeaderCollection headers)
        {
            var batchCollection = new BatchCollection();
            batchCollection.Entries = new List<BatchEntry>();
            batchOperationId = 0;

            foreach (string productId in ProductList)
            {
                var batchEntry = new BatchEntry(batchOperationId++, merchantId, "delete", productId, null);
                batchCollection.Entries.Add(batchEntry);
            }

            var batchOut = BatchRequest(url, headers, batchCollection);

            for (var i = 0; i < batchOut.Entries.Count; i++)
            {
                if (batchOut.Entries[i].Error != null)
                {
                    Console.WriteLine("Failed to delete product {0}.", 
                        batchCollection.Entries[(int)(batchOut.Entries[i].BatchId)].ProductId);
                    PrintErrors(batchOut.Entries[i].Error.Errors);
                }
                else
                {
                    Console.WriteLine("Deleted product " + batchCollection.Entries[i].ProductId);
                }
            }
        }


        // This example creates a single product that it adds to the store.
        // The calling code overwrites offerId to ensure a new product is added.

        private static Product GetProduct()
        {
            var product = new Product()
            {
                // The following properties are required.

                Availability = "in stock",
                Channel = Channel.Online.ToString(),
                Condition = Condition.New.ToString(),
                ContentLanguage = "en",
                Link = "http://www.contoso.com/apparel/men/tshirts.htm",
                ImageLink = "http://www.contoso.com/pics/tees.jpg",
                OfferId = "1",
                Price = new Price()
                {
                    Currency = "USD",
                    Value = (decimal)12.00
                },
                TargetCountry = "US",
                Title = "Mens T-Shirt",

                // If the manufacturer provides identifiers for brand, gtin
                // or mpn, you must set those fields, and set identifierExists
                // to true.
                
                IdentifierExists = false;
                
                // The following properties are optional.

                ExpirationDate = DateTime.UtcNow.AddDays(45).ToString("O")  // "2016-06-03T20:47:27.0437485Z"

                //SalePriceEffectiveDate = string.Format("{0:O}/{1:O}", 
                //    DateTime.UtcNow, DateTime.UtcNow.AddDays(10)),
                //ProductType = "Sporting Goods > Mens Shirts > Mens T-Shirts",
            };

            return product;
        }


        // Print out some field of the product offer.
        
        private static void PrintProduct(Product product)
        {
            Console.WriteLine("qualifiedProductId: " + product.Id);
            Console.WriteLine("channel : " + product.Channel);
            Console.WriteLine("language: " + product.ContentLanguage);
            Console.WriteLine("country: " + product.TargetCountry);
            Console.WriteLine("productId: " + product.OfferId);
            Console.WriteLine("expiry date: " + product.ExpirationDate);

            Console.WriteLine("title: " + product.Title);

            if (product.Price != null)
            {
                Console.WriteLine("price: {0} {1}", product.Price.Value, product.Price.Currency);
            }
        }

        // Print errors.
        
        private static void PrintErrors(List<Error> errors)
        {
            foreach (Error error in errors)
            {
                Console.WriteLine("reason: {0}\nmessage: {1}\nlocation type: {2}\nlocation: {3}\n",
                    error.Reason, error.Message, error.LocationType, error.Location);
            }
        }


        // Gets the AuthenticationToken and DeveloperToken headers 
        // that are required to call the API. This example use OAuth
        // instead of using the legacy credentials (username and password).

        private static WebHeaderCollection GetCredentialHeaders()
        {
            // TODO: Add logic to get the logged on user's refresh token 
            // from secured storage. 

            tokens = GetOauthTokens(storedRefreshToken);

            var headers = new WebHeaderCollection();
            headers.Add("AuthenticationToken", tokens.AccessToken);
            headers.Add("DeveloperToken", devToken);

            return headers;
        }

        // Gets the OAuth tokens. If the refresh token doesn't exist, get 
        // the user's consent and a new access and refresh token.
        private static CodeGrantOauth GetOauthTokens(string refreshToken)
        {
            CodeGrantOauth auth = null;

            if (string.IsNullOrEmpty(refreshToken))
            {
                auth = new CodeGrantOauth(clientId, clientSecret);
                auth.GetAccessToken();
            }
            else
            {
                auth = new CodeGrantOauth(clientId, clientSecret);
                auth.RefreshAccessToken(refreshToken);

                // Refresh tokens can become invalid for several reasons
                // such as the user's password changed.

                if (!string.IsNullOrEmpty(auth.Error))
                {
                    auth = GetOauthTokens(null);
                }
            }

            // TODO: Store the new refresh token in secured storage
            // for the logged on user.

            storedRefreshToken = auth.RefreshToken;
            tokenExpiration = DateTime.Now.AddSeconds(auth.Expiration);

            return auth;
        }

    }

    // Defines the BMC classes.

    class BatchCollection
    {
        [JsonProperty("entries")]
        public List<BatchEntry> Entries { get; set; }
    }

    class BatchEntry
    {
        public BatchEntry() { }

        public BatchEntry(int batchId, long merchantId, string method, string productId, Product product)
        {
            this.BatchId = batchId;
            this.MerchantId = merchantId;
            this.Method = method;
            this.ProductId = productId;
            this.Product = product;
        }

        [JsonProperty("batchId")]
        public long BatchId { get; set; }

        [JsonProperty("merchantId")]
        public long MerchantId { get; set; }

        [JsonProperty("method")]
        public string Method { get; set; }

        [JsonProperty("productId")]
        public string ProductId { get; set; }

        [JsonProperty("product")]
        public Product Product { get; set; }

        [JsonProperty("errors")]
        public BatchItemError Error { get; set; }
    }


    // Defines a product resource.
    
    public class Product
    {
        public Product() { }

        [JsonProperty("additionalImageLinks")]
        public List<string> AdditionalImageLinks { get; set; }

        [JsonProperty("adult")]
        public bool? IsAdult { get; set; }

        [JsonProperty("adwordsGrouping")]
        public string AdwordsGrouping { get; set; }

        [JsonProperty("adwordsLabels")]
        public List<string> AdwordsLabels { get; set; }

        [JsonProperty("adwordsRedirect")]
        public string AdwordsRedirect { get; set; }

        [JsonProperty("ageGroup")]
        public string AgeGroup { get; set; }

        [JsonProperty("availability")]
        public string Availability { get; set; }

        [JsonProperty("availabilityDate")]
        public string AvailabilityDate { get; set; }

        [JsonProperty("brand")]
        public string Brand { get; set; }

        [JsonProperty("channel")]
        public string Channel { get; set; }

        [JsonProperty("color")]
        public string Color { get; set; }

        [JsonProperty("condition")]
        public string Condition { get; set; }


        [JsonProperty("contentLanguage")]
        public string ContentLanguage { get; set; }

        [JsonProperty("customAttributes")]
        public List<ProductCustomAttribute> CustomAttributes { get; set; }

        [JsonProperty("customGroups")]
        public List<ProductCustomGroup> CustomGroups { get; set; }

        [JsonProperty("customLabel0")]
        public string CustomLabel0 { get; set; }

        [JsonProperty("customLabel1")]
        public string CustomLabel1 { get; set; }

        [JsonProperty("customLabel2")]
        public string CustomLabel2 { get; set; }

        [JsonProperty("customLabel3")]
        public string CustomLabel3 { get; set; }

        [JsonProperty("customLabel4")]
        public string CustomLabel4 { get; set; }

        [JsonProperty("description")]
        public string Description { get; set; }

        [JsonProperty("destinations")]
        public List<ProductDestination> Destinations { get; set; }

        [JsonProperty("energyEfficiencyClass")]
        public string EnergyEfficiencyClass { get; set; }

        [JsonProperty("expirationDate")]
        public string ExpirationDate { get; set; }

        [JsonProperty("gender")]
        public string Gender { get; set; }

        [JsonProperty("googleProductCategory")]
        public string GoogleProductCategory { get; set; }

        [JsonProperty("gtin")]
        public string Gtin { get; set; }

        [JsonProperty("id")]
        public string Id { get; set; }

        [JsonProperty("identifierExists")]
        public bool? IdentifierExists { get; set; }

        [JsonProperty("imageLink")]
        public string ImageLink { get; set; }

        [JsonProperty("isBundle")]
        public bool? IsBundle { get; set; }

        [JsonProperty("itemGroupId")]
        public string ItemGroupId { get; set; }

        [JsonProperty("kind")] ////For example: "kind":"content#product"
        public string Kind { get; set; }

        [JsonProperty("link")]
        public string Link { get; set; }

        [JsonProperty("material")]
        public string Material { get; set; }

        [JsonProperty("multipack")]
        public ulong? MerchantMultipackQuantity { get; set; }

        [JsonProperty("mobileLink")]
        public string MobileLink { get; set; }

        [JsonProperty("mpn")]
        public string Mpn { get; set; }

        [JsonProperty("offerId")]
        public string OfferId { get; set; }

        [JsonProperty("onlineOnly")]
        public bool? OnlineOnly { get; set; }

        [JsonProperty("pattern")]
        public string Pattern { get; set; }

        [JsonProperty("price")]
        public Price Price { get; set; }

        [JsonProperty("productType")]
        public string ProductType { get; set; }

        [JsonProperty("salePrice")]
        public Price SalePrice { get; set; }

        [JsonProperty("salePriceEffectiveDate")]
        public string SalePriceEffectiveDate { get; set; }

        [JsonProperty("shipping")]
        public List<ProductShipping> Shipping { get; set; }

        [JsonProperty("shippingWeight")]
        public ProductShippingWeight ShippingWeight { get; set; }

        [JsonProperty("shippingLabel")]
        public string ShippingLabel { get; set; }

        [JsonProperty("sizes")]
        public List<string> Sizes { get; set; }

        [JsonProperty("sizeSystem")]
        public string SizeSystem { get; set; }

        [JsonProperty("sizeType")]
        public string SizeType { get; set; }

        [JsonProperty("targetCountry")]
        public string TargetCountry { get; set; }

        [JsonProperty("taxes")]
        public List<ProductTax> Taxes { get; set; }

        [JsonProperty("title")]
        public string Title { get; set; }

        [JsonProperty("unitPricingBaseMeasure")]
        public UnitPricing UnitPricingBaseMeasure { get; set; }

        [JsonProperty("unitPricingMeasure")]
        public UnitPricing UnitPricingMeasure { get; set; }

        [JsonProperty("validatedDestinations")]
        public List<string> ValidatedDestinations { get; set; }
    }

    // Defines a product's price.
    
    public class Price
    {
        [JsonProperty("currency")]
        public string Currency { get; set; }

        [JsonProperty("value")]
        public decimal? Value { get; set; }
    }

    // Defines a product's tax.
    
    public class ProductTax
    {
        [JsonProperty("country")]
        public string Country { get; set; }

        [JsonProperty("locationId")]
        public long? LocationId { get; set; }

        [JsonProperty("postalCode")]
        public string PostalCode { get; set; }

        [JsonProperty("rate")]
        public double? Rate { get; set; }

        [JsonProperty("region")]
        public string Region { get; set; }

        [JsonProperty("taxShip")]
        public bool? TaxShip { get; set; }
    }

    // Defines a product's shipping weight.
    
    public class ProductShippingWeight
    {
        [JsonProperty("unit")]
        public string Unit { get; set; }

        [JsonProperty("value")]
        public double? Value { get; set; }
    }

    // Defines a product's shipping cost.
    
    public class ProductShipping
    {
        [JsonProperty("country")]
        public string Country { get; set; }

        [JsonProperty("locationGroupName")]
        public string LocationGroupName { get; set; }

        [JsonProperty("locationId")]
        public long? LocationId { get; set; }

        [JsonProperty("postalCode")]
        public string PostalCode { get; set; }

        [JsonProperty("price")]
        public Price Price { get; set; }

        [JsonProperty("region")]
        public string Region { get; set; }

        [JsonProperty("service")]
        public string Service { get; set; }
    }

    // Defines per unit pricing.
    
    public class UnitPricing
    {
        [JsonProperty("unit")]
        public string Unit { get; set; }

        [JsonProperty("value")]
        public double Value{ get; set; }
    }

    // Defines a destination.
    
    public class ProductDestination
    {
        [JsonProperty("destinationName")]
        public string DestinationName { get; set; }

        [JsonProperty("intention")]
        public string Intention { get; set; }
    }

    // Defines a product's custom attribute.
    
    public class ProductCustomAttribute
    {
        [JsonProperty("name")]
        public string Name { get; set; }

        [JsonProperty("type")]
        public string Type { get; set; }

        [JsonProperty("unit")]
        public string Unit { get; set; }

        [JsonProperty("value")]
        public string Value { get; set; }
    }

    // Defines a custom group of attributes.
    
    public class ProductCustomGroup
    {
        [JsonProperty("customGroups")]
        public List<ProductCustomAttribute> Attributes { get; set; }

        [JsonProperty("name")]
        public string Name { get; set; }
    }

    // Defines the BMC enumerations.

    public enum Channel
    {
        Online,
        Local
    }

    public enum AgeGroup
    {
        Adult,
        Kids,
        Toddler,
        Infant,
        Newborn
    }

    public enum Condition
    {
        New,
        Refurbished,
        Used
    }

    public enum Gender
    {
        Female,
        Male,
        Unisex
    }

    public enum ApparelCut
    {
        Regular,
        Maternity,
        Petite,
        Oversize
    }

    public enum Intention
    {
        Default,
        Excluded,
        Optional,
        Required
    }

    public enum AttributeType
    {
        Boolean,
        DateTimeRange,
        Float,
        Group,
        Int,
        Price,
        Text,
        Time,
        URL
    }

    public enum AttributeUnit
    {
        Int,
        Float
    }

    // Classes used to handle errors.
    
    public class Error
    {
        [JsonProperty("location")]
        public string Location { get; set; }

        [JsonProperty("locationType")]
        public string LocationType { get; set; }

        [JsonProperty("domain")]
        public string Domain { get; set; }

        [JsonProperty("message")]
        public string Message { get; set; }

        [JsonProperty("reason")]
        public string Reason { get; set; }
    }

    public class ErrorCollection
    {
        [JsonProperty("code")]
        public string Code { get; set; }

        [JsonProperty("errors")]
        public List<Error> Errors { get; set; }

        [JsonProperty("message")]
        public string Message { get; set; }

    }

    public class ContentError
    {
        [JsonProperty("error")]
        public ErrorCollection Error { get; set; }
    }

    public class BatchItemError
    {
        [JsonProperty("errors")]
        public List<Error> Errors { get; set; }
    }

}
```
