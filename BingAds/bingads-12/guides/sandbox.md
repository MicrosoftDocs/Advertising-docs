---
title: "Bing Ads Sandbox"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Bing Ads provides an API sandbox environment where you can test your application before deploying it to the production environment.
---
# Bing Ads Sandbox
Bing Ads provides an API sandbox environment where you can test your application before deploying it to the production environment. Ads that you create in sandbox are not served. Supported services in sandbox vary from production. To get the web service addresses for supported services, see [Bing Ads Web Service Addresses](../guides/web-service-addresses.md).

> [!NOTE]
> Sandbox may be down for maintenance, with or without prior notification. Efforts will be made to notify users before sandbox downtime. Notifications are posted in the [Bing Ads Developer Blog](https://blogs.msdn.microsoft.com/bing_ads_api/).

## <a name="access"></a>Get Sandbox Access
The sandbox and production environments use separate credentials. Although in production you need to get your own developer token, all Bing Ads customers can use the following universal developer token in sandbox: **BBD37VB98**

New customers are required to sign up for Bing Ads with a Microsoft Account, and to manage those accounts you must use OAuth. Existing users with legacy Bing Ads credentials may continue to specify the *UserName* and *Password* header elements with Bing Ads API version 11. Starting with Bing Ads API version 12, only OAuth authentication will be supported. Managed credentials i.e., the *UserName* and *Password* header elements will not be supported.

> [!NOTE]
> SDK Support for OAuth in sandbox is coming soon. Please follow the [API blog](https://blogs.msdn.microsoft.com/bing_ads_api/) and [release notes](release-notes.md) for announcements.

To authenticate with a Microsoft Account in sandbox you will follow the same work flow as described in [Authentication with OAuth](../guides/authentication-oauth.md) for production; however, you will use different endpoints.

For the sandbox environment, the following are the endpoints you must use to get Microsoft accounts and your application's client ID. Wherever you see endpoints mentioned in [Authentication with OAuth](../guides/authentication-oauth.md), substitute them with the sandbox endpoints. 

|Description|Production|Sandbox|
|---|---|---|
|Endpoint for sandbox email used when getting a sandbox Microsoft account|Any email address|outlook-int.com|
|Endpoint for getting a sandbox client ID|apps.dev.microsoft.com/#/appList|apps.dev.microsoft-int.com/#/appList|
|Endpoint for OAuth requests|login.live.com|login.live-int.com|

Also as mentioned above, supported services in sandbox vary from production. To get the web service addresses for sandbox, see [Bing Ads Web Service Addresses](../guides/web-service-addresses.md).

Follow these steps to get a sandbox customer. If you already have a sandbox customer, you can skip to the user invitation steps.

1.	Open a browser and navigate to sandbox.bingads.microsoft.com
2.	Click **Sign up for Bing Ads** or **Sign up now**
3.	Fill out the **Create Account** form
4.	For **Import/Create Campaign**, click **Skip campaign creation**
5.	For **Go Live**, click **Skip payment information**

The above steps create a Bing Ads legacy user name that is not supported from Bing Ads API version 12 onwards. To use OAuth in sandbox, you need a sandbox Microsoft account (MSA). To get an MSA that you can use in sandbox, you need to invite a user to work on your account. The following steps show how to invite a user to work on your account.

1.	In Bing Ads, click your user name (upper right corner)
2.	Click **Accounts & Billing**
3.	Click **Users**
4.	Click **Invite user**
5.	Enter the email address of the user to invite. The email server must be outlook.com (for example, someone@outlook.com).
6.	Click **Send**

Bing Ads sends an email invite to the user. If the invite doesn’t show up in the inbox, check the Junk Email folder. It may take a couple of minutes to receive the invite. The following steps show how to accept the invitation.

1.	Open the email from Bing Ads with subject line, Invitation to Bing Ads
2.	Click the embedded link
3.	Select **Create a new email address** to create an MSA
4.	Click **Next**
5.	Enter an MSA email address. The email server must be outlook**-int**.com (for example, someone@outlook-int.com).
6.	Finish the work flow by specifying the rest of your user information
7.  Exit Bing Ads after completing the MSA process.

After Bing creates the account, you may use the MSA in sandbox.

> [!NOTE]
> The MSA signup process returns you to the SI Bing Ads user interface (ui.si.bingads.microsoft.com). After completing the MSA process, sign out of the SI interface and then sign in using your new MSA email address at [https://ui.sandbox.bingads.microsoft.com](https://ui.sandbox.bingads.microsoft.com).

## <a name="bestpractices"></a>Sandbox Best Practices
Sandbox should not be used in the same capacity as production.

-   Make sure that when you deploy your application to the production environment, you use the production WSDLs and your production credentials.  
-   Sandbox contains the current production release, and will be updated with feature previews with or without prior notification.  
-   Capacity of the sandbox is less than that of production, and you should not use it to perform stress or capacity testing.  
-   Please do not use more than one thread.    

## <a name="adinsight"></a>Ad Insight Service
Opportunities are updated daily in sandbox for existing campaigns, ad groups, and keywords to test the end to end coding workflow. You may get test opportunities for up to 1,000 keywords across all accounts per Bing Ads customer. You should not use the test data to infer or expect similar performance for your campaigns, ad groups, or keywords in production.

> [!NOTE]
> Sandbox opportunity data is refreshed and updated each weekend, and is available by Monday.

### <a name="supportedkeywords"></a>Supported Keywords
Sandbox supports a limited set of keywords for testing Ad Insight service operations. You should not use the test data to infer or expect similar estimates for your keywords in production. You may use the following set of keywords to test your application.

|Supported Keywords for Ad Insight Sandbox|
|---------------------------------------------|
|air|
|auto|
|best deals|
|booking|
|car information|
|care|
|deal of the day|
|discounts|
|entertainment|
|finances|
|games|
|hotel reviews|
|insurance comparison|
|sport|
|the hotel|

### <a name="ad-insight-serviceops"></a>Service Operations
Ad Insight service operations differ from production, and limitations are described in the following table.

|Service Operation|Sandbox Limitations|
|---------------------|-----------------------|
|[GetBidLandscapeByKeywordIds](~/ad-insight-service/getbidlandscapebykeywordids.md)|Not supported. You can call the operation with existing keyword identifiers, but no data is returned.|
|[GetEstimatedBidByKeywordIds](~/ad-insight-service/getestimatedbidbykeywordids.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).|
|[GetEstimatedBidByKeywords](~/ad-insight-service/getestimatedbidbykeywords.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).|
|[GetEstimatedPositionByKeywordIds](~/ad-insight-service/getestimatedpositionbykeywordids.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />To increase chance of getting an estimate, the *MaxBid* element should be more than or equal to 5 US Dollar, or the equivalent in other currencies.|
|[GetEstimatedPositionByKeywords](~/ad-insight-service/getestimatedpositionbykeywords.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />To increase chance of getting an estimate, the *MaxBid* element should be more than or equal to 5 US Dollar, or the equivalent in other currencies.|
|[GetHistoricalKeywordPerformance](~/ad-insight-service/gethistoricalkeywordperformance.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />The *MatchType* and *AdPosition* elements must be set to *Aggregate*.<br /><br />The *Devices* element must be set to *Computers* or left nil.|
|[GetHistoricalSearchCount](~/ad-insight-service/gethistoricalsearchcount.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />The *EndMonthAndYear* element must be set to the previous month. For example if today's date is October 10, 2017, the end month should be October 2017.<br /><br />The *Devices* element must be set to *Computers* or left nil.|
|[GetKeywordCategories](~/ad-insight-service/getkeywordcategories.md)|There should be no difference in sandbox versus production.|
|[GetKeywordDemographics](~/ad-insight-service/getkeyworddemographics.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />The *Devices* element must be set to *Computers* or left nil.|
|[GetKeywordLocations](~/ad-insight-service/getkeywordlocations.md)|A limited set of keywords are supported. For more information, see [Supported Keywords](#supportedkeywords).<br /><br />The *Devices* element must be set to *Computers* or left nil.|
|[SuggestKeywordsForUrl](~/ad-insight-service/suggestkeywordsforurl.md)|There should be no difference in sandbox versus production.|
|[SuggestKeywordsFromExistingKeywords](~/ad-insight-service/suggestkeywordsfromexistingkeywords.md)|If the SuggestionType is set to 1, there should be no difference in behavior compared to production.<br /><br />For suggestion type values 2, 3, and 4, the results are limited to the set of keywords provided in sandbox. For more information, see [Supported Keywords](#supportedkeywords).|

## <a name="bulk"></a>Bulk Service
The file size limit for upload in production is 100MB or 2.5 million rows. For sandbox the limit is 20K rows. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

## <a name="campaign"></a>Campaign Management Service

### <a name="editorialsupport"></a>Editorial Support
Sandbox supports limited editorial reviews and appeals. Sandbox does not support testing of editorial rejections reason operations, for example [GetEditorialReasonsByIds](~/campaign-management-service/geteditorialreasonsbyids.md).

#### Magic Terms
If you know of editorial terms that will fail editorial review, you can use them. Otherwise, to test your application's editorial logic, use the following format to construct a *magic* term that determines, by country, whether editorial will approve or reject the ad or keyword, or put it in a pending state. These magic terms are supported in sandbox only.

{*MatchType*}{*Language*}{*FlagArea*}{m}{*StatusPerCountry*}{m1}

You must specify a value for each component of the term.

|Component|Description|
|-------------|---------------|
|*MatchType*|Determines whether the magic term is the only word in the keyword. The following are the possible match-type values (not case sensitive) that you can specify.<br /><br />e - Exact. The keyword must contain only the magic term.<br /><br />p - Phrase. The keyword can contain other words in addition to the magic term.|
|*Language*|Determines the editorial guidelines to apply. You should specify the same language that the ad group specifies. The following are the possible language values (not case sensitive) that you can specify.<br /><br />EN - English<br /><br />FR - French<br /><br />DE - German|
|*FlagArea*|Determines the area of the editorial guidelines to apply to the term. The following are the possible guideline areas that you can specify.<br /><br />3 - Alcohol<br /><br />15 - Gambling<br /><br />97 - Adult Erotica<br /><br />To specify more than one flag area for a keyword, specify multiple phrase magic terms. For example, pen3m569m1 pen15m569m1.|
|m|Literal. Must be m.|
|*StatusPerCountry*|Determines the editorial status to return for each language. The integer is broken down into 2-bit fields. Each 2-bit field represents the editorial status to apply for the country.<br /><br />The following shows each country's position in the integer for each *Language* value. The *Language* value determines the countries that you can include in the integer. For example, for English, United States (US) is in the most significant position and Ireland (IE) is in the least significant position.<br /><br />EN - IESGINCAGBUS<br /><br />FR - FRCA<br /><br />DE - DECHAT<br /><br />You can set each country's 2-bit value to one of the following values.<br /><br />00 - Approved<br /><br />01 - Rejected<br /><br />10 - Pending inactive<br /><br />11 - Pending active<br /><br />For example, to specify that you want the term rejected for US and pending inactive for CA, you would set the integer's bit fields to 000000100001 (or decimal 33).|
|m1|Literal. Must be m1.|

##### Where to use the magic term
You can use magic terms in the following locations.

-   A text ad's *Title* element.  
-   A text ad's *Description* element.  
-   A keyword's *Text* element.  

##### Example magic term
If you specified a term using the following components, the resulting term would be pen3m569m1.

-   Match type: Phrase 
-   Language: English   
-   Flag area: Alcohol  
-   Editorial status per country: 569 (001000111001), which is broken out as follows.
    -   Rejected in US  
    -   Pending inactive in GB  
    -   Pending active in CA  
    -   Approved in IN  
    -   Pending inactive in SG  
    -   Approved in IE

### <a name="productads"></a>Product Ads
Product ads are supported in sandbox in the United States. To be auto-approved you must create a catalog and a Bing Merchant Center store that ends with "sandbox" as follows.

1.  In the Bing Ads web application click on **Tools**.

2.  Under **Management Tools**, click on **Bing Merchant Center**.

3.  Click **Create store**, and enter a store name that ends with "**sandbox**" (case-insensitive).

4.  Add your store info, select **Product Ads** under **Catalog settings**, and click **Finish**.

5.  In your new store, click **Catalog management**, and then click **Create catalog**.

6.  Add your catalog name, select **Manually upload file later** under **Catalog feed file**, and click **Save**.

## <a name="billing"></a>Customer Billing Service
The Customer Billing service is not supported in sandbox.

## <a name="customer"></a>Customer Management Service
Most customer management service operations are supported in sandbox. Unsupported features include [AddClientLinks](~/customer-management-service/addclientlinks.md) and [UpdateClientLinks](~/customer-management-service/updateclientlinks.md).

## <a name="reporting"></a>Reporting Service
When you create a keyword, test performance data should be generated within a few hours. The data is provided to test generating, retrieving, and parsing reports in the sandbox. You should not use the test data to infer or expect similar performance for your keywords in production. 

Test data is generated only for the same day when the entity was added or updated. For example if you add a keyword today and download a keyword performance report for last week, there won’t be any data. You would have to pull a report that includes today in the report time period.

The following reports can return performance data in sandbox. All other report types can be submitted successfully, although the sandbox service will not return any example data i.e., the report download URL will be not be set when you poll for results.

-   [AccountPerformanceReportRequest](~/reporting-service/accountperformancereportrequest.md)  
-   [AdDynamicTextPerformanceReportRequest](~/reporting-service/addynamictextperformancereportrequest.md)  
-   [AdGroupPerformanceReportRequest](~/reporting-service/adgroupperformancereportrequest.md)  
-   [AdPerformanceReportRequest](~/reporting-service/adperformancereportrequest.md)  
-   [CallDetailReportRequest](~/reporting-service/calldetailreportrequest.md)  
-   [CampaignPerformanceReportRequest](~/reporting-service/campaignperformancereportrequest.md)  
-   [DestinationUrlPerformanceReportRequest](~/reporting-service/destinationurlperformancereportrequest.md)  
-   [KeywordPerformanceReportRequest](~/reporting-service/keywordperformancereportrequest.md)  
-   [UserLocationPerformanceReportRequest](~/reporting-service/userlocationperformancereportrequest.md)  

