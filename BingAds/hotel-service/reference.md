---
title: "Hotel API Reference"
description: Describes the endpoint, headers, query parameters, and objects of the Hotel Ads API.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Hotel API reference

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.
>
> The API and documentation are subject to change.

The Hotel API lets you manage your hotel ad campaigns and bidding.

## Endpoints

The following are the base URIs that you use to construct the endpoint.  

- Sandbox&mdash;`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/`
- Production&mdash;`https://partner.api.bingads.microsoft.com/Travel/v1/`

The endpoint must include the customer and account resources.

`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/Customers({customerId})/Accounts({accountId})/`

Set {customerId} to the customer's CustomerId and {accountId} to the customer's CustomerAccountId.

Next, append a template from the following table to add, get, and update hotel resources. For example, to get or add a hotel group, use the following endpoint:

`https://partner.api.sandbox.bingads.microsoft.com/Travel/V1/Customers({customerId})/Accounts({accountId})/SubAccounts('{subAccountId}')/HotelGroups`.  

> [!NOTE]
> The IDs for SubAccounts, HotelGroups, Hotels, and ReportJobs are strings and must be enclosed in single quotes. For example, SubAccounts('12345')/HotelGroups. This applies to SubAccounts, HotelGroups, Hotels, and ReportJobs only; do not use single quotes for Customers and Accounts.

|Template|Verb|Description|
|-|-|-
|<a name="listsubaccounts" />SubAccounts|GET|Gets the list of hotel campaigns defined for the specified account.<br /><br />NOTE: By default, the list contains a maximum of 1,000 campaigns. To determine the total number of campaigns in the subaccount, use the [$count](#count-param) query paramater. To specify the number of campaigns to return, use the [$top](#top-param) query parameter. To page through all campaigns in a subaccount, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [SubAccount](#subaccount) objects.
|<a name="addsubaccounts" />SubAccounts|POST|Adds the subaccount to the specified account. You can think of subaccounts as hotel campaigns. Use subaccounts to logically organize your hotel ad campaigns. You may have up to 1,000 active hotel campaigns per account.<br /><br />**NOTE**: For the Beta release, an account may have one subaccount only.<br /><br />**Request body**: Contains the [SubAccount](#subaccount) to add.<br /><br />**Response body**: If successful, contains an [AddResponse](#addresponse) object. The `value` field contains the ID of the added hotel campaign.
|<a name="getsubaccount" />SubAccounts('{subAccountId}')|GET|Gets the specified subaccount.<br /><br />**Response body**: Contains a [SubAccount](#subaccount) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to get.</li></ul>
|<a name="updatesubaccount" />SubAccounts('{subAccountId}')|PATCH|Updates the subaccount.<br /><br />**Request body**: Contains a [SubAccount](#subaccount) object that specifies only those fields to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to update.</li></ul>
|<a name="listhotelgroups" />SubAccounts('{subAccountId}')/HotelGroups|GET|Gets the list of hotel groups in the specified subaccount.<br /><br />NOTE: By default, the list contains a maximum of 1,000 hotel groups. To determine the total number of groups in the subaccount, use the [$count](#count-param) query paramater. To specify the number of groups to return, use the [$top](#top-param) query parameter. To page through all groups in a subaccount, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [HotelGroup](#hotelgroup) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel groups to get.</li></ul>
|<a name="addhotelgroup" />SubAccounts('{subAccountId}')/HotelGroups|POST|Adds the hotel group to the specified subaccount. Use hotel groups to create logical groupings of hotel ads. You may create up to 1,000 active hotel groups per subaccount.<br /><br />**Request body**: Contains the [HotelGroup](#hotelgroup) to add to the subaccount.<br /><br />**Response body**: If successful, contains an [AddResponse](#addresponse) object. The `value` field contains the ID of the added hotel group.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to add the hotel group to.</li></ul>
|<a name="gethotelgroup" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')|GET|Gets the specified hotel group.<br /><br />**Response body**: Contains a [HotelGroup](#hotelgroup) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroupId}`&mdash;Set to the ID of the hotel group to get.</li></ul>
|<a name="updatehotelgroup" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')|PATCH|Updates the hotel group.<br /><br />**Request body**: Contains a [HotelGroup](#hotelgroup) object that specifies only those fields to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroupId}`&mdash;Set to the ID of the hotel group to update.</li></ul>
|<a name="deletehotelgroup" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroupId}')|DELETE|Deletes the hotel group.<br /><br />**Request body**: None.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroupId}`&mdash;Set to the ID of the hotel group to delete.</li></ul>
|<a name="listallhotels" />SubAccounts('{subAccountId}')/Hotels|GET|Gets the list of hotel ads in the specified subaccount. The list contains all hotels across all hotel groups in the subaccount.<br /><br />NOTE: By default, the list contains a maximum of 1,000 hotels. To determine the total number of hotels in the subaccount, use the [$count](#count-param) query paramater. To specify the number of hotels to return, use the [$top](#top-param) query parameter. To page through all hotels in a subaccount, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [Hotel](#hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotels to get.</li></ul>.
|<a name="listhotels" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels|GET|Gets the list of hotel ads in the specified hotel group.<br /><br />NOTE: By default, the list contains a maximum of 1,000 hotels. To determine the total number of hotels in the hotel group, use the [$count](#count-param) query paramater. To specify the number of hotels to return, use the [$top](#top-param) query parameter. To page through all hotels in a group, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [Hotel](#hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotels to get.</li></ul>.
|<a name="gethotel" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels('{hotelId}')|GET|Gets the specified hotel ad.<br /><br />**Response body**: Contains a [Hotel](#hotel) object.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotel to get.</li><li>`{hotelId}`&mdash;Set to the hotel ad to get.</li></ul>
|<a name="updatehotel" />SubAccounts('{subAccountId}')/HotelGroups('{hotelGroup}')/Hotels('{hotelId}')|PATCH|Updates the hotel ad.<br /><br />**Request body**: Contains a [Hotel](#hotel) object that specifies only those fields to update.<br /><br />**Response body**: None. If successful, returns HTTP status code 204.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the hotel group.</li><li>`{hotelGroup}`&mdash;Set to the ID of the hotel group that contains the hotel to update.</li><li>`{hotelId}`&mdash;Set to the hotel ad to update.</li></ul>
|<a name="ungrouped" />SubAccounts('{subAccountId}')/Ungrouped|GET|Gets the list of hotels in the Ungrouped hotel group. When you create a subaccount, Bing creates the Ungrouped hotel group. All hotels from your hotel feed that are not otherwise associated with other groups are placed in this group. To associate a hotel in this group with a different hotel group, see the [Associate](#associate) template. <br /><br />NOTE: By default, the list contains a maximum of 1,000 hotels. To determine the total number of hotels in the Ungrouped hotel group, use the [$count](#count-param) query paramater. To specify the number of hotels to return, use the [$top](#top-param) query parameter. To page through all hotels in the group, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [Hotel](#hotel) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the ungrouped hotel ads to get.</li></ul>
|<a name="associations" />SubAccounts('{subAccountId}')/Associations|GET|Gets a list of hotel and hotel group associations.<br /><br />NOTE: By default, the list contains a maximum of 1,000 associations. To determine the total number of associations in the subaccount, use the [$count](#count-param) query paramater. To specify the number of associations to return, use the [$top](#top-param) query parameter. To page through all associations in a subaccount, use the $top and [$skip](#skip-param) query parameters. <br/><br/>**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains the list of [HotelAssociation](#hotelassociation) objects.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount that contains the associations to get.</li></ul>
|<a name="associate" />SubAccounts('{subAccountId}')/Associate|POST|Adds a list of hotel and hotel group associations to the subaccount.<br /><br />**Request body**: Contains an [AssociationCollection](#associationcollection) object. The `HotelAssociation` field contains a list with a maximum of 500 [HotelAssociation](#hotelassociation) objects. Each object associates a hotel with a hotel group. You can associate a hotel with only one hotel group.<br /><br />**Response body**: Contains a [CollectionResponse](#collectionresponse) object. The `value` field contains a list of [HotelAssociation](#hotelassociation) objects. The list contains only those associations that failed validation. The list is empty if there are no errors. The association's `Errors` field contains the list of reasons why the association failed.<br /><br />**Resource parameters**:<ul><li>`{subAccountId}`&mdash;Set to the ID of the subaccount to add the associations to.
|<a name="addreportjob" />ReportJobs|POST|Adds a report request to the report queue. <br /><br />**Request body**: Contains the [ReportJob](#reportjob) object that defines the report request that you're adding to the queue.<br /><br />**Response body**: If the report request is successfully added to the queue, the body is an [AddResponse](#addreponse) object that contains the ID of the report job. Use the ID in subsequent GET requests to get the status of the report job (see the [ReportJobs('{jobId}')](#getreportjob) template).
|<a name="getreportjob" />ReportJobs('{jobId}')|GET|Gets the status of the specified report job.<br /><br />**Response body**: Contains a [ReportJob](#reportjob) object. Use the `Status` field to determine when the job finishes. When the job is complete, use the URL in the `Url` field to download the report.<br /><br />**Resource parameters**:<ul><li>`{jobId}`&mdash;The ID of the report job to get the status of. Set to the ID of the report job that your POST request returned.</li></ul>


## Query Parameters

The following are the query parameters that the request may specify.

|Parameter|Description
|-|-
|<a name="count-param"/>$count|An OData parameter that determines whether the response includes an `@odata.count` field. Typically, you include this parameter when you request a list of entities, such as a list of hotel groups. The `@odata.count` field contains the total number of resource entities available, not those returned in the request. For example, if you set $top to 40, but 1,000 entities exist, `@odata.count` is set to 1,000, not 40. To include the count, set $count to **true**.
|<a name="filter-param"/>$filter|An OData parameter that specifies a list of expressions used to filter the data.<br/><br/>**NOTE:** You may use the $filter parameter only with the [/Associations](#associations) resource. For more information, see [Filtering hotel associations](manage-hotel-campaigns.md#filterassociations).
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
|[AddResponse](#addresponse)|Defines a response object for requests that add a resource.
|[AdsApiError](#adsapierror)|Defines an error that occurred.
|[AdvanceBookingWindowMultiplier](#advancebookingwindowmultiplier)|Defines the amount to adjust the base bid by if the user books the specified number of days in advance.
|[AssociationCollection](#associationcollection)|Defines a collection of hotel associations.
|[Budget](#budget)|Defines the daily budget for hotel ads in a subaccount.
|[CollectionResponse](#collectionresponse)|Defines a response object for requests that get a list of resources.
|[CheckinDayOfWeekMultiplier](#checkindayofweekmultiplier)|Defines the amount to adjust the base bid by if the user checks in on one of the specified weekdays.
|[DateTypeMultiplier](#datetypemultiplier)|Defines the amount to adjust the base bid by if the user searched for hotels using specific dates.
|[DeviceMultiplier](#devicemultiplier)|Defines the amount to adjust the base bid by if the user is using one of the specified devices to search for hotels.
|[FixedBid](#fixedbid)|Defines a fixed bid amount.
|[Hotel](#hotel)|Defines a hotel ad.
|[HotelAssociation](#hotelassociation)|Defines the association between a hotel and a hotel group.
|[HotelGroup](#hotelgroup)|Defines a logical grouping of hotel ads.
|[LengthOfStayMultiplier](#lengthofstaymultiplier)|Defines the amount to adjust the base bid by if the user stays the specified number of nights or longer.
|[PercentageBid](#percentagebid)|Defines a bid based on the percentage of the hotel room's rate.
|[ReportJob](#reportjob)|Defines a report job.
|[SiteMultiplier](#sitemultiplier)|Defines the amount to adjust the base bid by if the user is searching for hotels on one of the specified Bing sites.
|[SubAccount](#subaccount)|Defines the top-level hotel ads grouping. You can think of this logically as a hotel campaign.
|[UserCountryMultiplier](#usercountrymultiplier)|Defines the amount to adjust the base bid by if the user accesses one of the Bing domains.


### AddResponse

Defines a response object for requests that add a resource.

|Name|Value|Type
|-|-|-
|value|The ID of the resource that you added.|object


### AdsApiError

Defines an error that occurred.

|Name|Value|Type
|-|-|-
|Code|A symbolic code that identifies the error. For a list of codes, see [Error codes](#error-codes).|String
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
|HotelAssociations|The list of hotel and hotel group associations. The list may contain a maximum of 500 associations.|[HotelAssociation](#hotelassociation)[]|Required|N/A


### Bid

Defines the base class for a bid.

Do not specify this class, instead specify the [FixedBid](#fixedbid) or [PercentageBid](#percentagebid) class.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The dollar bid amount. For details about the valid bid range for your market, see the Currency Value table in the [Currencies](https://msdn.microsoft.com/library/bing-ads-currencies.aspx) topic. The customer's account specifies the currency used.|Double|Required|Optional


### Budget

Defines the daily budget for hotel ads in a subaccount.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The daily budget amount. For details about valid budgets for your market, see the Currency Value table in the [Currencies](https://msdn.microsoft.com/library/bing-ads-currencies.aspx) topic. The customer's account specifies the currency used for the budget.|Double|Required|Optional


### CheckinDayOfWeekMultiplier

Defines the amount to adjust the base bid by if the user checks in on one of the specified weekdays.


|Name|Value|Type|Add|Update
|-|-|-|-|-
|DaysOfWeek|A list of weekdays. Apply the multiplier if the user is checking on one of the specified days. The following are the possible case-sensitive values.<br /><br /><ul><li>Monday</li><li>Tuesday</li><li>Wednesday</li><li>Thursday</li><li>Friday</li><li>Saturday</li><li>Sunday</li></ul>|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.CheckinDayOfWeekMultiplier".|String|Required|Required


### CollectionResponse

Defines a response object for requests that get a list of resources.

|Name|Value|Type
|-|-|-
|value|The list of requested resources. Depending on the request, the list contains one of the following types of objects:<ul><li>[Hotel](#hotel)</li><li>[HotelGroup](#hotelgroup)</li><li>[SubAccount](#subaccount)</li><li>[HotelAssociation](#hotelassociation)</li></ul>For example, if you request a list of hotel groups, `value` contains a list of `HotelGroup` objects.|object[]
|@odata.count|The total number resource entities available, not the number of entities in `Value`. The response includes this field only if you include the $count query parameter in the request.


### DateTypeMultiplier

Defines the amount to adjust the base bid by if the user searched for hotels using specific dates.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|DateType|The type of date used in the search. The following are the possible case-sensitive values.<br /><br /><ul><li>Default&mdash;The user didn't search for hotels using specific dates</li><li>Selected&mdash;The user searched for hotels using specific dates.</li></ul>|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.DateTypeMultiplier".|String|Required|Required


### DeviceMultiplier

Defines the amount to adjust the base bid by if the user is using one of the specified devices to search for hotels.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|DeviceTypes|A list of device types. Apply the multiplier if the user is using one of the device types to search for hotels. The following are the possible case-sensitive values.<br /><br /><ul><li>Desktop</li><li>Mobile</li><li>Tablet</li></ul>|String[]|Required|Optional
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
|Bid|The base bid. Bing uses this bid in the auction unless you specify one or more multipliers (see `BidMultipliers`). If you don't specify a bid, the hotel inherits the bid from the hotel group or subaccount, in that order. When getting a hotel, if the hotel doesn't specify a bid, this field contains the inherited bid.<br /><br />Setting the bid to 0 prevents the hotel from serving.<br /><br />If the hotel specifies a bid and you want to remove it, set `Bid` to null.<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#fixedbid)</li><li>[PercentageBid](#percentagebid)</li></ul>|object|N/A|Optional
|BidMultipliers|A list of multipliers to apply to the base bid. Bing applies the multipliers to the base bid and uses the adjusted bid in the auction. If the hotel does not specify a bid, the multipliers adjust the inherited bid.<br /><br />If you don't specify multipliers, the hotel inherits them from the hotel group or subaccount, in that order. When getting a hotel, if the hotel doesn't specify multipliers, this field contains the inherited multipliers.<br /><br />If the hotel specifies multipliers and you want to remove them, set `BidMultipliers` to an empty array.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#advancebookingwindowmultiplier)</li><li>[CheckinDayOfWeekMultiplier](#checkindayofweekmultiplier)</li><li>[DateTypeMultiplier](#datetypemultiplier)</li><li>[DeviceMultiplier](#devicemultiplier)</li><li>[LengthOfStayMultiplier](#lengthofstaymultiplier)</li><li>[SiteMultiplier](#sitemultiplier)</li><li>[UserCountryMultiplier](#usercountrymultiplier)</li></ul>|object[]|N/A|Optional
|BidMultiplierSource|The source of the bid multipliers. The following are the possible values.<ul><li>SubAccount</li><li>HotelGroup</li><li>Hotel</li></ul>For example, if the hotel and hotel group didn't specify multipliers, the hotel inherits the multipliers from the subaccount. In this case, this field is set to SubAccount.|String|N/A|Read-only
|BidSource|The source of the bid. The following are the possible values.<ul><li>SubAccount</li><li>HotelGroup</li><li>Hotel</li></ul>For example, if the hotel specifies a bid, this field is set to Hotel.|String|N/A|Read-only
|CountryCode|The two-letter ISO 3116 county code of the country where the hotel is located. The country is the same country that you specified for the hotel in your hotel feed file.|String|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the hotel.|String|N/A|Required
|Name|The name of the hotel. The name is the same name you specified in your hotel feed file.|String|N/A|Read-only
|PartnerHotelId|The ID that you used to identify the hotel in the hotel feeds file.|String|N/A|Read-only
|Status|The status of the hotel entity. The following are the possible values.<ul><li>Active&mdash;The hotel is not deleted and may be updated.</li><li>Deleted&mdash;The user deleted the hotel. Users may delete hotels by using the UI only.</li></ul>|String|N/A|Read-only


### HotelAssociation

Defines the association between a hotel and a hotel group.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Errors|The list of reasons why the association failed validation.<br /><br />The response includes this field only if the association failed validation when you tried to add it.|[AdsApiError](#adsapierror)|Read-only|N/A
|HotelGroupId|The ID of the hotel group to associate the hotel with.|String|Required|N/A
|HotelGroupName|The name of the hotel group.|String|Read-only|N/A
|HotelId|The ID of the hotel to associate with the specified hotel group. You may associate the hotel with one hotel group only.<br /><br />By default, all hotels are associated with a hotel group whether it's a user-defined group or the default Ungrouped hotel group. To move a hotel from one group to another, post a new association that specifies the hotel ID and new hotel group ID.|String|Required|N/A
|HotelName|The name of the hotel.|String|Read-only|N/A
|PartnerHotelId|The ID that you used to specify the hotel in the hotel feeds file.|String|Read-only|N/A


### HotelGroup

Defines a logical grouping of hotels.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Bid|The base bid that hotels in the group inherit if they don't specify a bid. For usage, see `Bid` in the [Hotel](#hotel) object.<br /><br /> If you don't specify a bid, the group inherits the bid from the subaccount. When getting a hotel group, if the group doesn't specify a bid, this field contains the inherited bid.<br /><br />Setting the bid to zero (0) prevents hotels in the group from serving.<br /><br />If the hotel group specifies a bid and you want to remove it, set `Bid` to null.<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#fixedbid)</li><li>[PercentageBid](#percentagebid)</li></ul>|object|Optional|Optional
|BidMultipliers|A list of multipliers that hotels in the group inherit if they don't specify multipliers. For usage, see `BidMultipliers` in the [Hotel](#hotel) object.<br /><br /> If you don't specify multipliers, the group inherits them from the subaccount.<br /><br />If the hotel group specifies multipliers and you want to remove them, set `BidMultipliers` to an empty array.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#advancebookingwindowmultiplier)</li><li>[CheckinDayOfWeekMultiplier](#checkindayofweekmultiplier)</li><li>[DateTypeMultiplier](#datetypemultiplier)</li><li>[DeviceMultiplier](#devicemultiplier)</li><li>[LengthOfStayMultiplier](#lengthofstaymultiplier)</li><li>[SiteMultiplier](#sitemultiplier)</li><li>[UserCountryMultiplier](#usercountrymultiplier)</li></ul>|object[]|Optional|Optional
|BidMultiplierSource|The source of the bid multipliers. The following are the possible values. <ul><li>SubAccount</li><li>HotelGroup</li></ul>For example, if the hotel group didn't specify multipliers, the hotel group inherits the multipliers from the subaccount. In this case, this field is set to SubAccount.|String|Read-only|Read-only
|BidSource|The source of the bid. The following are the possible values. <ul><li>SubAccount</li><li>HotelGroup</li></ul>For example, if the hotel group specifies multipliers, this field is set to HotelGroup.|String|Read-only|Read-only
|HotelAssociationCount|The number of hotels associated with hotel groups in the subaccount.|Unsigned Integer|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the group.|String|Read-only|Required
|Name|The name of the group. The name may contain a maximum of 256 characters.|String|Required|Read-only
|Status|The status of the hotel group entity. The following are the possible values.<ul><li>Active&mdash;The hotel group is not deleted and may be updated.</li><li>Deleted&mdash;The user deleted the hotel group. Users may delete hotel groups by using the UI only.</li></ul>|String|Read-only|Read-only


### LengthOfStayMultiplier

Defines the amount to adjust the base bid by if the user stays the specified number of nights or longer.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|MinimumNumberOfNights|The minimum number of nights required to apply the multiplier. Apply the multiplier if the user is staying the specified number of nights or longer. Valid values are 1 through 14.|Integer|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.LengthOfStayMultiplier".|String|Required|Required


### Multiplier

Defines the base class for a multiplier.

Do not specify this class, instead specify one of the multiplier classes such as [UserCountryMultiplier](#usercountrymultiplier).

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional


### PercentageBid

Defines a bid based on the percentage of the hotel room's rate.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Amount|The percentage bid amount. The valid range is 0 through 1000. For example, to bid 5 percent of the room's rate, set `Amount` to 5.0.<br /><br />The bid amount is the per-night bid. For example, if the bid is 3% of a $99 room rate and the itinerary is for a 3-night stay, the final bid is $8.91.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.PercentageBid".|String|Required|Required


### ReportJob

Defines a report job.

|Name|Value|Type|Add
|-|-|-|-
|<a name="columns" />Columns|The list of columns to include in the report. The order that the report includes them is undetermined. The reporting service may also interleave other relevant columns not explicitly requested. The column names are case sensitive. For a list of column names, see Report Columns for the report type you're requesting (for example, for PerformanceReport, see [Performance report columns](reporting.md#performance-report-columns)). The columns must include at lease one dimension-type column and one metric-type column.|String[]|Required
|<a name="compression" />Compression|The type of compression to apply to the report. The following are the possible case-insensitive values.<ul><li>ZIP</li></ul>The default is no compression.|String|Optional
|<a name="enddate" />EndDate|The UTC end date of the report in the form YYYY-MM-dd. The month and day must contain two digits. For example, 2018-1-4 must be 2018-01-04.<br/><br/>The report contains data that falls within the start and end dates, inclusively. The end date must be on or later than the start date.<br><br>**NOTE:** When polling to get the status of the job, the service returns the date in the form YYYY-MM-ddTHH:mm:ssZ (for example, 2017-10-30T00:00:00Z).|String|Required
|<a name="filter" />Filter|The OData filter string to apply. The maximum length of the filter string is 1,000 characters. For information about using filters, see [Filtering report data](reporting.md#filtering-report-data).<br/><br/>**NOTE:** The report column names and enumeration values that you specify are case sensitive. For example, you must specify DeviceType instead of devicetype, and Desktop instead of desktop. |String|Optional
|<a name="format" />Format|The format of the contents in the report. The following are the possible case-insensitive values.<ul><li>CSV</li></ul>The default is CSV.|String|Optional
|<a name="hotelgroupid" />HotelGroupId|The ID of the hotel to limit the report to. To set this field, you must also set `SubaccountId`.|String|Optional
|Id|An ID that uniquely identifies the report job.|String|Read-only
|<a name="includenonperforminghotels" />IncludeNonPerformingHotels|A Boolean value that determines whether the report includes hotels that haven't received impressions during the reporting period. To include non-performing hotels, set this field to **true**; otherwise, **false**. The default is **false**.<br/><br/>For limitations about the columns that you may specify when requesting non-performing hotels, see [Including non-performing hotels in the report](reporting.md#including-non-performing-hotels-in-the-report).|Boolean|Optional
|<a name="reporttype" />ReportType|The type of entity or report to download. The following are the possible case-sensitive values. <ul><li>[Performance](reporting.md#performance-report-columns)</li></ul>|String|Required
|<a name="startdate" />StartDate|The UTC start date of the report in the form YYYY-MM-dd. The month and day must contain two digits. For example, 2018-1-4 must be 2018-01-04. The earliest date that you may specify is three years from today.<br><br>**NOTE:** When polling to get the status of the job, the service returns the date in the form YYYY-MM-ddTHH:mm:ssZ (for example, 2017-10-30T00:00:00Z).|String|Required
|<a name="status" />Status|The status of the report job. The following are the possible values.<ul><li>Completed&mdash;The report job completed successfully. Use the URL in the `Url` field to download the report.</li><li>Failed&mdash;The job failed for some reason. In case the error is a transient error, you may want to resubmit the job. If the job fails again, capture the the request ID in the X-MS-RequestId header and contact support.</li><li>InProgress&mdash;The service is in the process of building the report.</li><li>PendingExecution&mdash;The report request is queued</li></ul>|String|Read-only
|<a name="subaccountid" />SubaccountId|The ID of the subaccount to limit the report to.|String|Optional
|<a name="url" />Url|The URL of the report to download. The service provides the URL when `Status` is Completed. The URL is valid for five (5) minutes from the time you get a report job with `Status` set to Completed. If the URL expires, send a GET request to get the status of the job again and a new URL.


### SiteMultiplier

Defines the amount to adjust the base bid by if the user is searching for hotels on one of the specified Bing sites.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|Sites|A list of sites. Apply the multiplier if the user is using one of the sites to search for hotels. The following are the possible case-sensitive values.<br /><br /><ul><li>LocalUniversal&mdash;The user is searching for hotels on Bing.com.</li><li>MapResults&mdash;The user is searching for hotels on Bing.com/maps.</li></ul>|String[]|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.SiteMultiplier".|String|Required|Required


### SubAccount

Defines the top-level hotel ads grouping. You can think of this logically as a hotel campaign.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Bid|The base bid that hotels inherit if they, or the group they belong to, don't specify a bid. For usage, see `Bid` in the [Hotel](#hotel) object.<br /><br />Setting the bid to 0 prevents hotels in the subaccount from serving.<br /><br />The following are the types of bids that you may specify.<ul><li>[FixedBid](#fixedbid)</li><li>[PercentageBid](#percentagebid)</li></ul>|object|Required|Optional
|BidMultipliers|A list of multipliers that hotels inherit if they, or the group they belong to, don't specify multipliers. For usage, see `BidMultipliers` in the [Hotel](#hotel) object.<br /><br />If the subaccount specifies multipliers and you want to remove them, set `BidMultipliers` to an empty array.<br /><br />The following are the types of multipliers that you may specify.<ul><li>[AdvanceBookingWindowMultiplier](#advancebookingwindowmultiplier)</li><li>[CheckinDayOfWeekMultiplier](#checkindayofweekmultiplier)</li><li>[DateTypeMultiplier](#datetypemultiplier)</li><li>[DeviceMultiplier](#devicemultiplier)</li><li>[LengthOfStayMultiplier](#lengthofstaymultiplier)</li><li>[SiteMultiplier](#sitemultiplier)</li><li>[UserCountryMultiplier](#usercountrymultiplier)</li></ul>|object[]|Optional|Optional
|DailyBudget|The daily budget to spread through-out the day.<br /><br />Setting the budget to 0 prevents hotels in the subaccount from serving.|[Budget](#budget)|Required|Optional
|HotelAssociationCount|The number of hotels associated with hotel groups in the subaccount.|Unsigned Integer|Read-only|Read-only
|Id|A system-generated ID that uniquely identifies the subaccount.|String|Read-only|Required
|MaximumBid|The not-to-exceed bid amount.|[FixedBid](#fixedbid)|Optional|Optional
|Name|The name of the subaccount. The name may contain a maximum of 128 characters.|String|Required|Read-only
|Status|The status of the subaccount entity. The following are the possible values.<ul><li>Active&mdash;The sub account is not deleted and may be updated.</li><li>Deleted&mdash;The user deleted the subaccount. Users may delete subaccounts by using the UI only.</li></ul>|String|Read-only|Read-only


### UserCountryMultiplier

Defines the amount to adjust the base bid by if the user accesses one of the Bing domains.

|Name|Value|Type|Add|Update
|-|-|-|-|-
|Countries|A list of two-letter ISO 3116 county codes. For a list of possible country codes, see [Bing Ads country codes](https://help.bingads.microsoft.com/apex/index/3/en-us/50873#!).<br /><br />Apply the multiplier if the user accesses the Bing domain with the specified country code. For example, if the list includes US and DE, Bing uses the multiplier if the user uses Bing.com with the *us* or *de* country code (for example, bing.com?cc=de).|String[]|Required|Optional
|Factor|The percentage amount to adjust the base bid by. The valid range is 0.0 through 10.0, with a precision of two decimal places. For example, if the fixed bid is $5 and the multiplier is 5, the final bid is $25. Using the same multiplier, if the percentage bid is 5% and the room rate is $100, the final bid is $25.|Double|Required|Optional
|@odata.type|The object's type. This field is set to "#Model.UserCountryMultiplier".|String|Required|Required






## HTTP status codes

The requests may return the following HTTP status codes.

|Status code|Description
|-----------|-----------
|200|Successfully retrieved the resource.
|201|Successfully added the resource.
|204|Successfully updated or deleted the resource.
|400|Bad request. Either a query parameter value is not valid or content in the request body is not valid.
|401|Unauthorized. The user's credentials are not valid.
|403|Forbidden. The download URL for the report has expired. You have seven days from the time you get the URL to download the report. If the URL expires, you must submit a new job request. 
|404|Not found. 
|429|Too many requests. The API limits the number of requests you may make per minute. The limit is not documented and is subject to change. The API returns this status code if you exceed the limit. You must wait 60 after receiving this error before resending the request.
|500|Server error.



## Error codes

### Reporting error codes

|Error code|Description
|-|-
|CompressionTypeNotSupported|The `Compression` field is set to a value this is not supported. For a list of supported compression algorithms, see [Compression](#compression).
|DuplicateValues|The [Columns](#columns) field contains the same column name more than once.</li></ul>
|FilterTooLong|The OData filter string that you set `Filter` to is too long. For the allowed maximum length, see [Filter](#filter).
|FormatVersionNotSupported|The `Format` field is set to a value this is not supported. For a list of supported formats, see [Format](#format).
|InvalidDateRange|The reporting period that you specified is not valid. For information about specifying a valid date range, see the [StarteDate](#startdate) and [EndDate](#enddate) fields.
|InvalidReportName|The `ReportType` field is set to a report name that is not valid. For a list of valid report names, see [ReportType](#reporttype).
|InvalidSelect|One or more of the columns that you specified are not valid. Compare the column names that you used to those documented for the report you requested. Remember, the names are case sensitive.

