---
title: RuleItemGroup Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains a list of remarketing list rule items that apply to the same visited page.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# RuleItemGroup Data Object - Campaign Management
Defines an object that contains a list of remarketing list rule items that apply to the same visited page. 

## Syntax
```xml
<xs:complexType name="RuleItemGroup" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Items" nillable="true" type="tns:ArrayOfRuleItem" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="items"></a>Items|The list of rule items.<br/><br/>The maximum number of rule items in a rule item group is 100. The rule items must all be of the same concrete type derived from the [RuleItem](ruleitem.md) base class. Currently only a list of [StringRuleItem](stringruleitem.md) objects are supported.<br/><br/>The list of [StringRuleItem](stringruleitem.md) objects apply to same visited page, and the rule conditions are joined using the logical *AND* operator. In other words to add a visitor to the remarketing list, one page must meet all of the conditions in this rule item list. To create a list of rules for another page, you must add a separate *RuleItemGroup*.<br/><br/>**Add:** Required<br/>**Update:** Optional. If you want to keep any of the previous rule items, then you must explicitly set them again during update.|[RuleItem](ruleitem.md) array|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[PageVisitorsRule](pagevisitorsrule.md)  
[PageVisitorsWhoDidNotVisitAnotherPageRule](pagevisitorswhodidnotvisitanotherpagerule.md)  
[PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md)  
