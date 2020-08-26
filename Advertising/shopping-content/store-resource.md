---
title: "Store Resource"
description: "Describes the Store resource and related programming elements of Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---

# Store Resource

> [!NOTE]
> The Store resource is available to closed-beta participants only. For information about participating in the closed-beta or open-beta program, please contact your account manager.
>
> All Store programming elements and documentation are subject to change during the beta.

Use the Store resource to manage the stores that the user owns. You can add stores, get a specific store, or get all stores owned by the user.  

<!--
For an overview of how the process works, see [How Do I Get the Status of Product Offers?](../shopping-content/how-get-status-product-offers.md)

For a code example that shows how to get the catalog's status and download the report, see [Downloading the Catalog Status Report](../shopping-content/code-examples.md#status).
-->


## Base URI

The following is the base URI that you append the [templates](#templates) to.  

`https://content.api.ads.microsoft.com/v9.1/bmc`

For example, to add a store or get a list of stores owned by the user, use the following endpoint:

`https://https://content.api.ads.microsoft.com/v9.1/bmc/stores` 


## Templates

These are the templates that you append to the [base URI](#base-uri) to create an HTTP endpoint.

### /stores template

|HTTP Verb|Description|Resource
|-|-|-
|POST|Adds a store. The following limits apply and are subject to change:<ul><li>A customer may add a maximum of 14 stores that specify the same store URL.</li><li>A customer may add a maximum of 1,024 stores.</li></ul>|Request: [StoreCreate](#storecreate)<br/>Response: [Store](#store)
|GET|Gets a list of stores owned by the user.|Request: N/A<br/>Response: [StoreCollection](#storecollection)


### /stores/{merchantId} template

|HTTP Verb|Description|Resource
|-|-|-
|GET|Gets the specified store. Set `{merchantId}` to the ID of the store you want to get.|Request: N/A<br/>Response: [Store](#store)


## Query parameters

The request may include the following query parameters:

|Parameter|Description
|-|-
|<a name="dryrun"></a>dry-run|Optional. Use to test or debug your application. Calls that include this parameter won't affect production data (stores are not added); however, the response will contain any errors that the call generates.<br/><br/>Consider the following limitations when using this parameter.<ul><li>Add operations don't return IDs.</li><li>The service doesn't generate or return secondary error messages such as data quality, editorial issues, and database-related validations.</li></ul>For more information about testing your application, see [Sandbox](test-code-sandbox.md). 


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
|[Store](#store)|Defines a store in Microsoft Merchant Center.
|[StoreCollection](#storecollection)|Defines a collection of stores in Microsoft Merchant Center.
|[StoreCreate](#storecreate)|Defines a store to add to Microsoft Merchant Center.
|[StoreStatus](#storestatus)|Defines the store's status.


### Error

Defines an error.

|Name|Value|Type
|-|-|-
|domain|For internal use only.|String
|location|Not used.|String
|locationType|Not used.|String
|message|A description of the error.|String
|reason|The reason why the request failed. For example, the store failed validation.


### ErrorResponse

Defines the top-level error object.

|Name|Value|Type
|-|-|-
|error|A list of errors that occurred while processing the request.|[Errors](#errors)[]


### Store

Defines a store in Microsoft Merchant Center.

|Name|Value|Type
|-|-|-
|isBlockAggregator|A Boolean value that indicates whether you want to prevent aggregators from serving any ads for the entire domain of your store. For example, if there are two stores (one for the United States and one for the United Kingdom) that use http://www.contoso.com and either one of them blocks aggregators, we will block aggregators for both stores. Aggregators consolidate product offers from multiple, often unrelated, businesses. By default, aggregators can include your catalog in their ads.<br/><br/>Is **true** if you want to prevent your products from showing up in aggregators' ads on Bing.|Boolean
|isSslCheckout|A Boolean value that indicates whether your store is SSL enabled. All stores must have SSL log-in and checkout pages. Is **true** if your store's website is SSL enabled.|Boolean|
|merchantId|The store's ID.|Unsigned long
|notificationEmail|A list of recipients to receive technical notification emails. The emails notify you when the store is approved or if there are validation errors with the store.|String[]
|notificationLanguage|The language used to write the notification. The language is in the form, \<language>-<country/region>.|String
|storeDescription|A description that describes the store's use.|String
|storeName|The store's name.|String
|storeUrl|The store's destination URL. The destination URL is the web page people are directed to when they click your ad.|String


### StoreCollection

Defines a list of stores.

|Name|Value|Type
|-|-|-
|stores|A list of stores owned by the user.|[Store](#store)[]


### Store

Defines a store to add to Microsoft Merchant Center.

|Name|Value|Type|Required
|-|-|-|-
|isBlockAggregator|A Boolean value that indicates whether you want to prevent aggregators from serving any ads for the entire domain of your store. For example, if there are two stores (one for the United States and one for the United Kingdom) that use http://www.contoso.com and either one of them blocks aggregators, we will block aggregators for both stores. Aggregators consolidate product offers from multiple, often unrelated, businesses. By default, aggregators can include your catalog in their ads.<br/><br/>Set to **true** to prevent your products from showing up in aggregators' ads on Bing. Defaults to **false**.|Boolean|No
|isSslCheckout|A Boolean value that indicates whether your store is SSL enabled. All stores must have SSL log-in and checkout pages. Set to **true** if your store's website is SSL enabled.<br/><br/>Defaults to **true**.|Boolean|No
|notificationEmail|A list of recipients to receive technical notification emails. The emails notify you when the store is approved or if there are validation errors with the store. The maximum number of recipients is 14.|String[]|Yes
|notificationLanguage|The language used to write the notification. The language is in the form, \<language>-<country/region>. The following are the possible case-insensitive values that you may specify.<ul><li>en-US (English-United States)</li><li>en-AU (English-Australia)</li><li>en-GB (English-United Kingdom)</li><li>fr-FR (French-France)</li><li>de-DE(German-Germany)</li><li>ja-JP (Japanese-Japan)</li></ul>|String|Yes
|storeDescription|A description that describes the store's use. The description is limited to a maximum of 350 characters and may contain only alphanumeric characters ([a-zA-Z0-9]). If not specified, the description defaults to the store's name.|String|No
|storeName|The store's name. The name must be unique within Bing Merchant Center, is limited to a maximum of 70 characters, and may contain only alphanumeric characters ([a-zA-Z0-9]). The store's name appears in your product ads, so be sure to use a name that accurately represents your website.|String|Yes
|storeUrl|The store's destination URL. The destination URL is the web page people are directed to when they click your ad. This is the URL that you claimed belonged to the user (see <a href="https://help.ads.microsoft.com/#apex/3/en/50888/1" target="_blank">Verify and claim your website's URL</a>). The URL must be well formed, use the HTTPS protocol if `isSslCheckout` is true, and have a maximum of 1,024 characters.|String|Yes


### StoreStatus

Defines the store's status.

|Name|Value|Type|Required
|-|-|-|-
|message|The reason whey the store was disapproved. The object includes this field only if `status` is Disapproved.|String
|status|The store's status. The following are the possible values.<ul><li>Approved</li><li>Disapproved</li><li>ManualReview</li></ul>If the store is disapproved, see `message` for the reason.<br/><br/>A store that was initially automatically approved, may move from Approved to ManualReview. You cannot add products to a store that's under manual review and products in the store do not serve.|String


## HTTP status codes

The requests may return the following HTTP status codes.

|Status code|Description
|-|-
|200|Success.
|201|Store successfully added.
|400|Bad request. Most likely the body of the POST request contains invalid data or is malformed.
|401|Unauthorized. The user's credentials are not valid. 
|404|Not found. The requested store was not found. 
|500|Server error.
