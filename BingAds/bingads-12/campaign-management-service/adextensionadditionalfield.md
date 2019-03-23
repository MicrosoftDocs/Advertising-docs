---
title: AdExtensionAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional ad extension properties that you can request when calling GetAdExtensionsAssociations and GetAdExtensionsByIds.
---
# AdExtensionAdditionalField Value Set - Campaign Management
Defines a list of optional ad extension properties that you can request when calling [GetAdExtensionsAssociations](getadextensionsassociations.md) and [GetAdExtensionsByIds](getadextensionsbyids.md). The additional field values enable you to get the latest features using the current version of Bing Ads Campaign Management API, and in the next version the corresponding properties will be included in the ad extension by default.  

## Syntax
```xml
<xs:simpleType name="AdExtensionAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="FinalUrlSuffix" />
        <xs:enumeration value="ActionTypesPhase2" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="actiontypesphase2"></a>ActionTypesPhase2|Request that the new *ActionType* values be included within each returned [ActionAdExtension](actionadextension.md#actiontype). If the action type is either Directions, FindStore, SwitchNow, or VisitStore, then Campaign Management API Version 12 returns Unknown by default.|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Request that the *FinalUrlSuffix* element be included within each returned [ActionAdExtension](actionadextension.md#finalurlsuffix), [AppAdExtension](appadextension.md#finalurlsuffix), [ImageAdExtension](imageadextension.md#finalurlsuffix), [PriceAdExtension](priceadextension.md#finalurlsuffix), and [SitelinkAdExtension](sitelinkadextension.md#finalurlsuffix) object.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[GetAdExtensionsAssociations](getadextensionsassociations.md)  
[GetAdExtensionsByIds](getadextensionsbyids.md)  
