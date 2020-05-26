---
title: ImportEntityStatistics Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: The statistical import results for an entity type.
---
# ImportEntityStatistics Data Object - Campaign Management
The statistical import results for an entity type.

## Syntax
```xml
<xs:complexType name="ImportEntityStatistics" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Additions" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="Changes" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="Deletions" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="EntityType" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Errors" nillable="true" type="xs:int" />
    <xs:element minOccurs="0" name="Total" nillable="true" type="xs:int" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="additions"></a>Additions|The count of items added during import of the [entity type](#entitytype).|**int**|
|<a name="changes"></a>Changes|The count of items changed or updated during import of the [entity type](#entitytype).|**int**|
|<a name="deletions"></a>Deletions|The count of items deleted during import of the [entity type](#entitytype).|**int**|
|<a name="entitytype"></a>EntityType|The type of entity eligible for import.<br/><br/>For more information, see the [remarks](#remarks) below.|**string**|
|<a name="errors"></a>Errors|The count of errors during import of the [entity type](#entitytype).|**int**|
|<a name="total"></a>Total|The total count of additions, changes, deletions, and errors during import of the [entity type](#entitytype).|**int**|

## <a name="remarks"></a>Remarks
Import additions, updates, deletions, and errors results are available for the following entity types. New entity types might be added in the future, so you should not take any dependency on a fixed set of values. You can download similar Google import entity statistics as follows via the Microsoft Advertising web application. 

```txt
Campaigns
Ad Groups
Ads
Keywords
Ad extensions
Product Groups
Campaign Criteria
Campaign Auto Target Exclusions
Ad Group Auto Targets and Exclusions
Campaign Negative Keywords
Ad Group Negative Keywords
Campaign Negative Sites
Ad Group Negative Sites
Negative Keyword Lists
Shared Negative Keywords
Campaign Device Targets
Ad Group Device Targets
Campaign Day Time Targets
Ad Group Day Time Targets
Campaign Location Targets
Ad Group Location Targets
Campaign Negative Location Targets
Ad Group Negative Location Targets
Campaign Location Intent Targets
Ad Group Location Intent Targets
Campaign Radius Targets
Ad Group Radius Targets
Campaign Age Targets
Ad Group Age Targets
Ad Group Negative Age Targets
Campaign Gender Targets
Ad Group Gender Targets
Ad Group Negative Gender Targets
Campaign In-market Audience Targets
Ad Group In-market Audience Targets
Campaign Negative In-market Audience Targets
Ad Group Negative In-market Audience Targets
Feeds
Feed items
Remarketing lists
Combined lists
Ad Group Remarketing List Targets
Ad Group Negative Remarketing List Targets
Campaign Remarketing List Targets
Campaign Negative Remarketing List Targets
Ad Group Combined List Targets
Ad Group Negative Combined List Targets
Campaign Combined List Targets
Campaign Negative Combined List Targets
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[ImportResult](importresult.md)  
