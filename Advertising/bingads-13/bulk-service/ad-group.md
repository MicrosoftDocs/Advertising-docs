---
title: "Ad Group Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group Record - Bulk
Defines an ad group that can be uploaded and downloaded in a bulk file.

You can download all *Ad Group* records in the account by including the [DownloadEntity](downloadentity.md) value of *AdGroups* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. To include the [Keyword Relevance](#keywordrelevance), [Landing Page Relevance](#landingpagerelevance), [Landing Page User Experience](#landingpageuserexperience), and [Quality Score](#qualityscore) fields within the downloaded *Campaign* records, you must also include the [QualityScoreData](datascope.md#qualityscoredata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group if the correct campaign Id would be provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Start Date,End Date,Network Distribution,Ad Rotation,Cpc Bid,Language,Bid Adjustment,Name,Tracking Template,Final Url Suffix,Custom Parameter,Bid Strategy Type,Target Setting
Format Version,,,,,,,,,,,,,,,6.0,,,,,
Ad Group,Active,,-111,ParentCampaignNameGoesHere,Women's Red Shoe Sale,ClientIdGoesHere,,11/12/2018,12/31/2019,OwnedAndOperatedAndSyndicatedSearch,RotateAdsEvenly,0.1,English,10,,http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl},,{_promoCode}=PROMO1; {_season}=summer,ManualCpc,Audience
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkAdGroup* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroup
var bulkAdGroup = new BulkAdGroup
{
    // 'Campaign' column header in the Bulk file
    CampaignName = "ParentCampaignNameGoesHere",
    // 'Parent Id' column header in the Bulk file
    CampaignId = campaignIdKey,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
                  
    // Map properties in the Bulk file to the 
    // AdGroup object of the Campaign Management service.
    AdGroup = new AdGroup
    {
        // 'Ad Rotation' column header in the Bulk file
        AdRotation = new AdRotation
        {
            Type = AdRotationType.RotateAdsEvenly
        },
        // 'Bid Adjustment' column header in the Bulk file
        AudienceAdsBidAdjustment = 10,
        // 'Bid Strategy Type' column header in the Bulk file
        BiddingScheme = new ManualCpcBiddingScheme { },
        // 'Cpc Bid' column header in the Bulk file
        CpcBid = new Bid
        {
            Amount = 0.10
        },
        // 'End Date' column header in the Bulk file
        EndDate = new Microsoft.BingAds.V13.CampaignManagement.Date
        {
            Month = 12,
            Day = 31,
            Year = DateTime.UtcNow.Year + 1
        },
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Language' column header in the Bulk file
        Language = "English",
        // 'Ad Group' column header in the Bulk file
        Name = "Women's Red Shoe Sale",
        // 'Network Distribution' column header in the Bulk file
        Network = Network.OwnedAndOperatedAndSyndicatedSearch,
        // 'Privacy Status' column header in the Bulk file
        PrivacyStatus = null,
        // 'Target Setting' column header in the Bulk file
        Settings = new []
        {
            new TargetSetting
            {
                // Each target setting detail is delimited by a semicolon (;) in the Bulk file
                Details = new []
                {
                    new TargetSettingDetail
                    {
                        CriterionTypeGroup = CriterionTypeGroup.Audience,
                        TargetAndBid = true
                    }
                }
            }
        },
        // 'Start Date' column header in the Bulk file
        StartDate = new Microsoft.BingAds.V13.CampaignManagement.Date
        {
            Month = DateTime.UtcNow.Month,
            Day = DateTime.UtcNow.Day,
            Year = DateTime.UtcNow.Year
        },
        // 'Status' column header in the Bulk file
        Status = AdGroupStatus.Paused,
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

uploadEntities.Add(bulkAdGroup);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkServiceManager.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

For an *Ad Group* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Ad Rotation](#adrotation)
- [Bid Adjustment](#bidadjustment)
- [Bid Boost Value](#bidboostvalue)
- [Bid Option](#bidoption)
- [Bid Strategy Type](#bidstrategytype)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Cpc Bid](#cpcbid)
- [Custom Parameter](#customparameter)
- [End Date](#enddate)
- [Final Url Suffix](#finalurlsuffix)
- [Id](#id)
- [Inherited Bid Strategy Type](#inheritedbidstrategytype)
- [Keyword Relevance](#keywordrelevance)
- [Landing Page Relevance](#landingpagerelevance)
- [Landing Page User Experience](#landingpageuserexperience)
- [Language](#language)
- [Maximum Bid](#maximumbid)
- [Modified Time](#modifiedtime)
- [Network Distribution](#networkdistribution)
- [Parent Id](#parentid)
- [Privacy Status](#privacystatus)
- [Quality Score](#qualityscore)
- [Start Date](#startdate)
- [Status](#status)
- [Target Setting](#targetsetting)
- [Tracking Template](#trackingtemplate)

## <a name="adgroup"></a>Ad Group
The name of the ad group.

The name must be unique among all active ad groups within the campaign. The name can contain a maximum of 256 characters.

**Add:** Required  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="adrotation"></a>Ad Rotation
Ad rotation sets how often Microsoft Advertising selects which ads to serve, if you have multiple ads within an ad group. Since no more than one ad from your account can show at a time, ad rotation prioritizes ads that appear statistically more likely to perform better.

> [!NOTE]
> Ad rotation does not apply to Product Ads.

Possible values are *OptimizeForClicks* and *RotateAdsEvenly*.

If set to *OptimizeForClicks*, Microsoft Advertising prioritizes the ad from the ad group that appears to have the best chance of performing well, based on auction characteristics or factors, such as keyword, search term, device or location. Better-performing ads will show more frequently, and others will be served less often, if at all.

If set to *RotateAdsEvenly*, Microsoft Advertising provides more balance in rotation between your ads. That is, the ads in a particular ad group have a similar chance of being displayed in response to a searcher's query. Ads are prioritized lower if they have lower ad quality, and therefore might display less often, or not at all.
- The *RotateAdsEvenly* setting can allow lower-performing ads to display as often as better-performing ads. This might impact ad group performance.
- The *RotateAdsEvenly* setting will be ignored if you use an automated bid strategy i.e., *MaxClicks*, *MaxConversions*, or *TargetCpa*, as these bid strategies prioritize better-performing ads.

**Add:** Optional. The default value is *OptimizeForClicks*.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="bidadjustment"></a>Bid Adjustment
The percent amount by which to adjust your bid for audience ads above or below the base ad group or keyword bid.

> [!NOTE]
> This property is available in Search campaigns if the customer is enabled for the Microsoft Audience Network.

Supported values are negative one hundred (-100) through positive nine hundred (900). Setting the bid adjustment to -100 percent will prevent audience ads from showing for this ad group.

Set this field to zero (0) if you do not want any bid adjustment for audience ads. If this field is empty you will inherit the *Bid Adjustment* setting of the ad group's [Campaign](campaign.md).

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If the ad group already has an audience ads bid adjustment, and you want to remove it to effectively inherit the *Bid Adjustment* setting of the ad group's [Campaign](campaign.md), set this field to *delete_value*. The *delete_value* keyword removes the previous setting.   
**Delete:** Read-only  

## <a name="bidboostvalue"></a>Bid Boost Value
The percentage (greater than zero) that allows your cooperative bid to flex.

For example, let's say your partner bids $5 USD on a keyword. If your bid boost set to 20 percent and your maximum value is 50 cents, your share would be 50 cents and not $1 USD.

> [!NOTE]
> This setting is only applicable for ad groups in Microsoft Shopping Campaigns that are setup for Cooperative bidding. Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon.

**Add:** Required if the [Bid Option](#bidoption) is set to BidBoost, and otherwise you may not set this field.  
**Update:** Optional if the [Bid Option](#bidoption) is set to BidBoost, and otherwise you may not set this field.       
**Delete:** Read-only  

## <a name="bidoption"></a>Bid Option
Determines whether or not to amplify your partner's bid.

Supported values are BidBoost and BidValue. A bid value ad group allows you to bid on products that your merchandising partner doesn't target. A bid boost allows you to amplify your partner's bid via the [Bid Boost Value](#bidboostvalue) and [Maximum Bid](#maximumbid) fields.

> [!NOTE]
> This setting is only applicable for ad groups in Microsoft Shopping Campaigns that are setup for Cooperative bidding. Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon.

**Add:** Optional. If this field is not set, the default Cooperative bidding option for the ad group is "bid value" i.e., the auction will use the fixed bid that you set for each [Ad Group Product Partition](ad-group-product-partition.md).  
**Update:** Read-only. If you attempt to change the previous bid option an error will be returned.     
**Delete:** Read-only  

## <a name="bidstrategytype"></a>Bid Strategy Type
The bid strategy type for how you want to manage your bids. For ad groups you can use either of the *InheritFromParent* or *ManualCpc* bid strategy types. For details about supported bid strategies per campaign type, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).

> [!IMPORTANT] 
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group's or keyword's bid strategy to *ManualCpc*. For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).  
> - You can continue to set the ad group and keyword bids; however they will not be used by Microsoft Advertising.
> - Microsoft Advertising will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Microsoft Advertising may change them at any time using this bid strategy type.
> - You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Microsoft Advertising about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
> - Even if the [Ad Rotation](#adrotation) is set to *RotateAdsEvenly*, it will be ignored as these bid strategies prioritize better-performing ads.

> [!TIP] 
> You can set your campaign's bid strategy to *EnhancedCpc*, *MaxClicks*, *MaxConversions*, or *TargetCpa* and then, at any time, set an individual ad group's or keyword's bid strategy to *ManualCpc*. 

> [!NOTE]
> For campaigns of type *Shopping* the product partitions inherit the ad group [Bid Strategy Type](#bidstrategytype).

**Add:** Optional. If you do not set this field, then *InheritFromParent* is used by default.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Campaign](#campaign) field.

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="cpcbid"></a>Cpc Bid
The default bid to use when the user’s query and the ad group’s keywords match by using either a broad, exact, or phrase match comparison.

The minimum and maximum bid range depends on the account's currency. For more information, see [Currencies](../guides/currencies.md).

Specifying a broad, exact, or phrase match bid at the keyword level overrides the ad group’s search bid value for the corresponding match type.

**Add:** Optional. If you do not set a bid, it will be set to the minimum depending on your account's currency.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

- Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

- Microsoft Advertising will accept the first 3 custom parameter key and value pairs that you include, and any additional custom parameters will be ignored. For customers in the Custom Parameters Limit Increase Phase 1 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 532), Microsoft Advertising will accept the first 8 custom parameter key and value pairs that you include, and if you include more than 8 custom parameters an error will be returned. During calendar year 2019 the limit will be increased from 3 to 8 for all customers. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

- A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

- The Key cannot exceed 16 UTF-8 bytes, and the Value cannot exceed 200 UTF-8 bytes. The Key is required and the Value is optional. The maximum size of the Key does not include the braces and underscore i.e., '{', '_', and '}'. 

    > [!NOTE] 
    > With the Bulk service the Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}. With the Campaign Management service you cannot specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

## <a name="enddate"></a>End Date
The date that the ads in the ad group will expire.

If you do not specify an end date, the ads will not expire. The end date can be extended to make an ad group's ads eligible for delivery, even after the ad group expires.

The end date is inclusive. For example, if you set *End Date* to 12/31/2020, the ads in the ad group will expire at 11:59 PM on 12/31/2020. The time is based on the time zone that you specify at the campaign level.

**Add:** Optional. To set no end date when adding an ad group, do not set this field.  
**Update:** Optional. If no value is set for the update, this setting is not changed. To delete the current end date and effectively set no end date, set this field to the "delete_value" string. When you retrieve the ad group next time, this field will not be set.    
**Delete:** Read-only  

## <a name="finalurlsuffix"></a>Final Url Suffix
The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides. 

> [!NOTE]
> This feature is only available for customers in the Final URL Suffix Phase 1 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 533). If you are not in the pilot and attempt to set this property an error will be returned. During calendar year 2019 this feature will be enabled for all customers.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.  
**Delete:** Read-only  

## <a name="id"></a>Id
The system generated identifier of the ad group.

**Add:** Optional. You must either leave this field empty, or specify a negative identifier. A negative identifier set for the ad group can then be referenced in the *Parent Id* field of dependent record types such as ads, keywords, or criterion. This is recommended if you are adding new ad groups and new dependent records in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

## <a name="inheritedbidstrategytype"></a>Inherited Bid Strategy Type
The bid strategy type that is inherited from the parent campaign if the ad group's [Bid Strategy Type](#bidstrategytype) is set to *InheritFromParent*. This value is equal to the parent campaign's [Bid Strategy Type](#bidstrategytype) field. Possible values are *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="keywordrelevance"></a>Keyword Relevance
A numeric score that indicates how likely your ads will be clicked and how well your keyword competes against other keywords targeting the same traffic. This score predicts whether your keyword is likely to lead to a click on your ads, taking into account how well your keyword has performed in the past relative to your ad's position.

> [!NOTE]
> Keyword Relevance is equivalent to the **Expected Click-Through Rate** label used in the Microsoft Advertising web application.

A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.

If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.

Data for this column is typically updated 14-18 hours after the UTC day ends.

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="landingpagerelevance"></a>Landing Page Relevance
A numeric score that indicates how relevant your ad and landing page are to the customer's search query or other input.

> [!NOTE]
> Landing Page Relevance is equivalent to the **Ad Relevance** label used in the Microsoft Advertising web application.

A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.

If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.

Data for this column is typically updated 14-18 hours after the UTC day ends.

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="landingpageuserexperience"></a>Landing Page User Experience
A numeric score that indicates whether your landing page is likely to provide a good experience to customers who click your ad and land on your website.

> [!NOTE]
> Landing Page User Experience is equivalent to the **Landing Page Experience** label used in the Microsoft Advertising web application.

A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.

If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.

Data for this column is typically updated 14-18 hours after the UTC day ends.

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="language"></a>Language
Your ad language setting determines the language you will use when you write your ads and should be the language of your customers.  

> [!IMPORTANT]
> If languages are set at both the ad group and campaign level, the ad group level language will override the campaign level language. 

The supported language strings for Search and Shopping campaigns are: Danish, Dutch, English, Finnish, French, German, Italian, Norwegian, Portuguese, Spanish, Swedish, and TraditionalChinese.

For Dynamic Search Ads campaigns, the campaign and ad group level language settings are ignored in favor of the website [domain language](campaign.md#domainlanguage). You should set campaign [languages](campaign.md#language) to "All" and leave the ad group level language empty.

For ad groups in Audience campaigns, ad group level language is not supported, and you must set the [Language](campaign.md#language) field of the ad group's campaign to "All".

**Add:** Optional if the campaign has one or more languages set, and otherwise the language is required for most campaign types. You are not allowed to set this element for ad groups in Audience campaigns.  
**Update:** Optional. If no value is set for the update, this setting is not changed. To remove the language and defer to the campaign level languages, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. The ad group language cannot be removed until campaign language updates have been processed, which could take up to 12 hours after the campaign languages have been set for the first time.   
**Delete:** Read-only  

## <a name="maximumbid"></a>Maximum Bid
The flat amount of your cooperative bid.

> [!NOTE]
> This setting is only applicable for ad groups in Microsoft Shopping Campaigns that are setup for Cooperative bidding. Not everyone is enabled for Cooperative bidding yet. If you don't, don't worry. It's coming soon.

**Add:** Required if the [Bid Option](#bidoption) is set to BidBoost, and otherwise you may not set this field.  
**Update:** Optional if the [Bid Option](#bidoption) is set to BidBoost, and otherwise you may not set this field.       
**Delete:** Read-only  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="networkdistribution"></a>Network Distribution
The search networks where you want your ads to display.

Possible values are *OwnedAndOperatedAndSyndicatedSearch*, *OwnedAndOperatedOnly*, and *SyndicatedSearchOnly*. The default is *OwnedAndOperatedAndSyndicatedSearch*. For more information about networks and ad distribution, see the [About Ad Distribution](https://help.ads.microsoft.com/#apex/3/en/50871/0) help article.

For ad groups in Audience campaigns, ad group level network is not supported and this field will be empty. The ad groups are in the Microsoft Audience Network.

If you select one of the syndicated search options, you can call the [SetNegativeSitesToAdGroups](../campaign-management-service/setnegativesitestoadgroups.md) or [SetNegativeSitesToCampaigns](../campaign-management-service/setnegativesitestocampaigns.md) operation to prevent the ads from displaying on specific syndicated search websites.

**Add:** Optional. The default is *OwnedAndOperatedAndSyndicatedSearch*.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The system generated identifier of the campaign that contains the ad group.

This bulk field maps to the *Id* field of the [Camnpaign](campaign.md) record.

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are adding new ad groups to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Campaign](#campaign) field.

## <a name="privacystatus"></a>Privacy Status
Indicates whether or not your ad group target criteria are too narrow for ad groups in Audience campaigns.

|Status|Description|
|-----|-----|
|<a name="active"></a>Active|The ad group is eligible to serve.|
|<a name="pending"></a>Pending|The privacy evaluation is still in progress, and the ad group is not yet eligible to serve.|
|<a name="targetingtoonarrow"></a>TargetingTooNarrow|The ad group is not eligible to serve because your ad group target criteria e.g., [Ad Group Company Name Criterion](ad-group-company-name-criterion.md) are too narrowly defined. Update your target criteria or remarketing lists to broaden your audience and increase estimated unique users.|

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="qualityscore"></a>Quality Score
The numeric score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. The quality score is calculated by Microsoft Advertising using the *Keyword Relevance*, *Landing Page Relevance*, and *Landing Page User Experience* sub scores. If available, the quality score can range from a low of 1 to a high of 10.

Quality score is based on the last rolling 30 days for the owned and operated search traffic. A quality score can be assigned without any impressions, in the case where a keyword bid did not win any auctions. Traffic for syndicated networks do not affect quality score. The value in the file will be "" (empty string) if the score was not computed. This can occur if there have been no impressions for the keyword for 30 days or more.<br/><br/>Quality score is typically updated 14-18 hours after the UTC day ends. Keywords in all time zones will be assigned a quality score for the corresponding UTC day.

If you run the report multiple times in a day, the quality score values could change from report to report based on when you run the report relative to when the scores are calculated.

If you specify a time period that spans multiple days, the quality score is the current and most recently calculated score and will be reported as the same for each day in the time period. Use the historic quality score to find out how quality score may have changed over time. Historical quality score is a daily snapshot of the rolling quality score. For more information on historic quality score, see the *HistoricalQualityScore* column in [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="startdate"></a>Start Date
The date that the ads in the ad group can begin serving; otherwise, the service can begin serving the ads in the ad group the day that the ad group becomes active.

The start date is inclusive. For example, if you set *Start Date* to 5/5/2019, the ads in the ad group will start at 12:00 AM on 5/5/2019. The time is based on the time zone that you specify at the campaign level.

**Add:** Optional. If you do not set the start date, then it will default to today's date and the service can begin serving the ads in the ad group as soon as the ad group status is active.  
**Update:** Optional. If no value is set for the update, this setting is not changed. The start date cannot be updated after the ad group is submitted i.e., once the start date has arrived.  
**Delete:** Read-only  

## <a name="status"></a>Status
The status of the ad group.

Possible values are *Active*, *Deleted*, *Expired*, and *Paused*. The *Expired* status is read-only.

**Add:** Optional. The default value is *Paused*.  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Required. The Status must be set to Deleted.

## <a name="targetsetting"></a>Target Setting
The target settings that are applicable for criterion types e.g., audiences that are associated with this ad group. 

Include the criterion type group name in this field if you want the "target and bid" option. In this case we will only deliver ads to people who meet at least one of your criteria, while letting you make bid adjustments for specific criteria. 

Exclude the criterion type group name from this field if you want the "bid only" option. In this case we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific criteria.

Each criterion type group name is delimited in the Bulk file by a semicolon (";"), for example *Age;Audience;CompanyName;Gender;Industry;JobFunction*. When you download the Bulk file, only the types that are setup to use the "target and bid" option will be included in this field.

If the [Campaign Type](campaign.md#campaigntype) is set to Audience, the supported values for this field are Age, Audience, CompanyName, Gender, Industry, and JobFunction. Otherwise the only value currently supported for other campaign types e.g., Search campaigns is "Audience". In other words, the "target and bid" option for the Audience criterion type is supported with all campaign types, whereas the "target and bid" option for Age, CompanyName, Gender, Industry, and JobFunction criterion groups is only supported with the Audience campaign type. New values may be supported in the future so you should not depend on a fixed set of values. Having said that, any possible values for this field should also be defined in the [CriterionTypeGroup](../campaign-management-service/criteriontypegroup.md) value set of the Campaign Management API. 

> [!NOTE]
> Do not confuse the Audience campaign type with the Audience criterion type group name. 

|Criterion Type Group|Supported Campaigns|Description|
|-----------------|---------------|---------------|
|Age|Audience|If you include the Age criterion type group name in this field, we will only deliver ads to people who meet at least one of your age criteria, while letting you make bid adjustments for specific age ranges. This setting ensures that the people seeing your ads meet your age criteria.<br/><br/>If you exclude the Age criterion type group name from this field, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific age ranges. This setting lets you bid more (or less) aggressively for the people who meet specific age criteria, without restricting your ads to those people.|
|Audience|All|Include the Audience criterion type group name in this field if you want to show ads only to people included in the audience, with the option to change the bid amount. Ads in this ad group will only show to people included in the audience.<br/><br/>Exclude the Audience criterion type group name from this field if you want to show ads to people searching for your ad, with the option to change the bid amount for people included in the audience. Ads in this ad group can show to everyone but the bid adjustment will apply to people included in the audience.|
|CompanyName|Audience|If you include the CompanyName criterion type group name in this field, we will only deliver ads to people who meet at least one of your company criteria, while letting you make bid adjustments for specific companies. This setting ensures that the people seeing your ads meet your company criteria.<br/><br/>If you exclude the CompanyName criterion type group name from this field, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific companies. This setting lets you bid more (or less) aggressively for the people who meet specific company criteria, without restricting your ads to those people.|
|Gender|Audience|If you include the Gender criterion type group name in this field, we will only deliver ads to people who meet your gender criteria, while letting you make bid adjustments for a specific gender. This setting ensures that the people seeing your ads meet your gender criteria.<br/><br/>If you exclude the Gender criterion type group name from this field, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for a specific gender. This setting lets you bid more (or less) aggressively for the people who meet specific gender criteria, without restricting your ads to those people.|
|Industry|Audience|If you include the Industry criterion type group name in this field, we will only deliver ads to people who meet at least one of your industry criteria, while letting you make bid adjustments for specific industries. This setting ensures that the people seeing your ads meet your industry criteria.<br/><br/>If you exclude the Industry criterion type group name from this field, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific industries. This setting lets you bid more (or less) aggressively for the people who meet specific industry criteria, without restricting your ads to those people.|
|JobFunction|Audience|If you include the JobFunction criterion type group name in this field, we will only deliver ads to people who meet at least one of your job function criteria, while letting you make bid adjustments for specific job functions. This setting ensures that the people seeing your ads meet your job function criteria.<br/><br/>If you exclude the JobFunction criterion type group name from this field, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific job functions. This setting lets you bid more (or less) aggressively for the people who meet specific job function criteria, without restricting your ads to those people.|

An entity such as a remarketing list can be associated with multiple ad groups, and each ad group's target settings (e.g., the Audience criterion group name for remarketing lists) are applied independently for delivery. For example the same remarketing list can be associated with Ad Group A and Ad Group B. The Target Setting field for each ad group are set independently, and therefore the same remarketing list might be associated via the "target and bid" option for Ad Group A while associated via the "bid only" option for Ad Group B. 

**Add:** Optional. If the criterion type group name is excluded from this field, then the default setting is effectively "bid only".  
**Update:** Optional. If no value is set for the update, this setting is not changed. To remove all criterion type group names, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of criterion type group names, specify the criterion type group names that you want to keep and omit any that you do not want to keep. The new set of criterion type group names will replace any previous criterion groups that were set for the ad group.    
**Delete:** Read-only  

## <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for all URLs in your ad group.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Microsoft Advertising does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed. 
**Delete:** Read-only  
