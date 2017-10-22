---
title: RemarketingRule Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines the base object of a remarketing rule.
---
# RemarketingRule Data Object - Campaign Management
Defines the base object of a remarketing rule.

Do not try to instantiate a *RemarketingRule*. You can create one or more following objects that derive from it.
- [CustomEventsRule](../campaign-management-service/customeventsrule.md)
- [PageVisitorsRule](../campaign-management-service/pagevisitorsrule.md)
- [PageVisitorsWhoDidNotVisitAnotherPageRule](../campaign-management-service/pagevisitorswhodidnotvisitanotherpagerule.md) 
- [PageVisitorsWhoVisitedAnotherPageRule](../campaign-management-service/pagevisitorswhovisitedanotherpagerule.md)

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
<Rule xmlns:e145="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V10" p4:nil="false" p4:type="-- specify derived type here with the appropriate prefix --">
  <e145:Type p4:nil="false"></e145:Type>
  <!--Keep these fields if you set the i:type attribute to PageVisitorsRule-->
  <e145:RuleItemGroups p4:nil="false">
    <e145:RuleItemGroup>
      <e145:Items p4:nil="false">
        <e145:RuleItem p4:type="-- specify derived type here with the appropriate prefix --">
          <e145:Type p4:nil="false"></e145:Type>
          <!--Keep these fields if you set the i:type attribute to StringRuleItem-->
          <e145:Operand p4:nil="false"></e145:Operand>
          <e145:Operator></e145:Operator>
          <e145:Value p4:nil="false"></e145:Value>
        </e145:RuleItem>
      </e145:Items>
    </e145:RuleItemGroup>
  </e145:RuleItemGroups>
  <!--Keep these fields if you set the i:type attribute to PageVisitorsWhoVisitedAnotherPageRule-->
  <e145:AnotherRuleItemGroups p4:nil="false">
    <e145:RuleItemGroup>
      <e145:Items p4:nil="false">
        <e145:RuleItem p4:type="-- specify derived type here with the appropriate prefix --">
          <e145:Type p4:nil="false"></e145:Type>
          <!--Keep these fields if you set the i:type attribute to StringRuleItem-->
          <e145:Operand p4:nil="false"></e145:Operand>
          <e145:Operator></e145:Operator>
          <e145:Value p4:nil="false"></e145:Value>
        </e145:RuleItem>
      </e145:Items>
    </e145:RuleItemGroup>
  </e145:AnotherRuleItemGroups>
  <e145:RuleItemGroups p4:nil="false">
    <e145:RuleItemGroup>
      <e145:Items p4:nil="false">
        <e145:RuleItem p4:type="-- specify derived type here with the appropriate prefix --">
          <e145:Type p4:nil="false"></e145:Type>
          <!--Keep these fields if you set the i:type attribute to StringRuleItem-->
          <e145:Operand p4:nil="false"></e145:Operand>
          <e145:Operator></e145:Operator>
          <e145:Value p4:nil="false"></e145:Value>
        </e145:RuleItem>
      </e145:Items>
    </e145:RuleItemGroup>
  </e145:RuleItemGroups>
  <!--Keep these fields if you set the i:type attribute to PageVisitorsWhoDidNotVisitAnotherPageRule-->
  <e145:ExcludeRuleItemGroups p4:nil="false">
    <e145:RuleItemGroup>
      <e145:Items p4:nil="false">
        <e145:RuleItem p4:type="-- specify derived type here with the appropriate prefix --">
          <e145:Type p4:nil="false"></e145:Type>
          <!--Keep these fields if you set the i:type attribute to StringRuleItem-->
          <e145:Operand p4:nil="false"></e145:Operand>
          <e145:Operator></e145:Operator>
          <e145:Value p4:nil="false"></e145:Value>
        </e145:RuleItem>
      </e145:Items>
    </e145:RuleItemGroup>
  </e145:ExcludeRuleItemGroups>
  <e145:IncludeRuleItemGroups p4:nil="false">
    <e145:RuleItemGroup>
      <e145:Items p4:nil="false">
        <e145:RuleItem p4:type="-- specify derived type here with the appropriate prefix --">
          <e145:Type p4:nil="false"></e145:Type>
          <!--Keep these fields if you set the i:type attribute to StringRuleItem-->
          <e145:Operand p4:nil="false"></e145:Operand>
          <e145:Operator></e145:Operator>
          <e145:Value p4:nil="false"></e145:Value>
        </e145:RuleItem>
      </e145:Items>
    </e145:RuleItemGroup>
  </e145:IncludeRuleItemGroups>
  <!--Keep these fields if you set the i:type attribute to CustomEventsRule-->
  <e145:Action p4:nil="false"></e145:Action>
  <e145:ActionOperator></e145:ActionOperator>
  <e145:Category p4:nil="false"></e145:Category>
  <e145:CategoryOperator></e145:CategoryOperator>
  <e145:Label p4:nil="false"></e145:Label>
  <e145:LabelOperator></e145:LabelOperator>
  <e145:Value p4:nil="false"></e145:Value>
  <e145:ValueOperator></e145:ValueOperator>
</Rule>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11  

## Used By
[RemarketingList](remarketinglist.md)  
