---
title: ProductPartitionType Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of product partitions.
---
# ProductPartitionType Value Set - Campaign Management
Defines the possible types of product partitions.

## Syntax
```xml
<xs:simpleType name="ProductPartitionType" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Subdivision">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Unit">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="subdivision"></a>Subdivision|The [ProductPartition](../campaign-management-service/productpartition.md) is a product group subdivision. A subdivision is also referred to as a branch node in a tree.|
|<a name="unit"></a>Unit|The [ProductPartition](../campaign-management-service/productpartition.md) is a product group unit. A unit is also referred to as a leaf node in a tree.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ProductPartition](productpartition.md)  
