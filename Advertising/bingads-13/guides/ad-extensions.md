---
title: "Ad Extensions"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Setup ad extensions with the Bing Ads API.
---
# Ad Extensions
Ad extensions are additional pieces of information about your business, like a phone number or a link to a specific page on your website, you can add to your ads. Ad extensions are free to add to your ads, with the usual charges for any clicks you get. Including ad extensions can improve the visibility of your ads, which can lead to more clicks and improve your ROI. There are many types of ad extensions available in Microsoft Advertising: [App Extensions](#appextensions), [Call Extensions](#callextensions), [Callout Extensions](#calloutextensions), [Image Extensions](#imageextensions), [Location Extensions](#locationextensions), [Price Extensions](#priceextensions), [Review Extensions](#reviewextensions), [Sitelink Extensions](#sitelinkextensions), and [Structured Snippet Extensions](#structuredsnippetextensions). For more about ad extensions, see the [About ad extensions](https://help.ads.microsoft.com/#apex/3/en/51001/1) help article.

> [!TIP]
> Providing extension data allows our algorithms to evaluate all the possible layouts for your ad. It increases the changes of additional space being allocated and increasing clicks for your ad.

Ad extensions are stored in a shared library at the account level. After adding the extension to your shared library, you must also explicitly associate it with the account or one or more campaigns or ad groups within the account for the extension to become eligible for delivery. For more details on associating ad extensions, see [Managing Ad Extensions with the Bulk Service](#bulkservice) and [Managing Ad Extensions with the Campaign Management Service](#campaignservice) in the sections below. For ad extension association limits per entity, please see [Entity Limits for Ad Extensions](entity-hierarchy-limits.md#adextensions).

> [!NOTE]
> Call ad extensions can only be associated at the campaign level. 
> 
> Location ad extensions can only be associated at the account and campaign level i.e., cannot be associated with ad groups.

Ad extensions that are associated at a lower level e.g., ad group will override ad extensions of the same type that are associated at a higher level e.g., campaign. For example if you have 2 callout extensions set for *Campaign A*, zero callout extensions associated with *Ad Group AA*, and one callout extension associated with *Ad Group AB*, then only *Ad Group AA* is eligible to have its ads decorated with callouts. 

You can manage ad extensions with either the [Bulk Service](../bulk-service/bulk-service-reference.md) or [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md). You should use the [Bulk Service](../bulk-service/bulk-service-reference.md) if you need to upload or download a high volume of entity settings. For example you can update all ad extensions for your entire account in a single upload. In comparison, with the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) you can only update 100 ad extensions per call. For details see the following sections.

## <a name="adextensiontypes"></a>Ad Extension Types
Ad extension types include [App Extensions](#appextensions), [Call Extensions](#callextensions), [Callout Extensions](#calloutextensions), [Image Extensions](#imageextensions), [Location Extensions](#locationextensions), [Price Extensions](#priceextensions), [Review Extensions](#reviewextensions), [Sitelink Extensions](#sitelinkextensions), and [Structured Snippet Extensions](#structuredsnippetextensions). 

### <a name="appextensions"></a>App Extensions
You can associate app ad extensions with your campaigns and ad groups, and your ads will include a link to install an application.

![App Ad Extension](media/overview-appadextension.png "App Ad Extension")

### <a name="callextensions"></a>Call Extensions
With Call Extensions, you can provide a phone number that is not associated with a particular location, but is appropriate for all locations where your ads display. In comparison, you typically use Location Extensions to provide an address and local phone number associated with a local location.

If the campaign is also associated with a [Location Extensions](#locationextensions), the call extension phone number will override the location extension phone number.

![Call Ad Extension](media/overview-calladextension.png "Call Ad Extension")

### <a name="calloutextensions"></a>Callout Extensions
With Callout Extensions, you can provide an extra snippet of text that highlights your business, products, or services to include in An ad. This extension is not clickable and can appear in addition to your ad's description. Providing additional details about your store can make your ad more relevant to potential customers.

Each account, campaign, or ad group can be associated with between 2 and 20 callout ad extensions. If you associate one or fewer callout extensions with your account, campaign, or ad group, no callout text will serve with your ad. An ad may include between 2 to 4 callouts per impression.

![Callout Ad Extension](media/callout-ad-extension.png "Callout Ad Extension")

### <a name="imageextensions"></a>Image Extensions
You can associate image ad extensions with your campaigns and ad groups, and your ads may include an image or alternative text.

![Image Ad Extension](media/image-ad-extension.png "Image Ad Extension")

### <a name="locationextensions"></a>Location Extensions
When you enable Location Extensions, you can choose to show the address of your business location that is closest to the customer and also include a local phone number. Better yet, if the customer is viewing your ad on a smartphone, they can click that number to give you a call.

If the campaign is also associated with a [Call Extensions](#callextensions), the phone number in the call extension will override the location extension phone number.

![Location Ad Extension](media/overview-locationadextension.png "Location Ad Extension")

### <a name="priceextensions"></a>Price Extensions
You can use Price Extensions to display your products or services with their corresponding prices to potential customers on mobile devices. Price Extensions only show on ads listed at the top of the results page, helping to increase your clicks. Keep in mind that though Price Extensions are free to add to your ad, they may not always show for every query.

![Price Ad Extension](media/price-ad-extension.png "Price Ad Extension")

### <a name="reviewextensions"></a>Review Extensions
Potential customers like to know about other customers' experiences when searching for products or services. Share positive reviews from a reputable third-party source about your business, products, or services in your ads with a Review Extension. An ad will only include one review per impression.

![Review Ad Extension](media/review-ad-extension.png "Review Ad Extension")

### <a name="sitelinkextensions"></a>Sitelink Extensions
Sitelink Extensions are additional links in your ads that take customers to specific pages on your website. This allows you to promote certain products, services, or sections of your website and take potential customers to exactly the information they were searching for. This can increase both click-through-rate and conversions.

You may associate site links ad extensions with your campaigns or ad groups, and your ads will include up to 10 links to relevant web pages within your website. When displaying an ad, Microsoft Advertising determines which links are most relevant to the ad being displayed and includes those with your ad. You can influence which links are included. Links that you specify at the beginning of your list receive higher priority than those toward then end of your list.

![Sitelink Ad Extension](media/overview-sitelinkadextension.png "Sitelink Ad Extension")

### <a name="structuredsnippetextensions"></a>Structured Snippet Extensions
Structured Snippet Extensions give potential customers more context on a specific aspect of your products and services. A Structured snippet is made up of a header and a list of 3-10 values which correspond to the header. For example, you might use the header "Brands:" and the values "Windows, Xbox, Skype" to let customers know about what brands are available at your store.

![Structured Snippet Ad Extension](media/structured-snippet-ad-extension.png "Structured Snippet Ad Extension")

This extension is not clickable and, similar to other extensions, will appear beneath your ad's description. Structured Snippets have no impact on the other extensions you're already using. Structured Snippets should not duplicate what is already stated in the ad. Our full list of Structured Snippet policies can be found [here](https://about.ads.microsoft.com/en-us/resources/policies/ad-extensions-policies).

An ad will only include one structured snippet (one headline with 3 - 10 values) per impression. Keep in mind that your ads won't always show Structured Snippets and if they do show Structured Snippets, the format they appear may vary. Structured Snippets are free to add to your ad, available in all Microsoft Advertising markets (excluding Hong Kong and Taiwan), and serve on desktop and tablet devices. 


## <a name="bulkservice"></a>Managing Ad Extensions with the Bulk Service
You can use the [Bulk Service](../bulk-service/bulk-service-reference.md) i.e., [Bulk Download and Upload](bulk-download-upload.md) to create, get, update, and delete both ad extensions and ad extension associations. 

The following Bulk records are available for managing ad extensions and ad extension associations. 

### App Extensions
- [App Ad Extension](../bulk-service/app-ad-extension.md)
- [Ad Group App Ad Extension](../bulk-service/ad-group-app-ad-extension.md)
- [Campaign App Ad Extension](../bulk-service/campaign-app-ad-extension.md)

### Call Ad Extensions
- [Call Ad Extension](../bulk-service/call-ad-extension.md)
- [Campaign Call Ad Extension](../bulk-service/campaign-call-ad-extension.md)

### Callout Ad Extensions
- [Callout Ad Extension](../bulk-service/callout-ad-extension.md)
- [Ad Group Callout Ad Extension](../bulk-service/ad-group-callout-ad-extension.md)
- [Campaign Callout Ad Extension](../bulk-service/campaign-callout-ad-extension.md)

### Image Ad Extensions
- [Image Ad Extension](../bulk-service/image-ad-extension.md)
- [Ad Group Image Ad Extension](../bulk-service/ad-group-image-ad-extension.md)
- [Campaign Image Ad Extension](../bulk-service/campaign-image-ad-extension.md)

### Location Ad Extensions
- [Location Ad Extension](../bulk-service/location-ad-extension.md)
- [Campaign Location Ad Extension](../bulk-service/campaign-location-ad-extension.md)

### Price Ad Extensions
- [Price Ad Extension](../bulk-service/price-ad-extension.md)
- [Ad Group Price Ad Extension](../bulk-service/ad-group-price-ad-extension.md)
- [Campaign Price Ad Extension](../bulk-service/campaign-price-ad-extension.md)

### Review Ad Extensions
- [Review Ad Extension](../bulk-service/review-ad-extension.md)
- [Ad Group Review Ad Extension](../bulk-service/ad-group-review-ad-extension.md)
- [Campaign Review Ad Extension](../bulk-service/campaign-review-ad-extension.md)

### Sitelink Ad Extensions
- [Sitelink Ad Extension](../bulk-service/sitelink-ad-extension.md)
- [Ad Group Sitelink Ad Extension](../bulk-service/ad-group-sitelink-ad-extension.md)
- [Campaign Sitelink Ad Extension](../bulk-service/campaign-sitelink-ad-extension.md)

### Structured Snippet Ad Extensions
- [Structured Snippet Ad Extension](../bulk-service/structured-snippet-ad-extension.md)
- [Ad Group Structured Snippet Ad Extension](../bulk-service/ad-group-structured-snippet-ad-extension.md)
- [Campaign Structured Snippet Ad Extension](../bulk-service/campaign-structured-snippet-ad-extension.md)

## <a name="campaignservice"></a>Managing Ad Extensions with the Campaign Management Service
You can use the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) to create, get, update, and delete both ad extensions and ad extension associations. 

For code examples that show how to set up ad extensions using the Campaign Management service, see [Ad Extensions Code Example](code-example-ad-extensions.md).

### Entities
These are the ad extension entities that can be accessed using the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md). You can create, read, update, and delete these entities.

- [AppAdExtension](../campaign-management-service/appadextension.md)
- [CallAdExtension](../campaign-management-service/calladextension.md)
- [CalloutAdExtension](../campaign-management-service/calloutadextension.md)
- [ImageAdExtension](../campaign-management-service/imageadextension.md)
- [LocationAdExtension](../campaign-management-service/locationadextension.md)
- [PriceAdExtension](../campaign-management-service/priceadextension.md)
- [ReviewAdExtension](../campaign-management-service/reviewadextension.md)
- [SitelinkAdExtension](../campaign-management-service/sitelinkadextension.md)
- [StructuredSnippetAdExtension](../campaign-management-service/structuredsnippetadextension.md)

> [!NOTE]
> The [AdExtension](../campaign-management-service/adextension.md) object is the base class from which all ad extensions are derived.

### Service Operations
These are the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) service operations that can be used to add, get, update, and delete ad extensions.

- [AddAdExtensions](../campaign-management-service/addadextensions.md)  
- [SetAdExtensionsAssociations](../campaign-management-service/setadextensionsassociations.md)  
- [GetAdExtensionsByIds](../campaign-management-service/getadextensionsbyids.md)  
- [GetAdExtensionIdsByAccountId](../campaign-management-service/getadextensionidsbyaccountid.md)  
- [GetAdExtensionsAssociations](../campaign-management-service/getadextensionsassociations.md)  
- [UpdateAdExtensions](../campaign-management-service/updateadextensions.md)
- [DeleteAdExtensions](../campaign-management-service/deleteadextensions.md)  
- [DeleteAdExtensionsAssociations](../campaign-management-service/deleteadextensionsassociations.md)

> [!NOTE]
> Partial update is not supported for ad extensions. Any optional elements which are not sent with the [UpdateAdExtensions](../campaign-management-service/updateadextensions.md) request will in effect be deleted from the extension.
> 
> Partial success is not supported when adding, updating, and deleting ad extensions. For example if you submit 10 ad extensions and 2 fail, the entire batch will fail.
> 
> Partial success is supported for [GetAdExtensionsAssociations](../campaign-management-service/getadextensionsassociations.md) and [SetAdExtensionsAssociations](../campaign-management-service/setadextensionsassociations.md). For example if you submit 10 ad extension associations and 2 fail, the remaining 8 will succeed. For more information, see [Partial Success using the Campaign Management Service](handle-service-errors-exceptions.md#partial-success).

## <a name="editorial"></a>Editorial Review
When you associate an ad extension with a campaign or ad group, the extension goes through an initial editorial review. For more information, see [Ad Extension Editorial Review](editorial-review-appeals.md#adextensioneditorialreview).

## <a name="reporting"></a>Reporting
You can use the following reports to get statistics about the effectiveness of the ad extensions that you've included in your ads.

- [AdExtensionByAdReportRequest](../reporting-service/adextensionbyadreportrequest.md) - Aggregates performance data by ad for a specified time period. By including performance details, such as clicks, conversion, and spend, you can identify ad extensions that are performing well, and those that may need to be adjusted to optimize the monthly budget.

- [AdExtensionByKeywordReportRequest](../reporting-service/adextensionbykeywordreportrequest.md) - Aggregates performance data by keyword for a specified time period. By including performance details, such as clicks, conversion, and spend, you can identify ad extensions that are performing well, and those that may need to be adjusted to optimize the monthly budget.

- [AdExtensionDetailReportRequest](../reporting-service/adextensiondetailreportrequest.md) - Lists all versions of an ad extension by account. You can use this information along with the performance data from the other two reports to determine which version performed better.

For more information about reporting, see [Reports](reports.md) and [Request and Download a Report](request-download-report.md).


## See Also
[Bing Ads API Web Service Addresses](web-service-addresses.md)

