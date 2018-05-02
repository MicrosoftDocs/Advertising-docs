---
title: TargetSettingDetail Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group.
---
# TargetSettingDetail Data Object - Campaign Management
Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group. 

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

## Syntax
```xml
<xs:complexType name="TargetSettingDetail" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CriterionTypeGroup" type="tns:CriterionTypeGroup" />
    <xs:element minOccurs="0" name="TargetAndBid" type="xs:boolean" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="criteriontypegroup"></a>CriterionTypeGroup|The criterion type group that you want to set either the "target and bid" option or the "bid only" target option.<br/><br/>The supported values are Age, CompanyName, Gender, Industry, and JobFunction. For more details see the [Remarks](#remarks) below.<br/><br/>**Add:** Required<br/>**Update:** Required|[CriterionTypeGroup](criteriontypegroup.md)|
|<a name="targetandbid"></a>TargetAndBid|Determines whether you want to use the "target and bid" option or the "bid only" target option for the criterion type group. A value of *True* corresponds to the "target and bid" option, and in this case we will only deliver ads to people who meet at least one of your criteria, while letting you make bid adjustments for specific criteria. A value of *False* corresponds to the "bid only" option, and in this case we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific criteria.<br/><br/>**Add:** Required<br/>**Update:** Required|**boolean**|

## <a name="remarks"></a>Remarks
The supported values are Age, CompanyName, Gender, Industry, and JobFunction. 

> [!NOTE]
> Do not confuse the Audience campaign type with the Audience criterion type group name. 

|Criterion Type Group|Supported Campaigns|Description|
|-----------------|---------------|---------------|
|Age|Audience|If you set [TargetAndBid](#targetandbid) true for age criterions, we will only deliver ads to people who meet at least one of your age criteria, while letting you make bid adjustments for specific age ranges. This setting ensures that the people seeing your ads meet your age criteria.<br/><br/>If you set [TargetAndBid](#targetandbid) false for age criterions, or if no TargetSettingDetail object exists with the [CriterionTypeGroup](#criteriontypegroup) set to Age, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific age ranges. This setting lets you bid more (or less) aggressively for the people who meet specific age criteria, without restricting your ads to those people.|
|Audience|Not supported|<br/><br/>In Bing Ads API Version 12, you can use the [CriterionTypeGroup](targetsettingdetail.md#criteriontypegroup) value of *Audience*. In Bing Ads API Version 11 you must use the [RemarketingTargetingSetting](adgroup.md#remarketingtargetingsetting) property of the [AdGroup](adgroup.md) instead.|
|CompanyName|Audience|If you set [TargetAndBid](#targetandbid) true for company name criterions, we will only deliver ads to people who meet at least one of your company criteria, while letting you make bid adjustments for specific companies. This setting ensures that the people seeing your ads meet your company criteria.<br/><br/>If you set [TargetAndBid](#targetandbid) false for company name criterions, or if no TargetSettingDetail object exists with the [CriterionTypeGroup](#criteriontypegroup) set to CompanyName, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific companies. This setting lets you bid more (or less) aggressively for the people who meet specific company criteria, without restricting your ads to those people.|
|Gender|Audience|If you set [TargetAndBid](#targetandbid) true for gender criterions, we will only deliver ads to people who meet your gender criteria, while letting you make bid adjustments for a specific gender. This setting ensures that the people seeing your ads meet your gender criteria.<br/><br/>If you set [TargetAndBid](#targetandbid) false for gender criterions, or if no TargetSettingDetail object exists with the [CriterionTypeGroup](#criteriontypegroup) set to Gender, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for a specific gender. This setting lets you bid more (or less) aggressively for the people who meet specific gender criteria, without restricting your ads to those people.|
|Industry|Audience|If you set [TargetAndBid](#targetandbid) true for industry criterions, we will only deliver ads to people who meet at least one of your industry criteria, while letting you make bid adjustments for specific industries. This setting ensures that the people seeing your ads meet your industry criteria.<br/><br/>If you set [TargetAndBid](#targetandbid) false for industry criterions, or if no TargetSettingDetail object exists with the [CriterionTypeGroup](#criteriontypegroup) set to Industry, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific industries. This setting lets you bid more (or less) aggressively for the people who meet specific industry criteria, without restricting your ads to those people.|
|JobFunction|Audience|If you set [TargetAndBid](#targetandbid) true for job function criterions, we will only deliver ads to people who meet at least one of your job function criteria, while letting you make bid adjustments for specific job functions. This setting ensures that the people seeing your ads meet your job function criteria.<br/><br/>If you set [TargetAndBid](#targetandbid) false for job function criterions, or if no TargetSettingDetail object exists with the [CriterionTypeGroup](#criteriontypegroup) set to JobFunction, we will deliver ads to everyone who meets your other targeting criteria, while letting you make bid adjustments for specific job functions. This setting lets you bid more (or less) aggressively for the people who meet specific job function criteria, without restricting your ads to those people.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[TargetSetting](targetsetting.md)  
