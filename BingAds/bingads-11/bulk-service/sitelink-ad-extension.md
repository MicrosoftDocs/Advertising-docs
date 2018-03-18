---
title: "Sitelink Ad Extension Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Sitelink Ad Extension fields in a Bulk file.
dev_langs:
  - csharp
---
# Sitelink Ad Extension Record - Bulk
Defines a sitelink ad extension that can be downloaded and uploaded in a bulk file.

The *Sitelink Ad Extension* record adheres to the nested sitelink data model, where each sitelink ad extension has *multiple* sitelinks. Each sitelink is represented as a single *Sitelink Ad Extension* record in the bulk file. In other words, to represent multiple sitelinks for one sitelink ad extension, you must read and write multiple rows in the bulk file. Ad extension level properties such as *Id* and *Parent Id* columns will be the same for all sitelinks, while the sitelink level properties such as *Sitelink Extension Order* and *Sitelink Extension Link Text* will differ for each record.

> [!NOTE]
> During calendar year 2017, Bing Ads upgraded all [Sitelink Ad Extension](sitelink-ad-extension.md) records (contains multiple sitelinks per ad extension) to [Sitelink2 Ad Extension](sitelink2-ad-extension.md) records (contains one sitelink per ad extension). In a future version of the API the deprecated sitelink programming interface will be consolidated and the '2' suffix will be removed from the new sitelink ad extensions.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Sitelink Ad Extension* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Schedule](#adschedule)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Device Preference](#devicepreference)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [End Date](#enddate)
- [Final Url](#finalurl)
- [Id](#id)
- [Mobile Final Url](#mobilefinalurl)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Sitelink Extension Description1](#sitelinkextensiondescription1)
- [Sitelink Extension Description2](#sitelinkextensiondescription2)
- [Sitelink Extension Destination Url](#sitelinkextensiondestinationurl)
- [Sitelink Extension Link Text](#sitelinkextensionlinktext)
- [Sitelink Extension Order](#sitelinkextensionorder)
- [Start Date](#startdate)
- [Status](#status)
- [Tracking Template](#trackingtemplate)
- [Use Searcher Time Zone](#usesearchertimezone)
- [Version](#version)

You can download all fields of the *Sitelink Ad Extension* record by including the [DownloadEntity](downloadentity.md) value of *SiteLinksAdExtensions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new Sitelink Ad Extension to the account's shared library. 

```csv
Type,Status,Id,Parent Id,Client Id,Modified Time,Start Date,End Date,Device Preference,Name,Ad Schedule,Use Searcher Time Zone,Sitelink Extension Order,Sitelink Extension Link Text,Sitelink Extension Destination Url,Sitelink Extension Description1,Sitelink Extension Description2,Final Url,Mobile Final Url,Tracking Template,Custom Parameter
Format Version,,,,,,,,,5,,,,,,,,,,,
Sitelink Ad Extension,,-17,0,,,,12/31/2018,,,(Monday[09:00-21:00]),FALSE,1,Women's Shoe Sale,,Simple & Transparent.,No Upfront Cost.,http://www.contoso.com/womenshoesale,http://mobile.contoso.com/womenshoesale,,{_promoCode}=PROMO1; {_season}=summer
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkSiteLinkAdExtension* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkSiteLinkAdExtension
var bulkSiteLinkAdExtension = new BulkSiteLinkAdExtension
{
    // 'Parent Id' column header in the Bulk file
    AccountId = 0,
                
    // Map properties in the Bulk file to the 
    // SiteLinksAdExtension object of the Campaign Management service.
    SiteLinksAdExtension = new SiteLinksAdExtension
    {
        // 'Id' column header in the Bulk file
        Id = siteLinksAdExtensionIdKey,
        SiteLinks = new []
        {
            // Map properties in the Bulk file to the 
            // SiteLink object of the Campaign Management service.
            new SiteLink
            {
                // 'Sitelink Extension Description1' column header in the Bulk file
                Description1 = "Simple & Transparent.",
                // 'Sitelink Extension Description2' column header in the Bulk file
                Description2 = "No Upfront Cost.",
                // 'Text' column header in the Bulk file
                DisplayText = "Women's Shoe Sale",
                // 'Destination Url' column header in the Bulk file
                DestinationUrl = "",
                // 'Final Url' column header in the Bulk file
                FinalUrls = new[] {
                    // Each Url is delimited by a semicolon (;) in the Bulk file
                    "http://www.contoso.com/womenshoesale"
                },
                // 'Mobile Final Url' column header in the Bulk file
                FinalMobileUrls = new[] {
                    // Each Url is delimited by a semicolon (;) in the Bulk file
                    "http://mobile.contoso.com/womenshoesale"
                },
                // 'Ad Schedule' column header in the Bulk file
                Scheduling = new Schedule
                {
                    // Each day and time range is delimited by a semicolon (;) in the Bulk file
                    DayTimeRanges = new[]
                    {
                        // Within each day and time range the format is Day[StartHour:StartMinue-EndHour:EndMinute].
                        new DayTime
                        {
                            Day = Day.Monday,
                            StartHour = 9,
                            StartMinute = Minute.Zero,
                            EndHour = 21,
                            EndMinute = Minute.Zero,
                        },
                    },
                    // 'End Date' column header in the Bulk file
                    EndDate = new Microsoft.BingAds.V10.CampaignManagement.Date
                    {
                        Month = 12,
                        Day = 31,
                        Year = DateTime.UtcNow.Year + 1
                    },
                    // 'Start Date' column header in the Bulk file
                    StartDate = null,
                    // 'Use Searcher Time Zone' column header in the Bulk file
                    UseSearcherTimeZone = false,
                },
                // 'Tracking Template' column header in the Bulk file
                TrackingUrlTemplate = null,
                // 'Custom Parameter' column header in the Bulk file
                UrlCustomParameters = new CustomParameters
                {
                    // Each custom parameter is delimited by a semicolon (;) in the Bulk file
                    Parameters = new[] {
                        new CustomParameter(){
                            Key = "promoCode",
                            Value = "PROMO1"
                        },
                        new CustomParameter(){
                            Key = "season",
                            Value = "summer"
                        },
                    }
                },
            }
        },
                    
        // 'Status' column header in the Bulk file
        Status = AdExtensionStatus.Active,
    },
};

// Map properties in the Bulk file to the BulkSiteLink
var bulkSiteLink = new BulkSiteLink
{
    // 'Parent Id' column header in the Bulk file
    AccountId = 0,
    // 'Id' column header in the Bulk file
    AdExtensionId = siteLinksAdExtensionIdKey,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // SiteLink object of the Campaign Management service.
    SiteLink = new SiteLink
    {
        // 'Sitelink Extension Description1' column header in the Bulk file
        Description1 = "Simple & Transparent.",
        // 'Sitelink Extension Description2' column header in the Bulk file
        Description2 = "No Upfront Cost.",
        // 'Text' column header in the Bulk file
        DisplayText = "Women's Shoe Sale",
        // 'Destination Url' column header in the Bulk file
        DestinationUrl = "",
        // 'Final Url' column header in the Bulk file
        FinalUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://www.contoso.com/womenshoesale"
        },
        // 'Mobile Final Url' column header in the Bulk file
        FinalMobileUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://mobile.contoso.com/womenshoesale"
        },
        // 'Ad Schedule' column header in the Bulk file
        Scheduling = new Schedule
        {
            // Each day and time range is delimited by a semicolon (;) in the Bulk file
            DayTimeRanges = new[]
            {
                // Within each day and time range the format is Day[StartHour:StartMinue-EndHour:EndMinute].
                new DayTime
                {
                    Day = Day.Monday,
                    StartHour = 9,
                    StartMinute = Minute.Zero,
                    EndHour = 21,
                    EndMinute = Minute.Zero,
                },
            },
            // 'End Date' column header in the Bulk file
            EndDate = new Microsoft.BingAds.V10.CampaignManagement.Date
            {
                Month = 12,
                Day = 31,
                Year = DateTime.UtcNow.Year + 1
            },
            // 'Start Date' column header in the Bulk file
            StartDate = null,
            // 'Use Searcher Time Zone' column header in the Bulk file
            UseSearcherTimeZone = false,
        },
        // 'Tracking Template' column header in the Bulk file
        TrackingUrlTemplate = null,
        // 'Custom Parameter' column header in the Bulk file
        UrlCustomParameters = new CustomParameters
        {
            // Each custom parameter is delimited by a semicolon (;) in the Bulk file
            Parameters = new[] {
                new CustomParameter(){
                    Key = "promoCode",
                    Value = "PROMO1"
                },
                new CustomParameter(){
                    Key = "season",
                    Value = "summer"
                },
            }
        },
    },
                
    // 'Status' column header in the Bulk file
    Status = AdExtensionStatus.Active,
};

// BulkSiteLinkAdExtension does not support 'Client Id' and
// replaces all sitelinks for the ad extension, whereas BulkSiteLink
// enables you to add, update, or delete one sitelink at a time.
// Since we are adding sitelinks for the first time, this example uses
// BulkSiteLinkAdExtension. 

uploadEntities.Add(bulkSiteLinkAdExtension);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="adschedule"></a>Ad Schedule
The list of day and time ranges that you want the sitelink to be displayed with your ads. Each day and time range includes the scheduled day of week, start/end hour, and start/end minute. Each day and time range is enclosed by left and right parentheses, and separated from other day and time ranges with a semicolon (;) delimiter. Within each day and time range the format is *Day[StartHour:StartMinue-EndHour:EndMinute]*.

The possible values of *StartHour* range from 00 to 23, where *00* is equivalent to 12:00AM and *12* is 12:00PM.

The possible values of *EndHour* range from 00 to 24, where *00* is equivalent to 12:00AM and *12* is 12:00PM.

The possible values of *StartMinute* and *EndMinute* range from 00 to 60.

The following example demonstrates day and time ranges during weekdays from 9:00AM through 9:00PM: *(Monday[09:00-21:00]);(Tuesday[09:00-21:00]);(Wednesday[09:00-21:00]);(Thursday[09:00-21:00]);(Friday[09:00-21:00])*

**Add:** Optional. If you do not set this field, then sitelink will be eligible for scheduling anytime during the calendar start and end dates.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. The individual day and time ranges cannot be updated. You can effectively update the day and time ranges by sending a new set that should replace the prior set. If you do not set this field, then the existing settings will be retained. If you set this field to *delete_value*, then you are effectively removing all existing day and time ranges.    
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

-   Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

-   You may include up to 3 custom parameter key and value pairs. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

-   A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

-   The Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}.

    **Note:** With the Bulk service the surrounding braces and underscore are required. The maximum length of 16 UTF-8 bytes does not include the braces and underscore: '{', '_', and '}'. With the Campaign Management service the maximum length is 16 UTF-bytes, and you may not specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

### <a name="devicepreference"></a>Device Preference
This field determines whether the preference is for the ad extension to be displayed on mobile devices or all devices.

Possible values are *All* and *Mobile*, which differ from values used in the campaign management service. 

The default value is *All*.

In the bulk download and upload results file, this field will never be empty. If you did not specify a device preference, the default value of *All* will be returned.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value*, then you are effectively resetting to the default value of *All*.    
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad extension that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad extension.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdExtensionEditorialStatus Value Set](../campaign-management-service/adextensioneditorialstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="enddate"></a>End Date
The sitelink scheduled end date string formatted as *MM/DD/YYYY*.

The end date is inclusive. For example, if you set this field to 3/10/2017, the sitelink will stop being shown at 11:59 PM on 3/10/2017.

**Add:** Optional. If you do not specify an end date, the sitelink will continue to be delivered unless you pause the associated campaigns, ad groups, or ads.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. The end date can be shortened or extended, as long as the start date is either null or occurs before the new end date. If you do not set this field, then the existing settings will be retained. If you set this field to *delete_value*, then you are effectively removing the end date and the sitelink will continue to be delivered unless you pause the associated campaigns, ad groups, or ads.    
**Delete:** Read-only  

### <a name="finalurl"></a>Final Url
The landing page URL to use with optional tracking template and custom parameters.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

Also note that  if the *Tracking Template* or *Custom Parameter* fields are set, then the *Final Url* is required.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the ad extension.

**Add:** Optional. You must either leave this field empty, or specify a negative identifier. A negative identifier set for the ad extension can then be referenced in the *Id* field of dependent record types such as [AdGroup Sitelink Ad Extension](adgroup-sitelink-ad-extension.md) and [Campaign Sitelink Ad Extension](campaign-sitelink-ad-extension.md). This is recommended if you are adding new ad extensions and new dependent records in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="mobilefinalurl"></a>Mobile Final Url
The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

Also note that you may not specify *Mobile Final Url* if the *Device Preference* is set to *Mobile*.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.   
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the account that contains the ad extension.

This bulk field maps to the *Id* field of the [Account](account.md) record.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  
  
### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="sitelinkextensiondescription1"></a>Sitelink Extension Description1
The sitelink description line 1.

The maximum input length is 35 characters. If any Traditional Chinese characters are included, the limit is 15 characters.

> [!NOTE]
> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.

> [!NOTE]
> If you specify *Sitelink Extension Description1* then *Sitelink Extension Description2* is required.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="sitelinkextensiondescription2"></a>Sitelink Extension Description2
The sitelink description line 2.

The maximum input length is 35 characters. If any Traditional Chinese characters are included, the limit is 15 characters.

> [!NOTE]
> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.

> [!NOTE]
> If you specify *Sitelink Extension Description2* then *Sitelink Extension Description1* is required.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="sitelinkextensiondestinationurl"></a>Sitelink Extension Destination Url
The URL of the webpage that users are taken to when they click the sitelink.

The URL can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Available parameters section within the Bing Ads help article [How do I set up destination URL tracking?](https://help.bingads.microsoft.com/#apex/3/en/51091/2).

The URL can contain a maximum of 1,024 characters. If the URL does not specify a protocol, the system uses the HTTP protocol when a user clicks the ad. If the URL specifies the HTTP protocol when you add an ad, the service will remove the http:// protocol string (the HTTP protocol string does not count against the 1,024 character limit); however, the service will not remove an HTTPS protocol string (https://) from the URL.

> [!IMPORTANT]
> If you are currently using Destination URLs, you must eventually replace them with Final URLs. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="sitelinkextensionlinktext"></a>Sitelink Extension Link Text
The site-link text displayed in the ad.

If you specify *Sitelink Extension Description1* or *Sitelink Extension Description2* then the display text can contain a maximum of 25 characters; otherwise, the display text can contain a maximum of 35 characters. If any Traditional Chinese characters are included, the limits are 11 characters given *Sitelink Extension Description1* or *Sitelink Extension Description2*, and 15 characters otherwise.

> [!NOTE]
> Starting the week of September 18th, the limit will be relaxed such that only the Traditional Chinese characters will be counted double against the character limit. Each Traditional Chinese character will count as two and each English character will count only as one character.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="sitelinkextensionorder"></a>Sitelink Extension Order
This field value represents the order of this record in the comparable list of [SiteLink](../campaign-management-service/sitelink.md) objects. For example if this row in the bulk file represents the first item in the list, this field's value is 1 (one).

For the campaign management service, the SiteLinks element of the [SiteLinksAdExtension](../campaign-management-service/sitelinksadextension.md) object is a list of [SiteLink](../campaign-management-service/sitelink.md) objects.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="startdate"></a>Start Date
The sitelink scheduled start date string formatted as *MM/DD/YYYY*.

The start date is inclusive. For example, if you set *StartDate* to 3/5/2017, the sitelink will start being shown at 12:00 AM on 3/5/2017.

**Add:** Optional. If you do not specify a start date, the sitelink is immediately eligible to be scheduled during the day and time ranges.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. The start date can be shortened or extended, as long as the end date is either null or occurs after the new start date. If you do not set this field, then the existing settings will be retained. If you set this field to *delete_value*, then you are effectively removing the start date and the sitelink is immediately eligible to be scheduled during the day and time ranges.    
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the ad extension.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to *Deleted*.

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use for your sitelink URLs.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="usesearchertimezone"></a>Use Searcher Time Zone
Determines whether to use the account time zone or the time zone of the search user where the ads could be delivered.

Set this property to *TRUE* if you want the sitelink to be shown in the search user's time zone, and otherwise set it to *FALSE*.

**Add:** Optional. If you do not specify this field or leave it empty, the default value of *FALSE* will be set and the account time zone will be used.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value*, then you are effectively resetting to the default value of *FALSE*.   
**Delete:** Read-only  

### <a name="version"></a>Version
The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it’s revised.

**Add:** Read-only  
**Update:** Read-only    
**Delete:** Read-only  


