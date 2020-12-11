---
title: "Microsoft Advertising Sandbox"
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Microsoft Advertising provides an API sandbox environment where you can test your application before deploying it to the production environment.
---
# Microsoft Advertising Sandbox
Microsoft Advertising provides an API sandbox environment where you can test your application before deploying it to the production environment. Ads that you create in sandbox are not served. Supported services in sandbox vary from production. To get the web service addresses for supported services, see [Bing Ads API Web Service Addresses](web-service-addresses.md).

> [!NOTE]
> Sandbox may be down for maintenance, with or without prior notification. Efforts will be made to notify users before sandbox downtime. 

## <a name="access"></a>Get Sandbox Access
The sandbox and production environments use separate credentials. 

Although in production you must use your own developer token, all Microsoft Advertising customers can use the following universal developer token in sandbox. 

```string
BBD37VB98
```

Although in production you must use your own application ID (a.k.a. client ID), all Microsoft Advertising customers can use the following public application ID in sandbox. 

```string
db41b09d-6e50-4f4a-90ac-5a99caefb52f
```

> [!NOTE]
> The "Sandbox Tutorial App" client ID is limited to desktop or console applications, and cannot be used with any client secret in a web application. You can use this for testing authentication locally in sandbox, and then register your own production application for more advanced scenarios e.g., web applications with custom redirect URIs. 
> 
> Note the sandbox application registration site at [apps.dev.microsoft-int.com/#/appList](https://apps.dev.microsoft-int.com/#/appList) has been deprecated since May 2019 and functionality for registering and managing converged applications removed starting September 2019.

To authenticate with a Microsoft Account in sandbox you will follow the same work flow as described in [Live Connect](authentication-oauth-live-connect.md) for production; however, you will use different endpoints. Wherever you see endpoints mentioned in [Live Connect](authentication-oauth-live-connect.md), substitute them with the following sandbox endpoints. 

> [!NOTE]
> For Bing Ads API sandbox the [Live Connect](authentication-oauth-live-connect.md) endpoint is the only OAuth option. For production authentication the [Live Connect](authentication-oauth-live-connect.md) endpoint is no longer the recommended approach, so you should use the [Microsoft identity platform endpoint](authentication-oauth-identity-platform.md). For details see [Upgrade to the Microsoft identity platform endpoint FAQ](authentication-oauth.md#upgrade-identity-platform-faq).  

|Description|Production|Sandbox|
|---|---|---|
|Domain for email used when getting a Microsoft account|Any email address|outlook-int.com|
|Endpoint to change the Microsoft account password|[account.live.com/password/change](https://account.live.com/password/change)|[account.live-int.com/password/change](https://account.live-int.com/password/change)|
|Endpoint for OAuth requests via [Live Connect](authentication-oauth-live-connect.md)|login.live.com|login.live-int.com|

Also as mentioned above, supported services in sandbox vary from production. To get the web service addresses for sandbox, see [Bing Ads API Web Service Addresses](web-service-addresses.md).

### <a name="initial-sign-up"></a>Initial Customer Sign Up
Follow these steps to get a new sandbox customer. If you already have a sandbox customer and want to add a new user e.g., with Microsoft account credentials, you can skip to the [user invitation](#invite-user) steps.

1. Open a browser and navigate to [sandbox.bingads.microsoft.com](https://secure.sandbox.bingads.microsoft.com/)
2. Click **Sign up for Microsoft Advertising** or **Sign up now**
3. Select **Create a new email address** to create an MSA. Do not use an existing email address. 
4. Click **Next**
5. Enter an MSA email address. The email server must be outlook**-int**.com (for example, someone@outlook-int.com). 

   > [!IMPORTANT]
   > Sandbox supports MSAs created using an outlook**-int**.com email account only. You may not use an outlook.com email account. Also, you may not use an email account from another email service (for example, @contoso.com) even if the account is linked to an outlook.com or outlook**-int**.com email account. 

6. Finish the MSA work flow by specifying the rest of your user and security information. You will then be redirected to Microsoft Advertising to continue the sandbox customer and account sign up. 
7. Fill out the **Create Account** form
8. For **Import/Create Campaign**, click **Skip campaign creation**
9. For **Go Live**, click **Skip payment information**

### <a name="invite-user"></a>Invite More Users
To use OAuth in sandbox, you need a sandbox Microsoft account (MSA). If your sandbox customer does not yet have user credentials via a Microsoft account, you need to invite a user to work on your [sandbox](https://secure.sandbox.bingads.microsoft.com/) account via the following steps.

1. In Microsoft Advertising [sandbox](https://secure.sandbox.bingads.microsoft.com/), click your user name (upper right corner)
2. Click **Accounts & Billing**
3. Click **Users**
4. Click **Invite user**
5. Enter the email address of the user to invite. The email server must be outlook.com (for example, someone@outlook.com). 

   > [!IMPORTANT]
   > You may send invites to outlook.com email accounts only. You may not send invites to any other domain, even if the account is linked to an outlook.com email account. If you try to send an invite to another domain (for example, someone@contoso.com), the BingAds UI will show the invite as pending indefinitely (the invite is never sent).

6. Click **Send**

Microsoft Advertising sends an email invite to the user. If the invite doesn’t show up in the inbox, check the Junk Email folder. It may take a couple of minutes to receive the invite. The following steps show how to accept the invitation.

1. Open the email from Microsoft Advertising with subject line, Invitation to Microsoft Advertising
2. Click the embedded link
3. Select **Create a new email address** to create an MSA. Do not use an existing email address. 
4. Click **Next**
5. Enter an MSA email address. The email server must be outlook**-int**.com (for example, someone@outlook-int.com). 

   > [!IMPORTANT]
   > Sandbox supports MSAs created using an outlook**-int**.com email account only. You may not use an outlook.com email account. Also, you may not use an email account from another email service (for example, @contoso.com) even if the account is linked to an outlook.com or outlook**-int**.com email account. 

6. Finish the work flow by specifying the rest of your user information
7. Exit Microsoft Advertising after completing the MSA process.

After Bing creates the account, you may use the outlook**-int**.com credentials in sandbox and during [app registration](authentication-oauth-live-connect.md#registerapplication).

> [!NOTE]
> The MSA signup process returns you to the SI Microsoft Advertising user interface (ui.si.bingads.microsoft.com). After completing the MSA process, sign out of the SI interface and then sign in using your new MSA email address at [https://secure.sandbox.bingads.microsoft.com/](https://secure.sandbox.bingads.microsoft.com/).

## <a name="bestpractices"></a>Sandbox Best Practices
Sandbox should not be used in the same capacity as production.

- Make sure that when you deploy your application to the production environment, you use the production WSDLs and your production credentials. 
- Sandbox contains the current production release, and will be updated with feature previews with or without prior notification. 
- Capacity of the sandbox is less than that of production, and you should not use it to perform stress or capacity testing. 
- Please do not use more than one thread.  

## <a name="adinsight"></a>Ad Insight Service
Sandbox supports a limited set of keywords for testing Ad Insight service operations. You should not use the test data to infer or expect similar estimates for your keywords in production. Some of the limitations are described in the following table. 

> [!TIP]
> Use the Ad Insight service in production instead of sandbox. Sandbox only offers a subset of production service operations, and the insight data lags behind production. Sandbox opportunity data is refreshed and updated each weekend, and is available by Monday. The keyword idea data in sandbox may lag behind production by several months. If an operation fails due to an invalid date range, try submitting the request again with an earlier date range.

|Service Operation|Sandbox Limitations|
|---------------------|-----------------------|
|[GetBidLandscapeByKeywordIds](../ad-insight-service/getbidlandscapebykeywordids.md)|Not supported. You can call the operation with existing keyword identifiers, but no data is returned.|
|[GetEstimatedBidByKeywordIds](../ad-insight-service/getestimatedbidbykeywordids.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.|
|[GetEstimatedBidByKeywords](../ad-insight-service/getestimatedbidbykeywords.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.|
|[GetEstimatedPositionByKeywordIds](../ad-insight-service/getestimatedpositionbykeywordids.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>To increase chance of getting an estimate, the *MaxBid* element should be more than or equal to 5 US Dollar, or the equivalent in other currencies.|
|[GetEstimatedPositionByKeywords](../ad-insight-service/getestimatedpositionbykeywords.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>To increase chance of getting an estimate, the *MaxBid* element should be more than or equal to 5 US Dollar, or the equivalent in other currencies.|
|[GetHistoricalKeywordPerformance](../ad-insight-service/gethistoricalkeywordperformance.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>The *MatchType* and *AdPosition* elements must be set to *Aggregate*.<br/><br/>The *Devices* element must be set to *Computers* or left nil.|
|[GetHistoricalSearchCount](../ad-insight-service/gethistoricalsearchcount.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>The *EndMonthAndYear* element must be set to the previous month. For example if today's date is April 1, 2020, the end month should be March 2020.<br/><br/>The *Devices* element must be set to *Computers* or left nil.|
|[GetKeywordCategories](../ad-insight-service/getkeywordcategories.md)|There should be no difference in sandbox versus production.|
|[GetKeywordDemographics](../ad-insight-service/getkeyworddemographics.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>The *Devices* element must be set to *Computers* or left nil.|
|[GetKeywordIdeas](../ad-insight-service/getkeywordideas.md)|Sandbox test data is refreshed every 3 months, so you will need to set an earlier dater range.|
|[GetKeywordLocations](../ad-insight-service/getkeywordlocations.md)|A limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.<br/><br/>The *Devices* element must be set to *Computers* or left nil.|
|[SuggestKeywordsForUrl](../ad-insight-service/suggestkeywordsforurl.md)|There should be no difference in sandbox versus production.|
|[SuggestKeywordsFromExistingKeywords](../ad-insight-service/suggestkeywordsfromexistingkeywords.md)|If the SuggestionType is set to 1, there should be no difference in behavior compared to production.<br/><br/>For suggestion type values 2, 3, and 4, a limited set of keywords are supported: air, auto, best deals, booking, car information, care, deal of the day, discounts, entertainment, finances, games, hotel reviews, insurance comparison, sport, the hotel.|

## <a name="bulk"></a>Bulk Service
The file size limit for upload in production is 100MB or 2.5 million rows. For sandbox the limit is 20K rows. For more information, see [Bulk Download and Upload](bulk-download-upload.md).

## <a name="campaign"></a>Campaign Management Service

### <a name="editorialsupport"></a>Editorial Support
Sandbox supports limited editorial reviews and appeals. You cannot get the reasons for editorial issues in sandbox as you could in production, for example via the [GetEditorialReasonsByIds](../campaign-management-service/geteditorialreasonsbyids.md) service operation.

### <a name="productads"></a>Product Ads
Product ads are supported in sandbox in the United States. To be auto-approved you must create a catalog and a Microsoft Merchant Center store that ends with "sandbox" as follows.

1. In the Microsoft Advertising web application click on **Tools**.

2. Under **Management Tools**, click on **Microsoft Merchant Center**.

3. Click **Create store**, and enter a store name that ends with "**sandbox**" (case-insensitive).

4. Add your store info, select **Product Ads** under **Catalog settings**, and click **Finish**.

5. In your new store, click **Catalog management**, and then click **Create catalog**.

6. Add your catalog name, select **Manually upload file later** under **Catalog feed file**, and click **Save**.

## <a name="billing"></a>Customer Billing Service
Payment methods are not supported in sandbox. 

## <a name="reporting"></a>Reporting Service
When you create a keyword, test performance data should be generated within a few hours. The data is provided to test generating, retrieving, and parsing reports in the sandbox. You should not use the test data to infer or expect similar performance for your keywords in production. 

Test data is generated only for the same day when the entity was added or updated. For example if you add a keyword today and download a keyword performance report for last week, there won’t be any data. You would have to pull a report that includes today in the report time period.

The following reports can return performance data in sandbox. All other report types can be submitted successfully, although the sandbox service will not return any example data i.e., the report download URL will be not be set when you poll for results.

- [AccountPerformanceReportRequest](../reporting-service/accountperformancereportrequest.md)  
- [AdDynamicTextPerformanceReportRequest](../reporting-service/addynamictextperformancereportrequest.md)  
- [AdGroupPerformanceReportRequest](../reporting-service/adgroupperformancereportrequest.md)  
- [AdPerformanceReportRequest](../reporting-service/adperformancereportrequest.md)  
- [CallDetailReportRequest](../reporting-service/calldetailreportrequest.md)  
- [CampaignPerformanceReportRequest](../reporting-service/campaignperformancereportrequest.md)  
- [DestinationUrlPerformanceReportRequest](../reporting-service/destinationurlperformancereportrequest.md)  
- [KeywordPerformanceReportRequest](../reporting-service/keywordperformancereportrequest.md)  
- [UserLocationPerformanceReportRequest](../reporting-service/userlocationperformancereportrequest.md)  

