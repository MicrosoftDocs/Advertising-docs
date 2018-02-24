---
title: "Managing your Catalogs"
description: "Learn how to manage catalogs using the Content API."
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---
# Managing your Catalogs
Content API is a RESTful API that uses the [Catalogs](/bingads/shopping-content/catalogs-resource.md) resource to manage catalogs in your Bing Merchant Center (BMC) store. 

The following are the base URIs that you may use to call the Content API. You may use either URI.

* `https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/`
* The tenant URL shown under **Store Settings** in the BMC web application

Each HTTP request must include the user's credentials and your developer token. To specify the user's credentials, set either the [AuthenticationToken](/bingads/shopping-content/catalogs-resource.md#authtoken) header or the [UserName](/bingads/shopping-content/catalogs-resource.md#username) and [Password](/bingads/shopping-content/catalogs-resource.md#password) headers, but not both. 

To specify your developer token, set the [DeveloperToken](/bingads/shopping-content/catalogs-resource.md#devtoken) header.

If you manage catalogs on behalf of other customers, you must set the [CustomerId](/bingads/shopping-content/catalogs-resource.md#customerid) header to the customer ID of the customer whose store you're managing, and the [CustomerAccountId](/bingads/shopping-content/catalogs-resource.md#customeraccountid) header to the account ID of any of the customer's accounts that you manage (it doesn't matter which managed account).

By default, the Content API uses JSON objects to represent the catalogs. To use XML, set the [alt](/bingads/shopping-content/products-resource.md#alt) query parameter to XML.

For details about using the Catalogs resource, see the following sections.

* [Getting a catalog from the store](#get)
* [Getting the list of catalogs from the store](#list)
* [Deleting a catalog from the store](#delete)
* [Adding a catalog to the store](#insert)
* [Updating a catalog in the store](#update)

For a code example that shows how to get, add, update, and delete catalogs, see [Managing Catalogs Code Example](/bingads/shopping-content/code-examples.md#catalog).


## <a name="get" /> Getting a catalog from the store

To get a catalog from the store, append the following template to the base URI.

`{bmcMerchantId}/catalogs/{catalogId}`

Set `{bmcMerchantId}` to your BMC store ID and set `{catalogId}` to the catalog's [ID](/bingads/shopping-content/catalogs-resource.md#id). 

Send an HTTP GET request to the resulting URL. If the catalog was found, the response will contain a [Catalog](/bingads/shopping-content/catalogs-resource.md#catalog) object that contains the catalog's details.


## <a name="list" /> Getting a list of catalogs from the store

To get a list of catalogs from the store, append the following template to the base URI.

`{bmcMerchantId}/catalogs`

Set `{bmcMerchantId}` to your BMC store ID.

Send an HTTP GET request to the resulting URL. If the store contains catalogs, the response will contain a [Catalogs](/bingads/shopping-content/catalogs-resource.md#catalogs) object that contains the list of catalogs. 


## <a name="delete" /> Deleting a catalog from the store

To delete a catalog from the store, append the following template to the base URI.

`{bmcMerchantId}/catalogs/{catalogId}`

Set `{bmcMerchantId}` to your BMC store ID and set `{catalogId}` to the catalog's [ID](/bingads/shopping-content/catalogs-resource.md#id). 

Send an HTTP DELETE request to the resulting URL. If the catalog was found, it will be deleted. 


## <a name="insert" /> Adding a catalog to the store

You use catalogs to logically group your products. To add a catalog to the store, append the following template to the base URI.

`{bmcMerchantId}/catalogs`

Set `{bmcMerchantId}` to your BMC store ID. 

Send an HTTP POST request to the resulting URL. If the catalog was added, the response will contain a [Catalog](/bingads/shopping-content/catalogs-resource.md#catalog) object. The `Catalog` object will include the catalog's [ID](/bingads/shopping-content/catalogs-resource.md#id), which you use to get and delete the catalog.

The body of the request is a [Catalog](/bingads/shopping-content/catalogs-resource.md#catalog) object. You must specify the following fields.

* [name](/bingads/shopping-content/catalogs-resource.md#name)
* [market](/bingads/shopping-content/catalogs-resource.md#market)
* [isPublishingEnabled](/bingads/shopping-content/catalogs-resource.md#ispublishingenabled)

The name that you specify must be unique within the store, and is limited to a maximum of 70 characters. The market identifies where the products are served. For a list of supported markets, see [market](/bingads/shopping-content/catalogs-resource.md#market). Products are served only if `isPublishingEnabled` is **true**. For details about how you can use `isPublishingEnabled` for testing your app, see [Testing your Code in Sandbox](/bingads/shopping-content/test-code-sandbox.md).
 

## <a name="update" /> Updating a catalog in the store

To update a catalog in the store, append the following template to the base URI.

`{bmcMerchantId}/catalogs/{catalogId}`

Set `{bmcMerchantId}` to your BMC store ID and set `{catalogId}` to the catalog's [ID](/bingads/shopping-content/catalogs-resource.md#id). 

The body of the request is a [Catalog](/bingads/shopping-content/catalogs-resource.md#catalog) object. You must specify both of the following fields.

* [name](/bingads/shopping-content/catalogs-resource.md#name)
* [isPublishingEnabled](/bingads/shopping-content/catalogs-resource.md#ispublishingenabled)

Send an HTTP PUT request to the resulting URL. If the catalog was updated, the response will contain the updated [Catalog](/bingads/shopping-content/catalogs-resource.md#catalog) object. 

