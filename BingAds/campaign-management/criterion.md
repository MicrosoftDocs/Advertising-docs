---
title: Criterion Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# Criterion Data Object
Defines the base object of a criterion.

Do not try to instantiate a *Criterion*. You can create one or more following objects that derive from it.
-  [AgeCriterion](../campaign-management/agecriterion.md)  
-  [AudienceCriterion](../campaign-management/audiencecriterion.md)  
-  [DayTimeCriterion](../campaign-management/daytimecriterion.md)  
-  [DeviceCriterion](../campaign-management/devicecriterion.md)  
-  [GenderCriterion](../campaign-management/gendercriterion.md)  
-  [LocationCriterion](../campaign-management/locationcriterion.md)  
-  [LocationIntentCriterion](../campaign-management/locationintentcriterion.md)  
-  [ProductScope](../campaign-management/productscope.md)  
-  [ProductPartition](../campaign-management/productpartition.md)  
-  [RadiusCriterion](../campaign-management/radiuscriterion.md)  
-  [Webpage](../campaign-management/webpage.md)  

For a list of criterion types that you can use with [CampaignCriterion](../campaign-management/campaigncriterion.md), see the [CampaignCriterionType](../campaign-management/campaigncriteriontype.md) value set.

For a list of criterion types that you can use with [AdGroupCriterion](../campaign-management/adgroupcriterion.md), see the [AdGroupCriterionType](../campaign-management/adgroupcriteriontype.md) value set.

## Syntax
```xml
<xs:complexType name="Criterion" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Type" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of criterion. For more information, see [Remarks](#remarks).|**string**|

## <a name="remarks"></a>Remarks
For Java and the .NET languages, do not set the *Type* element because the value is determined by whether you instantiate a location or other criterion type.

If you generate the SOAP manually, use the *type* attribute of the `<Criterion>` node to specify the type of criterion, as shown in the following example.

```xml
<Criterion i:type="LocationCriterion" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
   . . .
</Criterion>
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroupCriterion](adgroupcriterion.md)  
[CampaignCriterion](campaigncriterion.md)  
