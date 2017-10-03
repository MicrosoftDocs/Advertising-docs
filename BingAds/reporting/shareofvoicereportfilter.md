---
title: ShareOfVoiceReportFilter Data Object
ms.service: bing-ads-reporting
ms.topic: article
author: eric-urban
ms.author: eur
---
# ShareOfVoiceReportFilter Data Object
Defines the criteria to use to filter the share of voice report data.

## Syntax
```xml
<xs:complexType name="ShareOfVoiceReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="AccountStatus" nillable="true" type="tns:AccountStatusReportFilter" />
    <xs:element minOccurs="0" name="AdDistribution" nillable="true" type="tns:AdDistributionReportFilter" />
    <xs:element minOccurs="0" name="AdGroupStatus" nillable="true" type="tns:AdGroupStatusReportFilter" />
    <xs:element minOccurs="0" name="BidMatchType" nillable="true" type="tns:BidMatchTypeReportFilter" />
    <xs:element minOccurs="0" name="BidStrategyType" nillable="true" type="tns:BidStrategyTypeReportFilter" />
    <xs:element minOccurs="0" name="CampaignStatus" nillable="true" type="tns:CampaignStatusReportFilter" />
    <xs:element minOccurs="0" name="DeliveredMatchType" nillable="true" type="tns:DeliveredMatchTypeReportFilter" />
    <xs:element minOccurs="0" name="DeviceType" nillable="true" type="tns:DeviceTypeReportFilter" />
    <xs:element minOccurs="0" name="KeywordStatus" nillable="true" type="tns:KeywordStatusReportFilter" />
    <xs:element minOccurs="0" name="Keywords" nillable="true" type="q22:ArrayOfstring" xmlns:q22="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="LanguageCode" nillable="true" type="q23:ArrayOfstring" xmlns:q23="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountstatus"></a>AccountStatus|The report will include data for only the account status. For example, you can use the filter to include data for only active accounts.<br /><br />You can specify one or more account statuses.|[AccountStatusReportFilter](accountstatusreportfilter.md)|
|<a name="addistribution"></a>AdDistribution|The report will include data for only the specified distribution medium. For example, you can use the filter to include data for only search ads.<br /><br />You can specify one or more distribution mediums.|[AdDistributionReportFilter](addistributionreportfilter.md)|
|<a name="adgroupstatus"></a>AdGroupStatus|The report will include data for only the ad group status. For example, you can use the filter to include data for only active ad groups.<br /><br />You can specify one or more ad group statuses.|[AdGroupStatusReportFilter](adgroupstatusreportfilter.md)|
|<a name="bidmatchtype"></a>BidMatchType|The report will include data for only the specified bid match types. For example, you can use the filter to include data for ads that were bid on using the exact or phrase match type.<br /><br />You can specify one or more bid match types.<br /><br />To filter on delivered match types, see the *DeliveredMatchType* element.|[BidMatchTypeReportFilter](bidmatchtypereportfilter.md)|
|<a name="bidstrategytype"></a>BidStrategyType|The report will include data for only the specified bid strategy type or types. For example, you can use the filter to include data only for keywords that were bid on using the enhanced bid strategy type.<br /><br />You can specify one or more bid strategy types.|[BidStrategyTypeReportFilter](bidstrategytypereportfilter.md)|
|<a name="campaignstatus"></a>CampaignStatus|The report will include data for only the campaign status. For example, you can use the filter to include data for only active campaigns.<br /><br />You can specify one or more campaign statuses.|[CampaignStatusReportFilter](campaignstatusreportfilter.md)|
|<a name="deliveredmatchtype"></a>DeliveredMatchType|The report will include data for only the specified delivered match types. For example, you can use the filter to include data for ads that were delivered using the exact or phrase match type.<br /><br />You can specify one or more delivered match types.<br /><br />To filter on bid match types, see the *BidMatchType* element.|[DeliveredMatchTypeReportFilter](deliveredmatchtypereportfilter.md)|
|<a name="devicetype"></a>DeviceType|The report will include data for only the specified types of devices on which the ad is displayed. For example, you can use the filter to include data only for text ads displayed on smartphones.<br /><br />You can specify one or more device types.|[DeviceTypeReportFilter](devicetypereportfilter.md)|
|<a name="keywordstatus"></a>KeywordStatus|The report will include data for only the keyword status. For example, you can use the filter to include data for only active keywords.<br /><br />You can specify one or more keyword statuses.|[KeywordStatusReportFilter](keywordstatusreportfilter.md)|
|<a name="keywords"></a>Keywords|The report will include data for only the specified keywords. You can specify a maximum of 75 keywords. Each keyword can contain a maximum of 100 characters.|**string**|
|<a name="languagecode"></a>LanguageCode|The report will include data for only websites that used the specified languages. For a list of possible values, see [Ad Languages](~/guides/ad-languages.md).|**string**|

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

## Used By
[ShareOfVoiceReportRequest](shareofvoicereportrequest.md)  
