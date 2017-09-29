---
title: "Managing Catalogs in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# Managing Catalogs in C# #
This example shows how to get, add, update, and delete catalogs in the specified store using C#.  

The example uses the CodeGrantFlow class shown in [Authenticating Microsoft Account Credentials in C#](../shopping-content/authentication-oauth-csharp.md) example.

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

namespace Catalogs
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<CLIENTIDGOESHERE>";
        private static string clientSecret = "<CLIENTSECRETGOESHERE>";
        private static string storedRefreshToken = "<REFRESHTOKENGOESHERE>";
        private static CodeGrantOauth tokens = null;
        private static DateTime tokenExpiration;

        private static string devToken = "<DEVELOPERTOKENGOESHERE>";

        // URI templates used to get resources.

        public const string BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
        public static string BmcUri = BaseUri + "/bmc/{0}";
        public static string CatalogsUri = BmcUri + "/catalogs";
        public static string CatalogUri = CatalogsUri + "/{1}";

        // Replace with your store id.

        public static ulong merchantId = <STOREIDGOESHERE>;

        static void Main(string[] args)
        {
            try
            {
                var headers = GetCredentialHeaders();

                // Build the catalogs endpoint URL.

                var url = string.Format(CatalogsUri, merchantId);

                // Get and print the current list of catalogs.

                var collection = GetResource(url, headers, typeof(CatalogCollection)) as CatalogCollection;
                PrintCatalogs(collection);

                // Add a couple of catalogs.

                var catalogs = AddCatalogs(url, headers);

                // Get and print the current list of catalogs.

                collection = GetResource(url, headers, typeof(CatalogCollection)) as CatalogCollection;
                PrintCatalogs(collection);

                // Update the first catalog that we added
                // to enable it for publishing. When you update the 
                // catalog, you must specify both Name and IsPublishingEnabled.

                Console.WriteLine("*** Updating Catalog ***\n");
                var catalogUrl = string.Format(CatalogUri, merchantId, catalogs[0].Id);
                var catalog = new Catalog()
                {
                    Name = catalogs[0].Name,
                    IsPublishingEnabled = true
                };
                UpdateResource(catalogUrl, headers, catalog);

                // Get and print the updated catalog.

                var updatedCatalog = GetResource(catalogUrl, headers, typeof(Catalog)) as Catalog;
                PrintCatalogDetails(updatedCatalog);

                // Delete the catalogs that we created.

                DeleteCatalogs(CatalogUri, headers, merchantId, catalogs);

                // Get and print the current list of catalogs.

                collection = GetResource(url, headers, typeof(CatalogCollection)) as CatalogCollection;
                PrintCatalogs(collection);
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

                        // Deserialize error string into errors object.

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

        // Gets catalog data from the store.
        
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

        // Adds a catalog to the store.
        
        private static Catalog AddResource(string uri, WebHeaderCollection headers, Catalog catalog)
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "POST";
            request.Headers = headers;
            request.ContentType = "application/json";

            var json = JsonConvert.SerializeObject(catalog);
            request.ContentLength = json.Length;
            using (Stream requestStream = request.GetRequestStream())
            {
                StreamWriter writer = new StreamWriter(requestStream);
                writer.Write(json);
                writer.Close();
            }

            var response = (HttpWebResponse)request.GetResponse();

            Catalog catalogOut = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                catalogOut = JsonConvert.DeserializeObject<Catalog>(jsonOut);
            }

            return catalogOut;
        }

        // Updates a catalog's attributes.
        
        private static ulong UpdateResource(string uri, WebHeaderCollection headers, Catalog catalog)
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "PUT";
            request.Headers = headers;
            request.ContentType = "application/json";

            var json = JsonConvert.SerializeObject(catalog);
            request.ContentLength = json.Length;
            using (Stream requestStream = request.GetRequestStream())
            {
                StreamWriter writer = new StreamWriter(requestStream);
                writer.Write(json);
                writer.Close();
            }

            var response = (HttpWebResponse)request.GetResponse();

            Catalog catalogOut = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                catalogOut = JsonConvert.DeserializeObject<Catalog>(jsonOut);
            }

            return catalogOut.Id;
        }

        // Deletes a catalog from the store.
        
        private static ContentError DeleteResource(string uri, WebHeaderCollection headers)
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "DELETE";
            request.ContentType = "application/json";
            request.Headers = headers;

            var response = (HttpWebResponse)request.GetResponse();

            ContentError error = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                error = JsonConvert.DeserializeObject<ContentError>(jsonOut);
            }

            return error;
        }

        private static List<Catalog> AddCatalogs(string url, WebHeaderCollection headers)
        {
            var catalogs = new List<Catalog>();

            Console.WriteLine("*** Adding Catalogs ***\n");

            // This catalog is not enabled for publishing.

            var catalog = new Catalog()
            {
                Name = "Mens Apparel",
                Market = "en-US",
                IsPublishingEnabled = false
            };

            catalogs.Add(AddResource(url, headers, catalog));

            // This catalog is enabled for publishing.

            catalog = new Catalog()
            {
                Name = "Womens Apparel",
                Market = "en-US",
                IsPublishingEnabled = true
            };

            catalogs.Add(AddResource(url, headers, catalog));

            return catalogs;
        }

        private static void DeleteCatalogs(string uri, WebHeaderCollection headers, ulong merchantId, List<Catalog> catalogs)
        {
            Console.WriteLine("*** Deleting Catalogs ***\n");

            foreach (var catalog in catalogs)
            {
                // Build the endpoint URL.

                var url = string.Format(uri, merchantId, catalog.Id);

                // Delete the catalog from the store.

                var errors = DeleteResource(url, headers);

                if (errors != null)
                {
                    Console.WriteLine("Error deleting catalog: " + catalog.Id);
                    PrintErrors(errors);
                }
                else
                {
                    Console.WriteLine("Deleted catalog: " + catalog.Id);
                }
            }

            Console.WriteLine();
        }

        private static void PrintCatalogs(CatalogCollection collection)
        {
            Console.WriteLine("There are " + collection.Catalogs.Count + " catalogs.\n");

            foreach (Catalog catalog in collection.Catalogs)
            {
                PrintCatalogDetails(catalog);
            }
        }

        // Print catalog details.

        private static void PrintCatalogDetails(Catalog catalog)
        {
            Console.WriteLine("Name: " + catalog.Name);
            Console.WriteLine("ID: " + catalog.Id);
            Console.WriteLine("Market: " + catalog.Market);
            Console.WriteLine("IsDefault: " + catalog.IsDefault);
            Console.WriteLine("IsPublishingEnabled: " + catalog.IsPublishingEnabled);
            Console.WriteLine();
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
}

public class Catalog
{
    [JsonProperty("id", DefaultValueHandling = DefaultValueHandling.Ignore)]
    public ulong Id { get; set; }

    [JsonProperty("name")]
    public string Name { get; set; }

    [JsonProperty("market", DefaultValueHandling = DefaultValueHandling.Ignore)]
    public string Market { get; set; }

    [JsonProperty("isPublishingEnabled")]
    public Boolean IsPublishingEnabled { get; set; }

    [JsonProperty("isDefault", DefaultValueHandling = DefaultValueHandling.IgnoreAndPopulate)]
    public Boolean IsDefault { get; set; }
}

public class CatalogCollection
{
    [JsonProperty("catalogs")]
    public List<Catalog> Catalogs { get; set; }
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
```
