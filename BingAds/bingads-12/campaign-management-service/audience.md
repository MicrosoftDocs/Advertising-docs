---
title: Audience Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of an audience.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Audience Data Object - Campaign Management
Defines the base object of an audience.

Do not try to instantiate an *Audience*. You can create one or more following objects that derive from it.
- [CustomAudience](customaudience.md)  
- [InMarketAudience](inmarketaudience.md)  
- [RemarketingList](remarketinglist.md)  

## Syntax
```xml
<xs:complexType name="Audience" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q83:ArrayOfKeyValuePairOfstringstring" xmlns:q83="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="MembershipDuration" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ParentId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Scope" nillable="true" type="tns:EntityScope" />
    <xs:element minOccurs="0" name="SearchSize" nillable="true" type="xs:long">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
    <xs:element minOccurs="0" name="Type" type="tns:AudienceType" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description"></a>Description|The description of the audience. Use a description to help you remember what audience you are targeting.<br/><br/>The description can contain a maximum of 1,024 characters.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The Bing Ads identifier of the audience.|**long**|
|<a name="membershipduration"></a>MembershipDuration|When you create an audience, you can specify how far back in time Bing Ads should look for actions that match your audience definition.<br/><br/>The mimimum duration is 1 day and the maximum duration allowed is 180 days.|**int**|
|<a name="name"></a>Name|The name of the audience. The name can contain a maximum of 128 characters.|**string**|
|<a name="parentid"></a>ParentId|The Bing Ads identifier of the account or customer. <br/><br/>If the *Scope* is set to *Account*, this is the account ID, and otherwise it is the customer ID.|**long**|
|<a name="scope"></a>Scope|Scope defines what accounts can use this audience.<br/><br/> If scope is set to *Account*, the audience can only be associated with ad groups within one specified account (*ParentId*). If scope is set to *Customer*, the audience can be associated with any ad groups across all of the customer's accounts.|[EntityScope](entityscope.md)|
|<a name="searchsize"></a>SearchSize|The total number of people who belong to this audience. This gives you an idea of how many search users you can target.<br/><br/>This property will be nil or empty if the search audience size is less than 1,000. The audience needs to have at least 1,000 people before Bing Ads will use it for optimizations.<br/><br/>This property will be nil or empty for up to 24 hours while the audience is being built, for example if you add or update the remarketing list membership duration, rule, or tag identifier. Likewise if you have imported new custom audiences from DMP, it takes 24 hours to build the audience, and in the meantime this property will be nil or empty.<br/><br/>This property will be nil or empty if the UET tag associated with the remarketing list has a status of Unverified or Inactive, because the remarketing list can't receive the customer information from your website that it needs to build the list.|**long**|
|<a name="type"></a>Type|The type of the audience. For more information about audience types, see the [Remarks](#remarks).|[AudienceType](audiencetype.md)|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by whether you instantiate a custom audience or another type of audience. If you generate the SOAP manually, use the *type* attribute of the *Audience* node as shown in the following example.

```xml
<Audiences xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
  <Audience i:type="CustomAudience">
    <Description i:nil="false">Custom Audience Description</Description>
    <ForwardCompatibilityMap xmlns:e43="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
      <e43:KeyValuePairOfstringstring>
        <e43:key i:nil="false"></e43:key>
        <e43:value i:nil="false"></e43:value>
      </e43:KeyValuePairOfstringstring>
    </ForwardCompatibilityMap>
    <Id i:nil="true" />
    <MembershipDuration i:nil="false">30</MembershipDuration>
    <Name i:nil="false">Custom Audience Name</Name>
    <ParentId i:nil="false">ParentIdHere</ParentId>
    <Scope>Customer</Scope>
  </Audience>
</Audiences>
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AddAudiences](addaudiences.md)  
[GetAudiencesByIds](getaudiencesbyids.md)  
[UpdateAudiences](updateaudiences.md)  
