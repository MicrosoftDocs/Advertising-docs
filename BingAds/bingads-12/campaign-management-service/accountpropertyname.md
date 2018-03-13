---
title: AccountPropertyName Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the name of account level properties.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# AccountPropertyName Value Set - Campaign Management
Defines the name of account level properties.

## Syntax
```xml
<xs:simpleType name="AccountPropertyName" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="None" />
    <xs:enumeration value="TrackingUrlTemplate" />
    <xs:enumeration value="MSCLKIDAutoTaggingEnabled" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="msclkidautotaggingenabled"></a>MSCLKIDAutoTaggingEnabled|Used to get or set the property that determines whether MSCLKID auto-tagging is enabled for the account.|
|<a name="none"></a>None|Reserved for internal use.|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Used to get or set the account's tracking template.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[AccountProperty](accountproperty.md)  
[GetAccountProperties](getaccountproperties.md)  
