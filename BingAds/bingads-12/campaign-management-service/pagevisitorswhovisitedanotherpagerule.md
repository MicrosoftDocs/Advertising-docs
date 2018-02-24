---
title: PageVisitorsWhoVisitedAnotherPageRule Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a page visitors who visited another page remarketing rule.
---
# PageVisitorsWhoVisitedAnotherPageRule Data Object - Campaign Management
Defines a page visitors who visited another page remarketing rule. 

Remarketing rules are conditions used to determine who to add to your remarketing list. For the *PageVisitorsWhoVisitedAnotherPage* rule, you must include one or more rule item groups for the page visited (*RuleItemGroups*), and you must also include one or more rule item groups for another page that must have been visited (*AnotherRuleItemGroups*). 

For each rule item group within *RuleItemGroups*, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. 

Likewise for each rule item group within *AnotherRuleItemGroups*, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. 

In other words the visitor will be added to your remarketing list if any of the rule item group conditions are met, and any of the another rule item group conditions are met. 

For a detailed example, see the [Remarks](#Remarks) section below.

## Syntax
```xml
<xs:complexType name="PageVisitorsWhoVisitedAnotherPageRule" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:RemarketingRule">
      <xs:sequence>
        <xs:element minOccurs="0" name="AnotherRuleItemGroups" nillable="true" type="tns:ArrayOfRuleItemGroup" />
        <xs:element minOccurs="0" name="RuleItemGroups" nillable="true" type="tns:ArrayOfRuleItemGroup" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="anotherruleitemgroups"></a>AnotherRuleItemGroups|The list of rule item groups related to other pages the audience visited.<br/><br/>The maximum number of rule item groups in this element is 100. The maximum number of rule items per rule item group is 100. <br/><br/>**Add:** Required<br/>**Update:** Required. If you want to keep any of the previous rule item groups, then you must explicitly set them again during update.|[RuleItemGroup](ruleitemgroup.md) array|
|<a name="ruleitemgroups"></a>RuleItemGroups|The list of rule item groups related to pages the audience visited.<br/><br/>The maximum number of rule item groups in this element is 100. The maximum number of rule items per rule item group is 100.<br/><br/>**Add:** Required<br/>**Update:** Required. If you want to keep any of the previous rule item groups, then you must explicitly set them again during update.|[RuleItemGroup](ruleitemgroup.md) array|

The [PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsremarketingrule"></a>Inherited Elements from RemarketingRule
The [PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md) object derives from the [RemarketingRule](remarketingrule.md) object, and inherits the following elements. The descriptions below are specific to [PageVisitorsWhoVisitedAnotherPageRule](pagevisitorswhovisitedanotherpagerule.md), and might not apply to other objects that inherit the same elements from the [RemarketingRule](remarketingrule.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the remarketing rule. For more information about remarketing rule types, see the [RemarketingRule Data Object Remarks](../campaign-management-service/remarketingrule.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## <a name="remarks"></a>Remarks
Remarketing rules are conditions used to determine who to add to your remarketing list. For the *PageVisitorsWhoVisitedAnotherPage* rule, you must include one or more rule item groups for the page visited (*RuleItemGroups*), and you must also include one or more rule item groups for another page that must have been visited (*AnotherRuleItemGroups*). 

For each rule item group within *RuleItemGroups*, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. 

Likewise for each rule item group within *AnotherRuleItemGroups*, the rule item conditions for the same page are joined using the logical *AND* operator. Then, each result from the list of rule item groups are joined using the logical *OR* operator. 

In other words the visitor will be added to your remarketing list if any of the rule item group conditions are met, and any of the another rule item group conditions are met.

For example let's say that the following rule item groups are set.

```xml
<Rule i:type="a:PageVisitorsWhoVisitedAnotherPageRule" xmlns:a="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11">
  <a:Type>PageVisitorsWhoVisitedAnotherPage</a:Type>
  <a:AnotherRuleItemGroups>
    <a:RuleItemGroup>
      <a:Items>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>Url</a:Operand>
          <a:Operator>BeginsWith</a:Operator>
          <a:Value>A</a:Value>
        </a:RuleItem>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>ReferrerUrl</a:Operand>
          <a:Operator>BeginsWith</a:Operator>
          <a:Value>B</a:Value>
        </a:RuleItem>
      </a:Items>
    </a:RuleItemGroup>
    <a:RuleItemGroup>
      <a:Items>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>Url</a:Operand>
          <a:Operator>Contains</a:Operator>
          <a:Value>C</a:Value>
        </a:RuleItem>
      </a:Items>
    </a:RuleItemGroup>
  </a:AnotherRuleItemGroups>
  <a:RuleItemGroups>
    <a:RuleItemGroup>
      <a:Items>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>Url</a:Operand>
          <a:Operator>Contains</a:Operator>
          <a:Value>X</a:Value>
        </a:RuleItem>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>ReferrerUrl</a:Operand>
          <a:Operator>NotEquals</a:Operator>
          <a:Value>Z</a:Value>
        </a:RuleItem>
      </a:Items>
    </a:RuleItemGroup>
    <a:RuleItemGroup>
      <a:Items>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>Url</a:Operand>
          <a:Operator>DoesNotBeginWith</a:Operator>
          <a:Value>Y</a:Value>
        </a:RuleItem>
      </a:Items>
    </a:RuleItemGroup>
    <a:RuleItemGroup>
      <a:Items>
        <a:RuleItem i:type="a:StringRuleItem">
          <a:Type>String</a:Type>
          <a:Operand>ReferrerUrl</a:Operand>
          <a:Operator>Equals</a:Operator>
          <a:Value>Z</a:Value>
        </a:RuleItem>
      </a:Items>
    </a:RuleItemGroup>
  </a:RuleItemGroups>
</Rule>
```

The above definition is translated to the following logical expression:

*(((Url Contains X) and (ReferrerUrl NotEquals Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))) and (((Url BeginsWith A) and (ReferrerUrl BeginsWith B)) or ((Url Contains C)))*

Evaluation of the logical expression determines which of the following example users will be added to the remarketing list.

|User|Url Visited|Referrer Url|Added to List|
|-----------|---------------|-------------|-------------|
|User 1|A<br/>|X|No. Evaluation of the logical expression results as *False*.<br/><br/>*(((Url Contains X) and (ReferrerUrl NotEquals Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))) and (((Url BeginsWith A) and (ReferrerUrl BeginsWith B)) or ((Url Contains C)))*<br/><br/>*((False and True) or (True) or (False)) and ((True and False) or (False))*<br/><br/>*(False or True or False) and (False or False)*<br/><br/>*True and False*<br/><br/>*False*|
|User 2|B<br/>|Y|No. Evaluation of the logical expression results as *False*.<br/><br/>*(((Url Contains X) and (ReferrerUrl NotEquals Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))) and (((Url BeginsWith A) and (ReferrerUrl BeginsWith B)) or ((Url Contains C)))*<br/><br/>*((False and True) or (True) or (False)) and ((False and False) or (False))*<br/><br/>*(False or True or False) and (False or False)*<br/><br/>*True and False*<br/>*False*<br/>|
|User 3|C<br/>|Z|Yes. Evaluation of the logical expression results as *True*.<br/><br/>*(((Url Contains X) and (ReferrerUrl NotEquals Z)) or ((Url DoesNotBeginWith Y)) or ((ReferrerUrl Equals Z))) and (((Url BeginsWith A) and (ReferrerUrl BeginsWith B)) or ((Url Contains C)))*<br/><br/>*((False and True) or (True) or (True)) and ((False and False) or (True))*<br/><br/>*(False or True or True) and (False or True)*<br/><br/>*True and True*<br/><br/>*True*|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: http\://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11  

