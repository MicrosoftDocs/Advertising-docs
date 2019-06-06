---
title: "Bing Ads API Release Notes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get information about changes to Bing Ads API Version 13 by month. 
---
# Bing Ads API Release Notes
See below for information about changes to Bing Ads API Version 13 by month. 

## <a name="june2019"></a>June 2019
See below for Bing Ads API updates during this calendar month. 

- [Feeds via Bulk API](#feeds-june2019)  

## <a name="feeds-june2019"></a>Feeds via Bulk API
The [Feed](../bulk-service/feed.md) and [Feed Item](../bulk-service/feed-item.md) Bulk records are added to support [Bulk download and upload](bulk-download-upload.md) of both [Ad Customizer Feeds](ad-customizer-feeds.md) and [Page Feeds](page-feeds.md). 

> [!NOTE]
> The Bulk API for feeds and documentation are subject to change.  

## <a name="may2019"></a>May 2019
See below for Bing Ads API updates during this calendar month. 

- [Assisted Conversions](#assistedconversions-may2019)  
- [Dynamic Search Ads Text Part 2](#textpart2dsa-may2019)  
- [Bing Ads API SDK Updates](#sdk-may2019)  

## <a name="assistedconversions-may2019"></a>Assisted Conversions
Assisted conversions are conversions resulting from the clicks on your ads that have received co-bids from your manufacturer partners. This performance statistic is only applicable for cooperative shopping campaigns. The AssistedConversions column is added to the following reports.

- [ProductDimensionPerformanceReportColumn Value Set](../reporting-service/productdimensionperformancereportcolumn.md)  
- [ProductPartitionPerformanceReportColumn Value Set](../reporting-service/productpartitionperformancereportcolumn.md)  
- [ProductPartitionUnitPerformanceReportColumn Value Set](../reporting-service/productpartitionunitperformancereportcolumn.md)  
- [ProductSearchQueryPerformanceReportColumn Value Set](../reporting-service/productsearchqueryperformancereportcolumn.md)  

## <a name="textpart2dsa-may2019"></a>Dynamic Search Ads Text Part 2
Dynamic Search Ads Text Part 2 is available for pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 600). Later this year it will be available in all customers. 

The [TextPart2](../campaign-management-service/dynamicsearchad.md#textpart2) element is available in the [DynamicSearchAd](../campaign-management-service/dynamicsearchad.md) Campaign Management object. The [Text Part 2](../bulk-service/dynamic-search-ad.md#textpart2) field is available in the [Dynamic Search Ad](../bulk-service/dynamic-search-ad.md#textpart2) Bulk record. 

### <a name="sdk-may2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.2), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.2), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.2), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.2) SDK version 12.13.2. 

## <a name="april2019"></a>April 2019
See below for Bing Ads API updates during this calendar month. 

- [New Production OAuth Endpoint](#oauth-april2019)  
- [Bing Ads API SDK Updates](#sdk-april2019)  
- [Version 13 General Availability](#v13-april2019)  

## <a name="oauth-april2019"></a>New Production OAuth Endpoint
The [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md) for developers is now available. The Microsoft identity platform endpoint allows both work or school accounts from Azure AD and personal Microsoft accounts (MSA), such as hotmail.com, outlook.com, and msn.com. The [Live Connect](authentication-oauth-live-connect.md) endpoint only allows authentication with personal accounts. 

> [!IMPORTANT]
> Even if your users do not have work or school accounts, and even if you do not use the Bing Ads API SDKs we encourage you to update the authorization URL during calendar year 2019, since the Live Connect endpoint is no longer the recommended approach for Microsoft Advertising users. For details see [Upgrade to the Microsoft identity platform endpoint FAQ](authentication-oauth.md#upgrade-identity-platform-faq) and [Authentication with the Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). 

### <a name="sdk-april2019"></a>Bing Ads API SDK Updates
The Bing Ads .NET, Java, Php, and Python SDKs are updated with support for version 13. For details please see release notes for Microsoft Advertising [.NET](https://github.com/BingAds/BingAds-dotNet-SDK/releases/tag/v12.13.1), [Java](https://github.com/BingAds/BingAds-Java-SDK/releases/tag/v12.13.1), [Php](https://github.com/BingAds/BingAds-PHP-SDK/releases/tag/v0.12.13.1), and [Python](https://github.com/BingAds/BingAds-Python-SDK/releases/tag/v12.13.1) SDK version 12.13.1. 

### <a name="v13-april2019"></a>Version 13 General Availability
Bing Ads API version 13 is now generally available. With the availability of Bing Ads API version 13, version 12 is deprecated and will sunset by October 31, 2019. For more details, see [Migrate to Version 13](migration-guide.md).  

## <a name="march2019"></a>March 2019
See below for Bing Ads API updates during this calendar month. 

- [Version 13 Preview](#v13-march2019)  

### <a name="v13-march2019"></a>Version 13 Preview
Bing Ads API version 13 is available for preview. For more details about migrating from version 12, see [Migrate to Version 13](migration-guide.md). 
