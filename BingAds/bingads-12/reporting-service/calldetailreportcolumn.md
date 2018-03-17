---
title: CallDetailReportColumn Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the attributes and performance statistics columns that you can include in the CallDetailReportRequest.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# CallDetailReportColumn Value Set - Reporting
Defines the attributes and performance statistics columns that you can include in the [CallDetailReportRequest](calldetailreportrequest.md).

The attribute columns that you include in a report can affect how the statistics are aggregated. In other words the number of rows increase by a factor of the unique attributes. For more information, see [Columns that Group the Data](../guides/reports.md#columnsdata).

For a list of columns that you must include, please see the [Required Columns](#requiredcolumns) section below.

To see how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report, see [Report Data Retention Time Periods](../guides/report-data-retention-time-periods.md).

## Syntax
```xml
<xs:simpleType name="CallDetailReportColumn" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="AccountName" />
    <xs:enumeration value="CampaignName" />
    <xs:enumeration value="AdGroupName" />
    <xs:enumeration value="StartTime" />
    <xs:enumeration value="EndTime" />
    <xs:enumeration value="Duration" />
    <xs:enumeration value="CallStatus" />
    <xs:enumeration value="CallTypeName" />
    <xs:enumeration value="AreaCode" />
    <xs:enumeration value="City" />
    <xs:enumeration value="State" />
    <xs:enumeration value="AccountId" />
    <xs:enumeration value="CampaignId" />
    <xs:enumeration value="AdGroupId" />
    <xs:enumeration value="AccountStatus" />
    <xs:enumeration value="CampaignStatus" />
    <xs:enumeration value="AdGroupStatus" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="accountid"></a>AccountId|The Bing Ads assigned identifier of an account.|
|<a name="accountname"></a>AccountName|The account name.|
|<a name="accountstatus"></a>AccountStatus|The account status.|
|<a name="adgroupid"></a>AdGroupId|The Bing Ads assigned identifier of an ad group.|
|<a name="adgroupname"></a>AdGroupName|The ad group name.|
|<a name="adgroupstatus"></a>AdGroupStatus|The ad group status.|
|<a name="areacode"></a>AreaCode|The area code where the user was physically located when they clicked the ad.|
|<a name="callstatus"></a>CallStatus|The call status. This column is deprecated and will be removed in a future API version. Bing Ads stopped charging for manual calls to a tracked number on March 12, 2014, and the CallStatus value is empty for any dates since.|
|<a name="calltypename"></a>CallTypeName|The name of the call type. This column is deprecated and will be removed in a future API version. Bing Ads stopped charging for manual calls to a tracked number on March 12, 2014, and the CallTypeName value is empty for any dates since.|
|<a name="campaignid"></a>CampaignId|The Bing Ads assigned identifier of a campaign.|
|<a name="campaignname"></a>CampaignName|The campaign name.|
|<a name="campaignstatus"></a>CampaignStatus|The campaign status.|
|<a name="city"></a>City|The city used to deliver the ad. The location where the user was in physically when they clicked the ad.|
|<a name="duration"></a>Duration|The duration of each forwarded call that originated from a call ad extension.|
|<a name="endtime"></a>EndTime|The end time of the call.|
|<a name="starttime"></a>StartTime|The start time of the call.|
|<a name="state"></a>State|The state used to deliver the ad. The location where the user was in physically when they clicked the ad.|

## <a name="remarks"></a>Remarks
### <a name="requiredcolumns"></a>Required Columns
The report must include the following columns, and one or more of the performance statistics columns. For more information, see [Report Attributes and Performance Statistics](../guides/report-attributes-performance-statistics.md).

> [!NOTE]
> The TimePeriod column is required for all aggregation types except Summary.

|Column|
|----------|
|CallStatus|
|CallTypeName|
|EndTime|
|StartTime|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v12/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[CallDetailReportRequest](calldetailreportrequest.md)  
