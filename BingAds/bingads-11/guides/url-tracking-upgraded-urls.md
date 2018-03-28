---
title: "URL Tracking with Upgraded URLs"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: URL tracking allows you to find out how people got to your website by adding tracking parameters in Bing Ads and then using a third-party tracking tool or service to analyze the data.
---
# URL Tracking with Upgraded URLs
URL tracking allows you to find out how people got to your website by adding tracking parameters in Bing Ads and then using a third-party tracking tool or service to analyze the data. When an ad is served, the tracking parameters are dynamically appended to your landing page URL. This landing page URL is recorded on your web server and then a third-party tracking tool, like Adobe or Google Analytics, can interpret the data.

If you have set up [tracking in Bing Ads](https://help.bingads.microsoft.com/#apex/3/en/56798/2) by adding URL parameters to your destination URLs, you will be interested in Upgraded URLs. Upgraded URLs separate the landing page URL from the tracking or URL parameters so if you want to edit your URL parameters, your ad doesn't have to go through another editorial review. It also allows you to define a separate mobile landing page URL if you have a website that is optimized for smaller devices.

By separating the tracking template details from the final URLs you can take advantage of the following benefits:
-   You can define tracking templates for one or more account, campaign, ad group, keyword, ad, or Sitelink Extension. If you use a common tracking template for all ads in your campaign for example, you can update it once at the campaign level instead of making changes to all of your ads. Tracking templates and custom parameters defined for lower level entities e.g. keyword override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](entity-hierarchy-limits.md).  
-   When you update your tracking template information, the URL doesn't need to go through editorial review and your ads will continue to serve uninterrupted. Editorial review is only required when you change your actual ads, keywords or extensions.  
-   Doing so helps Bing Ads understand what information is URL versus tracking template information, and reduces crawling on your website.  

For an overview of Final URLs and tracking templates, see the following Bing Ads help articles.
-   [How do I create an account tracking template?](http://help.bingads.microsoft.com/#apex/3/en/56772/-1)  
-   [Can I use custom parameters?](http://help.bingads.microsoft.com/#apex/3/en/56774/-1)  
-   [What are Upgraded URLs and how do I upgrade?](http://help.bingads.microsoft.com/#apex/3/en/56751/-1)  

You can manage Final URLs, Custom Parameters, and Tracking Templates with either the [Bulk Service](../bulk-service/bulk-service-reference.md) or [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md). You should use the [Bulk Service](../bulk-service/bulk-service-reference.md) service if you need to upload or download a high volume of entity settings. For example you can update all keyword bids for your entire account in a single upload. In comparison, with the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md) service you can only update 1,000 keywords per call and those keywords must be in the same ad group. For more details about Final URLs and tracking templates using the Bing Ads API, see the sections below.
-   [Tracking Templates](#trackingtemplatevalidation)  
-   [Final URLs](#finalurlvalidation)  
-   [Custom Parameters](#customparametersvalidation)  
-   [URL Tracking with the Bulk Service](#bulkservice)  
-   [URL Tracking with the Campaign Management Service](#campaignservice)  
-   [URL Tracking with the Reporting Service](#reportingservice)  

## <a name="trackingtemplatevalidation"></a>Tracking Templates
Tracking templates can be used in tandem with final URLs to assemble the landing page URL where a user is directed after the ad is clicked. Here is an example:

**Final URL:** *http://contoso.com/contact-us*

**Tracking template:** *{lpurl}?ref=bing&keyword={Keyword}&cmpid={CampaignID}&agid={AdGroupID}&adid={AdID}*. The *{lpurl}* tag references the Landing Page URL. Bing will replace this with your Final URL when your ad is served.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2) 
- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](entity-hierarchy-limits.md).  
- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.  
- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.   
- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

For an account, campaign, or ad group level tracking template, please note the following:

-   Additionally you must include at least one of the following landing page URL tags: *{lpurl}*, *{lpurl+2}*, *{lpurl+3}*, *{unescapedlpurl}*, *{escapedlpurl}*.

We recommend adding a default tracking template at the account level so that all the campaigns, ad groups, ads, and Sitelink Extensions use the same URL format. If you add more tracking templates at the campaign, ad group, ad or Sitelink Extension level, they will override the account level settings. You can set the account level tracking template as the value of the *TrackingUrlTemplate* key within the *ForwardCompatibilityMap* element of the [Account Data Object](../customer-management-service/account.md).

**Important:** Only super admin and standard users can update an account.

## <a name="finalurlvalidation"></a>Final URLs
The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Final URLs must each be a well-formed URL starting with either http:// or https://.

- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.

- You may not specify *FinalMobileUrls* if the device preference is set to mobile.

Also note the following validation rules for ad and site link final URLs.

-   You may not specify final mobile URLs if the device preference is set to mobile.

-   If the ad or site link's tracking template or custom parameters are specified, then at least one final URL is required.


## <a name="customparametersvalidation"></a>Custom Parameters
URL parameters are used to track information about the source of an ad click. By adding these parameters to your ads and campaigns, you can learn if people who clicked on your ads came from mobile devices, where they were located when they clicked your ads, and much more. For example if you use the {AdId} tag in your URL, then when the user clicks your ad the unique system identifier for that ad will be included in the URL where the user lands. For a list of supported parameters, see the *Available parameters* sections within the Bing Ads help article [How do I create an account tracking template?](https://help.bingads.microsoft.com/#apex/3/en/56772/-1).

Custom parameters work exactly the same as URL parameters with respect to dynamic substitutions, except that you will choose the parameter names and values (also known as key and value pairs). You can define custom parameters for one or more campaign, ad group, keyword, ad, or Sitelink Extension. If you use a common custom parameter for all ads in your campaign for example, you can update it once at the campaign level instead of making changes to all of your ads.

Custom parameters are helpful with sharing dynamic information across multiple URLs in a meaningful way for you to report on. Similarly how dynamic texts are provided by Bing Ads to give you more campaign insights on your performance. Custom parameters are advertiser created. 

The following validation rules apply to custom parameters.
-  Custom parameters defined for lower level entities e.g. keyword override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](entity-hierarchy-limits.md).  
-  You may include up to 3 custom parameters per entity.

## <a name="bulkservice"></a>URL Tracking with the Bulk Service
The [Bulk Service](../bulk-service/bulk-service-reference.md) create, update, and delete operations can be completed using Bulk upload. You can use Bulk download to read back your data. For more information see [Bulk File Schema](../bulk-service/bulk-file-schema.md) and [Bulk Download and Upload](bulk-download-upload.md).

These are the Bing Ads entities with properties for managing URLs that can be accessed using the [Bulk Service](../bulk-service/bulk-service-reference.md).

-   [Campaign](../bulk-service/campaign.md)
-   [Ad Group](../bulk-service/ad-group.md)
-   [Ad Group Dynamic Search Ad Target](../bulk-service/ad-group-dynamic-search-ad-target.md) 
-   [Ad Group Product Partition](../bulk-service/ad-group-product-partition.md) 
-   [App Install Ad](../bulk-service/app-install-ad.md)
-   [Expanded Text Ad](../bulk-service/expanded-text-ad.md)
-   [Text Ad](../bulk-service/text-ad.md)
-   [Keyword](../bulk-service/keyword.md)
-   [Sitelink Ad Extension](../bulk-service/sitelink-ad-extension.md)
-   [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md)

## <a name="campaignservice"></a>URL Tracking with the Campaign Management Service
These are the Bing Ads entities with properties for managing URLs that can be accessed using the [Campaign Management Service](../campaign-management-service/campaign-management-service-reference.md). You can create, read, update, and delete these entities.
-  [AdGroup](../campaign-management-service/adgroup.md)  
-  [AppInstallAd](../campaign-management-service/appinstallad.md)  
-  [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md)  
-  [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md)  
-  [ExpandedTextAd](../campaign-management-service/expandedtextad.md)  
-  [Keyword](../campaign-management-service/keyword.md)  
-  [SiteLink](../campaign-management-service/sitelink.md)  
-  [Sitelink2AdExtension](../campaign-management-service/sitelink2adextension.md)  
-  [TextAd](../campaign-management-service/textad.md)  

## <a name="reportingservice"></a>URL Tracking with the Reporting Service
The following reports can be submitted and downloaded with the [Reporting Service](../reporting-service/reporting-service-reference.md) to get performance data for Final URLs and Tracking Templates. 

The *TrackingTemplate* and *CustomParameters* columns for upgraded URLs are available in several reports for example, the [AdPerformanceReportColumn](../reporting-service/adperformancereportcolumn.md).

## See Also
[Bing Ads Web Service Addresses](web-service-addresses.md)

