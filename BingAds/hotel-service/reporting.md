---
title: "Hotel Ads Reporting"
description: Describes how to request and download a Hotel Ads report.
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
manager: ehansen
ms.author: "scottwhi"
---

# Hotel Ads Reporting API

> [!NOTE]
> This beta release of Hotel Ads is available to select participants only. For information about participating in the beta release program, please contact your account manager.
>
> The API and documentation are subject to change.

Reporting is an asynchronous process where you send a request with report parameters to the reporting service and it puts the request in a queue. You then poll the service for status of the report job. When the status is Completed, you use the URL that the service provides to download the report.

For an example that shows how to request and download a report, see [Reporting code example](code-example-reporting.md).

## Requesting a report

To request a report, send an HTTP POST request to the following endpoint (for the sandbox endpoint, see [Endpoints](reference.md#endpoints)):

`https://partner.api.bingads.microsoft.com/Travel/v1/Customers({customerId})/Accounts({accountId})/ReportJobs`

The body of the request is a [ReportJob](reference.md#reportjob) object. The following are the fields that you must specify in the request.

- StartDate&mdash;The start of the reporting period
- EndDate&mdash;The end of the reporting period
- Columns&mdash;The columns to include in the report
- ReportType&mdash;The type of report or entity to download

All other fields are optional.

The following example shows a `ReportJob` request for a performance report.

```json
{
    "ReportType":"Performance", 
    "StartDate":"2017-11-06", 
    "EndDate":"2017-11-13", 
    "Columns":[  
        "HotelId", 
        "Clicks" 
    ] 
}
```

The above request asks to generate a performance report. By default, the service generates reports in uncompressed CSV format. To compress the report and improve download performance, specify the [Compression](reference.md#compression) field and set it to ZIP.

The response to the POST contains a report job ID (see [AddResponse](reference.md#addresponse)). For example:

```json
{
    "value":"1080"
}
```


## Polling for the status of a report job

After getting the ID, use it to get the status of the report job. To get the status, send an HTTP GET request to:

https://partner.api.bingads.microsoft.com/Travel/v1/Customers({customerId})/Accounts({accountId})/ReportJobs('{jobId}')

The report job is valid for an undertermined amount of time after it completes but typically for at least seven days. After seven days, you should submit a new report request.

The body of the response is a [ReportJob](reference.md#reportjob) object. To determine the job's status, access the `Status` field. When the job finishes, `Status` is set to Completed and the `Url` field contains the URL that you use to download the report. The URL is valid for seven days. If the URL expires, you must submit a new job request. 

How long it takes for report jobs to finish is undetermined and is based on several variables that are constantly changing such number of jobs in the queue, amount of data, and size of reporting period. Generally, you should poll for the status of the job every five seconds until the job's status is Completed or Failed. 



## Downloading the report

When the report job's status is Completed, the job will contain the URL that you use to download the report in the job's `Url` field. To download the report, send an HTTP GET request to the specified URL.

For uncompressed reports, the GET response's Content-Type header contains text/csv. For compressed reports, the header contains application/zip.

If you asked the service to compress the report data (see the report job's `Compression` field), the service places the file in a folder and uses ZIP compression to compress the report. Remember to uncompress the folder before accessing and reading the report. The name of the report file is auto-generated and has the form, performance-\<request ID\>.



## Filtering report data

To filter the data in the report, use the `Filter` field in the [ReportJob](reference.md#reportjob) request object. You may filter the report on the following dimension columns and any [measure column](#measure-columns). The column names are case sensitive.

- SubaccountId/Name
- HotelGroupId/Name
- HotelId/Name, PartnerHotelId
- DeviceType

Using filters is an AND operation. For example, if you filter on HotelPartnerId equal to 123 and DeviceType equal to Mobile, the report will contain data only where the partner's hotel ID is 123 AND the device type is mobile.

Set `Filter` to an OData [$filter](http://www.odata.org/getting-started/basic-tutorial/#queryData) string. The following example shows how to filter the report for ads shown on desktops and tablets. The enumeration values that you use in the filter are case sensitive. For example, use Desktop instead of desktop.

```json
{
    "ReportType":"Performance", 
    "StartDate":"2017-11-06", 
    "EndDate":"2017-11-13", 
    "Columns":[  
        "HotelId", 
        "Clicks" 
    ], 
    "Filter":"DeviceType eq Enum.DeviceType'Desktop' or DeviceType eq Enum.DeviceType'Tablet'", 
}
```

In addition to using `Filter`, you can use the `SubaccountId` and `HotelGroupId` fields in the [ReportJob](reference.md#reportjob) request object to limit the report to the specified subaccount or hotel group. If you want to limit the scope to a single subaccount or hotel group, using these fields offer better performance than using `Filter`. Also, If you use these request fields, you should not include them in the filter.



## Performance report columns


Reports contain [dimension](#dimension-columns) columns and [measure](#measure-columns) columns (metrics). The metric data rolls up to the lowest-level dimension in the dimension hierarchy that you specify in your report request.

The following is the hierarchy for Performance Report.

1. Date
1. SubaccountId/Name
2. HotelGroupId/Name
3. HotelId/Name, PartnerHotelId
4. HotelCountry
5. UserCountry
6. SlotType
7. LengthOfStay
8. DeviceType

For example, if the request contains SubaccountId and Clicks, the clicks roll up to SubaccountId.

|Date|Subaccount|Clicks
|-|-|-
|2017-11-16|123|40

And if the request contains SubaccountId, HotelGroupId, and Clicks, the clicks roll up to HotelGroupId. 

|Date|Subaccount|Hotel group|Clicks
|-|-|-|-
|2017-11-16|123|987|12
|2017-11-16|123|654|13
|2017-11-16|123|321|15


The request must include at least one dimension column and one measure column.


### Dimension columns

|Column name|Report column name|Description
|-|-|-
|Date|Date|A date within the reporting period. This column is automatically added to the report if not specified. The format is YYYY-MM-dd (for example, 2017-11-16).
|DeviceType|Device type|The type of device that the ads were displayed on. The following are the possible values.<ul><li>Desktop</li><li>Mobile</li><li>Tablet</li></ul>
|HotelCountry|Hotel country|The two-letter ISO 3116 country code of the country where the hotel is located. For example, US for United States.
|HotelGroupId|Hotel group ID|The ID that uniquely identifies the hotel group.
|HotelGroupName|Hotel group name|The hotel group's display name.
|HotelId|Hotel ID|The ID that uniquely identifies the hotel.
|HotelName|Hotel name|The hotel's name.
|LengthOfStay|Length of stay|The itinerary's length of stay.
|PartnerHotelId|Partner hotel ID|The ID that the partner uses to uniquely identify the hotel.
|SlotType|Slot type|The placement of the ads on the results page. The following are the possible values.<ul><li>A&mdash;The priority slot where ads are shown on the results page when it loads.</li><li>M&mdash;The secondary slot where ads are shown only after the user clicks *More rates*.</li></ul>
|SubAccountId|Subaccount ID|The ID that uniquely identifies the subaccount (hotel campaign).
|SubAccountName|Subaccount name|The subaccount's display name.
|UserCountry|User country|The two-letter ISO 3116 country code of the country where the user is located. For example, US for United States.


### Measure columns

|Column name|Report column name|Description
|-|-|-
|AverageCPC|Avg. CPC|The average cost per click, which is calculated by dividing the total cost of all clicks by the number of clicks. The cost is in the account's currency.  Data is available starting from 12/06/2017.
|AverageCPCUSD|Avg. CPC USD|The average cost per click, which is calculated by dividing the total cost of all clicks by the number of clicks. The cost is in US dollars.
|AveragePosition|Avg. pos.|The average position of ads on the results page. Position refers to the order of the ad on the page relative to all other ads across all slots.
|AverageSlotPosition|Avg. slot pos.|The average position of ads in the slot type. If you include this metric, you should also include the SlotType dimension column.
|Clicks|Clicks|The number of time ads were clicked.
|CTR|CTR|The click-through-rate of the ads. CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.
|Impressions|Impr.|The number of times ads were shown.
|Spend|Spend|The total cost of all clicks. The cost is in the account's currency.  Data is available starting from 12/06/2017.
|SpendUSD|Spend USD|The total cost of all clicks. The cost is in US dollars.


## Sample Performance report

The following shows an example of the report's header rows and columns.

```
"Performance report (October 30, 2017 - November 29, 2017)"
Request Id: f11b6610-5b85-4d7f-97ad-69668eb9da11

Date,Subaccount ID,Hotel group ID,Clicks,CTR,Impr.,Spend,User country
```

The first header row contains the report's name and requested reporting period. The second header row contains the report's request ID. If there's a problem with the report, you'd use the ID when you contact support to get help with the issue.
