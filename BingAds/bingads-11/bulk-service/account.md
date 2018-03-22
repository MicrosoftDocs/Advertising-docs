---
title: "Account Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Account fields in a Bulk file.
---
# Account Record - Bulk
Defines an account that can be uploaded and downloaded in a bulk file.   

> [!NOTE]
> Only super admin and standard users can update an account.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Account* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Id](#id)
- [MSCLKID Auto Tagging Enabled](#msclkidautotaggingenabled)
- [Parent Id](#parentid)
- [Sync Time](#synctime)
- [Tracking Template](#trackingtemplate)

The *Account* record is included in the Bulk download file automatically everytime you call the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. 

### <a name="id"></a>Id
The system generated identifier of the account.

> [!IMPORTANT]
> The Bing Ads Bulk API only supports one account per file. This field is ignored during upload, and effectively set to the account ID that is specified in the [GetBulkUploadUrl](../bulk-service/getbulkuploadurl.md) service request.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="msclkidautotaggingenabled"></a>MSCLKID Auto Tagging Enabled
Determines whether auto-tagging of the MSCLKID query string parameter is enabled. The MSCLKID is a 32-character GUID that is unique for each ad click.

You might want to enable auto-tagging of MSCLKID for tracking leads via offline conversion goals. If auto-tagging of MSCLKID is enabled, the MSCLKID is automatically appended to the landing page URL when a customer clicks on your ad. For example, *www.contoso.com/?msclkid={msclkid}*. The click ID is unique for each ad click and multiple clicks on the same ad from the same user will result in multiple click IDs.

If the value is *True*, then the MSCLKID auto tagging feature is enabled. Otherwise the MSCLKID auto tagging feature is not enabled.

> [!IMPORTANT]
> Every time you add or update a new [DurationGoal](../campaign-management-service/durationgoal.md), [EventGoal](../campaign-management-service/eventgoal.md), [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md), [PagesViewedPerVisitGoal](../campaign-management-service/pagesviewedpervisitgoal.md) or [UrlGoal](../campaign-management-service/urlgoal.md) via either the Bing Ads web application or Campaign Management API, the *MSCLKID Auto Tagging Enabled* field is set to *True* automatically. For more information, see [Tracking offline conversions](https://help.bingads.microsoft.com/#apex/3/en/help:app54554/1/en-US/#ext:ConversionTracking_Load).

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the customer that contains the account.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  
 

### <a name="synctime"></a>Sync Time
Where the Account row intersects with the Sync Time column, the field value is represented as **MM/DD/YYYY HH:MM**, or month, day, year, hour, and minute relative to the UTC time zone. Save this value and use it with the bulk service to only get the changes between the current and the next download.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  


### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for all URLs in your account.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  



