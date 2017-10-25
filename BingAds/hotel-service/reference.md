---
title: "Hotel API Reference"
description: Describes the endpoint, headers, query parameters, and objects of the Hotel Ads API.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
ms.date: 11/1/2017
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
ms.date: 11/1/2017
---

# Hotel API reference

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.
>
> The API and documentation are subject to change.

The Hotel API lets you manage your hotel ad campaigns and bidding.

## Endpoints

The following is the base URI that you use to construct the endpoint.  

`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/`

The endpoint must include the customer and account resources.

`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/Customers({customerId})/Accounts({accountId})/`

Set {customerId} to the customer's CustomerId and {accountId} to the customer's CustomerAccountId.

Next, append a template from the following table to add, get, and update hotel resources. For example, to get or add a hotel group, use the following endpoint:

`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/Customers({customerId})/Accounts({accountId})/SubAccounts('{subAccountId}')/HotelGroups`.  

> [!NOTE]
> The IDs for SubAccounts, HotelGroups, and Hotels are strings and must be enclosed in single quotes. For example, SubAccounts('12345')/HotelGroups. This applies to SubAccounts, HotelGroups, and Hotels only; do not use single quotes for Customers and Accounts.

|Template|Verb|Description|
|-|-|-
|<a name="listsubaccounts" />SubAccounts|GET|Gets the list of hotel campaigns defined for the specified account.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [SubAccount](#SubAccount) objects.
|<a name="addsubaccounts" />SubAccounts|POST|Adds the subaccount to the specified account. You can think of subaccounts as hotel campaigns. Use subaccounts to logically organize your hotel ad campaigns. You may have up to 1,000 active hotel campaigns per account.<br /><br />**NOTE**: For the Alpha release, an account may have one subaccount only.<br /><br />**Request body**: Contains the [SubAccount](#SubAccount) to add.<br /><br />**Response body**: If successful, contains an [AddResponse](#AddResponse) object. The `value` field contains the ID of the added hotel campaign.
|<a name="getsubaccount" />SubAccounts('{subAccountId}')|GET|Gets the specified subaccount.<br /><br />**Response body**: Contains a [SubAccount](#SubAccount) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to get.</li></ul>
|<a name="updatesubaccount" />SubAccounts('{subAccountId}')|PATCH|Updates the subaccount.<br /><br />**Request body**: Contains a [SubAccount](#SubAccount) object that specifies only those field to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to update.</li></ul>
|<a name="listhotelgroups" />SubAccounts('{subAccountId}')/HotelGroups|GET|Gets the list of hotel groups in the specified subaccount.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [HotelGroup](#HotelGroup) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel groups to get.</li></ul>
|<a name="addhotelgroup" />SubAccounts('{subAccountId}')/HotelGroups|POST|Adds the hotel group to the specified subaccount. Use hotel groups to create logical groupings of hotel ads. You may create up to 1,000 active hotel groups per subaccount.<br /><br />**Request body**: Contains the [HotelGroup](#HotelGroup) to add to the subaccount.<br /><br />**Response body**: If successful, contains an [AddResponse](#AddResponse) object. The `value` field contains the ID of the added hotel group.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to add the hotel group to.</li></ul>
|<a name="gethotelgroup" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')|GET|Gets the specified hotel group.<br /><br />**Response body**: Contains a [HotelGroup](#HotelGroup) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroupId}`&mdash;Set to the ID of the hotel group to get.</li></ul>
|<a name="updatehotelgroup" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')|PATCH|Updates the hotel group.<br /><br />**Request body**: Contains a [HotelGroup](#HotelGroup) object that specifies only those fields to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroupId}`&mdash;Set to the ID of the hotel group to update.</li></ul>
|<a name="listallhotels" />SubAccounts('{subAccountId}')/Hotels|GET|Gets the list of hotel ads in the specified subaccount. The list contains all hotels across all hotel groups in the subaccount.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [Hotel](#Hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotels to get.</li></ul>.
|<a name="listhotels" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels|GET|Gets the list of hotel ads in the specified hotel group.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [Hotel](#Hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotels to get.</li></ul>.
|<a name="gethotel" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels('{hotelId}')|GET|Gets the specified hotel ad.<br /><br />**Response body**: Contains a [Hotel](#Hotel) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotel to get.</li><li>`{hotelId}`&mdash;Set to the hotel ad to get.</li></ul>
|<a name="updatehotel" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels('{hotelId}')|PATCH|Updates the hotel ad.<br /><br />**Request body**: Contains a [Hotel](#Hotel) object that specifies only those fields to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotel to update.</li><li>`{hotelId}`&mdash;Set to the hotel ad to update.</li></ul>
|<a name="ungrouped" />SubAccounts('{subAccountId}')/Ungrouped|GET|Gets the list of hotels in the Ungrouped hotel group. When you create a subaccount, Bing creates the Ungrouped hotel group. All hotels from your hotel feed that are not otherwise associated with other groups are placed in this group. To associate a hotel in this group with a different hotel group, see the [Associate](#associate) template. <br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [Hotel](#Hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the ungrouped hotel ads to get.</li></ul>
|<a name="associations" />SubAccounts('{subAccountId}')/Associations|GET|Gets a list of hotel and hotel group associations.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains the list of [HotelAssociation](#HotelAssociation) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the associations to get.</li></ul>
|<a name="associate" />SubAccounts('{subAccountId}')/Associate|POST|Adds a list of hotel and hotel group associations to the subaccount.<br /><br />**Request body**: Contains an [AssociationCollection](#AssociationCollection) object. The `HotelAssociation` field contains a list with a maximum of 500 [HotelAssociation](#HotelAssociation) objects. Each object associates a hotel with a hotel group. You can associate a hotel with only one hotel group.<br /><br />**Response body**: Contains a [CollectionResponse](#CollectionResponse) object. The `value` field contains a list of [HotelAssociation](#HotelAssociation) objects. The list contains only those associations that failed validation. The list is empty if there are no errors. The association's `Errors` field contains the list of reasons why the association failed.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to add the associations to.


## Query Parameters

The following are the query parameters that the request may specify.

|Parameter|Description
|-|-
|<a name="count-param"/>$count|An OData parameter that determines whether the response includes an `@odata.count` field. Typically, you include this parameter when you request a list of entities, such as a list of hotel groups). The `@odata.count` field contains the total number of resource entities available, not those returned in the request. For example, if you set $top to 40, but 1,000 entities exist, `@odata.count` is set to 1,000, not 40. To include the count, set $count to **true**.
|<a name="select-param"/>$select|An OData parameter that specifies a comma-delimited list of the fields to include in the response. The field names are case sensitive. For example, to include the hotel's name, partner ID, and bid fields in the response, specify the following parameter:<br /><br />`$select=Name,PartnerHotelId,Bid` 
|<a name="skip-param"/>$skip|An OData parameter that specifies the number of resource entities to skip before returning entities. The $skip value must be a multiple of $top. If you specify a value that is out of range, the response contains an empty set. Use $top and $skip to page through a list of resource entities.
|<a name="top-param"/>$top|An OData parameter that specifies the number of resource entities to return. The default value is 1,000 and the maximum value that you may specify is 5,000. Use $top and $skip to page through a list of resource entities. 



## Headers

The following are the request and response headers.
 
|Header|Description|
|---------|---------------|
|<a name="authorization-hdr"/>Authorization|Request header.<br/><br/>Set this header to a bearer OAuth access token. For example, "Authorization: Bearer QTkxRUFBRjEzOTUyNEIx...". For information about getting a token, see [Getting Started](../hotel-service/get-started.md).
|<a name="contenttype-hdr" />Content-Type|Request and response header.<br/><br/>The type of content in the body of the request or response. For POST and PATCH, set this header to `application/json`.
|<a name="requestid-hdr" />X-MS-RequestId|Response header.<br/><br/>The ID of the log entry that contains the details of the request. You should always capture this ID if an error occurs. If you are not able to determine and resolve the issue, include this ID along with the other information that you provide the Support team.

> [!NOTE]
> This API supports using OAuth access tokens only for authentication (see the Authorization header). You may not use the UserName and Password headers to specify legacy credentials.
>
>This API does not require a developer token. If you include the DeveloperToken header, the API ignores it. 



## Resource Objects

The following are the resource objects used by the API.
 

|Object|Description
|------|-----------
|[AddResponse](#AddResponse)|Defines a response object for requests that add a resource.
|[AdsApiError](#AdsApiError)|Defines an error that occurred.
|[AdvanceBookingWindowMultiplier](#AdvanceBookingWindowMultiplier)|Defines the amount to adjust the base bid by if the user books the specified number of days in advance.
|[AssociationCollection](#AssociationCollection)|Defines a collection of hotel associations.
|[Budget](#Budget)|Defines the daily budget for hotel ads in a subaccount.
|[CollectionResponse](#CollectionResponse)|Defines a response object for requests that get a list of resources.
|[CheckinDayOfWeekMultiplier](#CheckinDayOfWeekMultiplier)|Defines the amount to adjust the base bid by if the user checks in on one of the specified week days.
|[DateTypeMultiplier](#DateTypeMultiplier)|Defines the amount to adjust the base bid by if the user searched for hotels using specific dates.
|[DeviceMultiplier](#DeviceMultiplier)|Defines the amount to adjust the base bid by if the user is using one of the specified devices to search for hotels.
|[FixedBid](#FixedBid)|Defines a fixed bid amount.
|[Hotel](#Hotel)|Defines a hotel ad.
|[HotelAssociation](#HotelAssociation)|Defines the association between a hotel and a hotel group.
|[HotelGroup](#HotelGroup)|Defines a logical grouping of hotel ads.
|[LengthOfStayMultiplier](#LengthOfStayMultiplier)|Defines the amount to adjust the base bid by if the user stays the specified number of nights or longer.
|[PercentageBid](#PercentageBid)|Defines a bid based on the percentage of the hotel room's rate.
|[SiteMultiplier](#SiteMultiplier)|Defines the amount to adjust the base bid by if the user is searching for hotels on one of the specified Bing sites.
|[SubAccount](#SubAccount)|Defines the top-level hotel ads grouping. You can think of this logically as a hotel campaign.
|[UserCountryMultiplier](#UserCountryMultiplier)|Defines the amount to adjust the base bid by if the user accesses one of the Bing domains.



### AddResponse

Defines a response object for requests that add a resource.

|Name|Value|Type
|-|-|-
|value|The ID of the resource that you added.|object


### AdsApiError

Defines an error that occurred.

|Name|Value|Type
|-|-|-
|Code|A symbolic code that identifies the error.|String
|Message|A description of the error.|String
|Parameter|The name of the object, field, or parameter that caused the error.|String



### AdvanceBookingWindowMultiplier

Defines the amount to adjust the base bid by if the user books the specified number of days in advance.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|MinimumNumberOfDays|The minimum number of days in advance of the booking. Apply the multiplier if the booking would occur the specified number of days in advance or longer.|Integer|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.AdvanceBookingWindowMultiplier".|String|Required|Required


### AssociationCollection

Defines a collection of hotel associations.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|HotelAssociations|The list of hotel and hotel group associations. The list may contain a maximum of 500 associations.|[HotelAssociation](#HotelAssociation)[]|Required|N/A


### Bid

Defines the base class for a bid.

Do not specify this class, instead specify the [FixedBid](#FixedBid) or [PercentageBid](#PercentageBid) class.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The dollar bid amount. For details about the valid bid range for your market, see the Currency Value table in the [Currencies](https://msdn.microsoft.com/library/bing-ads-currencies.aspx) topic. The customer's account specifies the currency used.|Double|Required|Optional


### Budget

Defines the daily budget for hotel ads in a subaccount.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The daily budget amount. For details about valid budgets for your market, see the Currency Value table in the [Currencies](https://msdn.microsoft.com/library/bing-ads-currencies.aspx) topic. The customer's account specifies the currency used for the budget.|Double|Required|Optional


### CheckinDayOfWeekMultiplier

Defines the amount to adjust the base bid by if the user checks in on one of the specified week days.


|Name|Value|Type|Add|Update
|-|-|-|-|-
|DaysOfWeek|A list of week days. Apply the multiplier if the user is checking on one of the specified days. The following are the possible values.<br /><br /><ul><li>Monday</li><li>Tuesday</li><li>Wednesday</li><li>Thursday</li><li>Friday</li><li>Saturday</li><li>Sunday</li></ul>|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.CheckinDayOfWeekMultiplier".|String|Required|Required


### CollectionResponse

Defines a response object for requests that get a list of resources.

|Name|Value|Type
|-|-|-
|value|The list of requested resources. Depending on the request, the list contains one of the following types of objects:<ul><li>[Hotel](#Hotel)</li><li>[HotelGroup](#HotelGroup)</li><li>[SubAccount](#SubAccount)</li><li>[HotelAssociation](#HotelAssociation)</li></ul>For example, if you request a list of hotel groups, `value` contains a list of `HotelGroup` objects.|object[]
|@odata.count|The total number resource entities available, not the number of entities in `Value`. The response includes this field only if you include the $count query parameter in the request.


### DateTypeMultiplier

Defines the amount to adjust the base bid by if the user searched for hotels using specific dates.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|DateType|The type of date used in the search. The following are the possible values.<br /><br /><ul><li>Default&mdash;The user didn't search for hotels using specific dates</li><li>Selected&mdash;The user searched for hotels using specific dates.</li></ul>|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.DateTypeMultiplier".|String|Required|Required


### DeviceMultiplier

Defines the amount to adjust the base bid by if the user is using one of the specified devices to search for hotels.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|DeviceTypes|A list of device types. Apply the multiplier if the user is using one of the device types to search for hotels. The following are the possible values.<br /><br /><ul><li>Desktop</li><li>Mobile</li><li>Tablet</li></ul>|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.DeviceMultiplier".|String|Required|Required


### FixedBid

Defines a fixed bid amount.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The fixed dollar bid amount. For details about the valid bid range for your market, see the Currency Value table in the [Currencies](https://msdn.microsoft.com/library/bing-ads-currencies.aspx) topic. The customer's account specifies the currency used.<br /><br />The bid amount is the per-night bid. For example, if the bid is $3.50 and the itinerary is for a 3-night stay, the final bid is $10.50.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.FixedBid".|String|Required|Required


### Hotel

Defines a hotel ad.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Bid|The base bid. Bing uses this bid in the auction unless you specify one or more multipliers (see `BidMultipliers`). If you don't specify a bid, the hotel inherits the bid from the hotel group or subaccount, in that order. When getting a hotel, if the hotel doesn't specify a bid, this field contains the inherited bid.<br /><br />Setting the bid to 0 pauses the hotel (see `Status`).<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#FixedBid)</li><li>[PercentageBid](#PercentageBid)</li></ul>|object|N/A|Optional
|BidMultipliers|A list of multipliers to apply to the base bid. Bing applies the multipliers to the base bid and uses the adjusted bid in the auction. If the hotel does not specify a bid, the multipliers adjust the inherited bid.<br /><br />If you don't specify multipliers, the hotel inherits them from the hotel group or subaccount, in that order. When getting a hotel, if the hotel doesn't specify multipliers, this field contains the inherited multipliers.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#AdvanceBookingWindowMultiplier)</li><li>[CheckinDayOfWeekMultiplier](#CheckinDayOfWeekMultiplier)</li><li>[DateTypeMultiplier](#DateTypeMultiplier)</li><li>[DeviceMultiplier](#DeviceMultiplier)</li><li>[LengthOfStayMultiplier](#LengthOfStayMultiplier)</li><li>[SiteMultiplier](#SiteMultiplier)</li><li>[UserCountryMultiplier](#UserCountryMultiplier)</li></ul>|object[]|N/A|Optional
|BidMultiplierSource|The source of the bid multipliers. The following are the possible values.<ul><li>SubAccount</li><li>HotelGroup</li><li>Hotel</li></ul>For example, if the hotel and hotel group didn't specify multipliers, the hotel inherits the multipliers from the subaccount. In this case, this field is set to SubAccount.|String|N/A|Read-only
|BidSource|The source of the bid. The following are the possible values.<ul><li>SubAccount</li><li>HotelGroup</li><li>Hotel</li></ul>For example, if the hotel specifies a bid, this field is set to Hotel.|String|N/A|Read-only
|CountryCode|The two-letter ISO 3116 county code of the country where the hotel is located. The country is the same country that you specified for the hotel in your hotel feed file.|String|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the hotel.|String|N/A|Required
|Name|The name of the hotel. The name is the same name you specified in your hotel feed file.|String|N/A|Read-only
|PartnerHotelId|The ID that you used to identify the hotel in the hotel feeds file.|String|N/A|Read-only
|Status|The status of the hotel. The following are the possible values.<ul><li>Active&mdash;The hotel is active. The hotel may participate in auctions if it is associated with an active hotel group and subaccount.</li><li>Paused&mdash;The hotel ad is paused. The hotel ad will not participate in auctions until the owner activates it again.</li><li>Deleted&mdash;The user deleted the hotel. Users may delete hotels by using the UI only.</li></ul>By default, hotels are active. To pause an active hotel ad, set the `Bid` field to 0. To resume a paused hotel ad, set the `Bid` field to a non-zero value.<br /><br />If a hotel ad is not serving, it may be because the hotel group it's associated with or the subaccount is not active.|String|N/A|Read-only


### HotelAssociation

Defines the association between a hotel and a hotel group.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Errors|The list of reasons why the association failed validation.<br /><br />The response includes this field only if the association failed validation when you tried to add it.|[AdsApiError](#AdsApiError)|Read-only|N/A
|HotelGroupId|The ID of the hotel group to associate the hotel with.|String|Required|N/A
|HotelGroupName|The name of the hotel group.|String|Read-only|N/A
|HotelId|The ID of the hotel to associate with the specified hotel group. You may associate the hotel with one hotel group only.<br /><br />By default, all hotels are associated with a hotel group whether it's a user-defined group or the default Ungrouped hotel group. To move a hotel from one group to another, post a new association that specifies the hotel ID and new hotel group ID.|String|Required|N/A
|HotelName|The name of the hotel.|String|Read-only|N/A
|PartnerHotelId|The ID that you used to specify the hotel in the hotel feeds file.|String|Read-only|N/A


### HotelGroup

Defines a logical grouping of hotels.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Bid|The base bid that hotels in the group inherit if they don't specify a bid. For usage, see `Bid` in the [Hotel](#Hotel) object.<br /><br /> If you don't specify a bid, the group inherits the bid from the subaccount. When getting a hotel group, if the group doesn't specify a bid, this field contains the inherited bid.<br /><br />Setting the bid to zero (0) pauses the hotel group and any hotels associated with the group (see `Status`).<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#FixedBid)</li><li>[PercentageBid](#PercentageBid)</li></ul>|object|Optional|Optional
|BidMultipliers|A list of multipliers that hotels in the group inherit if they don't specify multipliers. For usage, see `BidMultipliers` in the [Hotel](#Hotel) object.<br /><br /> If you don't specify multipliers, the group inherits them from the subaccount.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#AdvanceBookingWindowMultiplier)</li><li>[CheckinDayOfWeekMultiplier](#CheckinDayOfWeekMultiplier)</li><li>[DateTypeMultiplier](#DateTypeMultiplier)</li><li>[DeviceMultiplier](#DeviceMultiplier)</li><li>[LengthOfStayMultiplier](#LengthOfStayMultiplier)</li><li>[SiteMultiplier](#SiteMultiplier)</li><li>[UserCountryMultiplier](#UserCountryMultiplier)</li></ul>|object[]|Optional|Optional
|BidMultiplierSource|The source of the bid multipliers. The following are the possible values. <ul><li>SubAccount</li><li>HotelGroup</li></ul>For example, if the hotel group didn't specify multipliers, the hotel group inherits the multipliers from the subaccount. In this case, this field is set to SubAccount.|String|Read-only|Read-only
|BidSource|The source of the bid. The following are the possible values. <ul><li>SubAccount</li><li>HotelGroup</li></ul>For example, if the hotel group specifies multipliers, this field is set to HotelGroup.|String|Read-only|Read-only
|HotelAssociationCount|The number of hotels associated with hotel groups in the subaccount.|Unsigned Integer|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the group.|String|Read-only|Required
|Name|The name of the group. The name may contain a maximum of 256 characters.|String|Required|Read-only
|Status|The status of the hotel group. The following are the possible values.<ul><li>Active&mdash;The hotel group is active. Hotels in the group may actively participate in auctions.</li><li>Paused&mdash;The hotel group is paused. Hotels in the group will not participate in auctions until the owner activates the group again.</li><li>Deleted&mdash;The user deleted the hotel group. Users may delete hotel groups by using the UI only.</li></ul>By default, when you create a hotel group, it is active. To pause an active hotel group, set the `Bid` field to 0. To resume a paused hotel group, set the `Bid` field to a non-zero value.<br /><br />If hotels in the hotel group are not serving, it may be because the subaccount that the hotel group belongs to is not active.|String|Read-only|Read-only


### LengthOfStayMultiplier

Defines the amount to adjust the base bid by if the user stays the specified number of nights or longer.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|MinimumNumberOfNights|The minimum number of nights required to apply the multiplier. Apply the multiplier if the user is staying the specified number of nights or longer. Valid values are 1 through 14.|Integer|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.LengthOfStayMultiplier".|String|Required|Required


### Multiplier

Defines the base class for a multiplier.

Do not specify this class, instead specify one of the multiplier classes such as [UserCountryMultiplier](#UserCountryMultiplier).

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional


### PercentageBid

Defines a bid based on the percentage of the hotel room's rate.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The percentage bid amount. The valid range is 0 through 1000. For example, to bid 5 percent of the room's rate, set `Amount` to 5.0.<br /><br />The bid amount is the per-night bid. For example, if the bid is 3% of a $99 room rate and the itinerary is for a 3-night stay, the final bid is $8.91.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.PercentageBid".|String|Required|Required


### SiteMultiplier

Defines the amount to adjust the base bid by if the user is searching for hotels on one of the specified Bing sites.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|Sites|A list of sites. Apply the multiplier if the user is using one of the sites to search for hotels. The following are the possible values.<br /><br /><ul><li>LocalUniversal&mdash;The user is searching for hotels on Bing.com or a partner site.</li><li>MapResults&mdash;The user is searching for hotels on Bing.com/maps.</li></ul>|String[]|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.SiteMultiplier".|String|Required|Required


### SubAccount

Defines the top-level hotel ads grouping. You can think of this logically as a hotel campaign.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Bid|The base bid that hotels inherit if they, or the group they belong to, don't specify a bid. For usage, see `Bid` in the [Hotel](#Hotel) object.<br /><br />Setting the bid to 0 will pause the subaccount (see `Status`). Pausing the subaccount also pauses the subaccount's hotel groups and hotels.<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#FixedBid)</li><li>[PercentageBid](#PercentageBid)</li></ul>|object|Required|Optional
|BidMultipliers|A list of multipliers that hotels inherit if they, or the group they belong to, don't specify multipliers. For usage, see `BidMultipliers` in the [Hotel](#Hotel) object.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#AdvanceBookingWindowMultiplier)</li><li>[CheckinDayOfWeekMultiplier](#CheckinDayOfWeekMultiplier)</li><li>[DateTypeMultiplier](#DateTypeMultiplier)</li><li>[DeviceMultiplier](#DeviceMultiplier)</li><li>[LengthOfStayMultiplier](#LengthOfStayMultiplier)</li><li>[SiteMultiplier](#SiteMultiplier)</li><li>[UserCountryMultiplier](#UserCountryMultiplier)</li></ul>|object[]|Optional|Optional
|DailyBudget|The daily budget to spread through-out the day.<br /><br />Setting the budget to 0 will pause the subaccount (see `Status`). Pausing the subaccount also pauses the subaccount's hotel groups and hotels.|[Budget](#Budget)|Required|Optional
|HotelAssociationCount|The number of hotels associated with hotel groups in the subaccount.|Unsigned Integer|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the subaccount.|String|Read-only|Required
|MaximumBid|The not-to-exceed bid amount.|[FixedBid](#FixedBid)|Optional|Optional
|Name|The name of the subaccount. The name may contain a maximum of 128 characters.|String|Required|Read-only
|Status|The status of the subaccount. The following are the possible values.<ul><li>Active&mdash;The sub account is active. Hotels in the subaccount may actively participate in auctions.</li><li>Paused&mdash;The subaccount is paused. Hotels in the subaccount will not participate in auctions until the owner activates the subaccount again.</li><li>Deleted&mdash;The user deleted the subaccount. Users may delete subaccounts by using the UI only.</li></ul>By default, when you create a subaccount, it is active. To pause an active subaccount, set the `Bid` or `Budget` field to 0. To resume a paused subaccount, set the `Bid` and `Budget` fields to a non-zero value.|String|Read-only|Read-only


### UserCountryMultiplier

Defines the amount to adjust the base bid by if the user accesses one of the Bing domains.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Countries|A list of two-letter ISO 3116 county codes. Apply the multiplier if the user access the Bing domain with the specified country code. For example, if the list includes US and DE, Bing uses the multiplier if the user uses Bing.com with the *us* or *de* country code (i.e., bing.com?cc=de).|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.UserCountryMultiplier".|String|Required|Required






## HTTP Status Codes

The requests may return the following HTTP status codes.

|Status code|Description
|-----------|-----------
|200|Successfully retrieved the resource.
|201|Successfully added the resource.
|204|Successfully updated the resource.
|400|Bad request. Either a query parameter value is not valid or content in the request body is not valid.
|401|Unauthorized. The user's credentials are not valid. 
|404|Not found. 
|429|Too many requests. The API limits the number of requests you may make per minute. The limit is not documented and is subject to change. The API returns this status code if you exceed the limit. You must wait 60 after receiving this error before resending the request.
|500|Server error.

