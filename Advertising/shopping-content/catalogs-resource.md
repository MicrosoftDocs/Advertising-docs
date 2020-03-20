---
title: "Catalogs Resource"
description: "Provides information about the catalogs resource and related elements of the Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---
# Catalogs Resource
The Catalogs resource lets you manage catalogs in your Microsoft Merchant Center store (MMC). For information about using the Catalogs resources, see [Managing your Catalogs](../shopping-content/manage-catalogs.md). For examples that show how to add, delete, and get catalogs, see [Code Examples](../shopping-content/code-examples.md#catalog).

## Base URI

The following is the base URI that you append the templates to.  

`https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/`


## <a name="templates"/>Templates

To create the endpoints that you use to manage your catalogs, append the appropriate template to the base URI.

|Template|HTTP Verb|Description|Resource
|--------|---------|-----------|--------
|{mmcMerchantId}/catalogs|POST|Use to add a catalog to the store. To add a catalog, its name must be unique. You may add a maximum of 100 catalogs to a store.<br/><br/>Set `{mmcMerchantId}` to the MMC store ID.|Request: [Catalog](#catalog)<br>Response: [Catalog](#catalog) 
|{mmcMerchantId}/catalogs/{catalogId}|PUT|Use to update a catalog in the store. The only fields you may update are the `name` and `isPublishingEnabled` fields, and you must specify both.<br/><br/>Set `{mmcMerchantId}` to the MMC store ID.|Request: [Catalog](#catalog)<br>Response: [Catalog](#catalog) 
|{mmcMerchantId}/catalogs/{catalogId}|DELETE|Use to delete a catalog from the store.<br/><br/>Set `{mmcMerchantId}` to the MMC store ID.<br/><br/>Set `{catalogId}` to the catalog's ID.|Request: N/A<br>Response: N/A
|{mmcMerchantId}/catalogs/{catalogId}|GET|Use to get a catalog from the store.<br/><br/>Set `{mmcMerchantId}` to the MMC store ID.<br/><br/>Set `{catalogId}` to the catalog's ID.|Request: N/A<br>Response: [Catalog](#catalog) 
|{mmcMerchantId}/catalogs|GET|Use to get a list of catalogs from the store.<br/><br/>Set `{mmcMerchantId}` to the MMC store ID.|Request: N/A<br>Response: [Catalogs](#catalogs)


## <a name="queryparameters"/> Query parameters

The endpoints may include the following query parameters.

|Parameter|Description|
|---------|-----------|
|<a name="alt"/>alt|Optional. Use to specify the type of content that's used in the request and response. The possible values are `json` and `xml`. The default is `json`.


## <a name="headers"/> Headers

The following are the request and response headers.
 
|Header|Description|
|---------|---------------|
|<a name="authtoken"/>AuthenticationToken|Request header.<br/><br/>Set this header to an OAuth authentication token. For information about getting a token, see [Authenticating your credentials](../shopping-content/get-started.md#authentication).
|Content-Location|Response header.<br/><br/>A URL that identifies the store that the catalog was inserted into. This header is included in the response of an Insert request. 
|<a name="customeraccountid"/> CustomerAccountId|Request header.<br/><br/>The account ID of any of the accounts that you manage on behalf of the customer specified in the `CustomerId` header. It doesn't matter which account you specify. Specify this header only if you manage an account on behalf of the customer.
|<a name="customerid"/> CustomerId|Request header.<br/><br/>The customer ID of the customer whose store you manage. Specify this header only if you manage the store on behalf of the customer. If you set this header, you must also set the `CustomerAccountId` header.  
|<a name="devtoken"/> DeveloperToken|Request header.<br/><br/>The client application's developer access token. Each request must include this header. For information about getting a token, see [Do you have your Microsoft Advertising credentials and developer token?](../shopping-content/get-started.md#credentials)
|Location|Response header.<br/><br/>A URL that identifies the store that the catalog was inserted into. This header is included in the response of an Insert request. 
|WebRequestActivityId|Response header.<br/><br/>The ID of the log entry that contains details about the request. You should always capture this ID if an error occurs. If you are not able to determine and resolve the issue, include this ID along with the other information that you provide the Support team.


## <a name="objects"/> Request and response objects

The following are the request and response objects used by the API.
 
Each object defines the JSON key name and XML element name that you use depending on the content type that you specify for the request. 

|Object|Description
|------|-----------
|[Catalog](#catalog)|Defines a catalog.
|[Catalogs](#catalogs)|Defines the list of catalogs.

 
### <a name="catalog"/>Catalog

Defines a catalog.

|Name|Value|Type|XML element name
|----|-----|----|--------
|<a name="id"/>id|An ID that uniquely identifies the catalog in the store.<br/><br/>This field is read-only; do not set this field.|Unsigned Long|\<id\> 
|<a name="isdefault"/>isDefault|A Boolean value that determines whether the catalog is the store's default catalog. Is **true** if the catalog is the store's default catalog; otherwise, **false**.<br/><br/>When you create a store, you get a default catalog that products are written to if you do not specify another catalog.<br/><br/>This field is read-only; do not set this field.|Boolean|\<is_default\> 
|<a name="ispublishingenabled"/>isPublishingEnabled|A Boolean value that determines whether Microsoft may publish products from the catalog. Set to **true** if Microsoft may publish products from the catalog; otherwise, set it to **false**.<br/><br/>You may update this field.<br/><br/>You can also use this field to test your application before deploying it to production. By setting this field to **false**, you may make [Products Resource](../shopping-content/products-resource.md) calls without changing or publishing your production data.|Boolean|\<is_publishing_enabled\>
|<a name="market"/>market|The market where products in the catalog are published to. The following are the possible markets that you may specify.<ul><li>de-DE (German-Germany)</li><li>en-AU (English-Australia)</li><li>en-CA (English-Canada)</li><li>en-GB (English-Great Britain)</li><li>en-IN (English-India)</li><li>en-US (English-United States)</li><li>fr-CA (French-Canada)</li><li>fr-FR (French-France)</li><li>nl-NL (Dutch-Netherlands)</li></ul>All products that you add to the catalog must specify the same market (see [contentLanguage](../shopping-content/products-resource.md#contentlanguage) and [targetCountry](../shopping-content/products-resource.md#targetcountry)).<br/><br/>You may not update this field after adding the catalog to the store.<br/><br/>In the above list, de-DE is the market value that you specify; do not include (German-Germany) in your market string.|String|\<market\>
|<a name="name"/>name|The name of the store. The name may contain a maximum of 70 characters.<br/><br/>You may update this field.|String|\<name\> 


### <a name="catalogs"/>Catalogs

Defines a list of catalogs.

|Name|Value|Type|XML element name
|----|-----|----|--------
|catalogs|A list of catalogs in the store.|[Catalog](#catalog)[]|\<catalogs\> 



## HTTP status codes

The requests may return the following HTTP status codes.

|Status code|Description
|-----------|-----------
|200|Success.
|201|Successfully added the catalog.
|204|Successfully deleted the catalog.
|400|Bad request. Either a query parameter value is not valid or something in the request body is not valid.
|401|Unauthorized. The user's credentials are not valid. 
|404|Not found. 
|500|Server error.

