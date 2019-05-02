---
title: KeywordStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of a keyword.
---
# KeywordStatus Value Set - Campaign Management
Defines the possible status values of a keyword.

## Syntax
```xml
<xs:simpleType name="KeywordStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Paused" />
    <xs:enumeration value="Deleted" />
    <xs:enumeration value="Inactive" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The keyword can be used to match user search queries.|
|<a name="deleted"></a>Deleted|This status is for internal use only. Because all Get operations do not return deleted objects, you will not see an object with this status.|
|<a name="inactive"></a>Inactive|The keyword is undergoing editorial review or has failed editorial review. To determine the keyword editorial status, see [KeywordEditorialStatus](keywordeditorialstatus.md).|
|<a name="paused"></a>Paused|The keyword cannot be used to match user search queries until the owner resumes it.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[Keyword](keyword.md)  
