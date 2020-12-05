---
title: ImportEntityIdMapping Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the ImportEntityIdMapping Value Set.
---
# ImportEntityIdMapping Value Set - Campaign Management
Defines the ImportEntityIdMapping Value Set.

## Syntax
```xml
<xs:simpleType name="ImportEntityIdMapping" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="None">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">0</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ImportEntityIdMapping](importentityidmapping.md) value set has the following values: [None](#none).

|Value|Description|
|-----------|---------------|
|<a name="none"></a>None|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetImportEntityIdsMapping](getimportentityidsmapping.md)  
