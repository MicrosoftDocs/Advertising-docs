---
title: "Expanded Text Ad Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Expanded Text Ad fields in a Bulk file.
dev_langs:
  - csharp
---
# Expanded Text Ad Record - Bulk
Defines an expanded text ad that can be downloaded and uploaded in a bulk file.

This ad format works seamlessly on mobile, tablet and desktop devices so you can focus more on crafting your longer ad copy and optimizing your ad text to better engage your customers before they click your ad.

> [!NOTE]
> Before you can use expanded text ads, you must upgrade to Final Urls. For more information, see [URL Tracking with Upgraded URLs](/bingads/guides/url-tracking-upgraded-urls.md).

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Expanded Text Ad* record, the following attribute fields are available in the [Bulk File Schema](/bingads/bulk-service/bulk-file-schema.md). 

- [Ad Format Preference](#adformatpreference)
- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Editorial Appeal Status](#editorialappealstatus)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Final Url](#finalurl)
- [Id](#id)
- [Mobile Final Url](#mobilefinalurl)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Path 1](#path1)
- [Path 2](#path2)
- [Publisher Countries](#publishercountries)
- [Status](#status)
- [Text](#text)
- [Title Part 1](#titlepart1)
- [Title Part 2](#titlepart2)
- [Tracking Template](#trackingtemplate)

You can download all fields of the *Expanded Text Ad* record by including the [DownloadEntity](/bingads/bulk-service/downloadentity.md) value of *ExpandedTextAds* in the [DownloadCampaignsByAccountIds](/bingads/bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](/bingads/bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](/bingads/bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](/bingads/guides/bulk-download-upload.md).

The following Bulk CSV example would add a new expanded text ad given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Title,Text,Display Url,Destination Url,Promotion,Device Preference,Ad Format Preference,Name,App Platform,App Id,Final Url,Mobile Final Url,Tracking Template,Custom Parameter,Title Part 1,Title Part 2,Path 1,Path 2
Format Version,,,,,,,,,,,,,,5,,,,,,,,,,
Expanded Text Ad,Active,,-1111,ParentCampaignNameGoesHere,AdGroupNameHere,ClientIdGoesHere,,,Find New Customers & Increase Sales! Start Advertising on Contoso Today.,,,,,False,,,,http://www.contoso.com/womenshoesale,http://mobile.contoso.com/womenshoesale,,{_promoCode}=PROMO1; {_season}=summer,Contoso,Quick & Easy Setup,seattle,shoe sale
```

If you are using the [Bing Ads SDKs](/bingads/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkExpandedTextAd* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkExpandedTextAd
var bulkExpandedTextAd = new BulkExpandedTextAd
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
    // ExpandedTextAd object of the Campaign Management service.
    ExpandedTextAd = new ExpandedTextAd
    {
        // 'Mobile Final Url' column header in the Bulk file
        FinalMobileUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://mobile.contoso.com/womenshoesale"
        },
        // 'Final Url' column header in the Bulk file
        FinalUrls = new[] {
            // Each Url is delimited by a semicolon (;) in the Bulk file
            "http://www.contoso.com/womenshoesale"
        },
        ForwardCompatibilityMap = new []
        {
            // 'Ad Format Preference' column header in the Bulk file
            new KeyValuePair\<string,string>("NativePreference", "False")
        },
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Path 1' column header in the Bulk file
        Path1 = "seattle",
        // 'Path 2' column header in the Bulk file
        Path2 = "shoe sale",
        // 'Status' column header in the Bulk file
        Status = AdStatus.Active,
        // 'Text' column header in the Bulk file
        Text = "Find New Customers & Increase Sales! Start Advertising on Contoso Today.",
        // 'Title Part 1' column header in the Bulk file
        TitlePart1 = "Contoso",
        // 'Title Part 2' column header in the Bulk file
        TitlePart2 = "Quick & Easy Setup",
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

uploadEntities.Add(bulkExpandedTextAd);

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

### <a name="adformatpreference"></a>Ad Format Preference
The *Ad Format Preference* field is used to indicate whether or not you prefer the ad copy to be shown to users as a search or native ad. Search ads tend to be written as a call to action, whereas native ads should be written in more of an informational style. By defining at least one ad that should be used as native, the search ads will only be shown in search results.

> [!IMPORTANT]
> You must define at least one expanded text ad per ad group that is not native preferred, otherwise the ad copy of all expanded text ads will be eligible for both search and native ads.

Possible values are *Native* and *All*. If set to *All*, the ad will be eligible for both search and native ad formats. If set to *Native*, the ad will only be eligible for the native ad format.

**Add:** Optional. If you do not set this field when creating an expanded text ad, by default the ad format preference will be set to *All*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value* when updating an expanded text ad, the ad format preference will be set to the default value i.e. *All*.    
**Delete:** Read-only  

### <a name="adgroup"></a>Ad Group
The name of the ad group that contains the ad.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

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

### <a name="editorialappealstatus"></a>Editorial Appeal Status
Determines whether you can appeal the issues found by the editorial review.

Possible values include *Appealable*, *AppealPending*, and *NotAppealable*. For more details, see [AppealStatus Value Set](/binga/bingads/campaign-management-service/appealstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Failure Reason Codes](/bingads/guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdEditorialStatus Value Set](/binga/bingads/campaign-management-service/adeditorialstatus.md).

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
The landing page URL.

The domain portion of the URL in combination with the path 1 and path 2 strings cannot exceed 67 characters.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

Also note that  if the *Tracking Template* or *Custom Parameter* fields are set, then at least one Final URL is required.

> [!NOTE]
> This URL is used only if the keyword does not specify a final URL.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the ad.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="mobilefinalurl"></a>Mobile Final Url
The mobile landing page URL.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url.

> [!NOTE]
> This URL is used only if the keyword does not specify a *Mobile Final Url*.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the ad.

This bulk field maps to the *Id* field of the [Ad Group](/bingads/bulk-service/ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](/bingads/bulk-service/ad-group.md) record. This is recommended if you are adding new ads to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](/binga/bingads/bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="path1"></a>Path 1
The first part of the optional path that will be appended to the domain portion of your display URL. The domain portion of your display URL e.g. *http://www.contoso.com* will be generated from the domain of your Final URL (*Final Url* field).  Then if you have specified a value for *Path 1* it will be appended to the display URL. If you have also specified a value for *Path 2*, then it will also be appended to the display URL after *Path 1*. For example if your *Final Url* contains *http://www.contoso.com*, *Path 1* is set to *subdirectory1*, and *Path 2* is set to *subdirectory2*, then the URL displayed will be *http://www.contoso.com/subdirectory1/subdirectory2*.

The path can contain a countdown function. For more details see [Countdown Functions](/bingads/guides/expanded-text-ads.md#countdown). 

The path can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).

The maximum input length of the path is 50 characters with dynamic text strings. However, the ad will fail to display if the path exceeds 15 characters after dynamic text substitution occurs. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of the path is 25 characters, and the path is limited to 7 characters after substitution.

> [!IMPORTANT]
> The double-width characters are determined by the characters you use instead of the character set of the campaign or ad group language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. 

The path cannot contain the forward slash (/) or newline (\n) characters.

If the path includes a space, it will be replaced with an underscore (_) when the ad is shown.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="path2"></a>Path 2
The second part of the optional path that will be appended to the domain portion of your display URL. The domain portion of your display URL e.g. *http://www.contoso.com* will be generated from the domain of your Final URL (*Final Url* field).  Then if you have specified a value for *Path 1* it will be appended to the display URL. If you have also specified a value for *Path 2*, then it will also be appended to the display URL after *Path 1*. For example if your *Final Url* contains *http://www.contoso.com*, *Path 1* is set to *subdirectory1*, and *Path 2* is set to *subdirectory2*, then the URL displayed will be *http://www.contoso.com/subdirectory1/subdirectory2*.

You can only specify *Path 2* if *Path 1* is also set.

The path can contain a countdown function. For more details see [Countdown Functions](/bingads/guides/expanded-text-ads.md#countdown). 
	
The path can contain dynamic parameters such as {MatchType}. For a list of supported parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2).

The maximum input length of the path is 50 characters with dynamic text strings. However, the ad will fail to display if the path exceeds 15 characters after dynamic text substitution occurs. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of the path is 25 characters, and the path is limited to 7 characters after substitution.

> [!IMPORTANT]
> The double-width characters are determined by the characters you use instead of the character set of the campaign or ad group language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. 

The path cannot contain the forward slash (/) or newline (\n) characters.
	
If the path includes a space, it will be replaced with an underscore (_) when the ad is shown.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

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
The ad copy.

The text must contain at least one word.

The text can contain a countdown function. For more details see [Countdown Functions](/bingads/guides/expanded-text-ads.md#countdown). 

The text can contain dynamic text strings such as {keyword}. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).

The maximum input length of the copy is 300 characters, and can contain dynamic text strings. However, the ad will fail to display if the copy exceeds 80 characters after dynamic text substitution occurs. Note that for ad groups that use Traditional Chinese the maximum input length of the copy is 150 characters, and the text is limited to 40 characters after substitution.

> [!IMPORTANT]
> The double-width characters are determined by the characters you use instead of the character set of the campaign or ad group language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. 

The text cannot contain the newline (\n) character.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="titlepart1"></a>Title Part 1
The first part of the ad title. The *Title Part 1* and *Title Part 2* values will be automatically separated by a space, dash, and space (" - ") when the ad is shown, and you may not specify the dash in either of the title parts. Each part of the title must contain at least one word. 

The title can contain a countdown function. For more details see [Countdown Functions](/bingads/guides/expanded-text-ads.md#countdown). 

The title can contain dynamic text strings such as {keyword}. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).

The maximum input length of each title part is 30 characters without dynamic text. If dynamic text strings are used, the maximum input length of *Title Part 1* and *Title Part 2* combined is 77 characters. However, the ad will fail to display if either *Title Part 1* or *Title Part 2* exceeds 30 characters after dynamic text substitution occurs. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of each title part is 15 characters without dynamic text. If dynamic text strings are used, the maximum input length of *Title Part 1* and *Title Part 2* combined is 37 characters. However, the ad will fail to display if either *Title Part 1* or *Title Part 2* exceeds 15 characters after dynamic text substitution occurs.

> [!IMPORTANT]
> The double-width characters are determined by the characters you use instead of the character set of the campaign or ad group language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. 

The title cannot contain the newline (\n) character.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="titlepart2"></a>Title Part 2
The second part of the ad title. The *Title Part 1* and *Title Part 2* values will be automatically separated by a space, dash, and space (" - ") when the ad is shown, and you may not specify the dash in either of the title parts. Each part of the title must contain at least one word.

The title can contain a countdown function. For more details see [Countdown Functions](/bingads/guides/expanded-text-ads.md#countdown). 

The title can contain dynamic text strings such as {keyword}. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](http://help.bingads.microsoft.com/#apex/3/en/50811/1).
    
The maximum input length of each title part is 30 characters without dynamic text. If dynamic text strings are used, the maximum input length of *Title Part 1* and *Title Part 2* combined is 77 characters. However, the ad will fail to display if either *Title Part 1* or *Title Part 2* exceeds 30 characters after dynamic text substitution occurs. Note that for languages with double-width characters e.g. Traditional Chinese the maximum input length of each title part is 15 characters without dynamic text. If dynamic text strings are used, the maximum input length of *Title Part 1* and *Title Part 2* combined is 37 characters. However, the ad will fail to display if either *Title Part 1* or *Title Part 2* exceeds 15 characters after dynamic text substitution occurs.

> [!IMPORTANT]
> The double-width characters are determined by the characters you use instead of the character set of the campaign or ad group language settings. Double-width characters include Korean, Japanese and Chinese languages characters as well as Emojis. 

The title cannot contain the newline (\n) character.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for the URL specified with FinalUrls.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](/bingads/guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  


## <a name="entityperformancedata"></a>Performance Data Fields in the Bulk File
If the [DataScope Value Set](/bingads/bulk-service/datascope.md) element of the download request includes *EntityPerformanceData*, the download file will also include the following fields in this record.

|Column Header|Description|
|-----------------|---------------|
|*Spend*|The cost per click (CPC) summed for each click.|
|*Impressions*|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|*Clicks*|The number of times that the ads in the account were clicked.|
|*CTR*|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).<br/><br/>The formula for calculating CTR is *(Clicks / Impressions) * 100*.|
|*Avg CPC*|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.<br/><br/>The formula for calculating the average CPC is *(Spend /Clicks)*.|
|*Avg CPM*|The average of the cost-per-thousand impressions of the ads.<br/><br/>The value will be 0 (zero) if the corresponding ad groups do not specify the Content ad distribution medium.|
|*Avg position*|The average position of the ad on a webpage.|
|*Conversions*|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|*CPA*|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.<br/><br/>Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|

