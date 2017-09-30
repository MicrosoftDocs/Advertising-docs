---
title: "Getting a List of Product Offers in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Getting a List of Product Offers in C# #
This example shows how to get a list of product offers from the store using C#. The example uses the CodeGrantFlow class shown in [Authenticating Microsoft Account Credentials in C#](../shopping-content/authentication-oauth-csharp.md) example.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Threading.Tasks;
using System.Net;
using Content.OAuth;
using Newtonsoft.Json;           // NuGet Json.NET

namespace List
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<CLIENTIDGOESHERE>";
        private static string clientSecret = "<CIENTSECRETHGOESHERE>";
        private static string storedRefreshToken = "<REFRESHTOKENGOESHERE OR NULL>";
        private static CodeGrantOauth tokens = null;
        private static DateTime tokenExpiration;

        private static string devToken = <DEVTOKENGOESHERE>;

        // URI templates used to get resources.
        
        public const string BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
        public static string BmcUri = BaseUri + "/bmc/{0}";
        public static string ListUri = BmcUri + "/products";

        // Query strings.
        // Used to get the first page of results.
        
        public static string queryString = "?max-results=250&alt=json";
        
        // Used to get subsequent pages.
        
        public static string queryStringWithStartToken = "?max-results=250&start-token={1}&alt=json";

        // Replace with your store ID.
        
        public static long merchantId = <STOREIDGOESHERE>;


        static void Main(string[] args)
        {
            try
            {
                var headers = GetCredentialHeaders();

                // Build URL with query string and store id.

                var url = string.Format(ListUri + queryString, merchantId);

                while (url != null)
                {
                    // Get list of products.

                    var products = GetResource(url, headers, typeof(ProductCollection)) as ProductCollection;

                    foreach (var product in products.Resources)
                    {
                        PrintProduct(product);
                        Console.WriteLine();
                    }

                    // Build URI for subsequent pages.

                    if (products.nextPageToken != null)
                    {
                        url = string.Format(ListUri + queryStringWithStartToken, 
                                            merchantId,
                                            products.nextPageToken);
                    }
                    else
                    {
                        url = null;
                    }
                }

            }
            catch (WebException e)
            {
                Console.WriteLine("\n" + e.Message);

                HttpWebResponse response = (HttpWebResponse)e.Response;

                // If the request is bad, the API returns the errors in the 
                // body of the request. For cases where the path may be valid, but
                // the resource does not belong to the user, the API returns not found.

                if (HttpStatusCode.BadRequest == response.StatusCode ||
                    HttpStatusCode.NotFound == response.StatusCode ||
                    HttpStatusCode.InternalServerError == response.StatusCode)
                {
                    using (Stream stream = response.GetResponseStream())
                    {
                        StreamReader reader = new StreamReader(stream);
                        string json = reader.ReadToEnd();
                        reader.Close();

                        try
                        {
                            var errors = JsonConvert.DeserializeObject<ContentError>(json);

                            PrintErrors(errors);
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


        // Gets the requested product offer.
        
        private static object GetResource(string uri, WebHeaderCollection headers, Type resourceType)
        {
            object resource = null;
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "GET";
            request.Headers = headers;
            request.Accept = "application/json";
            var response = (HttpWebResponse)request.GetResponse();

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                string json = reader.ReadToEnd();
                reader.Close();
                resource = JsonConvert.DeserializeObject(json, resourceType);
            }

            return resource;
        }

        // Print out each field of a product object.

        private static void PrintProduct(Product product)
        {
            Console.WriteLine("qualifiedProductId: " + product.Id);
            Console.WriteLine("channel : " + product.Channel);
            Console.WriteLine("language: " + product.ContentLanguage);
            Console.WriteLine("country: " + product.TargetCountry);
            Console.WriteLine("productId: " + product.OfferId);
            Console.WriteLine("expiry date: " + product.ExpirationDate);

            Console.WriteLine("title: " + product.Title);
            Console.WriteLine("description: " + product.Description);

            if (product.Price != null)
            {
                Console.WriteLine("price: {0} {1}", 
                     product.Price.Value, 
                     product.Price.Currency);
            }

            if (product.SalePrice != null)
            {
                Console.WriteLine("sale effective date: " + product.SalePriceEffectiveDate);
                Console.WriteLine("sale price: {0} {1}", 
                     product.SalePrice.Value, 
                     product.SalePrice.Currency);
            }
            Console.WriteLine("unit pricing base: " + product.UnitPricingBaseMeasure);
            Console.WriteLine("unit pricing measure: " + product.UnitPricingMeasure);

            Console.WriteLine("url: " + product.Link);
            Console.WriteLine("mobile link: " + product.MobileLink);
            Console.WriteLine("imageUrl: " + product.ImageLink);
            Console.WriteLine("additional images: ");
            if (product.AdditionalImageLinks != null)
            {
                foreach (var url in product.AdditionalImageLinks)
                {
                    Console.WriteLine("\t" + url);
                }
            }
            Console.WriteLine("product type: " + product.ProductType);
            Console.WriteLine("isAdult: " + product.IsAdult);

            Console.WriteLine("availability: " + product.Availability);
            if (product.Availability != "in stock")
            {
                Console.WriteLine("date available: " + product.AvailabilityDate);
            }

            Console.WriteLine("brand: " + product.Brand);
            Console.WriteLine("GTIN: " + product.Gtin);
            Console.WriteLine("MPN: " + product.Mpn);

            Console.WriteLine("age group:" + product.AgeGroup);
            Console.WriteLine("gender: " + product.Gender);
            Console.WriteLine("color: " + product.Color);
            Console.WriteLine("condition: " + product.Condition);
            Console.WriteLine("material: " + product.Material);
            Console.WriteLine("pattern: " + product.Pattern);
            Console.WriteLine("sizes: ");
            if (product.Sizes != null)
            {
                foreach (var size in product.Sizes)
                {
                    Console.WriteLine("\t" + size);
                }

                Console.WriteLine("sizing system: " + product.SizeSystem);
                Console.WriteLine("size type: " + product.SizeType);
            }
            Console.WriteLine("energy efficiency: " + product.EnergyEfficiencyClass);

            Console.WriteLine("custom attributes:");
            if (product.CustomAttributes != null)
            {
                foreach (var attribute in product.CustomAttributes)
                {
                    Console.WriteLine("\tname: " + attribute.Name);
                    Console.WriteLine("\tvalue: " + attribute.Value);
                    Console.WriteLine("\tunit: " + attribute.Unit);
                    Console.WriteLine("\ttype: " + attribute.Type);
                }
            }

            Console.WriteLine("custom groups:");
            if (product.CustomGroups != null)
            {
                foreach (var group in product.CustomGroups)
                {
                    Console.WriteLine("name: " + group.Name);

                    if (group.Attributes != null)
                    {
                        foreach (var attribute in group.Attributes)
                        {
                            Console.WriteLine("\tname: " + attribute.Name);
                            Console.WriteLine("\tvalue: " + attribute.Value);
                            Console.WriteLine("\tunit: " + attribute.Unit);
                            Console.WriteLine("\ttype: " + attribute.Type);
                        }
                    }
                }
            }

            Console.WriteLine("label 0: " + product.CustomLabel0);
            Console.WriteLine("label 1: " + product.CustomLabel1);
            Console.WriteLine("label 2: " + product.CustomLabel2);
            Console.WriteLine("label 3: " + product.CustomLabel3);
            Console.WriteLine("label 4: " + product.CustomLabel4);

            Console.WriteLine("destinations:");
            if (product.Destinations != null)
            {
                foreach (var destination in product.Destinations)
                {
                    Console.WriteLine("\tname: " + destination.DestinationName);
                    Console.WriteLine("\tintention: " + destination.Intention);
                }
            }
            Console.WriteLine("validated destinations");
            if (product.ValidatedDestinations != null)
            {
                foreach (var destination in product.ValidatedDestinations)
                {
                    Console.WriteLine("\t: " + destination);
                }
            }

            Console.WriteLine("isBundle: " + product.IsBundle);
            Console.WriteLine("item group ID: " + product.ItemGroupId);
            Console.WriteLine("multi-pack quantity: " + product.MerchantMultipackQuantity);

            Console.WriteLine("shipping label: " + product.ShippingLabel);
            Console.WriteLine("shipping price: ");
            if (product.Shipping != null)
            {
                foreach (var price in product.Shipping)
                {
                    Console.WriteLine("\tcountry:" + price.Country);
                    Console.WriteLine("\tregion:" + price.Region);
                    Console.WriteLine("\tpostalCode:" + price.PostalCode);

                    if (price.Price != null)
                    {
                        Console.WriteLine("\tprice: {0} {1}:", 
                             price.Price.Value, 
                             price.Price.Currency);
                    }
                    Console.WriteLine("\tservice:" + price.Service);
                    Console.WriteLine("\tlocation group name:" + price.LocationGroupName);
                    Console.WriteLine("\tlocation ID:" + price.LocationId);
                }

                if (product.ShippingWeight != null)
                {
                    Console.WriteLine("shipping weight: {0} {1}", 
                         product.ShippingWeight.Value, 
                         product.ShippingWeight.Unit);
                }
            }

            Console.WriteLine("taxes: ");
            if (product.Taxes != null)
            {
                foreach (var tax in product.Taxes)
                {
                    Console.WriteLine("\tcountry:" + tax.Country);
                    Console.WriteLine("\tregion:" + tax.Region);
                    Console.WriteLine("\tpostalCode:" + tax.PostalCode);
                    Console.WriteLine("\trate: {0}:", tax.Rate.Value);
                    Console.WriteLine("\tis shipping taxed:" + tax.TaxShip);
                    Console.WriteLine("\tlocation ID:" + tax.LocationId);
                }
            }

            Console.WriteLine("Adwords settings");
            Console.WriteLine("Google product category: " + product.GoogleProductCategory);
            Console.WriteLine("\tgrouping: " + product.AdwordsGrouping);
            Console.WriteLine("\tredirect: " + product.AdwordsRedirect);
            Console.WriteLine("\tlabels: ");
            if (product.AdwordsLabels != null)
            {
                foreach (var label in product.AdwordsLabels)
                {
                    Console.WriteLine("\t\t" + label);
                }
            }
        }

        // Print errors.
        
        private static void PrintErrors(ContentError contentError)
        {
            Console.WriteLine("HTTP status code: " + contentError.Error.Code);

            foreach (Error error in contentError.Error.Errors)
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


    // Defines a collection of products.

    class ProductCollection
    {
        [JsonProperty("kind")]  // Set to content#productsListResponse
        public string Kind { get; set; }

        [JsonProperty("nextPageToken")]
        public string nextPageToken { get; set; }

        [JsonProperty("resources")]
        public List<Product> Resources { get; set; }
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

    // Defines the possible distribution channels.
    
    public enum ProductChannel
    {
        Online,
        Local
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
}
```
