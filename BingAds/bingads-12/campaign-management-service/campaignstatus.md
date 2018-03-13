---
title: CampaignStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of a campaign.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CampaignStatus Value Set - Campaign Management
Defines the possible status values of a campaign.

## Syntax
```xml
<xs:simpleType name="CampaignStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="Active" />
    <xs:enumeration value="Paused" />
    <xs:enumeration value="BudgetPaused" />
    <xs:enumeration value="BudgetAndManualPaused" />
    <xs:enumeration value="Deleted" />
    <xs:enumeration value="Suspended" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The campaign is active, which indicates that the campaign's ads can be served.|
|<a name="budgetandmanualpaused"></a>BudgetAndManualPaused|The campaign is paused, which indicates that the campaign's ads will not serve. This status results when a user sets the campaign status to paused after the service pauses the campaign because the budget is depleted.|
|<a name="budgetpaused"></a>BudgetPaused|The campaign is paused, which indicates that the campaign's ads will not serve. The service sets this status when the budget is depleted. The service will set the status back to *Active* when the budget is restored.|
|<a name="deleted"></a>Deleted|The campaign is deleted. This status is for internal use only. Because all Get operations do not return deleted objects, you will not see an object with this status.|
|<a name="paused"></a>Paused|The campaign is paused, which indicates that the campaign's ads will not serve.|
|<a name="suspended"></a>Suspended|Your campaign has been suspended and no ads are eligible for delivery because of potentially fraudulent activity. <br />Please contact [Bing Ads Support](http://go.microsoft.com/fwlink/?LinkId=269631).|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[Campaign](campaign.md)  
