---
title: "Intent Ads"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Intent Ads
Bing Intent ads are an extension of search network, and are targeted to user intent based on various combinations of search history, page content, and past user behavior. Intent ads are created automatically by Bing Ads leveraging all of your Bing Ads creative elements including ad title, text, URL, and ad extensions including image extensions.  

The ads created using the search creative assets are then displayed to the user in native placements depending upon the surface area e.g. if a user is reading an email in Outlook then the placement will be native to the inbox environment versus if the user is clicking through a slideshow on MSN, then the ad will match the slideshow look and feel. This kind of native placement enhances user experience and delivers better engagement with the campaign. 

Intent ads are a part of standard Bing Ads campaigns on the search network and support all of the targeting available from Bing Ads. Intent ads have CPC pricing. 

> [!NOTE]
> Not everyone has this feature yet. If you don?t, don?t worry. It's coming soon.

You can set a bid adjustment for each campaign and ad group. The bid adjustment is the percent amount by which to adjust your bid for native ads above or below the base ad group or keyword bid. Supported values are negative one hundred (-100) through positive nine hundred (900). Setting the bid adjustment to -100 percent will prevent native ads from showing for the campaign or ad group. If you do not set a bid adjustment for your ad groups they will inherit from the campaign bid adjustment setting by default.

You can manage native ads settings with either the [Bulk Service](~/bulk/bulk-service-reference.md) or [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md). You should use the [Bulk Service](~/bulk/bulk-service-reference.md) if you need to upload or download a high volume of entity settings. For example you can update all ad groups for your entire account in a single upload. In comparison, with the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md) you can only update 100 ad groups per call and those ad groups must be in the same campaign. For details see the following sections.

-   [Intent Ads with the Bulk Service](#bulkservice)  
-   [Intent Ads with the Campaign Management Service](#campaignservice)  
-   [Getting Performance Reports for Native Ads](#reporting)  

## <a name="bulkservice"></a>Intent Ads with the Bulk Service
The [Bulk Service](~/bulk/bulk-service-reference.md) service create, update, and delete operations can be completed using Bulk upload. You can use Bulk download to read back your data. For more information see [Bulk File Schema](~/bulk/bulk-file-schema.md) and [Bulk Download and Upload](bulk-download-upload.md).

These are the Bing Ads entities with properties for managing Bing Intent ads that can be accessed using the [Bulk Service](~/bulk/bulk-service-reference.md). Use the *Bid Adjustment* column of the following records to get and set the Native ad placement bid adjustment.

-   [Campaign](~/bulk/campaign.md)  
-   [Ad Group](~/bulk/ad-group.md)  
-   [Image Ad Extension](~/bulk/image-ad-extension.md)  
-   [Campaign Image Ad Extension](~/bulk/campaign-image-ad-extension.md)  
-   [Ad Group Image Ad Extension](~/bulk/ad-group-image-ad-extension.md)  

For example you can follow these steps to set up an image ad extension for native ads.

**Note:** You can use the [Bulk Service](~/bulk/bulk-service-reference.md) for most steps, but you will still need to use the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md) to add media to your account's media library.

1.  Add one to six [Image](~/campaign-management/image.md) items to your account's media library with the [AddMedia](~/campaign-management/addmedia.md) operation. The images must be one of the supported [Media](~/campaign-management/media.md) types (aspect ratios) for an [Image Ad Extension](~/bulk/image-ad-extension.md).

    > [!NOTE]
    > While the minimum required for an image ad extension is one image, in order to qualify for all native ad placements you must provide four images, where each [Image](~/campaign-management/image.md) corresponds to one of the four supported [Media](~/campaign-management/media.md) types (aspect ratios). The supported aspect ratios for native ads are 16:9, 1.5:1, 4:3, and 1.2:1.

2.  Upload an [Image Ad Extension](~/bulk/image-ad-extension.md) record to your account's ad extension library. This will link the images from your media library to a specific image ad extension.

    > [!NOTE]
    > You will set the *Media Ids* field of the [Image Ad Extension](~/bulk/image-ad-extension.md) record with the media identifiers returned from [AddMedia](~/campaign-management/addmedia.md) in the previous step.

3.  Associate your [Image Ad Extension](~/bulk/image-ad-extension.md) record to one or more [Campaign](~/bulk/campaign.md) or [Ad Group](~/bulk/ad-group.md) records by uploading the corresponding [Campaign Image Ad Extension](~/bulk/campaign-image-ad-extension.md) or [Ad Group Image Ad Extension](~/bulk/ad-group-image-ad-extension.md) records.

4.  Optionally use the *Bid Adjustment* column of the [Campaign](~/bulk/campaign.md) and [Ad Group](~/bulk/ad-group.md) records to get and set the native ads bid adjustment.

## <a name="campaignservice"></a>Intent Ads with the Campaign Management Service
Bing Intent ads can be accessed using the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md). You can create, read, update, and delete these entities.

> [!NOTE]
> Partial success is supported for a subset of these operations. For example if you submit 10 ad groups and 2 fail, the remaining 8 will succeed. For more information, see [Partial Success using the Campaign Management Service](handle-service-errors-exceptions.md#partial-success).

1.  Add one to six [Image](~/campaign-management/image.md) items to your account's media library with the [AddMedia](~/campaign-management/addmedia.md) operation. The images must be one of the supported [Media](~/campaign-management/media.md) types (aspect ratios) for an [ImageAdExtension](~/campaign-management/imageadextension.md).

    > [!NOTE]
    > While the minimum required for an image ad extension is one image, in order to qualify for all native ad placements you must provide four images, where each [Image](~/campaign-management/image.md) corresponds to one of the four supported [Media](~/campaign-management/media.md) types (aspect ratios). The supported aspect ratios for native ads are 16:9, 1.5:1, 4:3, and 1.2:1.

2.  Add an [ImageAdExtension](~/campaign-management/imageadextension.md) to your account's ad extension library with the [AddAdExtensions](~/campaign-management/addadextensions.md) operation. This will link the images from your media library to a specific image ad extension. If you already have an image ad extension you can call [UpdateAdExtensions](~/campaign-management/updateadextensions.md) instead of [AddAdExtensions](~/campaign-management/addadextensions.md).

    > [!NOTE]
    > You will set the *ImageMediaIds* element of the [ImageAdExtension](~/campaign-management/imageadextension.md) with the media identifiers returned from [AddMedia](~/campaign-management/addmedia.md) in the previous step.

3.  Associate your [ImageAdExtension](~/campaign-management/imageadextension.md) to one or more [Campaign](~/campaign-management/campaign.md) or [AdGroup](~/campaign-management/adgroup.md) objects with the [SetAdExtensionsAssociations](~/campaign-management/setadextensionsassociations.md) operation.

4.  Optionally use the *NativeBidAdjustment* property of the [Campaign](~/campaign-management/campaign.md) and [AdGroup](~/campaign-management/adgroup.md) to get and set the native ads bid adjustment.

## <a name="reporting"></a>Getting Performance Reports for Native Ads
For Intent ads reporting and analysis you can use the Native ad distribution value in the following ways.

-   You can optionally set the [AdDistributionReportFilter](~/reporting/addistributionreportfilter.md) to Native if you only want native ads data.

-   You can include the *AdDistribution* column value that is available in most performance reports. The possible values are Search, Content, and Native, so you can quickly discover performance data specific to Intent ads.

Performance data for native ads will be included in existing reports by default, with a few exceptions. The *SearchQueryPerformanceReport* ([Request](~/reporting/searchqueryperformancereportrequest.md) | [Filter](~/reporting/searchqueryperformancereportfilter.md) | [Column](~/reporting/searchqueryperformancereportcolumn.md)) and *ShareOfVoiceReport* ([Request](~/reporting/shareofvoicereportrequest.md) | [Filter](~/reporting/shareofvoicereportfilter.md) | [Column](~/reporting/shareofvoicereportcolumn.md)) reports will not have Native performance metrics even when ad distribution is an included column or included filter.

For more information about reporting, see [Reports](reports.md) and [Request and Download a Report](request-download-report.md).

You can also get performance data for Intent ads using the [Bulk Service](~/bulk/bulk-service-reference.md). You can get performance data for Intent ads when downloading the [Campaign](~/bulk/campaign.md), [Ad Group](~/bulk/ad-group.md), and [Keyword](~/bulk/keyword.md) records.

## See Also
[Bing Ads Web Service Addresses](web-service-addresses.md)  

