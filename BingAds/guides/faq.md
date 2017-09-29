---
title: "Frequently Asked Questions"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Frequently Asked Questions
This article contains answers to some frequently asked questions about the Bing Ads API.

## Q. What are the requirements to use the Bing Ads API?
To [get started](~/guides/get-started.md), you need to sign up for a [Bing Ads](https://secure.bingads.microsoft.com) account, and then get your developer token at the [Developer Portal](https://developers.bingads.microsoft.com/Account). 

## Q. Which programming languages and SDKs are supported?
You can develop Bing Ads applications with any programming language that supports web services. The [Bing Ads Software Development Kits (SDK)](~/guides/client-libraries.md) enhance the experience of developing Bing Ads applications with .NET, Java, PHP, and Python languages.  Each SDK includes a proxy to all Bing Ads API web services and abstracts low level details of authentication with OAuth. You can use the high level BulkServiceManager and ReportingServiceManager interfaces to abstract and execute operations in the low level Bulk and Reporting services. 

We have heard requests for additional SDKs e.g. Perl and Ruby, although there is no plan to add support in the near term.

## Q. Which API version should I use?
You should always use the latest version as soon as we announce support via the [blog](https://blogs.msdn.microsoft.com/bing_ads_api/) or [release notes](~/guides/release-notes.md). As of May 2017 Version 11 is the highest supported version for Ad Insight, Bulk, Campaign Management API, Customer Billing, Customer Management, and Reporting API. 

## Q. Should I use the Bulk or Campaign Management API?
The [Bulk service](~/bulk/bulk-service-reference.md) is recommended, especially if you need to add or update ads and keywords across multiple ad groups or campaigns in an account. Some features are not available in Bulk e.g. [AddUetTags](~/campaign-management/adduettags.md), [GetBMCStoresByCustomerId](~/campaign-management/getbmcstoresbycustomerid.md), [GetGeoLocationsFileUrl](~/campaign-management/getgeolocationsfileurl.md), and [GetMediaByIds](~/campaign-management/getmediabyids.md). For these features of course you must use the [Campaign Management service](~/campaign-management/campaign-management-service-reference.md). 

## Q. Which API performance reports are available and when will my data be available?
The Reporting service supports most of the same [report types](~/guides/report-types.md) that you can find in the Bing Ads web application. Be sure to check out the [Report Attributes and Performance Statistics](~/guides/report-attributes-performance-statistics.md) and [Reporting Data Retention Time Periods](~/guides/report-data-retention-time-periods.md) guides for availability details.

When a user clicks an ad, it can take up to two hours for the system to process the click (3 hours for conversions) and make it available for reporting. When all data for the previous day have been processed and made available for reporting, this state is referred to as Books Closed. For more information about when the books are closed for reporting, see [Determining When the Books Close](~/guides/reports.md#booksclose).

## Q. I want to run my application without user interaction. How can I authenticate without getting prompted for permission to use Bing Ads credentials?
To programatically manage a Bing Ads account, you must provide consent at least once through the web application consent flow. For repeat or long term authentication, you should follow the [authorization code grant flow](~/guides/authentication-oauth.md#authorizationcode) for obtaining an access token and refresh token. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. You may need to request user consent again for example, if the Microsoft Account password was changed or the Microsoft Account owner removed permissions for your application to authenticate on their behalf. 

## Q. When do the access and refresh tokens expire?
The access token typically expires after one hour, although you should always check the expiration time each time you request a new token. The refresh token does not have a published duration or expiration time, although you can expect it to last up to 1 year. As a best practice you should always securely store the latest refresh token each time you request new access and refresh tokens. 

