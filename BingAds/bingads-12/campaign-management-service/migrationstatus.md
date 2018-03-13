---
title: MigrationStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible migration status values.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# MigrationStatus Value Set - Campaign Management
Defines the possible migration status values.

## Syntax
```xml
<xs:simpleType name="MigrationStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="NotInPilot" />
    <xs:enumeration value="NotStarted" />
    <xs:enumeration value="InProgress" />
    <xs:enumeration value="Completed" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="completed"></a>Completed|The migration is complete, or migration is not needed because the account was created after all of the customer's other accounts were added to the pilot queue for the corresponding migration type.|
|<a name="inprogress"></a>InProgress|The migration is in progress.|
|<a name="notinpilot"></a>NotInPilot|None of the accounts for the customer are in the queue for the corresponding migration type. All of a customer's accounts are added to pilot at the same time. A customer cannot have a subset of their accounts in pilot.|
|<a name="notstarted"></a>NotStarted|The account is in the queue for the corresponding migration type, but the migration has not yet begun.|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[MigrationStatusInfo](migrationstatusinfo.md)  
