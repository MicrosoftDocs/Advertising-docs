---
title: RemarketingRule Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of a remarketing rule.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# RemarketingRule Data Object - Campaign Management
Defines the base object of a remarketing rule.

Do not try to instantiate a *RemarketingRule*. You can create one or more following objects that derive from it.
- [CustomEventsRule](customeventsrule.md)
- [PageVisitorsRule](pagevisitorsrule.md)
- [PageVisitorsWhoDidNotVisitAnotherPageRule](pagevisitorswhodidnotvisitanotherpagerule.md) 
- [PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md)

## Syntax
```xml
<xs:complexType name="RemarketingRule" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the remarketing rule. For more information about remarketing rule types, see the [Remarks](#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by which type of remarketing rule you instantiate.

If you generate the SOAP manually, use the *type* attribute of the `<Rule>` node as shown in the following example, to specify the type of the remarketing rule.

```xml
<Rule i:type="CustomEventsRule">
  <Type i:nil="true" />
  <Action>play</Action>
  <ActionOperator>Equals</ActionOperator>
  <Category>video</Category>
  <CategoryOperator>Equals</CategoryOperator>
  <Label>trailer</Label>
  <LabelOperator>Equals</LabelOperator>
  <Value>5.00</Value>
  <ValueOperator>Equals</ValueOperator>
</Rule>
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[RemarketingList](remarketinglist.md)  
