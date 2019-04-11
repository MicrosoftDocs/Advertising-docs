---
title: "Account Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Account fields in a Bulk file.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# Account Record - Bulk
Defines an account that can be uploaded and downloaded in a bulk file.   

> [!NOTE]
> Only super admin and standard users can update an account.

The *Account* record is included in the Bulk download file automatically everytime you call the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. 

The following is a Bulk CSV example download for account. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Website,Sync Time,Client Id,Modified Time,MSCLKID Auto Tagging Enabled,Name,Tracking Template,Final Url Suffix
Format Version,,,,,,,,,,,true,6.0,,
Account,,111,222,,,,,02/12/2019 15:32:34,,,true,,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to download the *BulkAccount* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

For an *Account* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Final Url Suffix](#finalurlsuffix)
- [Id](#id)
- [MSCLKID Auto Tagging Enabled](#msclkidautotaggingenabled)
- [Parent Id](#parentid)
- [Sync Time](#synctime)
- [Tracking Template](#trackingtemplate)

## <a name="finalurlsuffix"></a>Final Url Suffix
The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides. 

> [!NOTE]
> This feature is only available for customers in the Final URL Suffix Phase 1 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 533). If you are not in the pilot and attempt to set this property an error will be returned. During calendar year 2019 this feature will be enabled for all customers.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.  
**Delete:** Read-only  

## <a name="id"></a>Id
The system generated identifier of the account.

> [!IMPORTANT]
> The Bing Ads Bulk API only supports one account per file. This field is ignored during upload, and effectively set to the account ID that is specified in the [GetBulkUploadUrl](../bulk-service/getbulkuploadurl.md) service request.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="msclkidautotaggingenabled"></a>MSCLKID Auto Tagging Enabled
Determines whether auto-tagging of the MSCLKID query string parameter is enabled. The MSCLKID is a 32-character GUID that is unique for each ad click.

You might want to enable auto-tagging of MSCLKID for tracking leads via offline conversion goals. If auto-tagging of MSCLKID is enabled, the MSCLKID is automatically appended to the landing page URL when a customer clicks on your ad. For example, *www.contoso.com/?msclkid={msclkid}*. The click ID is unique for each ad click and multiple clicks on the same ad from the same user will result in multiple click IDs.

If the value is *True*, then the MSCLKID auto tagging feature is enabled. Otherwise the MSCLKID auto tagging feature is not enabled.

> [!IMPORTANT]
> Every time you add or update a new [DurationGoal](../campaign-management-service/durationgoal.md), [EventGoal](../campaign-management-service/eventgoal.md), [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md), [PagesViewedPerVisitGoal](../campaign-management-service/pagesviewedpervisitgoal.md) or [UrlGoal](../campaign-management-service/urlgoal.md) via either the Bing Ads web application or Campaign Management API, the *MSCLKID Auto Tagging Enabled* field is set to *True* automatically. For more information, see [Tracking offline conversions](https://help.bingads.microsoft.com/#apex/3/en/56852/2).

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The system generated identifier of the customer that contains the account.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="synctime"></a>Sync Time
Where the Account row intersects with the Sync Time column, the field value is represented as **MM/DD/YYYY HH:MM**, or month, day, year, hour, and minute relative to the UTC time zone. Save this value and use it with the bulk service to only get the changes between the current and the next download.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for all URLs in your account.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.  
**Delete:** Read-only  



