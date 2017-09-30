---
title: KeyValuePairOfstringstring Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# KeyValuePairOfstringstring Data Object
Reserved.

## Syntax
```xml
<xs:complexType name="KeyValuePairOfstringstring" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <GenericType Name="KeyValuePairOf{0}{1}{#}" Namespace="http://schemas.datacontract.org/2004/07/System.Collections.Generic" xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
        <GenericParameter Name="string" Namespace="http://www.w3.org/2001/XMLSchema" />
        <GenericParameter Name="string" Namespace="http://www.w3.org/2001/XMLSchema" />
      </GenericType>
      <IsValueType xmlns="http://schemas.microsoft.com/2003/10/Serialization/">true</IsValueType>
    </xs:appinfo>
  </xs:annotation>
  <xs:sequence>
    <xs:element name="key" nillable="true" type="xs:string" />
    <xs:element name="value" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="key"></a>key|Reserved.|**string**|
|<a name="value"></a>value|Reserved.|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/System.Collections.Generic  

## Used By
[Ad](ad.md)  
[AdExtension](adextension.md)  
[AdGroup](adgroup.md)  
[Audience](audience.md)  
[BatchError](batcherror.md)  
[BatchErrorCollection](batcherrorcollection.md)  
[Campaign](campaign.md)  
[CampaignCriterion](campaigncriterion.md)  
[Keyword](keyword.md)  
[SharedEntity](sharedentity.md)  
[SharedListItem](sharedlistitem.md)  
