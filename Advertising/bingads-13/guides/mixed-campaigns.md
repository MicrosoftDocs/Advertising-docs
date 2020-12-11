---
title: "Mixed Campaigns"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Setup Mixed Campaigns with Multiple Ad Group Types.
---
# Mixed Campaigns
A mixed campaign is a search campaign with dynamic search ads settings and multiple ad group types. Expanded text ads, responsive search ads and keywords are grouped into "SearchStandard" ad groups, while dynamic search ads and auto targets are grouped into "SearchDynamic" ad groups. Instead of creating and managing two campaigns with separate budgets, the same ad extension and audience associations, similar settings, reporting tasks and so on, you can just setup one mixed campaign. 

And of course, now you can also import your mixed campaigns from Google Ads. once an account is added to the pilot the SearchAndDsaMixedCampaignAsSearchCampaign option will be ignored. Whether the option is set true or false, both "SearchStandard" and "SearchDynamic" ad groups will be imported in a mixed campaign. 

You can add dynamic search ad groups to an existing search campaign, unless it is an experiment campaign or the base campaign of an experiment. Likewise you cannot create a new experiment campaign based on a mixed campaign. Experiments only support search campaigns without dynamic search ads settings. 

> [!NOTE]
> Mixed campaigns are only available for pilot accounts i.e., [GetAccountPilotFeatures](../customer-management-service/getaccountpilotfeatures.md) returns 791. 
> 
> Please note [GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) might also return 791 for internal use; however, for account level pilots such as 791 you should ignore the results of [GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md).  

Customers in the mixed campaigns pilot will no longer see the following options in the Microsoft Advertising web UI.  
 - Option to create a new Dynamic Search Ads campaign is not available. You can still manage existing Dynamic Search Ads campaigns in the UI.  
 - Option to choose search or DSA ad groups when importing from Google Ads is not available. Both search and DSA ad groups will be imported and any previous setting will be ignored. 

## <a name="campaign-campaignservice"></a>Create the campaign
You can create a mixed [campaign](../campaign-management-service/campaign.md) with the [AddCampaigns](../campaign-management-service/addcampaigns.md) operation. You can create a maximum of 100 mixed campaigns per ad account. 

- The [CampaignType](../campaign-management-service/campaign.md#campaigntype) must be set to "Search".  

- You must include a [DynamicSearchAdsSetting](../campaign-management-service/dynamicsearchadssetting.md) in the list of campaign [Settings](../campaign-management-service/campaign.md#settings). 

Here's an example [AddCampaigns](../campaign-management-service/addcampaigns.md) SOAP request with mixed campaign settings. 

```xml
<AddCampaignsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <AccountId>AccountIdGoesHere</AccountId>
    <Campaigns xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <Campaign>
            <BudgetType>DailyBudgetStandard</BudgetType>
            <DailyBudget>50</DailyBudget>
            <Name>Mixed Campaign</Name>
            <TimeZone>PacificTimeUSCanadaTijuana</TimeZone>
            <CampaignType>Search</CampaignType>
            <Settings>
                <Setting i:type="DynamicSearchAdsSetting">
                    <Type i:nil="true" />
                    <DomainName>contoso.com</DomainName>
                    <Language>English</Language>
                    <PageFeedIds xmlns:d8p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
                    <Source i:nil="true" />
                </Setting>
            </Settings>
            <BudgetId i:nil="true" />
            <Languages xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
                <d6p1:string>All</d6p1:string>
            </Languages>
        </Campaign>
    </Campaigns>
</AddCampaignsRequest>
```

## <a name="adgroup-campaignservice"></a>Create ad groups
You can create one or more [AdGroup](../campaign-management-service/adgroup.md) objects in each mixed campaign by calling the [AddAdGroups](../campaign-management-service/addadgroups.md) operation. 

Please note the [AdGroupType](../campaign-management-service/adgroup.md#adgrouptype) is not required and will default to "SearchStandard". 

```xml
<AddAdGroupsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v13">
    <CampaignId>CampaignIdGoesHere</CampaignId>
    <AdGroups xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroup>
            <CpcBid>
                <Amount>0.50</Amount>
            </CpcBid>
            <Name>DSA Ad Group</Name>
            <AdGroupType>SearchDynamic</AdGroupType>
        </AdGroup>
        <AdGroup>
            <CpcBid>
                <Amount>0.50</Amount>
            </CpcBid>
            <Name>Search Ad Group</Name>
            <AdGroupType>SearchStandard</AdGroupType>
        </AdGroup>
    </AdGroups>
    <ReturnInheritedBidStrategyTypes>false</ReturnInheritedBidStrategyTypes>
</AddAdGroupsRequest>
```

Supported entities and settings are restricted by ad group type.  

- If the ad group type is "SearchDynamic", then you can only add dynamic search ads. 
- If the ad group type is "SearchStandard", then you can add expanded text ads or responsive search ads. 
- In a Search campaign you can only apply [Webpage](../campaign-management-service/webpage.md) criterion to a "SearchDynamic" ad group. 

Other settings such as location targets and remarketing lists can be applied regardless of the ad group type. 

## See Also
[Bing Ads API Web Service Addresses](web-service-addresses.md)  
