---
title: "Hotel Code Example"
description: Shows you how to list, get, and update hotels.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
dev_langs:
  - csharp
ms.date: 11/1/2017
---

# Hotel code example

The following example shows the requests you use to list, get, and update hotels. The example also shows how to associate a hotel with a hotel group. 

For details about the elements used in this example, see the [reference](../hotel-service/reference.md) section. 

For additional information, see [Working with hotels](../hotel-service/manage-hotel-campaigns.md#workingwithhotels). 

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

namespace ListHotels
{
    class Program
    {
        // The client ID and secret that you were given when you
        // registered your application.

        private static string clientId = "<clientidgoeshere>";
        private static string clientSecret = null;  // Desktop app, so no secret
        private static string storedRefreshToken = "<refreshtokengoeshere";


        private static string customerId = "<customeridgoeshere>";
        private static string accountId = "<accountidgoeshere>";
        private static string subaccountId = "<subaccountidgoeshere>";
        private static string hotelGroupId = "<hotelgroupidgoeshere>";
        private static string hotelId = "<hotelidgoeshere>";
        private static string ungroupedHotelGroupId = "<hotelgroupidgoeshere>";


        private static string BaseUri = "https://partner.api.sandbox.bingads.microsoft.com/Travel/V1";
        private static string HotelsTemplate = "/Customers({0})/Accounts({1})/SubAccounts('{2}')/HotelGroups('{3}')/Hotels";
        private static string HotelTemplate = "/Customers({0})/Accounts({1})/SubAccounts('{2}')/HotelGroups('{3}')/Hotels('{4}')";
        private static string AssociateTemplate = "/Customers({0})/Accounts({1})/SubAccounts('{2}')/Associate";


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

                    Console.WriteLine("**** Listing hotels for hotel group {0} ****\n", hotelGroupId);

                    var uri = string.Format(BaseUri + HotelsTemplate, customerId, accountId, subaccountId, hotelGroupId);
                    var collection = GetResource(uri, headers, typeof(CollectionResponse)) as CollectionResponse;
                    PrintHotels(collection.value);


                    var multipliers = new List<object>();
                    multipliers.Add(new CheckInDayOfWeekMultiplier()
                    {
                        Factor = 1.2,
                        DaysOfWeek = new[] { "Thursday", "Friday", "Saturday" }.ToList<string>(),
                        type = "#Model.CheckinDayOfWeekMultiplier"
                    });
                    multipliers.Add(new CheckInDayOfWeekMultiplier()
                    {
                        Factor = .9,
                        DaysOfWeek = new[] { "Sunday", "Monday" }.ToList<string>(),
                        type = "#Model.CheckinDayOfWeekMultiplier"
                    });
                    multipliers.Add(new AdvanceWindowBookingMultiplier()
                    {
                        Factor = 1.3,
                        MinimumNumberOfDays = 3,
                        type = "#Model.AdvanceBookingWindowMultiplier"
                    });


                    Console.WriteLine("**** Getting hotel {0} from Ungrouped before update ****\n", hotelId);

                    uri = string.Format(BaseUri + HotelTemplate, customerId, accountId, subaccountId, ungroupedHotelGroupId, hotelId);
                    var hotel = GetResource(uri, headers, typeof(Hotel)) as Hotel;
                    PrintHotel(hotel);


                    hotel = new Hotel()
                    {
                        BidMultipliers = multipliers
                    };

                    Console.WriteLine("**** Updating multipliers for hotel {0} ****\n", hotelId);

                    AddUpdateResource(uri, headers, hotel, typeof(Hotel), typeof(AddResponse), "PATCH");

                    Console.WriteLine("**** Getting hotel {0} after update ****\n", hotelId);
                    hotel = GetResource(uri, headers, typeof(Hotel)) as Hotel;
                    PrintHotel(hotel);


                    Console.WriteLine("**** Associating hotel {0} with hotel group {1} ****\n", hotelId, hotelGroupId);

                    var associations = new List<HotelAssociation>();
                    associations.Add(new HotelAssociation()
                    {

                        HotelGroupId = hotelGroupId,
                        HotelId = hotelId
                    });

                    AssociationCollection associationCollection = new AssociationCollection()
                    {
                        HotelAssociations = associations
                    };

                    Console.WriteLine("**** Adding hotel association****\n");

                    uri = string.Format(BaseUri + AssociateTemplate, customerId, accountId, subaccountId);
                    collection = AddUpdateResource(uri, headers, associationCollection, typeof(AssociationCollection), typeof(CollectionResponse)) as CollectionResponse;

                    // The /Associate method will try to apply all associations in the
                    // request. It returns any associations that failed and the reason
                    // for the failure.

                    if (collection.value != null && collection.value.Count > 0)
                    {
                        PrintAssociationErrors(collection.value);
                    }

                    Console.WriteLine("**** Listing hotels for hotel group {0} ****\n", hotelGroupId);

                    uri = string.Format(BaseUri + HotelsTemplate, customerId, accountId, subaccountId, hotelGroupId);
                    collection = GetResource(uri, headers, typeof(CollectionResponse)) as CollectionResponse;
                    PrintHotels(collection.value);

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
            catch (OAuthTokenRequestException e)
            {
                Console.WriteLine("\n" + e.Message);
                Console.WriteLine("\n" + e.Details);
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

        private static object AddUpdateResource(string uri, WebHeaderCollection headers, object resource, Type requestType, Type responseType, string verb = "POST")
        {
            var request = (HttpWebRequest)WebRequest.Create(uri);
            request.Method = verb;
            request.Headers = headers;
            request.ContentType = "application/json";

            var serializerSettings = new JsonSerializerSettings();
            serializerSettings.NullValueHandling = NullValueHandling.Ignore;

            var json = JsonConvert.SerializeObject(resource, requestType, serializerSettings);
            request.ContentLength = json.Length;
            using (Stream requestStream = request.GetRequestStream())
            {
                StreamWriter writer = new StreamWriter(requestStream);
                writer.Write(json);
                writer.Close();
            }

            var response = (HttpWebResponse)request.GetResponse();

            object responseObject = null;

            using (Stream responseStream = response.GetResponseStream())
            {
                var reader = new StreamReader(responseStream);
                var jsonOut = reader.ReadToEnd();
                reader.Close();
                responseObject = JsonConvert.DeserializeObject(jsonOut, responseType);
            }

            return responseObject;
        }


        private static void PrintHotels(List<object> hotels)
        {
            foreach (var hotel in hotels)
            {
                var h = ((JObject)hotel).ToObject<Hotel>();

                PrintHotel(h);
            }

        }


        private static void PrintHotel(Hotel hotel)
        {
            Console.WriteLine("Hotel name: " + hotel.Name);
            Console.WriteLine("Hotel ID: " + hotel.Id);
            Console.WriteLine("Partner hotel ID: " + hotel.PartnerHotelId);
            Console.WriteLine("Hotel status: " + hotel.Status);
            Console.WriteLine("Country code: " + hotel.CountryCode);
            Console.WriteLine("Bid source: " + ((hotel.BidSource != null) ? hotel.BidSource : string.Empty));

            if (hotel.Bid != null)
            {
                var b = ((JObject)hotel.Bid).ToObject<Bid>();
                Console.WriteLine("{0}: {1}", (b.GetBidType() == "FixedBid") ? "Fixed bid" : "Percentage bid", b.Amount);
            }
            else
            {
                Console.WriteLine("Bid:");
            }
            
            
            Console.WriteLine("Bid multiplier source: " + ((hotel.BidMultiplierSource != null) ? hotel.BidMultiplierSource : string.Empty));


            if (hotel.BidMultipliers != null && hotel.BidMultipliers.Count > 0)
            {
                foreach (var multiplier in hotel.BidMultipliers)
                {
                    var m = ((JObject)multiplier).ToObject<Multiplier>();
                    Console.WriteLine("{0}: {1}", m.GetMultiplierType(), m.Factor);

                    switch (m.GetMultiplierType()) { 
                        case "UserCountryMultiplier" :
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
                                var dayOfWeekMultiplier = ((JObject)multiplier).ToObject<CheckInDayOfWeekMultiplier>();

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
                }
            }
            else
            {
                Console.WriteLine("Multipliers:");
            }

            Console.WriteLine();
        }



        private static void PrintAssociationErrors(List<object> associations)
        {
            foreach (var association in associations)
            {
                var a = ((JObject)association).ToObject<HotelAssociation>();

                PrintAssociationError(a);
            }
        }

        private static void PrintAssociationError(HotelAssociation association)
        {
            Console.WriteLine("Hotel group ID: " + association.HotelGroupId);
            Console.WriteLine("Hotel group name: " + association.HotelGroupName);
            Console.WriteLine("Hotel ID: " + association.HotelId);
            Console.WriteLine("Hotel group name: " + association.HotelName);

            foreach (var error in association.Errors)
            {
                Console.WriteLine("Error code: " + error.Code);
                Console.WriteLine("Error message: " + error.Message);
                Console.WriteLine("Error parameter: " + error.Property);
            }

            Console.WriteLine();
        }


        private static void PrintErrors(List<object> errors)
        {
            foreach (var error in errors)
            {
                var e = ((JObject)error).ToObject<AdsApiError>();

                PrintError(e);
            }
        }
        private static void PrintError(AdsApiError error)
        {
                Console.WriteLine("\nError code: " + error.Code);
                Console.WriteLine("Error message: " + error.Message);
                Console.WriteLine("Error parameter: " + error.Property);
        }
    }
}


// Defines a hotel.

class Hotel
{
    public string Id { get; set; }

    public string Name { get; set; }

    public string Status { get; set; }

    public object Bid { get; set; }

    public List<object> BidMultipliers { get; set; }

    public string BidSource { get; set; }

    public string BidMultiplierSource { get; set; }

    public string CountryCode { get; set; }

    public string PartnerHotelId { get; set; }
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

class CheckInDayOfWeekMultiplier : Multiplier
{
    public List<string> DaysOfWeek { get; set; }
}

// Defines the multiplier to use if the user specified check-in
// and check-out dates as part of the search.

class DateTypeMultiplier : Multiplier
{
    //public List<string> DateType { get; set; }
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
// lists of resources (i.e., /SubAccounts('12345')/HotelGroups('45678')/Hotels).

class CollectionResponse
{
    // Contains the list of requested resources.

    public List<object> value { get; set; }

    // The number of resources in the value list. The object
    // include this field only if the request specifies the $count query parameter.

    [JsonProperty("@odata.count")]
    public UInt32 count { get; set; }
}



// Defines a hotel association, which defines the relationship
// between a hotel and a hotel group. A hotel may belong
// to only one group.

class HotelAssociation
{
    public string HotelGroupId { get; set; }

    public string HotelGroupName { get; set; }

    public string HotelId { get; set; }

    public string HotelName { get; set; }

    public string PartnerHotelId { get; set; }

    public List<AdsApiError> Errors { get; set; }
}


// Defines a collection of hotel associations.

class AssociationCollection
{
    // Contains the list of requested resources.
    public List<HotelAssociation> HotelAssociations { get; set; }
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