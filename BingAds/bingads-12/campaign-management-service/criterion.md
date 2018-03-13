---
title: Criterion Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the base object of a criterion.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Criterion Data Object - Campaign Management
Defines the base object of a criterion.

Do not try to instantiate a *Criterion*. You can create one or more following objects that derive from it.
-  [AgeCriterion](agecriterion.md)  
-  [AudienceCriterion](audiencecriterion.md)  
-  [DayTimeCriterion](daytimecriterion.md)  
-  [DeviceCriterion](devicecriterion.md)  
-  [GenderCriterion](gendercriterion.md)  
-  [LocationCriterion](locationcriterion.md)  
-  [LocationIntentCriterion](locationintentcriterion.md)  
-  [ProductScope](productscope.md)  
-  [ProductPartition](productpartition.md)  
-  [RadiusCriterion](radiuscriterion.md)  
-  [Webpage](webpage.md)  

For a list of criterion types that you can use with [CampaignCriterion](campaigncriterion.md), see the [CampaignCriterionType](campaigncriteriontype.md) value set.

For a list of criterion types that you can use with [AdGroupCriterion](adgroupcriterion.md), see the [AdGroupCriterionType](adgroupcriteriontype.md) value set.

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
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AdGroupCriterion](adgroupcriterion.md)  
[CampaignCriterion](campaigncriterion.md)  
