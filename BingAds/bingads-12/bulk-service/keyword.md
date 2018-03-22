---
title: "Keyword Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Keyword fields in a Bulk file.
dev_langs:
  - csharp
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Keyword Record - Bulk
Defines a keyword that can be downloaded and uploaded in a bulk file.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Keyword* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Bid](#bid)
- [Bid Strategy Type](#bidstrategytype)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Custom Parameter](#customparameter)
- [Destination Url](#destinationurl)
- [Editorial Appeal Status](#editorialappealstatus)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Final Url](#finalurl)
- [Id](#id)
- [Inherited Bid Strategy Type](#inheritedbidstrategytype)
- [Keyword](#keyword)
- [Match Type](#matchtype)
- [Mobile Final Url](#mobilefinalurl)
- [Modified Time](#modifiedtime)
- [Param1](#param1)
- [Param2](#param2)
- [Param3](#param3)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Status](#status)
- [Tracking Template](#trackingtemplate)

You can download all fields of the *Keyword* record by including the [DownloadEntity](downloadentity.md) value of *Keywords* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new keyword given a valid ad group ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Keyword,Match Type,Bid,Param1,Param2,Param3,Name,Final Url,Mobile Final Url,Tracking Template,Custom Parameter,Bid Strategy Type
Format Version,,,,,,,,,,,,,,6,,,,,
Keyword,Active,,-1111,ParentCampaignNameGoesHere,AdGroupNameHere,ClientIdGoesHere,,red shoes,Broad,0.5,,,,,http://www.contoso.com/womenshoesale,http://mobile.contoso.com/womenshoesale,,{_promoCode}=PROMO1; {_season}=summer,ManualCpc
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkKeyword* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkKeyword
var bulkKeyword = new BulkKeyword
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
    // Keyword object of the Campaign Management service.
    Keyword = new Keyword
    {
        // 'Bid' column header in the Bulk file
        Bid = new Bid
        {
            Amount = 0.50,
        },
        // 'Bid Strategy Type' column header in the Bulk file
        BiddingScheme = new ManualCpcBiddingScheme { },
        // 'Destination Url' column header in the Bulk file
        DestinationUrl = null,
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
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Match Type' column header in the Bulk file
        MatchType = MatchType.Broad,
        // 'Param 1 column header in the Bulk file
        Param1 = null,
        // 'Param 2' column header in the Bulk file
        Param2 = null,
        // 'Param 3' column header in the Bulk file
        Param3 = null,
        // 'Status' column header in the Bulk file
        Status = KeywordStatus.Active,
        // 'Text' column header in the Bulk file
        Text = "red shoes",
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

uploadEntities.Add(bulkKeyword);

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
The name of the ad group that contains the keyword.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Ad Group* field.

### <a name="bid"></a>Bid
The bid to use when the user’s search term and the keyword match.

**Add:** Optional. If you do not specify a keyword level bid, the [Ad Group](ad-group.md) bid for the corresponding search or content match type will be used. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.  
**Delete:** Read-only  

### <a name="bidstrategytype"></a>Bid Strategy Type
The bid strategy type for how you want to manage your bids. For keywords you can use either of the *InheritFromParent* or *ManualCpc* bid strategy types. If you do not set this field, then *InheritFromParent* is used by default.

> [!IMPORTANT] 
> The *MaxClicks*, *MaxConversions*, and *TargetCpa* bid strategy types are available in several markets (For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).)  If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group’s or keyword’s bid strategy to *ManualCpc*.  
> -  You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
> -  Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any time using this bid strategy type.
> -  You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Bing Ads about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
> -  Whether you chose the *DailyBudgetAccelerated* or *DailyBudgetStandard* budget type, Bing Ads will use the *DailyBudgetStandard* budget type. 
> 
> Also note that you must have conversion tracking (a UET tag and a conversion goal) set up for the *EnhancedCpc*, *MaxConversions*, and *TargetCpa* bid strategy types to work. See [Universal Event Tracking](../guides/universal-event-tracking.md) for more information.
> 
> To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

> [!TIP]
> You can set your campaign’s bid strategy to *EnhancedCpc*, *MaxClicks*, *MaxConversions*, or *TargetCpa* and then, at any time, set an individual ad group’s or keyword’s bid strategy to *ManualCpc*.

> [!NOTE]
> The *Bid Strategy Type* field is not supported for Bing Shopping campaigns.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign that contains the keyword.

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

### <a name="destinationurl"></a>Destination Url
The URL of the webpage to take the user to when they click the ad. The keyword’s destination URL is used if specified; otherwise, the ad’s destination URL is used.

> [!IMPORTANT]
> If you are currently using Destination URLs, you must eventually replace them with Final URLs. For more information, see [URL Tracking with Upgraded URLs](../guides/url-tracking-upgraded-urls.md).

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.     
**Delete:** Read-only  

### <a name="editorialappealstatus"></a>Editorial Appeal Status
Determines whether you can appeal the issues found by the editorial review.

Possible values include *Appealable*, *AppealPending*, and *NotAppealable*. For more details, see [AppealStatus Value Set](../campaign-management-service/appealstatus.md).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the keyword that failed editorial review. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the keyword.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [KeywordEditorialStatus Value Set](../campaign-management-service/keywordeditorialstatus.md).

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
The landing page URL. The keyword’s final URL is used if specified; otherwise, the ad’s final URL is used.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url. 

Also note that  if the *Tracking Template* or *Custom Parameter* fields are set, then the *Final Url* field is required.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the keyword.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="inheritedbidstrategytype"></a>Inherited Bid Strategy Type
The bid strategy type that is inherited from the parent campaign or ad group if the keyword's *Bid Strategy Type* is set to *InheritFromParent*. This value is equal to the parent campaign or ad group's *Bid Strategy Type* field. Possible values are *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="keyword"></a>Keyword
The keyword text.

The text can contain a maximum of 100 characters.

You should specify the keyword in the locale of the Language value that you specified for the ad group to which the keyword belongs.

If the *Match Type* is Broad, your application should handle broad match modifiers. Broad match modified keywords can be modified or prefixed with a plus sign (+), to require that specific terms in your keyword be present in the search query. In the download file, broad match modified terms are preceded by an extra space character. For example if the keyword text is "+Hawaii +hotel", the text included in the bulk download file is " +Hawaii +hotel". For bulk upload you may specify the keyword with or without the preceding space. For more information about broad match modifiers, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).

**Add:** Required  
**Update:** Optional    
**Delete:** Read-only

### <a name="matchtype"></a>Match Type
The type of match to compare the keyword and the user's search term.

The supported match type values for a keyword are *Broad*, *Exact* and *Phrase*.

**Add:** Required  
**Update:** Read-only    
**Delete:** Read-only  

### <a name="mobilefinalurl"></a>Mobile Final Url
The mobile landing page URL. The keyword’s final mobile URL is used if specified; otherwise, the ad’s final mobile URL is used.

The following validation rules apply to Final URLs and Final Mobile URLs.

- The length of the URL is limited to 2,048 characters.

    **Note:** The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- You may specify up to 10 items for both Final URLs and Final Mobile URLs; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.

- Each URL is delimited by a semicolon and space ("; ").

- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".

- Each URL must be a well-formed URL starting with either http:// or https://.

- If you specify Final Mobile URLs, you must also specify Final Url. 

Also note that if the TrackingUrlTemplate or UrlCustomParameters element are set, then at least one final URL is required.

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

### <a name="param1"></a>Param1
The string to use as the substitution value in an ad if the ad’s title, text, display URL, or destination URL contains the {Param1} dynamic substitution string.

> [!NOTE]
> Although you can use {Param1} to specify an ad’s destination URL, you are encouraged not to. Instead, you should set the keyword's DestinationUrl element.

The string can contain a maximum of 1,022 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad’s title can contain a maximum of 25 characters.

When implementing dynamic text in your ad copy you should provide a default string e.g. {Param1:default} that the system will use if Param1 for a keyword is null or empty, or if including the Param1 substitution value will cause the expanded string to exceed the element’s limit; otherwise the ad will not serve with this keyword. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](https://help.bingads.microsoft.com/#apex/3/en/50811/1).

Also note that if the ad group only has one ad, and if that ad uses {Param1} but does not provide a default string e.g. {Param1:default}, then you must supply a valid Param1 value for that substitution. Otherwise this keyword cannot be added or updated.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="param2"></a>Param2
The string to use as the substitution value in an ad if the title, text, display URL, or destination URL contains the {Param2} dynamic substitution string.

Typically, you use the {Param2} substitution string in the title or text (ad copy description) elements of an ad.

The string can contain a maximum of 70 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad’s title can contain a maximum of 25 characters.

When implementing dynamic text in your ad copy you should provide a default string e.g. {Param2:default} that the system will use if Param2 for a keyword is null or empty, or if including the Param2 substitution value will cause the expanded string to exceed the element’s limit; otherwise the ad will not serve with this keyword. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](https://help.bingads.microsoft.com/#apex/3/en/50811/1).

Also note that if the ad group only has one ad, and if that ad uses {Param2} but does not provide a default string e.g. {Param2:default}, then you must supply a valid *Param2* value for that substitution. Otherwise this keyword cannot be added or updated. 

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="param3"></a>Param3
The string to use as the substitution value in an ad if the title, text, display URL, or destination URL contains the {Param3} dynamic substitution string.

Typically, you use the {Param3} substitution string in the title or text (ad copy description) elements of an ad.

The string can contain a maximum of 70 characters. The actual limit depends on the length of the element that references the substitution string. For example, the length of a text ad’s title can contain a maximum of 25 characters.

When implementing dynamic text in your ad copy you should provide a default string e.g. {Param3:default} that the system will use if Param3 for a keyword is null or empty, or if including the Param3 substitution value will cause the expanded string to exceed the element’s limit; otherwise the ad will not serve with this keyword. For more information, see the Bing Ads help article [Automatically customize your ads with dynamic text parameters](https://help.bingads.microsoft.com/#apex/3/en/50811/1).

Also note that if the ad group only has one ad, and if that ad uses {Param3} but does not provide a default string e.g. {Param3:default}, then you must supply a valid *Param3* value for that substitution. Otherwise this keyword cannot be added or updated. 

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the ad group that contains the keyword.

This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record.

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are adding new keywords to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
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
The status of the keyword.

Possible values are *Active*, *Paused*, *Inactive*, or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to *Deleted*.

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for the URL specified with FinalUrls.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete or remove an existing value, set this field to *delete_value*. The *delete_value* keyword removes the previous setting.    
**Delete:** Read-only  

## <a name="bidsuggestionsdata"></a>Bid Suggestions Data Fields in the Bulk File
If the requested download [DataScope Value Set](datascope.md) includes *BidSuggestionsData*, the download file can also contain the [Keyword Best Position Bid](keyword-best-position-bid.md), [Keyword Main Line Bid](keyword-main-line-bid.md), and [Keyword First Page Bid](keyword-first-page-bid.md) records corresponding to each downloaded keyword. 

## <a name="qualityscore"></a>Quality Score Fields in the Bulk File
If the [DataScope Value Set](datascope.md) element of the download request includes *QualityScore*, the download file will also include the following fields in this record.

|Column Header|Description|
|-----------------|---------------|
|*Quality Score*|The numeric score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. The quality score is calculated by Bing Ads using the *Keyword Relevance*, *Landing Page Relevance*, and *Landing Page User Experience* sub scores. If available, the quality score can range from a low of 1 to a high of 10.<br/><br/>Quality score is based on the last rolling 30 days for the owned and operated search traffic. A quality score can be assigned without any impressions, in the case where a keyword bid did not win any auctions. Traffic for syndicated networks do not affect quality score. The value in the report will be blank if the score was not computed. This can occur if there have been no impressions for the keyword for 30 days or more.<br/><br/>Quality score is typically updated 14-18 hours after the UTC day ends. Keywords in all time zones will be assigned a quality score for the corresponding UTC day.<br/><br/>If you run the report multiple times in a day, the quality score values could change from report to report based on when you run the report relative to when the scores are calculated.<br/><br/>If you specify a time period that spans multiple days, the quality score is the current and most recently calculated score and will be reported as the same for each day in the time period. Use the historic quality score to find out how quality score may have changed over time. Historical quality score is a daily snapshot of the rolling quality score. For more information on historic quality score, see the *HistoricQualityScore* column in [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).|
|*Keyword Relevance*|A numeric score that indicates how likely your ads will be clicked and how well your keyword competes against other keywords targeting the same traffic. This score predicts whether your keyword is likely to lead to a click on your ads, taking into account how well your keyword has performed in the past relative to your ad's position.<br/><br/>*Keyword Relevance* is equivalent to the **Expected Click-Through Rate** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
|*Landing Page Relevance*|A numeric score that indicates how relevant your ad and landing page are to the customer's search query or other input.<br/><br/>*Landing Page Relevance* is equivalent to the **Ad Relevance** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
|*Landing Page User Experience*|A numeric score that indicates whether your landing page is likely to provide a good experience to customers who click your ad and land on your website.<br/><br/>*Landing Page User Experience* is equivalent to the **Landing Page Experience** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
