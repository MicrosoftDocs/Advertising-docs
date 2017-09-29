---
title: "Downloading a Catalog Status Report in C#"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Downloading a Catalog Status Report in C# #
This example shows how to get the status of product offers that were uploaded to the specified catalog using C#. If offers failed validation or editorial review, the example downloads the report that shows the reasons why the offer failed the review. 

The example uses the CodeGrantFlow class shown in [Authenticating Microsoft Account Credentials in C#](../shopping-content/authentication-oauth-csharp.md) example.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.IO;
using System.Threading.Tasks;
using System.Net;
using System.Globalization;
using System.IO.Compression;     // Add reference System.IO.Compression.FileSystem
using Content.OAuth;
using Newtonsoft.Json;           // NuGet Json.NET


namespace StatusReport
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<CLIENTIDGOESHERE>";
        private static string clientSecret = "<CLIENTSECRETGOESHERE>";
        private static string storedRefreshToken = "<REFRESHTOKENGOESHERE OR NULL>";
        private static CodeGrantOauth tokens = null;
        private static DateTime tokenExpiration;

        private static string devToken = "<DEVELOPERTOKENGOESHERE>";

        // URI templates used to get resources.
        
        public const string BaseUri = "https://content.api.bingads.microsoft.com/shopping/v9.1";
        public static string BmcUri = BaseUri + "/bmc/{0}";
        public static string StatusUri = BmcUri + "/catalogs/{1}/status";

        // Query string.

        public static string queryString = "?alt=json";

        // Replace with your store ID and catalog ID.

        public static long merchantId = <STOREIDGOESHERE>;
        public static long catalogId = <CATALOGIDGOESHERE>;

        // The path where the compressed report is written to.

        public static string downloadPath = string.Format(@"c:\reports\{0}.zip",
            "Rejection_" + DateTime.Now.ToString("yyyyMMddThhmm"));

        static void Main(string[] args)
        {
            try
            {
                var headers = GetCredentialHeaders();

                // Build URL with query string and store id.

                var url = string.Format(StatusUri + queryString, merchantId, catalogId);

                // Get the catalog's status.

                var status = GetResource(url, headers, typeof(CatalogStatus)) as CatalogStatus;

                PrintCatalogStatus(status, catalogId);
                Console.WriteLine();
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

        // Gets the catalog's status.
        
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


        // Prints the catalog's status.
        
        private static void PrintCatalogStatus(CatalogStatus status, long catalogId)
        {
            Console.WriteLine("Catalog {0} Status Report", catalogId);
            Console.WriteLine("Published offers: " + status.PublishedCount);
            Console.WriteLine("Rejected offers: " + status.RejectedCount);

            if (status.RejectedCount > 0)
            {
                var reportPath = GetRejectionReport(status.RejectionReportUrl);
                Console.WriteLine("Report was written to " + reportPath);
            }
        }

        // Gets the rejection report. The report is 
        // named MerchantCatalogReport.csv.
        
        private static string GetRejectionReport(string url)
        {
            DownloadReport(url, downloadPath);
            var reportPath = DecompressZipFile(downloadPath);
            return reportPath;
        }

        // Downloads the rejection report and writes
        // it to the specified folder.
        
        private static void DownloadReport(string uri, string path)
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = "GET";
            request.Accept = "application/x-zip-compressed";
            var response = (HttpWebResponse)request.GetResponse();

            var fileInfo = new FileInfo(path);
            if (fileInfo.Directory != null && !fileInfo.Directory.Exists)
            {
                fileInfo.Directory.Create();
            }

            var bufferSize = 100 * 1024;
            var fileStream = new FileStream(fileInfo.FullName, FileMode.Create, FileAccess.Write, FileShare.None, bufferSize);

            using (BinaryReader reader = new BinaryReader(response.GetResponseStream()))
            {
                using (BinaryWriter writer = new BinaryWriter(fileStream))
                {
                    while (true)
                    {
                        byte[] buffer = reader.ReadBytes(bufferSize);
                        writer.Write(buffer);
                        if (buffer.Length != bufferSize)
                        {
                            break;
                        }
                    }
                }
            }

            fileStream.Close();
        }

        // Decompresses the report.
        
        private static string DecompressZipFile(String path)
        {
            var fileInfo = new FileInfo(downloadPath);
            var decompressedFileName = fileInfo.Name.Remove(fileInfo.Name.Length - fileInfo.Extension.Length);
            var decompressedPath = fileInfo.Directory.FullName + "\\" + decompressedFileName;
            ZipFile.ExtractToDirectory(downloadPath, decompressedPath);
            return decompressedPath;
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

    // Reporting classes.

    public class CatalogStatus
    {
        [JsonProperty("catalogId")]
        public ulong CatalogId { get; set; }

        [JsonProperty("publishedCount")]
        public ulong PublishedCount { get; set; }

        [JsonProperty("rejectedCount")]
        public ulong RejectedCount { get; set; }

        [JsonProperty("rejectionReportUrl")]
        public string RejectionReportUrl { get; set; }
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
