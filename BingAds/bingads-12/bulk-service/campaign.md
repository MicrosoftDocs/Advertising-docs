---
title: "Campaign Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Record - Bulk
Defines a campaign that can be uploaded and downloaded in a bulk file. 

You can download all *Campaign* records in the account by including the [DownloadEntity](downloadentity.md) value of *Campaigns* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. To include the [Keyword Relevance](#keywordrelevance), [Landing Page Relevance](#landingpagerelevance), [Landing Page User Experience](#landingpageuserexperience), and [Quality Score](#qualityscore) fields within the downloaded *Campaign* records, you must also include the [QualityScoreData](datascope.md#qualityscoredata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add one campaign of each type i.e. Search, Shopping, and Dynamic Search Ads campaign. 

```csv
Type,Status,Id,Parent Id,Campaign,Website,Client Id,Modified Time,Time Zone,Budget Id,Budget Name,Budget,Budget Type,Bid Adjustment,Name,Country Code,Store Id,Campaign Type,Priority,Tracking Template,Custom Parameter,Bid Strategy Type,Domain Language,Source
Format Version,,,,,,,,,,,,,,6,,,,,,,,,
Campaign,Active,-111,0,Search 2/6/2017 4:11:11 PM,,ClientIdGoesHere,,PacificTimeUSCanadaTijuana,,,50,DailyBudgetStandard,10,,,,Search,,,{_promoCode}=PROMO1; {_season}=summer,EnhancedCpc,,
Campaign,Active,-111,0,Shopping 2/6/2017 4:11:11 PM,,ClientIdGoesHere,,PacificTimeUSCanadaTijuana,,,50,DailyBudgetStandard,10,,US,StoreIdHere,Shopping,0,,{_promoCode}=PROMO1; {_season}=summer,,,
Campaign,Active,-111,0,DynamicSearchAds 2/6/2017 4:11:11 PM,contoso.com,ClientIdGoesHere,,PacificTimeUSCanadaTijuana,,,50,DailyBudgetStandard,10,,,,DynamicSearchAds,,,{_promoCode}=PROMO1; {_season}=summer,EnhancedCpc,EN,SystemIndex
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkCampaign* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

for(int i = 0; i < 3; i++)
{
    // Map properties in the Bulk file to the BulkCampaign
    var bulkCampaign = new BulkCampaign
    {
        // 'Parent Id' column header in the Bulk file
        AccountId = 0,
        // 'Client Id' column header in the Bulk file
        ClientId = "ClientIdGoesHere",
        // 'Modified Time' column header in the Bulk file is read-only
        // LastModifiedTime cannot be set in the Bulk entity

        // Map properties in the Bulk file to the 
        // Campaign object of the Campaign Management service.
        Campaign = new Campaign
        {
            // 'Bid Strategy Type' column header in the Bulk file
            BiddingScheme = new EnhancedCpcBiddingScheme { },
            // 'Budget Id' column header in the Bulk file
            BudgetId = null,
            // 'Budget Type' column header in the Bulk file
            BudgetType = BudgetLimitType.DailyBudgetStandard,
            // 'Campaign Type' column header in the Bulk file
            CampaignType = null,
            // 'Budget' column header in the Bulk file
            DailyBudget = 50,
            // 'Description' column header in the Bulk file
            Description = "Red shoes line.",
            // 'Id' column header in the Bulk file
            Id = campaignIdKey,
            // 'Language' column header in the Bulk file
            Languages = null,
            // 'Campaign' column header in the Bulk file
            Name = "Women's Shoes " + DateTime.UtcNow,
            // 'Bid Adjustment' column header in the Bulk file
            AudienceAdsBidAdjustment = 10,
            // 'Settings are not applicable for the Search campaign type
            Settings = null,
            // 'Status' column header in the Bulk file
            Status = CampaignStatus.Active,
            // 'Sub Type' column header in the Bulk file
            SubType = null,
            // 'Time Zone' column header in the Bulk file
            TimeZone = "PacificTimeUSCanadaTijuana",
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

    uploadEntities.Add(bulkCampaign);
}

// Set properties specific to the Search campaign type
((BulkCampaign)uploadEntities[0]).Campaign.Name = "Search " + DateTime.UtcNow;
((BulkCampaign)uploadEntities[0]).Campaign.CampaignType = CampaignType.Search;

// Set properties specific to the Shopping campaign type
((BulkCampaign)uploadEntities[1]).Campaign.Name = "Shopping " + DateTime.UtcNow;
// 'Bid Strategy Type' column header in the Bulk file
((BulkCampaign)uploadEntities[1]).Campaign.CampaignType = CampaignType.Shopping;
((BulkCampaign)uploadEntities[1]).Campaign.Settings = new[] {
    new ShoppingSetting {
        // 'Priority' column header in the Bulk file
        Priority = 0,
        // 'Country Code' column header in the Bulk file
        SalesCountryCode = "US",
        // 'Store Id' column header in the Bulk file
        StoreId = StoreIdHere
    }
};
            
// Set properties specific to the DynamicSearchAds campaign type
((BulkCampaign)uploadEntities[2]).Campaign.Name = "DynamicSearchAds " + DateTime.UtcNow;
((BulkCampaign)uploadEntities[2]).Campaign.CampaignType = CampaignType.DynamicSearchAds;
((BulkCampaign)uploadEntities[2]).Campaign.Settings = new[] {
    new DynamicSearchAdsSetting {
        // 'Website' column header in the Bulk file
        DomainName = "contoso.com",
        // 'Domain Language' column header in the Bulk file
        Language = "EN",
        // 'Source' column header in the Bulk file
        Source = "SystemIndex"
    }
};

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

For a *Campaign* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

|Column Header|Supported Campaign Types|
|-----------------|---------------|
|[Bid Adjustment](#bidadjustment)|All|
|[Bid Strategy MaxCpc](#bidstrategymaxcpc)|Search<br>DynamicSearchAds|
|[Bid Strategy TargetCpa](#bidstrategytargetcpa)|Search<br>DynamicSearchAds|
|[Bid Strategy Type](#bidstrategytype)|All|
|[Budget](#budget)|All|
|[Budget Id](#budgetid)|All|
|[Budget Name](#budgetname)|All|
|[Budget Type](#budgettype)|All|
|[Campaign](#campaign)|All|
|[Campaign Type](#campaigntype)|All|
|[Client Id](#clientid)|All|
|[Country Code](#countrycode)|Shopping|
|[Domain Language](#domainlanguage)|DynamicSearchAds|
|[Experiment Id](#experimentid)|Search|
|[Id](#id)|All|
|[Keyword Relevance](#keywordrelevance)|All|
|[Landing Page Relevance](#landingpagerelevance)|All|
|[Landing Page User Experience](#landingpageuserexperience)|All|
|[Language](#language)|All|
|[LocalInventoryAdsEnabled](#language)|Shopping|
|[Modified Time](#modifiedtime)|All|
|[Parent Id](#parentid)|All|
|[Priority](#priority)|Shopping|
|[Quality Score](#qualityscore)|All|
|[Source](#source)|DynamicSearchAds|
|[Status](#status)|All|
|[Store Id](#storeid)|Audience<br>Shopping|
|[Sub Type](#subtype)|Shopping|
|[Time Zone](#timezone)|All|
|[Tracking Template](#trackingtemplate)|All|
|[Website](#website)|DynamicSearchAds|

## <a name="bidadjustment"></a>Bid Adjustment
The percent amount by which to adjust your bid for audience ads above or below the base ad group or keyword bid.

> [!NOTE]
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.

Supported values are negative one hundred (-100) through positive nine hundred (900). Setting the bid adjustment to -100 percent will prevent audience ads from showing for this campaign.

Set this field to zero (0) if you do not want any bid adjustment for audience ads.

**Add:** Optional. If you do not set this field the system default bid adjustment will be used. The system default bid adjustment is currently zero (0), and is subject to change.   
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. If you set this field to *delete_value* the system default bid adjustment will be used. The *delete_value* keyword removes the previous setting. The system default bid adjustment is currently zero (0), and is subject to change. If you do not specify any value this field will be ignored.    
**Delete:** Read-only  

## <a name="bidstrategymaxcpc"></a>Bid Strategy MaxCpc
The maximum cost per click that you want to spend with the corresponding bid strategy type. 

This field is only used if the [Bid Strategy Type](#bidstrategytype) field is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, and otherwise this field is ignored.

> [!NOTE]
> The *MaxClicks* bid strategy is available only to advertisers from the following countries: Australia, Canada, France, Germany, India, Italy, Netherlands, Spain, Sweden, Switzerland, United Kingdom, and United States.
> 
> The *MaxConversions* bid strategy is available only to advertisers from the following countries: Australia, Canada, France, Germany, United Kingdom, and United States.
> 
> The *TargetCpa* bid strategy is available only to advertisers from the following countries: Australia, Canada, France, Germany, United Kingdom, and United States.

For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="bidstrategytargetcpa"></a>Bid Strategy TargetCpa
The target cost per acquisition (CPA) that you want used by Bing Ads to maximize conversions. 

This field is only used if the [Bid Strategy Type](#bidstrategytype) field is set to *TargetCpa*, and otherwise this field is ignored.

> [!NOTE]
> The *TargetCpa* bid strategy is available only to advertisers from the following countries: Australia, Canada, France, Germany, United Kingdom, and United States.

For more details, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).

**Add:** Required if the [Bid Strategy Type](#bidstrategytype) field is set to *TargetCpa*, and otherwise this field is ignored.   
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="bidstrategytype"></a>Bid Strategy Type
The bid strategy type for how you want to manage your bids. For details about supported bid strategies per campaign type, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).

A bid strategy type set at the [Ad Group](ad-group.md) or [Keyword](keyword.md) level will take precedence over the campaign level bid strategy type. 

For campaigns you can use any of the following bid strategy types. 
*  *EnhancedCpc* - Use the enhanced CPC bid strategy type to set your ad group and keyword bids, and Bing Ads will automatically adjust your bids in real time so that you bid up to 30% higher on users that are more likely to convert and up to 100% less on users less likely to convert. Bing Ads will still respect your campaign budget limit.  
*  *ManualCpc* - This is the default bid strategy type for your campaigns. Use the manual CPC bid strategy type if you will set your [Ad Group](ad-group.md) or [Keyword](keyword.md) bids, and Bing Ads will use these bids every time.  
*  *MaxClicks* - Defines an automated bidding strategy to maximize clicks given your maximum allowed budget.  
*  *MaxConversions* - Defines an automated bidding strategy to maximize conversions given your maximum allowed budget.    
*  *TargetCpa* - Defines an automated bidding strategy to maximize conversions at the target cost per acquisition (CPA). If you use this strategy type then you must also include the *Bid Strategy TargetCpa* field.    

> [!IMPORTANT] 
> If the campaign bid strategy type is set to *MaxClicks*, *MaxConversions*, or *TargetCpa*, the behavior of existing features will change unless you set an individual ad group's or keyword's bid strategy to *ManualCpc*. 
> - You can continue to set the ad group and keyword bids; however they will not be used by Bing Ads.
> - Bing Ads will periodically change your stored ad group or keyword bid settings. You can continue to set new bids, however Bing Ads may change them at any time using this bid strategy type.
> - You can continue to set bid adjustments e.g. for age, gender, or location; however, the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Bing Ads about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types. The valid range of values that you can use to inform auto bidding is -100.00 through 30.00.
> - Whether you chose the *DailyBudgetAccelerated* or *DailyBudgetStandard* budget type, Bing Ads will use the *DailyBudgetStandard* budget type. 
> 
> Also note that you must have conversion tracking (via [Universal Event Tracking](../guides/universal-event-tracking.md) tag and a conversion goal) set up for the *MaxConversions* and *TargetCpa* bid strategy types to work. To set the *MaxConversions* or *TargetCpa* bid strategy types, the campaign must have at least 15 conversions in the last 30 days. If you try to add or update a campaign to use one of these strategy types, the requested operation will fail if there is not enough conversion history. If an active campaign uses one of these bid strategy types, and then ceases to meet the minimum conversion history requirement at any time, Bing Ads will stop auto bidding but will continue to use the *DailyBudgetStandard* budget type. For a new campaign we recommend that you start with *EnhancedCpc* and then when the campaign has enough conversion history, you can update it to use either the *MaxConversions* or *TargetCpa* bid strategy.

> [!TIP] 
> You can set your campaign's bid strategy to *EnhancedCpc*, *MaxClicks*, *MaxConversions*, or *TargetCpa* and then, at any time, set an individual ad group's or keyword's bid strategy to *ManualCpc*. 

**Add:** Optional. Until January 28th, 2019 if you do not set this field, then *ManualCpc* is used by default. From January 28th, 2019 onwards if you do not set this field, then *EnhancedCpc* will be used by default.
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  If you update the bid strategy type, then any existing values in the *Bid Strategy MaxCpc* and *Bid Strategy TargetCpa* fields will be deleted.       
**Delete:** Read-only  

## <a name="budget"></a>Budget
The campaign's budget amount.

> [!WARNING]
> Your budget is a target; your actual spend might be higher or lower. Variations are caused by a number of factors, such as different traffic volumes in different days of the week, or automatic detection and refunding of fraud clicks that can give money back to a campaign within a few hours of the click. Bing Ads anticipates and automatically compensates for the fluctuations, and usually keeps overspend to less than 100% above your daily limit.
> 
> Also note that Bing Ads does not require your campaign budget to be higher than the ad group and keyword bids. In other words ad group and keyword bids are validated independently of the campaign budget. 

In the context of shared budgets, the budget amount is a read-only property that is always returned regardless of whether or not the campaign uses a shared budget. When a campaign is associated to a shared budget the amount returned is that of the shared budget. To determine whether the campaign uses a shared budget, check the value of the [Budget Id](#budgetid) field.

Business rules differ between shared and unshared budgets, and described in the table below.

|Action|Shared Budget|Unshared Budget|
|-----|-----|-----|
|**Add:**|Read-only|Required. You must set the daily budget amount if the [Budget Id](#budgetid) is not set.  
|**Update:**|Not allowed. If you try to update the budget amount of a campaign that has a shared budget, the service will return the *CampaignServiceCannotUpdateSharedBudget* error code.|Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:**|Read-only|Read-only|

## <a name="budgetid"></a>Budget Id
The system generated identifier of the [Budget](budget.md) that this campaign shares with other campaigns in the account.

If the field is empty, then the campaign is not using a shared budget. If the field is not empty and the value is greater than zero, then the campaign is using a shared budget. If the campaign is using a shared budget, and you prefer that it use its own budget amount, set this element to '0' (zero) and set the *Budget* field to a valid budget amount.

> [!NOTE]
> This value corresponds to the *Id* column of the [Budget](budget.md) record.
	
**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="budgetname"></a>Budget Name
The name of the shared budget.

This value corresponds to the *Budget Name* column of the [Budget](budget.md) record. You can only set this value using the [Budget](budget.md) record.

**Add:** Read-only  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="budgettype"></a>Budget Type
The budget type determines how the budget is spent. The possible values are *DailyBudgetAccelerated* and *DailyBudgetStandard*.

In the context of shared budgets, the budget type is a read-only property that is always returned regardless of whether or not the campaign uses a shared budget. To determine whether the campaign uses a shared budget, check the value of the *Budget Id* field. 

*Shared budget:*  
**Add:** Read-only  
**Update:** Not allowed. If you try to update the budget type of a campaign that has a shared budget, the service will return the *CampaignServiceCannotUpdateSharedBudget* error code.    
**Delete:** Read-only  

*Unshared budget:*  
**Add:** Required  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign.

**Add:** Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For update and delete, you must specify either the *Id* or *Campaign* field.

## <a name="campaigntype"></a>Campaign Type
The type of the campaign.

The campaign type determines whether the campaign is a Bing Shopping campaign, Dynamic Search Ads campaign, or Search campaign. Possible values include *Audience*, *DynamicSearchAds*, *Shopping*, and *Search*.

**Add:** Required for Audience campaigns, and otherwise this field is optional. If not specified, then default value of *Search* is used and you cannot set Audience, Dynamic Search Ads, or Shopping campaign settings. If the campaign type is *Shopping* then you must also include the *Country Code*, *Priority*, and *Store Id* fields. If the campaign type is *DynamicSearchAds* then you must also include the *Domain Language* and *Website* fields.  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="countrycode"></a>Country Code
The country code for the Bing Merchant Center store.

The Bing Merchant Center store catalog will be filtered to only include products for the specified country. 

For example, the following country code values are supported.
* *AU* - Australia
* *GB* - United Kingdom
* *DE* - Germany
* *FR* - France
* *US* - United States

To get the current list of supported country codes use the [GetBSCCountries](../campaign-management-service/getbsccountries.md) operation via the Campaign Management service.

**Add:** Required if the [Campaign Type](#campaigntype) field is set to *Shopping*. You cannot include this column for other campaign types.  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="customparameter"></a>Custom Parameter
Your custom collection of key and value parameters for URL tracking.

In a bulk file, the list of custom parameters are formatted as follows.

- Format each custom parameter pair as Key=Value, for example {_promoCode}=PROMO1.

- Bing Ads will accept the first 3 custom parameter key and value pairs that you include. Each key and value pair are delimited by a semicolon and space ("; "), for example {_promoCode}=PROMO1; {_season}=summer.

- A Key cannot contain a semicolon. If a Value contains a semicolon it must be escaped as '\;'. Additionally if the Value contains a backslash it must also be escaped as '\\'.

- The Key cannot exceed 16 UTF-8 bytes, and the Value cannot exceed 200 UTF-8 bytes. The Key is required and the Value is optional. The maximum size of the Key does not include the braces and underscore i.e., '{', '_', and '}'. 

    > [!NOTE] 
    > With the Bulk service the Key must be formatted with surrounding braces and a leading underscore, for example if the Key is promoCode, it must be formatted as {_promoCode}. With the Campaign Management service you cannot specify the surrounding braces and underscore.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. To remove all custom parameters, set this field to *delete_value*. The *delete_value* keyword removes the previous setting. To remove a subset of custom parameters, specify the custom parameters that you want to keep and omit any that you do not want to keep. The new set of custom parameters will replace any previous custom parameter set.    
**Delete:** Read-only  

## <a name="domainlanguage"></a>Domain Language
The language of the website pages that you want to target for dynamic search ads.

Currently the only supported language code is *EN*.

**Add:** Required if the [Campaign Type](#campaigntype) field is set to *DynamicSearchAds*. You cannot include this column for other campaign types.  
**Update:** Read-only. You cannot update the language.      
**Delete:** Read-only  

## <a name="experimentid"></a>Experiment Id
The system generated identifier of the [Experiment](experiment.md).

This field is only set for experiment campaigns i.e., campaigns that have been created for A/B testing based on another Search campaign. Base campaigns will not contain an experiment ID. Likewise, after an experiment has been [Graduated](experiment.md#status) to an independent campaign, this field will be empty, even though the campaign was previously an experiment campaign. 

With experiment campaigns you cannot update the [Budget](campaign.md#budget), [Budget Type](campaign.md#budgettype), or [Time Zone](campaign.md#timezone). The budget and time zone of an experiment campaign are always inherited from the base campaign settings. If you want to change an experiment's budget, you will need to change the base campaign's budget. The change in value will then be split based on your experiment [TrafficSplitPercent](#trafficsplitpercent) setting.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="id"></a>Id
The system generated identifier of the campaign.

**Add:** Optional. You must either leave this field empty, or specify a negative identifier. A negative identifier set for the campaign can then be referenced in the *Parent Id* field of dependent record types such as ad groups or criterion. This is recommended if you are adding new campaigns and new dependent records in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For update and delete, you must specify either the *Id* or *Campaign* field.

## <a name="keywordrelevance"></a>Keyword Relevance
A numeric score that indicates how likely your ads will be clicked and how well your keyword competes against other keywords targeting the same traffic. This score predicts whether your keyword is likely to lead to a click on your ads, taking into account how well your keyword has performed in the past relative to your ad's position.

> [!NOTE]
> Keyword Relevance is equivalent to the **Expected Click-Through Rate** label used in the Bing Ads web application.

A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.

If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.

Data for this column is typically updated 14-18 hours after the UTC day ends.

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="landingpagerelevance"></a>Landing Page Relevance
A numeric score that indicates how relevant your ad and landing page are to the customer's search query or other input.

> [!NOTE]
> Landing Page Relevance is equivalent to the **Ad Relevance** label used in the Bing Ads web application.

A score of 3 is Above Average; a score of 2 is Average; and a score of 1 is considered Below Average.

If you specify a time period that spans multiple days, the score will be the same for each day in the time period, and the value is the most recent calculated score.

Data for this column is typically updated 14-18 hours after the UTC day ends.

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="landingpageuserexperience"></a>Landing Page User Experience
A numeric score that indicates whether your landing page is likely to provide a good experience to customers who click your ad and land on your website.

> [!NOTE]
> Landing Page User Experience is equivalent to the **Landing Page Experience** label used in the Bing Ads web application.

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

For possible values, see the Language column of [Ad Languages](../guides/ad-languages.md#adlanguage). Each language in the bulk field is delimited by a semicolon (";"), for example *English;French;German*. You can specify multiple languages individually in the list, or only include one string in this field set to *All* if you want to target all languages.

For Audience campaigns you must include all languages i.e., set this field to *All*. 

**Add:** Required for Audience campaigns, and otherwise this field is optional. If there is no campaign language set, then the language of each ad group within the campaign will be required.   
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. Once campaign languages are set, you cannot delete all of them. The list of languages that you specify during update replaces the previous settings i.e. does not append to the existing set of languages.  
**Delete:** Read-only  

## <a name="localinventoryadsenabled"></a>LocalInventoryAdsEnabled
Determines whether local inventory ads are enabled for the Bing Merchant Center store.

Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.

Set this property to *TRUE* if you want to enable local inventory ads, and otherwise set it to *FALSE*.

**Add:** Optional. If you do not specify this field or leave it empty, the default value of *FALSE* will be set and local inventory ads will not be enabled.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The system generated identifier of the account that contains the campaign.

This bulk field maps to the *Id* field of the [Account](account.md) record.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  
  
## <a name="priority"></a>Priority
Helps determine which Bing Shopping campaign serves ads, in the event that two or more campaigns use the product catalog feed from the same Bing Merchant Center store.

You must specify one of the supported values: 0, 1, or 2. The higher numbers are given higher priority.

If two shopping campaigns use the product catalog feed from same Bing Merchant Center store, then  ads will be delivered for the [Ad Group Product Partition](ad-group-product-partition.md) with the highest bid.

> [!NOTE]
> If you create a Bing Shopping campaign in the Bing Ads web application, the default priority selected is "Low" which is the equivalent of '0'.

**Add:** Required if the [Campaign Type](#campaigntype) field is set to *Shopping*. You cannot include this column for other campaign types.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.  
**Delete:** Read-only  

## <a name="qualityscore"></a>Quality Score
The numeric score shows you how competitive your ads are in the marketplace by measuring how relevant your keywords and landing pages are to customers' search terms. The quality score is calculated by Bing Ads using the *Keyword Relevance*, *Landing Page Relevance*, and *Landing Page User Experience* sub scores. If available, the quality score can range from a low of 1 to a high of 10.

Quality score is based on the last rolling 30 days for the owned and operated search traffic. A quality score can be assigned without any impressions, in the case where a keyword bid did not win any auctions. Traffic for syndicated networks do not affect quality score. The value in the report will be "0" (zero) if the score was not computed. This can occur if there have been no impressions for the keyword for 30 days or more.<br/><br/>Quality score is typically updated 14-18 hours after the UTC day ends. Keywords in all time zones will be assigned a quality score for the corresponding UTC day.

If you run the report multiple times in a day, the quality score values could change from report to report based on when you run the report relative to when the scores are calculated.

If you specify a time period that spans multiple days, the quality score is the current and most recently calculated score and will be reported as the same for each day in the time period. Use the historic quality score to find out how quality score may have changed over time. Historical quality score is a daily snapshot of the rolling quality score. For more information on historic quality score, see the *HistoricalQualityScore* column in [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

**Add:** Read-only    
**Update:** Read-only  
**Delete:** Read-only  

## <a name="source"></a>Source
Determines whether to use Bing's index, advertiser supplied URLs, or both for dynamic search ads.

Possible values are in the table below.

|Value|Description|
|-----------|---------------|
|AdvertiserSuppliedUrls|Use URLs from my page feed only. Only URLs specified in the feed file will be served from this campaign. We recommend using this option for highly specific campaigns with tailored ad copy.|
|All|Use URLs from both Bing's index of my website and my page feed. Pages from both sources will be used but URLs within the feed file will be given priority.|
|SystemIndex|Use Bing's index of my website. This is the default behavior of dynamic search ad campaigns on Bing.|

**Add:** Optional if the [Campaign Type](#campaigntype) field is set to *DynamicSearchAds*. You cannot include this column for other campaign types. By default only Bing's index is used i.e., an empty value is effectively the same as specifying *SystemIndex*. 
**Update:** Optional if the [Campaign Type](#campaigntype) field is set to *DynamicSearchAds*. You cannot include this column for other campaign types. If no value is specified on update, this Bing Ads setting is not changed.      
**Delete:** Read-only  

## <a name="status"></a>Status
The status of the campaign.

Possible values for download and upload are Active, Paused, and Deleted. In addition, the values BudgetAndManualPaused, BudgetPaused, and Suspended are read-only via bulk download.

|Value|Description|
|-----------|---------------|
|Active|The campaign is active, which indicates that the campaign's ads can be served.|
|BudgetAndManualPaused|The campaign is paused, which indicates that the campaign's ads will not serve. This status results when a user sets the campaign status to paused after the service pauses the campaign because the budget is depleted.|
|BudgetPaused|The campaign is paused, which indicates that the campaign's ads will not serve. The service sets this status when the budget is depleted. The service will set the status back to Active when the budget is restored.|
|Deleted|The campaign is deleted. This status is for internal use only. Because all Get operations do not return deleted objects, you will not see an object with this status.|
|Paused|The campaign is paused, which indicates that the campaign's ads will not serve.|
|Suspended|Your campaign has been suspended because of suspicious activity, and no ads are eligible for delivery.<br/>Please contact [Bing Ads Support](http://go.microsoft.com/fwlink/?LinkId=269631).|

**Add:** Optional. The default value is Active.  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Required. The Status must be set to Deleted.

## <a name="storeid"></a>Store Id
The unique identifier for the Bing Merchant Center store that contains a product catalog feed that you want to use for the campaign.

Once you choose a store for a campaign, you can't change it. If at some point you want to use a different store, you would need to create a new shopping campaign with a new shopping setting.

To get your store identifiers, call the [GetBMCStoresByCustomerId](../campaign-management-service/getbmcstoresbycustomerid.md) operation.

**Add:** Required if the [Campaign Type](#campaigntype) field is set to *Shopping*. You cannot include this column for other campaign types.  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="subtype"></a>Sub Type
The campaign sub type.

This field is only applicable for campaigns of type *Shopping*, and will be empty for all other campaign types.

We are introducing Cooperative campaigns during calendar year 2018 as a sub type of Bing Shopping campaigns. More details about Cooperative campaigns are coming soon, and whether or not you plan to adopt Cooperative campaigns, you might need to make code changes if your application supports any Bing Shopping campaigns.

When you download campaigns and if the [Campaign Type](#campaigntype) field is set to *Shopping*, please also check the *Sub Type* of each campaign. If the *Sub Type* is not set then it is a standard Bing Shopping campaign. If the value is set to *ShoppingCoOperative*, the campaign is a Cooperative campaign with different requirements.  

**Add:** Optional and not applicable for most campaign types. For Cooperative campaigns you must set the sub type to *ShoppingCoOperative*.  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="timezone"></a>Time Zone
The time zone where the campaign operates.

The time zone is used for reporting and applying the start and end date of an ad group.

For possible values, see [Time Zones](../guides/time-zones.md).

**Add:** Required.   
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed. You may not update the time zone if the campaign contains or has ever contained ad groups in the *Active* or *Paused* state.    
**Delete:** Read-only  

## <a name="trackingtemplate"></a>Tracking Template
The tracking template to use as a default for all URLs in your campaign.

The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Bing Ads help article [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2)

- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](../guides/entity-hierarchy-limits.md).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*. 

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.

**Add:** Optional  
**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.    
**Delete:** Read-only  

## <a name="website"></a>Website
The domain name of the website that you want to target for dynamic search ads.

The length of the string is limited to 2,048 characters. If the domain name includes *www* it will be trimmed and not used.

**Add:** Required if the [Campaign Type](#campaigntype) field is set to *DynamicSearchAds*. You cannot include this column for other campaign types.  
**Update:** Read-only. You cannot update the domain name.      
**Delete:** Read-only  
