---
title: CampaignAdGroupIds Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Identifies a campaign and the list of its ad groups to include within the operation scope.
---
# CampaignAdGroupIds Data Object - Campaign Management
Identifies a campaign and the list of its ad groups to include within the operation scope. 

## Syntax
```xml
<xs:complexType name="CampaignAdGroupIds" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ActiveAdGroupsOnly" nillable="true" type="xs:boolean">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
    <xs:element name="AdGroupIds" nillable="true" type="q119:ArrayOflong" xmlns:q119="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element name="CampaignId" type="xs:long" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [CampaignAdGroupIds](campaignadgroupids.md) object has the following elements: [ActiveAdGroupsOnly](#activeadgroupsonly), [AdGroupIds](#adgroupids), [CampaignId](#campaignid).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="activeadgroupsonly"></a>ActiveAdGroupsOnly|Reserved.|**boolean**|
|<a name="adgroupids"></a>AdGroupIds|Identifies the list a campaign's ad groups to include within the operation scope.<br/><br/>If this element is nil or empty, include all ad groups of the campaign.|**long** array|
|<a name="campaignid"></a>CampaignId|Identifies a campaign to include within the operation scope.|**long**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GoogleImportJob](googleimportjob.md)  
