---
title: PageVisitorsRule Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a page visitors remarketing rule.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# PageVisitorsRule Data Object - Campaign Management
Defines a page visitors remarketing rule. 

Remarketing rules are conditions used to determine who to add to your remarketing list. For the *PageVisitors* rule, you must include one or more rule item groups. With each rule item group, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. In other words the user will be added to your remarketing list if all of the specified rule item conditions within any one of the rule item groups are met.

For a detailed example, see the [Remarks](#Remarks) section below.

## Syntax
```xml
<xs:complexType name="PageVisitorsRule" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:RemarketingRule">
      <xs:sequence>
        <xs:element minOccurs="0" name="RuleItemGroups" nillable="true" type="tns:ArrayOfRuleItemGroup" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ruleitemgroups"></a>RuleItemGroups|The list of rule item groups that you want applied to the remarketing list.<br/><br/>The maximum number of rule item groups in this element is 100. The maximum number of rule items per rule item group is 100.<br/><br/>**Add:** Required<br/>**Update:** Required. If you want to keep any of the previous rule item groups, then you must explicitly set them again during update.|[RuleItemGroup](ruleitemgroup.md) array|

The [PageVisitorsRule](pagevisitorsrule.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsremarketingrule"></a>Inherited Elements from RemarketingRule
The [PageVisitorsRule](pagevisitorsrule.md) object derives from the [RemarketingRule](remarketingrule.md) object, and inherits the following elements. The descriptions below are specific to [PageVisitorsRule](pagevisitorsrule.md), and might not apply to other objects that inherit the same elements from the [RemarketingRule](remarketingrule.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the remarketing rule. For more information about remarketing rule types, see the [RemarketingRule Data Object Remarks](remarketingrule.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## <a name="remarks"></a>Remarks
Remarketing rules are conditions used to determine who to add to your remarketing list. For the *PageVisitors* rule, you must include one or more rule item groups. With each rule item group, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. In other words the user will be added to your remarketing list if all of the specified rule item conditions within any one of the rule item groups are met.

For example let's say that the following rule item groups are set.

```xml
<Rule i:type="PageVisitorsRule">
  <Type i:nil="true" />
  <RuleItemGroups>
    <RuleItemGroup>
      <Items>
        <RuleItem i:type="StringRuleItem">
          <Type i:nil="true" />
          <Operand>Url</Operand>
          <Operator>Contains</Operator>
          <Value>X</Value>
        </RuleItem>
        <RuleItem i:type="StringRuleItem">
          <Type i:nil="true" />
          <Operand>ReferrerUrl</Operand>
          <Operator>DoesNotContain</Operator>
          <Value>Z</Value>
        </RuleItem>
      </Items>
    </RuleItemGroup>
    <RuleItemGroup>
      <Items>
        <RuleItem i:type="StringRuleItem">
          <Type i:nil="true" />
          <Operand>Url</Operand>
          <Operator>DoesNotBeginWith</Operator>
          <Value>Y</Value>
        </RuleItem>
      </Items>
    </RuleItemGroup>
    <RuleItemGroup>
      <Items>
        <RuleItem i:type="StringRuleItem">
          <Type i:nil="true" />
          <Operand>ReferrerUrl</Operand>
          <Operator>Equals</Operator>
          <Value>Z</Value>
        </RuleItem>
      </Items>
    </RuleItemGroup>
  </RuleItemGroups>
</Rule>
```

The above definition is translated to the following logical expression:

*((Url Contains X) and (ReferrerUrl DoesNotContain Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))*

Evaluation of the logical expression determines which of the following example users will be added to the remarketing list.

|User|Url Visited|Referrer Url|Added to List|
|-----------|---------------|-------------|-------------|
|User 1|A<br/>|X|Yes. Evaluation of the logical expression results as *True*.<br/><br/>*((Url Contains X) and (ReferrerUrl DoesNotContain Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))*<br/><br/>*(False and True) or (True) or (False)*<br/><br/>*False or True or False*<br/><br/>*True*|
|User 2|B<br/>|Y|No. Evaluation of the logical expression results as *False*.<br/><br/>*((Url Contains X) and (ReferrerUrl DoesNotContain Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))*<br/><br/>*(False and True) or (False) or (False)*<br/><br/>*False or False or False*<br/><br/>*False*|
|User 3|C<br/>|Z|Yes. Evaluation of the logical expression results as *True*.<br/><br/>*((Url Contains X) and (ReferrerUrl DoesNotContain Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))*<br/><br/>*(False and False) or (True) or (True)*<br/><br/>*False or True or True*<br/><br/>*True*|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

