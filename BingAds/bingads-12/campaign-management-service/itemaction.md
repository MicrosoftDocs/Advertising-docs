---
title: ItemAction Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible types of item actions, for example to add, delete, or update the product partition criterion.
---
# ItemAction Value Set - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Defines the possible types of item actions, for example to add, delete, or update the product partition criterion.

## Syntax
```xml
<xs:simpleType name="ItemAction" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Add">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Delete">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">2</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="Update">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">3</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="add"></a>Add|The requested action is to add the item, for example add the [ProductPartition](/bingads/campaign-management-service/productpartition.md).|
|<a name="delete"></a>Delete|The requested action is to delete the item, for example delete the [ProductPartition](/bingads/campaign-management-service/productpartition.md).|
|<a name="update"></a>Update|The requested action is to update the item, for example update the [ProductPartition](/bingads/campaign-management-service/productpartition.md).|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroupCriterionAction](adgroupcriterionaction.md)  