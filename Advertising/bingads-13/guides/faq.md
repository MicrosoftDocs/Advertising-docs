---
title: "Frequently Asked Questions"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Find answers to some frequently asked questions about the Bing Ads API.
---
# Frequently Asked Questions
This article contains answers to some frequently asked questions about the Bing Ads API.

## Get Help

### Q. Where can I get help?
The [Microsoft Q&A](https://docs.microsoft.com/answers/topics/advertising-api.html) forum is available for the developer community to ask and answer questions about the Bing Ads APIs and Microsoft Advertising Scripts. Microsoft monitors the forums and replies to questions that the community has not yet answered. 

> [!IMPORTANT]
> To make sure that we see your question, tag it with 'advertising-api'.  

If the investigation involves sensitive account or personal details, or if you are not finding the information you need to solve your problem via [Microsoft Q&A](https://docs.microsoft.com/answers/topics/advertising-api.html), please contact [Microsoft Advertising Support](https://about.ads.microsoft.com/en-us/microsoft-advertising-support). To resolve the issue efficiently, please provide support with the details requested in [Engaging Support](handle-service-errors-exceptions.md#contact-support). 

### Q. How can I find out about changes?
The [Release Notes](release-notes.md) and [Migration Guide](migration-guide.md) are great resources to start with. 

You can sign up for the monthly newsletter via the [News](https://developers.ads.microsoft.com/News) tab of the Developer Portal, and that's also where the latest [blog](https://go.microsoft.com/fwlink/?linkid=2026358) announcements are aggregated. 

## Get Started

### Q. What are the requirements to use the Bing Ads API?
To [get started](get-started.md), you need to sign up for a [Microsoft Advertising](https://ads.microsoft.com/) account, and then get your developer token at via the [Account](https://developers.ads.microsoft.com/Account) tab of the Developer Portal. 

### Q. Which programming languages and SDKs are supported?
You can develop Bing Ads API applications with any programming language that supports web services. The [Bing Ads API Software Development Kits (SDK)](client-libraries.md) enhance the experience of developing Bing Ads API applications with .NET, Java, PHP, and Python languages. Each SDK includes a proxy to all Bing Ads API web services and abstracts low level details of authentication with OAuth. You can use the high level BulkServiceManager and ReportingServiceManager interfaces to abstract and execute operations in the low level Bulk and Reporting services. 

We have heard requests for additional SDKs e.g. Perl and Ruby, although there is no plan to add support in the near term.

### Q. How can I view code samples in different programming languages?
In addition to the [Code Examples](code-examples.md) and services [Reference](reference.md) sections, you'll find code snippets in many of the technical guides e.g., the [Get Started](get-started.md) guide. You can use the language selector at the top or right of those pages to view examples in CSharp, Java, Php, or Python. When you choose a language, the setting is retained as you navigate other pages. The language selector will only include languages that have samples for that specific page, and will default to C# if the language you had previously set is not available for the page that you navigated to. 

### Q. Which API version should I use?
You should always use the latest version as soon as we announce support via the [blog](https://go.microsoft.com/fwlink/?linkid=2026358) or [release notes](release-notes.md). 

### Q. How can I view documentation and code examples for different versions of the API?
To navigate between versions, use the version selector near the table of contents at the top and left side of the page. 

![API Docs Version Selector](media/api-docs-version-selector.png "API Docs Version Selector")  

The ```view``` query string parameter will be updated and appended to the URL e.g., ```?view=bingads-13```. By default when you navigate to a page without any ```view``` query string parameter, the content for the latest generally available version will be shown even when a higher API version is available for preview. 

## Feature Availability

### Q. Should I use the Bulk or Campaign Management API?
The [Bulk service](../bulk-service/bulk-service-reference.md) is recommended, especially if you need to add or update ads and keywords across multiple ad groups or campaigns in an account. Some features are not available in Bulk e.g. [AddUetTags](../campaign-management-service/adduettags.md), [GetBMCStoresByCustomerId](../campaign-management-service/getbmcstoresbycustomerid.md), [GetGeoLocationsFileUrl](../campaign-management-service/getgeolocationsfileurl.md), and [GetMediaMetaDataByAccountId](../campaign-management-service/getmediametadatabyaccountid.md). For these features of course you must use the [Campaign Management service](../campaign-management-service/campaign-management-service-reference.md). 

### Q. Which API performance reports are available and when will my data be available?
The Reporting service supports most of the same [report types](report-types.md) that you can find in the Microsoft Advertising web application. Be sure to check out the [Report Attributes and Performance Statistics](report-attributes-performance-statistics.md) and [Reporting Data Retention Time Periods](report-data-retention-time-periods.md) guides for availability details.

When a user clicks an ad, it can take up to two hours for the system to process the click (3 hours for conversions) and make it available for reporting. When all data for the previous day have been processed and made available for reporting, this state is referred to as Books Closed. For more information about when the books are closed for reporting, see [Time Zones in Reporting](reports.md#reptimezones).

## OAuth 

### Q. I want to run my application without user interaction. How can I authenticate without getting prompted for permission to use Microsoft Advertising credentials?
To programmatically manage a Microsoft Advertising account, you must provide consent at least once through the web application consent flow. For repeat or long term authentication, you should follow the [authorization code grant flow](authentication-oauth.md) for obtaining an access token and refresh token. Thereafter you can use the latest refresh token to request new access and refresh tokens without any further user interaction. You may need to request user consent again for example, if the Microsoft Account owner went through account recovery, changed their password, or otherwise removed permissions for your application to authenticate on their behalf. 

### Q. When do the access and refresh tokens expire?
The access token typically expires after one hour, although you should always check the expiration time each time you request a new token. 

Refresh tokens are, and always will be, completely opaque to your application. They are long-lived e.g., 90 days for public clients, but the app should not be written to expect that a refresh token will last for any period of time. Refresh tokens can be invalidated at any moment, and the only way for an app to know if a refresh token is valid is to attempt to redeem it by making a token request. Even if you continuously refresh the token on the same device with the most recent refresh token, you should expect to start again and request user consent if, for example you signed the user out, the Microsoft Account user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf. At any time without prior warning Microsoft may determine that user consent should again be granted. As a best practice you should always securely store the latest refresh token each time you request new access and refresh tokens. 

### Q. Why do I need an access token and developer token?
The access token represents the user credentials who has access to one or more Microsoft Advertising accounts. The application ID (a.k.a. client_id) identifies your application for each Microsoft Advertising user who grants consent. The developer token gives your application permission to use the Bing Ads API. 

## Brand

### Q. Will Bing Ads API be rebranded along with the Microsoft Advertising platform?
Bing Ads is now Microsoft Advertising. Our new name reflects how we're growing our advertising solutions to help you reach more customers. There are no plans to rebrand any of the current API versions. The table below lists names that either have or haven't changed. For more information please see the [brand announcement](https://go.microsoft.com/fwlink/?linkid=2087052&s_cid=nowmsa_devportal). 

|Previous Name|Current Name|
|---------------|---------------|
|Ad Preview and Diagnostic Tool|Ad Preview and Diagnostic Tool|
|Bing Ads|Microsoft Advertising|
|Bing Ads Accredited Professionals|Bing Ads Accredited Professionals|
|Bing Ads API|Bing Ads API|
|Bing Ads App|Microsoft Advertising App|
|Bing Ads Content API|Bing Ads Content API|
|Bing Ads Editor|Microsoft Advertising Editor|
|Bing Ads Fans|Microsoft Advertising Fans|
|Bing Ads Intelligence|Microsoft Advertising Intelligence|
|Bing Ads Partner|Microsoft Advertising Partner|
|Bing Ads Scripts|Microsoft Advertising Scripts|
|Bing Ads SDK|Bing Ads SDK|
|Bing Hotel Center|Microsoft Hotel Center|
|Bing Merchant Center|Microsoft Merchant Center|
|Bing Network|Microsoft Advertising Network|
|Bing Network syndication|Microsoft Advertising Partner sites|
|Bing Partner Awards|Microsoft Advertising Partner Awards|
|Bing Partner Program|Microsoft Advertising Partner Program|
|Bing Shopping Campaigns|Microsoft Shopping Campaigns|
|Keyword Planner|Keyword Planner|
|Hotel Ads|Hotel Ads|
|Hotel API|Hotel API|
