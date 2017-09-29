---
title: "App Install Ad"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
dev_langs:
  - csharp
---
# App Install Ad
Defines an app install ad that can be downloaded and uploaded in a bulk file. Create an app install ad if your intention is to drive app downloads, and not necessarily to direct leads to a web site. If you want to direct leads to a web site in addition to driving app downloads, then you should create a text ad with app ad extensions.

> [!NOTE]
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.
>
> Before you can use app install ads, you must upgrade to Final Urls. For more information, see [URL Tracking with Upgraded URLs](~/guides/url-tracking-upgraded-urls.md).
>
> Bing Ads only supports *EN-US* apps.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *App Install Ad* record, the following attribute fields are available in the [Bulk File Schema](../bulk/bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [App Id](#appid)
- [App Platform](#appplatform)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Device Preference](#devicepreference)
- [Editorial Appeal Status](#editorialappealstatus)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Final Url](#finalurl)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Status](#status)
- [Text](#text)
- [Title](#title)
- [Tracking Template](#trackingtemplate)

You can download all fields of the *App Install Ad* record by including the [DownloadEntity](../bulk/downloadentity.md) value of *AppInstallAds* in the [DownloadCampaignsByAccountIds](../bulk/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](~/guides/bulk-download-upload.md).

The following Bulk CSV example would add a new app install ad given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Title,Text,Display Url,Destination Url,Promotion,Device Preference,Name,App Platform,App Id,Final Url,Mobile Final Url,Tracking Template,Custom Parameter,Title Part 1,Title Part 2,Path 1,Path 2
Format Version,,,,,,,,,,,,,,5,,,,,,,,,,
App Install Ad,Active,,-1111,ParentCampaignNameGoesHere,AdGroupNameHere,ClientIdGoesHere,,Contoso Quick Setup,Find New Customers & Increase Sales!,,,,All,,Android,AppStoreIdGoesHere,FinalUrlGoesHere,,,{_promoCode}=PROMO1; {_season}=summer,,,,
```

If you are using the [Bing Ads SDKs](~/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAppInstallAd* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAppInstallAd
var bulkAppInstallAd = new BulkAppInstallAd
{
    // 'Parent Id' column header in the Bulk file
    AdGroupId = adGroupIdKey,
    // 'Ad Group' column header in the Bulk file
    AdGroupName = "AdGroupNameHere",
    // 'Campaign' column header in the Bulk file
    CampaignName = "ParentCampaignNameGoesHere",
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
                
    // Map properties in the Bulk file to the 
    // AppInstallAd object of the Campaign Management service.
    AppInstallAd = new AppInstallAd
    {
        // 'App Platform' column header in the Bulk file
        AppPlatform = "Android",
        // 'App Id' column header in the Bulk file
        AppStoreId = "AppStoreIdGoesHere",
        // 'Device Preference' column header in the Bulk file
        DevicePreference = 0,
        // 'Final Url' column header in the Bulk file
        FinalUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "FinalUrlGoesHere"
        },
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Status' column header in the Bulk file
        Status = AdStatus.Active,
        // 'Text' column header in the Bulk file
        Text = "Find New Customers & Increase Sales!",
        // 'Title' column header in the Bulk file
        Title = "Contoso Quick Setup",
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
};

uploadEntities.Add(bulkAppInstallAd);

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

### <a name="adgroup"></a>Ad Group
The name of the ad group that contains the ad.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="appid"></a>App Id
The application identifier provided by the app store.

If the application is new, please expect to wait 4-7 days before the ad will be eligible to deliver.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="appplatform"></a>App Platform
The application platform.

Possible values include *iOS* and *Android*.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group and ad.

**Add:** Read-only  
**Update:** Read-only  
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
This field determines whether the preference is for app install ads to be displayed on mobile and tablet devices or only on mobile devices. (App install ads are not currently supported on desktop computers.)

Possible values are *All* (mobile and tablet devices) and *Mobile* (i.e. excluding tablets), which differ from values used in the campaign management service. 

The default value is *All*.

In the bulk download and upload results file, this field will never be empty. If you did not specify a device preference, the default value of *All* will be returned.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value*, then you are effectively resetting to the default value of *All*.    
**Delete:** Read-only  

### <a name="editorialappealstatus"></a>Editorial Appeal Status
Determines whether you can appeal the issues found by the editorial review.

Possible values include *Appealable*, *AppealPending*, and *NotAppealable*. For more details, see [AppealStatus Value Set](~/campaign-management/appealstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Failure Reason Codes](~/guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdEditorialStatus Value Set](~/campaign-management/adeditorialstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="finalurl"></a>Final Url
The URL where a search user lands and can choose to install an app.

The following validation rules apply to *Final Url* for app install ads.

*  The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.
*  You may specify only one Url in this field.
*  Each URL is delimited by a semicolon and space ("; ").
*  Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".
*  Each URL must be a well-formed URL starting with either http:// or https://.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.     
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the ad.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the ad.

This bulk field maps to the *Id* field of the [Ad Group](../bulk/ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](../bulk/ad-group.md) record. This is recommended if you are adding new ads to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the ad.

Possible values are *Active*, *Paused*, or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to *Deleted*.

### <a name="text"></a>Text
The ad copy. The copy must contain at least one word. The ad’s copy and title combined must total at least three words.

The ad copy cannot contain dynamic text strings such as {keyword}. 

The maximum input length of the copy is 71 characters. Note that for ad groups that use Traditional Chinese, the text is limited to 38 characters.

The ad copy cannot contain the newline (\n) character.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="title"></a>Title
The title of the ad. The title must contain at least one word. The ad’s copy and title combined must total at least three words.

The title cannot contain dynamic text strings such as {keyword}.

The maximum input length of the title is 25 characters. Note that for ad groups that use Traditional Chinese, the title is limited to 15 characters.

The title cannot contain the newline (\n) character.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for the URL specified with FinalUrls.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](~/guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  


## <a name="entityperformancedata"></a>Performance Data Fields in the Bulk File
If the [DataScope Value Set](../bulk/datascope.md) element of the download request includes *EntityPerformanceData*, the download file will also include the following fields in this record.

|Column Header|Description|
|-----------------|---------------|
|*Spend*|The cost per click (CPC) summed for each click.|
|*Impressions*|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|*Clicks*|The number of times that the ads in the account were clicked.|
|*CTR*|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).

The formula for calculating CTR is *(Clicks / Impressions) * 100*.|
|*Avg CPC*|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.

The formula for calculating the average CPC is *(Spend /Clicks)*.|
|*Avg CPM*|The average of the cost-per-thousand impressions of the ads.

The value will be 0 (zero) if the corresponding ad groups do not specify the Content ad distribution medium.|
|*Avg position*|The average position of the ad on a webpage.|
|*Conversions*|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|*CPA*|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.

Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|

