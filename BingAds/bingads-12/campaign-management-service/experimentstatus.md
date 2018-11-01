---
title: ExperimentStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved for future use.
---
# ExperimentStatus Value Set - Campaign Management
Reserved for future use.

## Syntax
```xml
<xs:simpleType name="ExperimentStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Creating" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="Deleted" />
    <xs:enumeration value="Promoting" />
    <xs:enumeration value="Promoted" />
    <xs:enumeration value="Graduating" />
    <xs:enumeration value="Graduated" />
    <xs:enumeration value="CreationFailed" />
    <xs:enumeration value="PromoteFailed" />
    <xs:enumeration value="GraduateFailed" />
    <xs:enumeration value="Paused" />
    <xs:enumeration value="Scheduled" />
    <xs:enumeration value="Ended" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|Reserved.|
|<a name="creating"></a>Creating|Reserved.|
|<a name="creationfailed"></a>CreationFailed|Reserved.|
|<a name="deleted"></a>Deleted|Reserved.|
|<a name="ended"></a>Ended|Reserved.|
|<a name="graduated"></a>Graduated|Reserved.|
|<a name="graduatefailed"></a>GraduateFailed|Reserved.|
|<a name="graduating"></a>Graduating|Reserved.|
|<a name="paused"></a>Paused|Reserved.|
|<a name="promoted"></a>Promoted|Reserved.|
|<a name="promotefailed"></a>PromoteFailed|Reserved.|
|<a name="promoting"></a>Promoting|Reserved.|
|<a name="scheduled"></a>Scheduled|Reserved.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

