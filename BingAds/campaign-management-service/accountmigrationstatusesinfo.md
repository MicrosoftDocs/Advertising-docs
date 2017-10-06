---
title: AccountMigrationStatusesInfo Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that contains migration status for an account.
---
# AccountMigrationStatusesInfo Data Object
Defines an object that contains migration status for an account.

## Syntax
```xml
<xs:complexType name="AccountMigrationStatusesInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="AccountId" type="xs:long" />
    <xs:element minOccurs="0" name="MigrationStatusInfo" nillable="true" type="tns:ArrayOfMigrationStatusInfo" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The Bing Ads identifier of the account.|**long**|
|<a name="migrationstatusinfo"></a>MigrationStatusInfo|The list of migration status info for the corresponding account.|[MigrationStatusInfo](migrationstatusinfo.md) array|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetAccountMigrationStatuses](getaccountmigrationstatuses.md)  
