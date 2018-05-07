---
title: "Managing your Products"
description: "Learn how to manage products using the Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---

# Managing your Products

Content API is a RESTful API that uses the [Products](../shopping-content/products-resource.md) resource to manage product offerings in your Bing Merchant Center (BMC) store. 

The following are the base URIs that you may use to call the Content API. You may use either URI.

* `https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/`
* The tenant URL shown under **Store Settings** in the BMC web application

Each HTTP request must include the user's credentials and your developer token. To specify the user's credentials, set either the [AuthenticationToken](../shopping-content/products-resource.md#authtoken) header or the [UserName](../shopping-content/products-resource.md#username) and [Password](../shopping-content/products-resource.md#password) headers, but not both. 

> [!IMPORTANT]
> The Bing Ads APIs, including Content API, will stop supporting managed user credentials (username and password) beginning August 1, 2018. At your earliest convenience, please migrate your account to use Microsoft accounts. For information, see [We're changing the way you sign in](https://help.bingads.microsoft.com/#apex/3/en/ext50875/-1/en-us). You will also need to change your code to use OAuth for authentication. For details about using OAuth, see [Authentication with OAuth](https://docs.microsoft.com/en-us/bingads/guides/authentication-oauth?view=bingads-12).



To specify your developer token, set the [DeveloperToken](../shopping-content/products-resource.md#devtoken) header.

If you manage catalogs on behalf of other customers, you must set the [CustomerId](../shopping-content/products-resource.md#customerid) header to the customer ID of the customer whose store you're managing, and the [CustomerAccountId](../shopping-content/products-resource.md#customeraccountid) header to the account ID of any of the customer's accounts that you manage (it doesn't matter which managed account).

By default, the Content API uses JSON objects to represent the product offer. To use XML, set the [alt](../shopping-content/products-resource.md#alt) query parameter to XML.

For details about using the Products resource, see the following sections.

* [Getting a product offer from the store](#get)
* [Getting a list of product offers from the store](#list)
* [Deleting an offer from the store](#delete)
* [Adding and updating a product offer](#insert)
* [Using batch processing](#batch)

## <a name="get"></a> Getting a product offer from the store

To get a specific product offer from the store, append the following template to the base URI.

`{bmcMerchantId}/products/{productUniqueId}`

Set `{bmcMerchantId}` to your BMC store ID and set `{productUniqueId}` to the fully qualified product [ID](../shopping-content/products-resource.md#productid) (for example, Online:en:US:Sku123), not the product's [offerId](../shopping-content/products-resource.md#offerid). Because the product ID is case sensitive, use the ID that the API returned to you when you added the product. 

Send an HTTP GET request to the resulting URL. If the product was found, the response will contain a [Product](../shopping-content/products-resource.md#product) object that contains the offer as last inserted or updated.

If you inserted a product with the same ID in multiple catalogs, the service will return only one of them, and which one is undetermined. You should not insert a product with the same product ID into multiple catalogs.

For a code example that shows how to get a product offer, see [Managing Products Code Example](../shopping-content/code-example-manage-products.md).


## <a name="list"></a> Getting a list of product offers from the store

To get a list of the product offers that are in the store, append the following template to the base URI.

`{bmcMerchantId}/products`

Set `{bmcMerchantId}` to your BMC store ID. 

To page through the list of offers, use the [max-results](../shopping-content/products-resource.md#maxresults) and [start-token](../shopping-content/products-resource.md#starttoken) query parameters. In your first call, set `max-results` to the maximum number of offers that you want the service to return. The maximum number of offers that the service can return is 250 and the default is 25. The following shows an example of the initial call.

`https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/{bmcMerchantId}/products?max-results=250` 

Send an HTTP GET request to the resulting URL. If the store contains offers, the response will contain a [Product](../shopping-content/products-resource.md#product) object that contains up to the requested number of offers.

If there are more offers available, the response will include the `nextPageToken` field (see [Products](../shopping-content/products-resource.md#products)), which contains the token value that you use to set the `start-token` parameter to in your next List request. The following shows an example that uses the token.

`https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/{bmcMerchantId}/products?max-results=250&start-token=DFSos893j...`

For a code example that shows how to get a list of product offers, see [Managing Products Code Example](../shopping-content/code-example-manage-products.md).


## <a name="delete"></a> Deleting an offer from the store

To delete a specific product offer from the store, append the following template to the base URI.

`{bmcMerchantId}/products/{productUniqueId}`

Set `{bmcMerchantId}` to your BMC store ID and set `{productUniqueId}` to the fully qualified product [ID](../shopping-content/products-resource.md#productid) (for example, Online:en:US:Sku123), not the product's [offerId](../shopping-content/products-resource.md#offerid). Because the product ID is case sensitive, use the ID that the API returned to you when you added the product. 

Send an HTTP DELETE request to the resulting URL. If the product was found, it will be deleted. 

If you inserted a product with the same product ID in multiple catalogs, the service will delete all of them. You should not insert a product with the same product ID into multiple catalogs.

For a code example that shows how to delete a product offer, see [Managing Products Code Example](../shopping-content/code-example-manage-products.md).

## <a name="insert"></a> Adding and updating a product offer

Adding or updating an offer is an insert operation. Because an update is an insert operation, you must include all fields of the offer in the request; you cannot not update a single field.

To insert a product offer, append the following template to the base URI.

`{bmcMerchantId}/products`

Set `{bmcMerchantId}` to your BMC store ID. 

If you send an HTTP POST request to the resulting URL, the offer will be written to the default store catalog. To write the offer to a specific catalog, include the [bmc-catalog-id](../shopping-content/products-resource.md#bmccatalogid) query parameter as shown in the following example.

`https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/{bmcMerchantId}/products?bmc-catalog-id=123456` 

If the product was inserted, the response will contain a [Product](../shopping-content/products-resource.md#product) object. The `Product` object will include the product [ID](../shopping-content/products-resource.md#productid), which you use to get and delete the offer.

An offer must include the following fields:

* [availability](../shopping-content/products-resource.md#availability)
* [channel](../shopping-content/products-resource.md#channel)
* [condition](../shopping-content/products-resource.md#condition)
* [contentLanguage](../shopping-content/products-resource.md#contentlanguage)
* [imageLink](../shopping-content/products-resource.md#imagelink)
* [link](../shopping-content/products-resource.md#link)
* [offerId](../shopping-content/products-resource.md#offerid)
* [price](../shopping-content/products-resource.md#price)
* [targetCountry](../shopping-content/products-resource.md#targetcountry)
* [title](../shopping-content/products-resource.md#title)

The `channel`, `contentLanguage`, `targetCountry`, and `offerId` are used to generate the product ID. Because these fields are used to generate the ID, you may not update them. The product ID is case sensitive; the ID will use the same casing that you used to specify `channel`, `contentLanguage`, `targetCountry`, and `offerId`. 

> [!CAUTION] 
> Be sure to use the same casing for `channel`, `contentLanguage`, `targetCountry`, and `offerId` because you can effectively add the same product multiple times if the casing is different.  

The following fields are also required if the manufacturer assigned values.

  - [brand](~/shopping-content/products-resource.md) 
  - [gtin](~/shopping-content/products-resource.md) 
  - [mpn](~/shopping-content/products-resource.md)  

You must specify the values if known. If you do not specify any of them, you must set the [identifierExists](~/shopping-content/products-resource.md) field to **false**. The default is **true**.

If the product is known to have these identifiers and you do not specify them, BMC will accept the product for now but the `Product` object in the response will include the `warnings` field. You should always check if the `warnings` field exists and fix all identified issues.

In addition to the required fields, you should also specify the date and time that you want the offer to expire (see [expirationDate](../shopping-content/products-resource.md#expirationdate)). By default, the offer will expire 30 days from the date and time it is written to the store or catalog. You should track products that are nearing expiration and before they expire either update their expiration date or simply update the product (you do not have to update any of the product's fields) which will automatically extend the expiration date another 30 days. If you explicitly set the expiration date, you must set a new expiration date yourself; updating the product will not automatically extend the expiration date another 30 days in this case. 

All other fields are considered optional; however, you should specify as many as are necessary to accurately describe the product. 

> [!NOTE]
> The `Product` object must include only fields that are set to values. Do not include null fields in the `Product` object. For example, do not include `"adult":null`.

Bing Ads does not use all of the `Product` fields. For a list of fields that the API accepts but does not use, see [What Google attributes can I use?](http://help.bingads.microsoft.com/#apex/3/en/51111/1-500). All of the other fields used by Bing Ads are used to filter the products when serving product ads. 

If you specify a field that is unknown to the Content API, the service ignores the field.  

When you insert an offer, the service will perform basic validations on the offer and return errors and warnings as appropriate. If an error occurs, the response contains an `ErrorResponse` object. If warnings occur, the response contains a `Product` object and the `warnings` field lists the warnings. 

If the offer passes the basic validations, it will undergo offline validations and reviews, such as editorial reviews, that can take up to 36 hours. The offer will not serve until all validations and reviews are complete. To determine the status of an offer, use the [Status](../shopping-content/status-resource.md) resource.

Note that the API does not provide concurrency controls such as ETags. If two apps are trying to add or update the same product, the last one wins.   

An offer that is displayed in a product ad  will include the price, title, store name (or sellerName if specified), link to the webpage that contains more information about the product, and an image of the product. 

For apparel products that are available in multiple colors, patterns or materials, create a product for each variant and use the [itemGroupId](../shopping-content/products-resource.md#itemgroupid) field to group all product variants.

For a code example that shows how to insert a product offer, see [Managing Products Code Example](../shopping-content/code-example-manage-products.md).


## <a name="batch" /> Using batch processing

If you're processing multiple product offers, you should consider using the API's batch processing feature. This feature lets you process multiple inserts, gets, and deletes in a single request. Processing multiple offers in the same request is more efficient than sending a separate request for each offer; the cost incurred  with processing a single request is spread over the thousands or offers in the request instead of incurring that cost for each request if you processed them separately.

Do not insert, get, or delete the same product in the same request.

To send a batch request, append the following template to the base URI.

`{bmcMerchantId}/products/batch`

Set `{bmcMerchantId}` to your BMC store ID. 

If you send an HTTP POST request to the resulting URL, the insert operations will be applied to the default store catalog. To apply the offers to a specific catalog, include the [bmc-catalog-id](../shopping-content/products-resource.md#bmccatalogid) query parameter as shown in the following example.

`https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/{bmcMerchantId}/products/batch?bmc-catalog-id=123456`

The body of the POST is a [Batch](../shopping-content/products-resource.md#batch) object which contains an array of [Item](../shopping-content/products-resource.md#item) objects. For all operations, set the `batchId`, `merchantId` and `method` fields. The `batchId` is a user-defined ID that you use to identify the batch item in the response; the `merchantId` is your store ID; and the `method` is the operation to be performed (for example, insert, delete or get).

If `method` is insert, set the `product` field to a [Product](../shopping-content/products-resource.md#product) object which contains the offer to add or update. Otherwise, if `method` is a get or delete, set `productId` to the fully qualified [ID](../shopping-content/products-resource.md#productid) of the offer that you want to get or delete.


The size of the body of a batch request may not exceed 4 MB. If the body exceeds 4 MB, the response returns HTTP status code 413. Depending on the size of each offer (the number of fields that you specify), you can send between 2,000 and 6,000 offers. If you compress the body, you can send the maximum number of offers, which is 12,000 (depending on their size).

To compress the body, use GZip compression only and set the request?s Content-Encoding header to ?gzip?.

The service will process each item in the batch. The response will contain a `Batch` object that contains each `Item` that was in the request. Note that there is no guarantee that the order of the items in the response will be in the same order as the items in the request. 

For insert operations, the item will include only the `batchId` and `product` fields. The `product` field will contain the same offer that you sent in the request but will also include the fully qualified product ID. If an error or warning occurs, the item will include the `batchId`, `method`, and `error` fields. The `error` field will contain the reasons why the insert failed or warnings about issues with the offer that you need to fix.

For get operations, the item includes the `batchId` and `product` fields. The `product` field will contain the offer that you requested. If the product is not found, the object will not include the `product` field. 

For delete operations, the item includes only the `batchId` field; there is no indication of whether the offer exists and was deleted.

For a code example that shows how to use batch processing, see [Creating a Batch Request](../shopping-content/code-examples.md#batch).
  
