---
title: RemarketingTargetingSetting Value Set
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# RemarketingTargetingSetting Value Set
The targeting setting that is applicable for all audiences e.g., custom audiences and remarketing lists that are associated with this ad group. Each audience can be associated with multiple ad groups, and each ad group's remarketing targeting setting is applied independently for delivery. 

## Syntax
```xml
<xs:simpleType name="RemarketingTargetingSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="BidOnly" />
    <xs:enumeration value="TargetAndBid" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="bidonly"></a>BidOnly|Show ads to people searching for your ad, with the option to change the bid amount for people included in the audience. Ads in this ad group can show to everyone but the bid adjustment will apply to people included in the audience.<br/><br/>**Note:** Bing Ads won't apply any bid boosts until the associated audience has at least 1000 users.|
|<a name="targetandbid"></a>TargetAndBid|Show ads only to people included in the audience, with the option to change the bid amount. Ads in this ad group will only show to people included in the audience.|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AdGroup](adgroup.md)  
