---
title: "How Do I Get the Status of Product Offers?"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "scottwhi"
---
# How Do I Get the Status of Product Offers?
When you add or update a product offer in a catalog or store, the contents of the offer are validated and it goes through editorial review. That process can take up to 36 hours. To see whether the offer passed the review process, use the [Status](../shopping-content/status-resource.md) resource. The resource lets you get the status of product offers that you uploaded to a catalog or store.

The following are the base URIs that you may use to get the `Status` resource. You may use either URI.

* `https://content.api.bingads.microsoft.com/shopping/v9.1/bmc/`
* The tenant URL shown under **Store Settings** in the BMC web application

Each HTTP request must include the user's credentials and your developer token. To specify the user's credentials, set either the [AuthenticationToken](../shopping-content/status-resource.md#authtoken) header or the [UserName](../shopping-content/status-resource.md#username) and [Password](../shopping-content/status-resource.md#password) headers, but not both. 

To specify your developer token, set the [DeveloperToken](../shopping-content/status-resource.md#devtoken) header.

If you manage catalogs on behalf of other customers, you must set the [CustomerId](../shopping-content/status-resource.md#customerid) header to the customer ID of the customer whose store you're managing, and the [CustomerAccountId](../shopping-content/status-resource.md#customeraccountid) header to the account ID of any of the customer's accounts that you manage (it doesn't matter which managed account).

You do not need to specify the user's credentials or developer token to download the report; you only need to specify them to get the status.

By default, the Content API uses JSON objects to represent the status. To use XML, set the [alt](../shopping-content/status-resource.md#alt) query parameter to XML.

To get the status of product offers, append the following template to the base URI.

`{bmcMerchantId}/catalogs/{catalogId}/status`

Set `{bmcMerchantId}` to your BMC store ID and set `{catalogId}` to the ID of the catalog that contains the product offers whose status you want to get. 

Send an HTTP GET request to the resulting URL. The response will contain a [Status](../shopping-content/status-resource.md#status) object that contains the number of offers that passed the review process in the last 30 days and the number that failed the review during the same period. If an offer failed the review, the `Status` resource includes an URL that you can use to download a report that describes why the offer failed.

The following shows an example `Status` object.

```
{
  "catalogId": 12345,
  "publishedCount": 80,
  "rejectedCount": 6,
  "rejectionReportUrl": "https://merchantcenter.bingads.microsoft.com/api/Public/DownloadFeedReport?token=..."
}
```

The report identifies the offer that failed but does not provide the timestamp or version control information that you can use to identify which of the updates the report is referring to. For example, if you uploaded an offer 2 days ago and then updated it yesterday, you will not know whether the reported issue is related to the version uploaded 2 days ago or the one uploaded yesterday. However, you may be able to use the item's attributes in the Offer Snippet column of the report to infer which version of the item is being reported.

The report file is ZIP compressed, so you must unzip the file to read the report. There is no limit to the number of reports that the system can store; however, the length of time that the reports are stored is undefined. For information about the contents of the report, see [Report Format](../shopping-content/status-resource.md#reportformat).

Depending on the activity associated with the catalog, the report can be large. You should not request the report anymore frequently than is necessary. The recommended interval is once per hour.

For a code example that shows how to get the catalog's status and download the report, see [Downloading the Catalog Status Report](../shopping-content/code-examples.md#status).

<a name="examplereport" />The following shows an example report.  

```
"Catalog Name","Catalog Id","Store Id","Upload Time"
"Default Catalog","1234","5678","04/21/2016 01:59:06"

"Item Id","Message","Type","Values","Offer Snippet"
"SKU1234","The product URL should be a sub-path of the store's domain. ","Error","",";eBay Motors>Parts & Accessories>Car & Truck Parts>Brakes>Brake Hoses>;http://contentapis.cloudapp.net/sku123;http://i.ebayimg.com/00/s/NzY4WDI5Mg==/z/irkAAOxyB9RS14Rj/$_1.JPG?set_id=880000500F;24.25;-1;;"
"SKU5678","The product URL should be a sub-path of the store's domain. ","Error","",";;http://www.contoso.com/;https://tse3.mm.bing.net/th?id=Ma8674a23cc755995efecf822b3836f07o0&pid=Api;1205;-1;;"
"SKU0987","The product URL should be a sub-path of the store's domain. ","Error","",";Apparel & Accessories > Clothing > Outerwear;http://v-vagancclaimedapi.cloudapp.net/;http://google.com/;1;-1;;"
"SKU6543","The price field is required.","Error","","Mens T-shirt;N/A;http://www.contoso.com/;https://tse3.mm.bing.net/th?id=OIP.Ma8674a23cc755995efecf822b3836f07o0&pid=Api;N/A"
"SKU2435","The offer expiration date is in the past.","Error","","full product title;Apparel & Accessories > Clothing > Outerwear;http://v-vagancclaimedapi.cloudapp.net/;http://google.com/;1.00"
"SKU8675","The price field is required.","Error","","Mens T-shirt;N/A;http://www.contoso.com/;https://tse3.mm.bing.net/th?id=OIP.Ma8674a23cc755995efecf822b3836f07o0&pid=Api;N/A"
```
