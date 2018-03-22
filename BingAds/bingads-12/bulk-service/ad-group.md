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
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Ad Group Record - Bulk
Defines an ad group that can be uploaded and downloaded in a bulk file.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Ad Rotation](#adrotation)
- [Bid Adjustment](#bidadjustment)
- [Bid Strategy Type](#bidstrategytype)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Cpc Bid](#cpcbid)
- [Custom Parameter](#customparameter)
- [End Date](#enddate)
- [Id](#id)
- [Inherited Bid Strategy Type](#inheritedbidstrategytype)
- [Language](#language)
- [Modified Time](#modifiedtime)
- [Network Distribution](#networkdistribution)
- [Parent Id](#parentid)
- [Search Network](#searchnetwork)
- [Start Date](#startdate)
- [Status](#status)
- [Target Setting](#targetsetting)
- [Tracking Template](#trackingtemplate)

You can download all fields of the *Ad Group* record by including the [DownloadEntity](downloadentity.md) value of *AdGroups* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group if the correct campaign Id would be provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Start Date,End Date,Network Distribution,Ad Rotation,Cpc Bid,Language,Bid Adjustment,Name,Tracking Template,Custom Parameter,Bid Strategy Type,Target Setting
Format Version,,,,,,,,,,,,,,,6,,,,
Ad Group,Active,,-111,ParentCampaignNameGoesHere,Women's Red Shoe Sale,ClientIdGoesHere,,11/5/2017,12/31/2018,OwnedAndOperatedAndSyndicatedSearch,RotateAdsEvenly,0.1,English,10,,http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl},{_promoCode}=PROMO1; {_season}=summer,ManualCpc,Audience
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroup* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

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
        // 'Bid Strategy Type' column header in the Bulk file
        BiddingScheme = new ManualCpcBiddingScheme { },
        // 'Cpc Bid' column header in the Bulk file
        CpcBid = new Bid
        {
            Amount = 0.10
        },
        // 'End Date' column header in the Bulk file
        EndDate = new Microsoft.BingAds.V12.CampaignManagement.Date
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
        // 'Bid Adjustment' column header in the Bulk file
        NativeBidAdjustment = 10,
        // 'Network Distribution' column header in the Bulk file
        Network = Network.OwnedAndOperatedAndSyndicatedSearch,
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
                        TargetAll = true
                    }
                }
            }
        },
        // 'Start Date' column header in the Bulk file
        StartDate = new Microsoft.BingAds.V12.CampaignManagement.Date
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

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="adgroup"></a>Ad Group
The name of the ad group.

The name must be unique among all active ad groups within the campaign. The name can contain a maximum of 256 characters.

**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="adrotation"></a>Ad Rotation
Determines how often you'd like the ads in your ad group to show in relation to one another. If you have multiple ads within an ad group, your ads will rotate because no more than one ad from your account can show at a time.

> [!NOTE]
> This feature is not supported for ad groups in Bing Shopping campaigns.

Possible values are *OptimizeForClicks* and *RotateAdsEvenly*.

If set to *OptimizeForClicks*, Bing Ads will predominantly show ads that have the highest click-through rate (CTR).

If set to *RotateAdsEvenly*, Bing Ads will rotate between your ads on an equal basis. That is, each ad in a particular ad group has an equal chance of being displayed in response to a searcher's query. Sometimes the ads that get the highest CTR are not the ads that get the highest conversions. Using *RotateAdsEvenly*, you can help ensure that ads with a higher CTR don't unintentionally get precedence over ads with a higher conversion rate. Also if you want to test new ad copy, using *RotateAdsEvenly* can help ensure that those new ads get an opportunity to be displayed, even if you have other ads within the same ad group that have an established and higher CTR performance history.

**Add:** Optional. The default value is *OptimizeForClicks*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="bidadjustment"></a>Bid Adjustment
The percent amount by which to adjust your bid for native ads above or below the base ad group or keyword bid.

> [!NOTE]
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.

Supported values are negative one hundred (-100) through positive nine hundred (900). Setting the bid adjustment to -100 percent will prevent native ads from showing for this ad group.

Set this field to zero (0) if you do not want any bid adjustment for native ads. If this field is empty you will inherit the *Bid Adjustment* setting of the ad group's [Campaign](campaign.md).

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If the ad group already has a native bid adjustment, and you want to remove it to effectively inherit the *Bid Adjustment* setting of the ad group's [Campaign](campaign.md), set this field to *delete_value*. The *delete_value* keyword removes the previous setting.   
**Delete:** Read-only  

### <a name="bidstrategytype"></a>Bid Strategy Type
The bid strategy type for how you want to manage your bids. For ad groups you can use either of the *InheritFromParent* or *ManualCpc* bid strategy types. 

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
> For campaigns of type *Shopping* the product partitions inherit the ad group *Bid Strategy Type*, and you must be in the Bing Shopping Enhanced CPC pilot. The pilot ID is 340.

**Add:** Optional. If you do not set this field, then *InheritFromParent* is used by default.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Campaign* field.

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="cpcbid"></a>Cpc Bid
The default bid to use when the user’s query and the ad group’s keywords match by using either a broad, exact, or phrase match comparison.

The minimum and maximum bid range depends on the account's currency. For more information, see [Currencies](../guides/currencies.md).

You can set a search bid if the *Search Network* ad distribution channel is set to *On*.

Specifying a broad, exact, or phrase match bid at the keyword level overrides the ad group’s search bid value for the corresponding match type.

**Add:** Optional. If you do not set a bid, it will be set to the minimum depending on your account's currency.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

-   Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

-   You may include up to 3 custom parameter key and value pairs. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

-   A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

-   The Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}.

    > [!NOTE]
    > With the Bulk service the surrounding braces and underscore are required. The maximum length of 16 UTF-8 bytes does not include the braces and underscore: '{', '_', and '}'. With the Campaign Management service the maximum length is 16 UTF-bytes, and you may not specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

### <a name="enddate"></a>End Date
The date that the ads in the ad group will expire.

If you do not specify an end date, the ads will not expire. The end date can be extended to make an ad group's ads eligible for delivery, even after the ad group expires.

The end date is inclusive. For example, if you set *End Date* to 12/31/2020, the ads in the ad group will expire at 11:59 PM on 12/31/2020. The time is based on the time zone that you specify at the campaign level.

**Add:** Optional. To set no end date when adding an ad group, do not set this field.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To delete the existing end date setting, and effectively set no end date when updating an ad group, set this field to a date equal to or later than January 2, 2050. When you retrieve the ad group next time, this field will be empty i.e. it will not be set to January 2, 2050.    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the ad group.

**Add:** Optional. You must either leave this field empty, or specify a negative identifier. A negative identifier set for the ad group can then be referenced in the *Parent Id* field of dependent record types such as ads, keywords, or criterion. This is recommended if you are adding new ad groups and new dependent records in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="inheritedbidstrategytype"></a>Inherited Bid Strategy Type
The bid strategy type that is inherited from the parent campaign if the ad group's *Bid Strategy Type* is set to *InheritFromParent*. This value is equal to the parent campaign's *Bid Strategy Type* field. Possible values are *EnhancedCpc*, *ManualCpc*, *MaxClicks*, *MaxConversions*, and *TargetCpa*.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="language"></a>Language
Your ad language setting determines the language you will use when you write your ads and should be the language of your customers.  

For possible values, see the Language column of [Ad Languages](../guides/ad-languages.md#adlanguage).

> [!IMPORTANT]
> Support for multiple languages at the campaign level is in pilot. If languages are set at both the ad group and campaign level, the ad group-level language will override the campaign-level language. The customer is enabled for the pilot if the [GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) response includes pilot number *310*. Pilot participants will be able to set multiple languages at the campaign level, and will be able to delete the ad group level language by setting this field to *delete_value*. The *delete_value* keyword removes the previous setting. If you leave this field nil, then the ad group language will not be updated. If your application depends on ad group language being set, then you must prepare for the possibility that ad group language will be nil. 

**Add:** Optional if the campaign has one or more languages set, and otherwise language is required.  
**Update:** Optional if the customer is in the *Campaign Languages* pilot, and otherwise update is not allowed. If you are not in the pilot and try to change the language during update, no error will be returned and the setting will not be changed.  
**Delete:** Read-only  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="networkdistribution"></a>Network Distribution
The search networks where you want your ads to display.

Possible values are *OwnedAndOperatedAndSyndicatedSearch*, *OwnedAndOperatedOnly*, and *SyndicatedSearchOnly*. The default is *OwnedAndOperatedAndSyndicatedSearch*. For more information about networks and ad distribution, see the [About Ad Distribution](http://help.bingads.microsoft.com/#apex/3/en/50871/0) help article.

If you select one of the syndicated search options, you can call the [SetNegativeSitesToAdGroups](../campaign-management-service/setnegativesitestoadgroups.md) or [SetNegativeSitesToCampaigns](../campaign-management-service/setnegativesitestocampaigns.md) operation to prevent the ads from displaying on specific syndicated search websites.

**Add:** Optional. The default is *OwnedAndOperatedAndSyndicatedSearch*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the campaign that contains the ad group.

This bulk field maps to the *Id* field of the [Camnpaign](campaign.md) record.

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are adding new ad groups to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Campaign* field.
  
### <a name="targetsetting"></a>Target Setting
The target settings that are applicable for criterion types e.g., audiences that are associated with this ad group. 

Include the criterion type group name in this field if you want the "target and bid" option. In this case we will only deliver ads to people who meet at least one of your criteria, while letting you make bid adjustments for specific criteria. 

Exclude the criterion type group name from this field if you want the "bid only" option. In this case we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific criteria.

If the [Campaign Type](campaign.md#campaigntype) is set to Audience, the supported values for this field are Age, Audience, CompanyName, Gender, Industry, and JobFunction. Otherwise the only value currently supported for other campaign types e.g., Search is Audience. New values may be supported in the future so you should not depend on a fixed set of values. Having said that, any possible values for this field should also be defined in the [CriterionTypeGroup](../campaign-management-service/criteriontypegroup.md) value set of the Campaign Management API. 

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

Each criterion type group name is delimited in the Bulk file by a semicolon (";"), for example *Age;Audience;CompanyName;Gender;Industry;JobFunction*.

An entity such as a remarketing list can be associated with multiple ad groups, and each ad group's target settings (e.g., the Audience criterion group name for remarketing lists) are applied independently for delivery. For example the same remarketing list can be associated with Ad Group A and Ad Group B. The Target Setting field for each ad group are set independently, and therefore the same remarketing list might be associated via the "target and bid" option for Ad Group A while associated via the "bid only" option for Ad Group B. 

**Add:** Optional. If the criterion type group name is excluded from this field, then the default setting is effectively "bid only".  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all criterion type group names, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of criterion type group names, specify the criterion type group names that you want to keep and omit any that you do not want to keep. The new set of criterion type group names will replace any previous criterion groups that were set for the ad group.    
**Delete:** Read-only  

### <a name="startdate"></a>Start Date
The date that the ads in the ad group can begin serving; otherwise, the service can begin serving the ads in the ad group the day that the ad group becomes active.

The start date cannot be updated after the ad group is submitted.

The start date is inclusive. For example, if you set *Start Date* to 11/5/2017, the ads in the ad group will start at 12:00 AM on 11/5/2017. The time is based on the time zone that you specify at the campaign level.

**Add:** Optional. If you do not set the start date, then it will default to today's date and the service can begin serving the ads in the ad group as soon as the ad group status is active.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

### <a name="status"></a>Status
The status of the ad group.

Possible values are *Active*, *Deleted*, *Expired*, and *Paused*. The *Expired* status is read-only.

**Add:** Optional. The default value is *Paused*.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to Deleted.

### <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for all URLs in your ad group.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="qualityscore"></a>Quality Score Fields in the Bulk File
If the [DataScope Value Set](datascope.md) element of the download request includes *QualityScore*, the download file will also include the following fields in this record.

|Column Header|Description|
|-----------------|---------------|
|*Quality Score*|The numeric score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. The quality score is calculated by Bing Ads using the *Keyword Relevance*, *Landing Page Relevance*, and *Landing Page User Experience* sub scores. If available, the quality score can range from a low of 1 to a high of 10.<br/><br/>Quality score is based on the last rolling 30 days for the owned and operated search traffic. A quality score can be assigned without any impressions, in the case where a keyword bid did not win any auctions. Traffic for syndicated networks do not affect quality score. The value in the report will be blank if the score was not computed. This can occur if there have been no impressions for the keyword for 30 days or more.<br/><br/>Quality score is typically updated 14-18 hours after the UTC day ends. Keywords in all time zones will be assigned a quality score for the corresponding UTC day.<br/><br/>If you run the report multiple times in a day, the quality score values could change from report to report based on when you run the report relative to when the scores are calculated.<br/><br/>If you specify a time period that spans multiple days, the quality score is the current and most recently calculated score and will be reported as the same for each day in the time period. Use the historic quality score to find out how quality score may have changed over time. Historical quality score is a daily snapshot of the rolling quality score. For more information on historic quality score, see the *HistoricQualityScore* column in [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).|
|*Keyword Relevance*|A numeric score that indicates how likely your ads will be clicked and how well your keyword competes against other keywords targeting the same traffic. This score predicts whether your keyword is likely to lead to a click on your ads, taking into account how well your keyword has performed in the past relative to your ad's position.<br/><br/>*Keyword Relevance* is equivalent to the **Expected Click-Through Rate** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
|*Landing Page Relevance*|A numeric score that indicates how relevant your ad and landing page are to the customer's search query or other input.<br/><br/>*Landing Page Relevance* is equivalent to the **Ad Relevance** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
|*Landing Page User Experience*|A numeric score that indicates whether your landing page is likely to provide a good experience to customers who click your ad and land on your website.<br/><br/>*Landing Page User Experience* is equivalent to the **Landing Page Experience** label used in the Bing Ads web application.<br/><br/>A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.<br/><br/>If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.<br/><br/>Data for this column is typically updated 14-18 hours after the UTC day ends.|
