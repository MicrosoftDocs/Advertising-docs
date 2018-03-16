---
title: NegativeKeywordConflictReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes columns that you can include in the NegativeKeywordConflictReportRequest.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# NegativeKeywordConflictReportColumn Value Set - Reporting
Defines the attributes columns that you can include in the [NegativeKeywordConflictReportRequest](negativekeywordconflictreportrequest.md).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

## Syntax
```xml
<xs:simpleType name="NegativeKeywordConflictReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="Keyword" />
    <xs:enumeration value="KeywordId" />
    <xs:enumeration value="NegativeKeyword" />
    <xs:enumeration value="ConflictLevel" />
    <xs:enumeration value="BidMatchType" />
    <xs:enumeration value="NegativeKeywordListId" />
    <xs:enumeration value="NegativeKeywordList" />
    <xs:enumeration value="NegativeKeywordId" />
    <xs:enumeration value="NegativeKeywordMatchType" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="KeywordStatus" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Bing Ads assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Bing Ads assigned number of an account.|
|<a name="accountstatus"></a>AccountStatus|The current account status.|
|<a name="adgroupid"></a>AdGroupId|The Bing Ads assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The current ad group status.|
|<a name="bidmatchtype"></a>BidMatchType|The keyword bid match type. This can be different from the *DeliveredMatchType* column, for example if you bid on a broad match and the search term was an exact match. For more information, see [Budget and Bid Strategies](../guides/budget-bid-strategies.md).The possible values are *Broad*, *Exact*, *Phrase*, and *Unknown*.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The current campaign status.|
|<a name="conflictlevel"></a>ConflictLevel|The entity level where the keyword and negative keyword conflict occurs.The possible values are AdGroup and Campaign.|
|<a name="keyword"></a>Keyword|The keyword text.|
|<a name="keywordid"></a>KeywordId|The Bing Ads assigned identifier of a keyword.|
|<a name="keywordstatus"></a>KeywordStatus|The current keyword status.|
|<a name="negativekeyword"></a>NegativeKeyword|The negative keyword text.|
|<a name="negativekeywordid"></a>NegativeKeywordId|The Bing Ads assigned identifier of a negative keyword.|
|<a name="negativekeywordlist"></a>NegativeKeywordList|The name of the negative keyword list.|
|<a name="negativekeywordlistid"></a>NegativeKeywordListId|The Bing Ads assigned identifier of a negative keyword list.|
|<a name="negativekeywordmatchtype"></a>NegativeKeywordMatchType|The type of match to compare the negative keyword and the user's search term. The possible values for a negative keyword are *Exact* and *Phrase*.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|AccountName|
|Keyword|
|NegativeKeyword|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[NegativeKeywordConflictReportRequest](negativekeywordconflictreportrequest.md)  
