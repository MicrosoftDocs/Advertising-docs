---
title: "ProductStatuses Resource"
description: "Describes the Product Statuses resource and related programming elements of Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "bing-ads-shopping-content"
ms.topic: "article"
ms.author: "scottwhi"
---

# ProductStatuses Resource

> [!NOTE]
> The Store resource is available to closed-beta participants only. For information about participating in the closed-beta or open-beta program, please contact your account manager.
>
> All Store programming elements and documentation are subject to change during the beta.

Use the ProductStatuses resource to get the status of product offers in a store.


<!--
For an overview of how the process works, see [How Do I Get the Status of Product Offers?](../shopping-content/how-get-status-product-offers.md)

For a code example that shows how to get the catalog's status and download the report, see [Downloading the Catalog Status Report](../shopping-content/code-examples.md#status).
-->


## Base URI

The following is the base URI that you append the [templates](#templates) to.  

`https://content.api.ads.microsoft.com/v9.1/bmc`

For example, to get a summary view of the status of product offers in a store, use the following endpoint:

`https://content.api.ads.microsoft.com/v9.1/bmc/stores/{merchantId}/productstatusessummary` 


## Templates

These are the templates that you append to the [base URI](#base-uri) to create an HTTP endpoint.

### /stores/{merchantId}/productstatusessummary

|HTTP Verb|Description|Resource
|-|-|-
|Get|Gets a summary view of the status of product offers in a store. This returns the number of offers approved, disapproved, and expiring in the store. Set `{merchantId}` to the ID of the store to get the statuses from.|Request: N/A<br/>Response:[ProductStatusesSummary](#productstatusessummary)


### /stores/{merchantId}/productstatuses 

|HTTP Verb|Description|Resource
|-|-|-
|Get|Gets a detail view of the status of product offers in a store. Details are returned for products with a status of disapproved or warning. Set `{merchantId}` to the ID of the store to get the statuses from.<br/><br/>This request get the first 25 statuses only. To page through all product status details, use the *max-results* and *start-token* [query parameters](#query-parameters).|Request: N/A<br/>Response:[ProductStatuses](#productstatuses)


## Query parameters

The request may include the following query parameters:

|Parameter|Description
|-|-
|<a name="maxresults"></a>max-results|Optional. Use to specify the maximum number of items to return in a List request such as `/stores/{merchantId}/productstatuses`. The maximum value that you may specify is 250. The default is 25. 
|<a name="continuationtoken"></a>continuation-token|Optional. Use to page through a store's list of product statuses. The token identifies the next page of product statuses to return. Do not specify this parameter in the first List request. If the store contains more than the requested number of products (see the *max-results* query parameter), the response includes the `nextPageToken` field. In the next request, set *continuation-token* to the token value in `nextPageToken`.


## Headers

The following are the request and response headers.
 
|Header|Description
|-|-
|<a name="authtoken"></a>AuthenticationToken|Request header.<br/><br/>Set this header to an OAuth access token. For information about getting an access token, see [Authenticating your credentials](get-started.md#authentication).
|Content-Type|Request header.<br/><br/>All POST requests must specify this header and it must be set to `application/json`.
|<a name="customeraccountid"></a>CustomerAccountId|Request header.<br/><br/>The account ID of any account that you manage on behalf of the customer specified in the `CustomerId` header. It doesn't matter which account you specify. Specify this header only if you manage an account on behalf of the customer.
|<a name="customerid"></a>CustomerId|Request header.<br/><br/>The customer ID of the customer whose store you manage. Specify this header only if you manage the store on behalf of the customer. If you set this header, you must also set the `CustomerAccountId`  header.  
|<a name="devtoken"></a>DeveloperToken|Request header.<br/><br/>The client application's developer token. Each request must include this header. For information about getting a token, see [Do you have your Microsoft Advertising credentials and developer token?](get-started.md#credentials)
|WebRequestActivityId|Response header.<br/><br/>The ID of the log entry that contains details of the request. You should always capture this ID if an error occurs. If you are not able to determine and resolve the issue, include this ID along with the other information that you provide the Support team.


## Request and response objects

The following are the request and response objects used by the API.
 
|Object|Description
|-|-
|[Error](#error)|Defines an error.
|[ErrorResponse](#errorresponse)|Defines the top-level error object.
|[ProductStatus](#productstatus)|Defines a product offer's status.
|[ProductStatuses](#productstatuses)|Defines a list of the product offers that have issues.
|[ProductStatusesSummary](#productstatusessummary)|Defines a summary view of the status of product offers in a store.
|[ProductStatusItemLevelIssue ](#productstatusitemlevelissue )|Defines an issue with the product offer.


### Error

Defines an error.

|Name|Value|Type
|-|-|-
|domain|For internal use only.|String
|location|Not used.|String
|locationType|Not used.|String
|message|A description of the error.|String
|reason|The reason why the request failed.|String


### ErrorResponse

Defines the top-level error object.

|Name|Value|Type
|-|-|-
|errors|A list of errors that occurred while processing the request.|[Error](#error)[]


### ProductStatus

Defines a product offer's status.

|Name|Value|Type
|-|-|-
|creationDate|The date and time when the product offer was created.|DateTime
|expirationDate|The date and time when the product offer is set to expire.|DateTime
|itemLevelIssues|The list of issues with the product offer.|[ProductStatusItemLevelIssue](#productstatusitemlevelissue)[]
|lastUpdateDate|The date and time when the product offer was last updated.|DateTime 
|productId|The product's ID.|String
|status|The product's approval status. Possible values are:<ul><li>Disapproved</li><li>Warning</li></ul>A warning status indicates that the product has issues that should be addressed but they won't prevent the product offer from serving.|String
|title|The product's title|String


### ProductStatuses

Defines a list of the product offers that have issues.

|Name|Value|Type
|-|-|-
|nextPageToken|The token to set the [continuation-token](#continuationtoken) query parameter to if there are more product offers available to get.|String
|resources|The list of product offers that have issues. The [max-results](#maxresults) query parameter determines the maximum number of offers in the list; the actual number may be less.|[ProductStatus](#productstatus)[]


### ProductStatusesSummary

Defines a summary view of the status of product offers in a store. If the store was just created, all values will be zero.

|Name|Value|Type
|-|-|-
|approved|The total number of products in the store that are approved.|Integer
|disapproved|The total number of products in the store that are disapproved due to errors.|Integer
|expiring|The total number of products in the store that will expire within the next 72 hours.|Integer
|merchantId|The ID of the store the products are in.|Unsigned long
|pending|The total number of products pending review.|Integer


### ProductStatusItemLevelIssue

Defines an issue with the product offer.

|Name|Value|Type
|-|-|-
|attributeName|The name of the product offer's property that is causing the issue.|String
|code|The error code that identifies the issue. For example, TitleTooLongErr.|String
|description|A description that explains the issue with the property.|String
|servability|A value that indicates whether the issue prevents the offer from serving. Possible values are:<ul><li>Disapproved</li><li>Unaffected</li></ul>If Disapproved, the offer will not serve.|String


## HTTP status codes

The requests may return the following HTTP status codes.

|Status code|Description
|-|-
|200|Success.
|400|Bad request. Most likely the request specifies an invalid query parameter or parameter value.
|401|Unauthorized. The user's credentials are not valid. 
|404|Not found. The requested store was not found. 
|500|Server error.


## Error codes

The requests may return the following error codes.

|Error code|Description
|-|-
|ContinuationTokenInvalidErr|The [continuation-token](#continuationtoken) query parameter value is not valid. Make sure you set the parameter using the value in the [ProductStatuses](#productstatuses) object's `nextPageToken` field.

