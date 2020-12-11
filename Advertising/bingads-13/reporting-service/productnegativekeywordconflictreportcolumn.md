---
title: ProductNegativeKeywordConflictReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes columns that you can include in the ProductNegativeKeywordConflictReportRequest.
---
# ProductNegativeKeywordConflictReportColumn Value Set - Reporting
Defines the attributes columns that you can include in the [ProductNegativeKeywordConflictReportRequest](productnegativekeywordconflictreportrequest.md).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

## Syntax
```xml
<xs:simpleType name="ProductNegativeKeywordConflictReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="AccountNumber" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AdGroupStatus" />
    <xs:enumeration value="MerchantProductId" />
    <xs:enumeration value="Title" />
    <xs:enumeration value="AdGroupCriterionId" />
    <xs:enumeration value="ProductGroup" />
    <xs:enumeration value="NegativeKeywordId" />
    <xs:enumeration value="NegativeKeyword" />
    <xs:enumeration value="NegativeKeywordListId" />
    <xs:enumeration value="ConflictLevel" />
    <xs:enumeration value="NegativeKeywordMatchType" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [ProductNegativeKeywordConflictReportColumn](productnegativekeywordconflictreportcolumn.md) value set has the following values: [AccountId](#accountid), [AccountName](#accountname), [AccountNumber](#accountnumber), [AccountStatus](#accountstatus), [AdGroupCriterionId](#adgroupcriterionid), [AdGroupId](#adgroupid), [AdGroupName](#adgroupname), [AdGroupStatus](#adgroupstatus), [CampaignId](#campaignid), [CampaignName](#campaignname), [CampaignStatus](#campaignstatus), [ConflictLevel](#conflictlevel), [MerchantProductId](#merchantproductid), [NegativeKeyword](#negativekeyword), [NegativeKeywordId](#negativekeywordid), [NegativeKeywordListId](#negativekeywordlistid), [NegativeKeywordMatchType](#negativekeywordmatchtype), [ProductGroup](#productgroup), [Title](#title).

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Microsoft Advertising assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountnumber"></a>AccountNumber|The Microsoft Advertising assigned number of an account.|
|<a name="accountstatus"></a>AccountStatus|The current account status.|
|<a name="adgroupcriterionid"></a>AdGroupCriterionId|The Microsoft Advertising assigned identifier of an ad group criterion.|
|<a name="adgroupid"></a>AdGroupId|The Microsoft Advertising assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The current ad group status.|
|<a name="campaignid"></a>CampaignId|The Microsoft Advertising assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The current campaign status.|
|<a name="conflictlevel"></a>ConflictLevel|The entity level where the keyword and negative keyword conflict occurs. The possible values are AdGroup and Campaign.|
|<a name="merchantproductid"></a>MerchantProductId|The unique identifier provided by a merchant for each product offer.|
|<a name="negativekeyword"></a>NegativeKeyword|The negative keyword text.|
|<a name="negativekeywordid"></a>NegativeKeywordId|The Microsoft Advertising assigned identifier of a negative keyword.|
|<a name="negativekeywordlistid"></a>NegativeKeywordListId|The Microsoft Advertising assigned identifier of a negative keyword list.|
|<a name="negativekeywordmatchtype"></a>NegativeKeywordMatchType|The type of match to compare the negative keyword and the user's search term. The possible values for a negative keyword are *Exact* and *Phrase*.|
|<a name="productgroup"></a>ProductGroup|The backward slash delimited list of product conditions, reported as Operand = Attribute. The attribute values are surrounded by "" (double quotes). Here is an example: * / Category="Animals & Pet Supplies" / Category="Pet Supplies" / Category="Bird Supplies". The "*" (single asterisk) refers to a product group that matches everything else besides the other filters for the product group.|
|<a name="title"></a>Title|The product item name. For example the title of a book, DVD, or game.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns. As a general rule, each report must include at least one non-impression share attribute column and at least one performance statistics column. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is expected for all aggregation types except Summary. It is important to note that if you do not include TimePeriod, the aggregation you chose will be ignored and Summary aggregation will be used regardless.

|Column|
|----------|
|AccountName|
|AdGroupName|
|CampaignName|
|NegativeKeyword|

## Requirements
Service: [ReportingService.svc v13](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v13/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v13  

## Used By
[ProductNegativeKeywordConflictReportRequest](productnegativekeywordconflictreportrequest.md)  
