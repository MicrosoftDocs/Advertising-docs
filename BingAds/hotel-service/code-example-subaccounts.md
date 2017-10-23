---
title: "Subaccount Code Example"
description: Shows hot to list, get, and update hotel subaccounts.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
dev_langs:
  - csharp
ms.date: 11/1/2017
---

# Subaccount code example

The following example shows the requests you use to list, get, and update subaccounts. 

For details about the elements used in this example, see the [reference](../hotel-service/reference.md) section. 

For additional information, see [Working with subaccounts](../hotel-service/manage-hotel-campaigns.md#workingwithsubaccounts). 

The example does not include calls to get the OAuth access and refresh tokens. For options in getting the tokens, see [Getting Started](../hotel-service/get-started.md). For a simple example that shows how to get an OAuth access and refresh token, see [C#](../hotel-service/code-example-oauth.md).

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;
using System.Net;
using System.Net.Http;
using System.Web;
using Newtonsoft.Json;       // NuGet Json.NET
using Newtonsoft.Json.Linq;

namespace ListSubAccounts
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<clientidgoeshere>";
        private static string clientSecret = null;  // Desktop app, so there's no secret
        private static string storedRefreshToken = "<refreshtokengoeshere>"; 

        private static string customerId = "<customeridgoeshere>";
        private static string accountId = "<accountidgoeshere>";


        private static string BaseUri = "https://partner.api.sandbox.bingads.microsoft.com/Travel/V1";
        private static string SubaccountsTemplate = "/Customers({0})/Accounts({1})/SubAccounts";
        private static string SubaccountTemplate = "/Customers({0})/Accounts({1})/SubAccounts('{2}')";


        static void Main(string[] args)
        {
            try
            {
                // TODO: Add the calls to the OAuth code that you use to get the access and 
                // refresh tokens. Consider using the Bing Ads SDK to get the tokens.

                tokens = GetOauthTokens(storedRefreshToken);

                if (tokens.AccessToken != null)
                {
                    var headers = new WebHeaderCollection();
                    headers.Add(HttpRequestHeader.Authorization, "Bearer " + tokens.AccessToken);

                    Console.WriteLine("**** Getting the list of subaccounts ****\n");

                    var uri = string.Format(BaseUri + SubaccountsTemplate, customerId, accountId);
                    var collection = GetResource(uri, headers, typeof(CollectionResponse)) as CollectionResponse;
                    PrintSubAccounts(collection.value);

                    // Creates a list of bid multipliers.

                    //var multipliers = new List<object>();
                    //multipliers.Add(new UserCountryMultiplier() {
                    //    Factor = 1.1,
                    //    Countries = new[] { "US" }.ToList<string>(),
                    //    type = "#Model.UserCountryMultiplier"
                    //});
                    //multipliers.Add(new SiteMultiplier() {
                    //    Factor = .85,
                    //    Sites = new[] { "LocalUniversal", "MapResults" }.ToList<string>(),
                    //    type = "#Model.SiteMultiplier"
                    //});
                    //multipliers.Add(new DeviceTypeMultiplier() {
                    //    Factor = .65,
                    //    DeviceTypes = new[] { "Desktop" }.ToList<string>(),
                    //    type = "#Model.DeviceMultiplier"
                    //});
                    //multipliers.Add(new LengthOfStayMultiplier() {
                    //    Factor = 1.3,
                    //    MinimumNumberOfNights = 5,
                    //    type = "#Model.LengthOfStayMultiplier"
                    //});
                    ////multipliers.Add(new DateTypeMultiplier() {
                    ////    Factor = .35,
                    ////    DateType = "Selected",
                    ////    type = "#Model.DateTypeMultiplier"
                    ////});
                    //multipliers.Add(new CheckinDayOfWeekMultiplier() {
                    //    Factor = 1.2,
                    //    DaysOfWeek = new[] { "Thursday", "Friday", "Saturday" }.ToList<string>(),
                    //    type = "#Model.CheckinDayOfWeekMultiplier"
                    //});
                    //multipliers.Add(new CheckinDayOfWeekMultiplier()
                    //{
                    //    Factor = .9,
                    //    DaysOfWeek = new[] { "Sunday", "Monday" }.ToList<string>(),
                    //    type = "#Model.CheckinDayOfWeekMultiplier"
                    //});
                    //multipliers.Add(new AdvanceWindowBookingMultiplier() {
                    //    Factor = 1.3,
                    //    MinimumNumberOfDays = 3,
                    //    type = "#Model.AdvanceBookingWindowMultiplier"
                    //});

                    //SubAccount subaccount = new SubAccount()
                    //{
                    //    Name = "scottwhi-test",
                    //    DailyBudget = new Budget()
                    //    {
                    //        Amount = 125.25
                    //    },
                    //    MaximumBid = new FixedBid()
                    //    {
                    //        Amount = 5.0,
                    //        type = "#Model.FixedBid"
                    //    },
                    //    Bid = new FixedBid()
                    //    {
                    //        Amount = 2.75,
                    //        type = "#Model.FixedBid"
                    //    },
                    //    BidMultipliers = multipliers
                    //};

                    //// NOTE: Adding the subaccount will fail because Bing currently allows only one subaccount.

                    //Console.WriteLine("**** Adding a subaccounts ****\n");

                    //var subaccountId = AddUpdateResource(uri, headers, subaccount, typeof(SubAccount)) as string;
                    //Console.WriteLine("Added subaccount {0}.\n", subaccountId); // ID of new subaccount

                    //Console.WriteLine("**** Getting the list of subaccounts after adding a subaccount ****\n");

                    //collection = GetResource(uri, headers, typeof(CollectionResponse)) as CollectionResponse;
                    //PrintSubAccounts(collection.value);


                    var subaccountId = ((JObject)collection.value[0]).ToObject<SubAccount>().Id;


                    // Specify only the fields of the subaccount that you want to update.

                    SubAccount subaccountToUpdate = new SubAccount()
                    {
                        Id = subaccountId,
                        //DailyBudget = new Budget()
                        //{
                        //    Amount = 125.25
                        //},
                        //MaximumBid = new FixedBid()
                        //{
                        //    Amount = 10.0,
                        //    type = "#Model.FixedBid"
                        //},
                        Bid = new FixedBid()
                        {
                            Amount = 3.48,
                            type = "#Model.FixedBid"
                        },
                        //BidMultipliers = multipliers
                    };

                    Console.WriteLine("**** Updating subaccount {0} ****\n", subaccountId);

                    uri = string.Format(BaseUri + SubaccountTemplate, customerId, accountId, subaccountId);
                    AddUpdateResource(uri, headers, subaccountToUpdate, typeof(SubAccount), "PATCH");

                    Console.WriteLine("**** Getting subaccount {0} after update ****\n", subaccountId);

                    var updatedSubaccount = GetResource(uri, headers, typeof(SubAccount)) as SubAccount;
                    PrintSubAccount(updatedSubaccount);
                }

            }
            catch (WebException e)
            {
                HttpWebResponse response = (HttpWebResponse)e.Response;

                Console.WriteLine("\nHTTP status: " + response.StatusCode);
                Console.WriteLine("\n" + e.Message);

                // If the request is bad, the API returns the errors in the 
                // body of the response. 

                if (response != null &&
                    (HttpStatusCode.BadRequest == response.StatusCode))
                {
                    using (Stream stream = response.GetResponseStream())
                    {
                        StreamReader reader = new StreamReader(stream);
                        string json = reader.ReadToEnd();
                        reader.Close();

                        var collection = JsonConvert.DeserializeObject<CollectionResponse>(json);

                        PrintErrors(collection.value);
                    }
                }
            }
            catch (Exception e)
            {
                Console.WriteLine("\n" + e.Message);
            }
        }


        // Gets the requested resource.

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


        // Adds or updates the resource.

        private static string AddUpdateResource(string uri, WebHeaderCollection headers, object resource, Type type, string verb = "POST")
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = verb;
            request.Headers = headers;
            request.ContentType = "application/json";

            var serializerSettings = new JsonSerializerSettings();
            serializerSettings.NullValueHandling = NullValueHandling.Ignore;

            var json = JsonConvert.SerializeObject(resource, type, serializerSettings);
            request.ContentLength = json.Length;
            using (Stream requestStream = request.GetRequestStream())
            {
                StreamWriter writer = new StreamWriter(requestStream);
                writer.Write(json);
                writer.Close();
            }

            var response = (HttpWebResponse)request.GetResponse();

            AddResponse addResponse = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                addResponse = JsonConvert.DeserializeObject<AddResponse>(jsonOut);
            }

            return addResponse.value;
        }



        private static void PrintSubAccounts(List<object> subaccounts)
        {
            foreach (var subaccount in subaccounts)
            {
                var s = ((JObject)subaccount).ToObject<SubAccount>();

                PrintSubAccount(s);
            }
        }


        private static void PrintSubAccount(SubAccount subaccount)
        {
            Console.WriteLine("Campaign name: " + subaccount.Name);
            Console.WriteLine("Campaign ID: " + subaccount.Id);
            Console.WriteLine("Campaign status: " + subaccount.Status);
            Console.WriteLine("Daily budget: " + subaccount.DailyBudget.Amount);
            Console.WriteLine("Maximum bid: " + subaccount.MaximumBid.Amount);

            var b = ((JObject)subaccount.Bid).ToObject<Bid>();
            Console.WriteLine("{0}: {1}", (b.GetBidType() == "FixedBid") ? "Fixed bid" : "Percentage bid", b.Amount);

            if (subaccount.BidMultipliers != null && subaccount.BidMultipliers.Count > 0)
            {
                foreach (var multiplier in subaccount.BidMultipliers)
                {
                    var m = ((JObject)multiplier).ToObject<Multiplier>();
                    Console.WriteLine("{0}: {1}", m.GetMultiplierType(), m.Factor);

                    switch (m.GetMultiplierType())
                    {
                        case "UserCountryMultiplier":
                            {
                                var userCountryMultiplier = ((JObject)multiplier).ToObject<UserCountryMultiplier>();

                                foreach (var country in userCountryMultiplier.Countries)
                                {
                                    Console.WriteLine("\t" + country);
                                }
                                break;
                            }
                        case "SiteMultiplier":
                            {
                                var siteMultiplier = ((JObject)multiplier).ToObject<SiteMultiplier>();

                                foreach (var site in siteMultiplier.Sites)
                                {
                                    Console.WriteLine("\t" + site);
                                }
                                break;
                            }
                        case "DeviceMultiplier":
                            {
                                var deviceMultiplier = ((JObject)multiplier).ToObject<DeviceTypeMultiplier>();

                                foreach (var device in deviceMultiplier.DeviceTypes)
                                {
                                    Console.WriteLine("\t" + device);
                                }
                                break;
                            }
                        case "CheckinDayOfWeekMultiplier":
                            {
                                var dayOfWeekMultiplier = ((JObject)multiplier).ToObject<CheckinDayOfWeekMultiplier>();

                                foreach (var device in dayOfWeekMultiplier.DaysOfWeek)
                                {
                                    Console.WriteLine("\t" + device);
                                }
                                break;
                            }
                        case "DateTypeMultiplier":
                            {
                                var dateTypeMultiplier = ((JObject)multiplier).ToObject<DateTypeMultiplier>();

                                Console.WriteLine("\t" + dateTypeMultiplier.DateType);
                                break;
                            }
                        case "LengthOfStayMultiplier":
                            {
                                var lengthOfStayMultiplier = ((JObject)multiplier).ToObject<LengthOfStayMultiplier>();

                                Console.WriteLine("\tMinimumNumberOfNights: " + lengthOfStayMultiplier.MinimumNumberOfNights);
                                break;
                            }
                        case "AdvanceWindowBookingMultiplier":
                            {
                                var advancedBookingMultiplier = ((JObject)multiplier).ToObject<AdvanceWindowBookingMultiplier>();

                                Console.WriteLine("\tMinimumNumberOfDays: " + advancedBookingMultiplier.MinimumNumberOfDays);
                                break;
                            }
                        default: break;
                    }

                    Console.WriteLine();
                }

            }
        }


        private static void PrintErrors(List<object> errors)
        {
            foreach (var error in errors)
            {
                var e = ((JObject)error).ToObject<AdsApiError>();

                Console.WriteLine("\nError code: " + e.Code);
                Console.WriteLine("Error message: " + e.Message);
                Console.WriteLine("Error parameter: " + e.Property);
            }
        }
    }
}


// Defines a subaccount (or hotel campaign).

class SubAccount
{
    public string Id { get; set; }
    public string Name { get; set; }
    public string Status { get; set; }
    public Budget DailyBudget { get; set; }
    public FixedBid MaximumBid { get; set; }
    public object Bid { get; set; }
    public List<object> BidMultipliers { get; set; }
}

// Defines a daily budget that spread throughout the day.

class Budget
{
    public double Amount { get; set; }
}

// Defines the base bid class. Do not create this object. Instead
// create either the FixedBid or PercentageBid object.

class Bid
{
    public double Amount { get; set; }

    [JsonProperty("@odata.type")]
    public string type { get; set; }

    public string GetBidType()
    {
        return type.Substring(type.LastIndexOf('.') + 1);
    }
}

// Defines a fixed bid.

class FixedBid : Bid
{
}

// Defines a bid that's a percentage of the hotel's room rate.

class PercentageBid : Bid
{
}

// Defines the base multiplier class. Do not create this object. Instead
// create one of the derived multiplier classes (for example, the 
// UserCountryMultiplier class).

class Multiplier
{
    public double Factor { get; set; }

    [JsonProperty("@odata.type")]
    public string type { get; set; }

    public string GetMultiplierType()
    {
        return type.Substring(type.LastIndexOf('.') + 1);
    }
}

// Defines the multiplier to use if the user is located in the specified country.

class UserCountryMultiplier : Multiplier
{
    public List<string> Countries { get; set; }
}

// Defines the multiplier to use if the user is searching on the specified Bing site.

class SiteMultiplier : Multiplier
{
    public List<string> Sites { get; set; }
}

// Defines the multiplier to use if the user is using the specified device.

class DeviceTypeMultiplier : Multiplier
{
    public List<string> DeviceTypes { get; set; }
}

// Defines the multiplier to use if the user is staying the specified 
// minimum number of nights.

class LengthOfStayMultiplier : Multiplier
{
    public int MinimumNumberOfNights { get; set; }
}

// Defines the multiplier to use if the user is booking the specified 
// number of days in advance.

class AdvanceWindowBookingMultiplier : Multiplier
{
    public int MinimumNumberOfDays { get; set; }
}

// Defines the multiplier to use if the user is checking in on
// the specified week day.

class CheckinDayOfWeekMultiplier : Multiplier
{
    public List<string> DaysOfWeek { get; set; }
}

// Defines the multiplier to use if the user specified check-in
// and check-out dates as part of the search.

class DateTypeMultiplier : Multiplier
{
    public string DateType { get; set; }
}


// Defines the response object that POSTs return when
// you add a resource.

class AddResponse
{
    // Contains the ID of the newly added resource.
    public string value { get; set; }
}


// Defines the response object for GETs that return
// lists of resources (i.e., /Subaccounts).

class CollectionResponse
{
    // Contains the list of requested resources.

    public List<object> value { get; set; }

    // The number of resources in the value list. The object
    // include this field only if the request specifies the $count query parameter.

    [JsonProperty("@odata.count")]
    public UInt32 count { get; set; }

}


// Defines the error object that an HTTP status code 400 includes in the
// response body. A 200 /Associate response may also include this object 
// as part of the HotelAssociation object if the association fails
// (see the Errors) field. 

class AdsApiError
{
    public string Code { get; set; }
    public string Message { get; set; }
    public string Property { get; set; }
}

```