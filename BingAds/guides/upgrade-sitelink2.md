---
title: "Upgrade from Multiple Sitelinks to One Sitelink Per Extension"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Upgrade from Multiple Sitelinks to One Sitelink Per Extension.
---
# Upgrade from Multiple Sitelinks to One Sitelink Per Extension
> [!NOTE]
> During calendar year 2017, Bing Ads upgraded all [Sitelink Ad Extension](../bulk-service/sitelink-ad-extension.md) records (contains multiple sitelinks per ad extension) to [Sitelink2 Ad Extension](../bulk-service/sitelink2-ad-extension.md) records (contains one sitelink per ad extension). In a future version of the API the deprecated sitelink programming interface will be consolidated and the '2' suffix will be removed from the new sitelink ad extensions.

Use this guide to prepare for migration from multiple sitelinks to one sitelink per ad extension. The sections below describe what you can expect before, during, and after migration.

The pre-migration ad extension ID will be deleted and new sitelink ad extensions will be created with new IDs. Reporting data for pre-migration sitelinks will be rolled up with the new IDs.

During migration the existing campaigns, ads, and extensions will continue to run. The editorial status of the pre-migrated ad extension will be copied to the new ad extensions, so that post-migration there will be no change in status or delays to delivery.   

> [!NOTE]
> It is not possible to have a "mixed mode" with both the deprecated sitelink extension type and new sitelink2 extension type in the same account. Each account will either have the deprecated type or the new type. All accounts per customer will be added to pilot at the same time, although each account will be migrated independently. You can expect each account to be migrated in parallel, although there could be a period of time where accounts for the same customer have different migration statuses.

## <a name="getmigrationstatus"></a> Checking for Migration Status
You should use the [GetAccountMigrationStatuses](~/campaign-management-service/getaccountmigrationstatuses.md) operation to determine which sitelink data model is in effect for each account. The operation will return one of the [MigrationStatus](~/campaign-management-service/migrationstatus.md) values listed in the table below. The sitelink data types that you can manage depend upon the migration status. Please see [Before Migration](#beforemigration), [During Migration](#migrationinprogress), and [After Migration](#migrationcompleted) for details.  

Migration Status|Bulk Records|Campaign Management Objects  
---------|---------|---------
NotInPilot, NotStarted|[Sitelink Ad Extension](~/bulk-service/sitelink-ad-extension.md)<br/>[AdGroup Sitelink Ad Extension](~/bulk-service/adgroup-sitelink-ad-extension.md)<br/>[Campaign Sitelink Ad Extension](~/bulk-service/campaign-sitelink-ad-extension.md) |[SiteLinksAdExtension](~/campaign-management-service/sitelinksadextension.md)<br/>[SiteLink](~/campaign-management-service/sitelink.md)         
InProgress|None|None         
Completed|[Sitelink2 Ad Extension](~/bulk-service/sitelink2-ad-extension.md)<br/>[Ad Group Sitelink2 Ad Extension](~/bulk-service/ad-group-sitelink2-ad-extension.md)<br/>[Campaign Sitelink2 Ad Extension](~/bulk-service/campaign-sitelink2-ad-extension.md) |[Sitelink2AdExtension](~/campaign-management-service/sitelink2adextension.md) 

## <a name="beforemigration"></a>Before Migration
Before migration the [GetAccountMigrationStatuses](~/campaign-management-service/getaccountmigrationstatuses.md) operation will return the [MigrationStatus](~/campaign-management-service/migrationstatus.md) value of either *NotInPilot* or *NotStarted*, and you can continue to add, delete, get, and update multiple sitelinks per ad extension. 

For example, when using the [Campaign Management](~/campaign-management-service/campaign-management-service-reference.md) service to retrieve [SiteLinksAdExtension](~/campaign-management-service/sitelinksadextension.md) objects you should continue to use the *SiteLinksAdExtension* value of the [AdExtensionsTypeFilter](~/campaign-management-service/adextensionstypefilter.md) value set when calling the [GetAdExtensionIdsByAccountId](~/campaign-management-service/getadextensionidsbyaccountid.md), [GetAdExtensionsAssociations](~/campaign-management-service/getadextensionsassociations.md), and [GetAdExtensionsByIds](~/campaign-management-service/getadextensionsbyids.md) operations. If you attempt to use the *Sitelink2AdExtension* filter, the *AdExtensionPilotNotEnabledForCustomer* error will be returned.

When using the [Bulk](~/bulk-service/bulk-service-reference.md) service you should continue to use the *SiteLinksAdExtensions*, *AdGroupSiteLinksAdExtensions*, and *CampaignSiteLinksAdExtensions* values of the [DownloadEntity](~/bulk-service/downloadentity.md) value set to download the corresponding [Sitelink Ad Extension](~/bulk-service/sitelink-ad-extension.md), [AdGroup Sitelink Ad Extension](~/bulk-service/adgroup-sitelink-ad-extension.md), and [Campaign Sitelink Ad Extension](~/bulk-service/campaign-sitelink-ad-extension.md) records in a Bulk file.  

> [!NOTE]
> After migration to sitelink2 ad extensions if you request a delta download where *LastSyncTimeInUTC* is set prior to the migration, and if you request *SiteLinksAdExtensions* in the download, the result file will include [Sitelink Ad Extension](~/bulk-service/sitelink-ad-extension.md) with *Status* set to *Deleted*. 

## <a name="migrationinprogress"></a>During Migration
During migration the [GetAccountMigrationStatuses](~/campaign-management-service/getaccountmigrationstatuses.md) operation will return the [MigrationStatus](~/campaign-management-service/migrationstatus.md) value of *InProgress*, and you will be unable to make changes to Sitelink Extensions of any data type until this is completed. From this point forward the service will not accept or return the pre-migration data types. 

## <a name="migrationcompleted"></a>After Migration
After migration the [GetAccountMigrationStatuses](~/campaign-management-service/getaccountmigrationstatuses.md) operation will return the [MigrationStatus](~/campaign-management-service/migrationstatus.md) value of *Completed*, and from this point forward you must use the new data model with one sitelink per ad extension. After migration the service will not accept or return the pre-migration data types. 

For example, when using the [Campaign Management](~/campaign-management-service/campaign-management-service-reference.md) service to retrieve [Sitelink2AdExtension](~/campaign-management-service/sitelink2adextension.md) objects you must use the *Sitelink2AdExtension* value of the [AdExtensionsTypeFilter](~/campaign-management-service/adextensionstypefilter.md) value set when calling the [GetAdExtensionIdsByAccountId](~/campaign-management-service/getadextensionidsbyaccountid.md), [GetAdExtensionsAssociations](~/campaign-management-service/getadextensionsassociations.md), and [GetAdExtensionsByIds](~/campaign-management-service/getadextensionsbyids.md) operations. If you attempt to use the *SiteLinksAdExtensions* filter, the *CampaignServiceInvalidAdExtensionType* error will be returned.

When using the [Bulk](~/bulk-service/bulk-service-reference.md) service you must use the *Sitelink2AdExtensions*, *AdGroupSitelink2AdExtensions*, and *CampaignSitelink2AdExtensions* values of the [DownloadEntity](~/bulk-service/downloadentity.md) value set to download the corresponding [Sitelink2 Ad Extension](~/bulk-service/sitelink2-ad-extension.md), [Ad Group Sitelink2 Ad Extension](~/bulk-service/ad-group-sitelink2-ad-extension.md), and [Campaign Sitelink2 Ad Extension](~/bulk-service/campaign-sitelink2-ad-extension.md) records in a Bulk file.  


## See Also
[Bing Ads Web Service Addresses](web-service-addresses.md)  

