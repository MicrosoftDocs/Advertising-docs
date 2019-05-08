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

Reporting is an asynchronous process. The following is the general flow for requesting a report.

- Create a request with the report parameters
- Send a request to the reporting service
- The service queues the request until it's able to process it
- Poll the service periodically to get the status of the report job
- When the status is Completed, use the URL that the service provides to download the report.

For an example that shows how to request and download a report, see [Reporting code example](code-example-reporting.md).

## Requesting a report

To request a report, send an HTTP POST request to the following endpoint (for the sandbox endpoint, see [Endpoints](reference.md#endpoints)):

`https://partner.api.bingads.microsoft.com/Travel/v1/Customers({customerId})/Accounts({accountId})/ReportJobs`

The body of the request is a [ReportJob](reference.md#reportjob) object. You must specify the following fields in the request:

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

By default, the service generates reports in uncompressed CSV format. To compress the report and improve download performance, include the [Compression](reference.md#compression) field and set it to ZIP.

The response to the POST contains a report job ID (see [AddResponse](reference.md#addresponse)). For example:

```json
{
    "value":"1080"
}
```


## Polling for the status of a report job

After getting the ID, use it to get the status of the report job. To get the status, send an HTTP GET request to:

`https://partner.api.bingads.microsoft.com/Travel/v1/Customers({customerId})/Accounts({accountId})/ReportJobs('{jobId}')`

The report job is valid for an undetermined amount of time after it completes but typically for at least seven days. After seven days, you should submit a new report request.

The body of the response is a [ReportJob](reference.md#reportjob) object. To determine the job's status, access the `Status` field. When the job finishes, `Status` is set to Completed and the `Url` field contains the URL that you use to download the report. The URL is valid for seven days. If the URL expires, you must submit a new job request. 

How long it takes for report jobs to finish is undetermined and is based on several variables that are constantly changing such number of jobs in the queue, amount of data, and size of reporting period. Generally, you should poll for the status of the job every five seconds until the job's status is Completed or Failed. 



## Downloading the report

When the report job's status is Completed, the job's `Url` field contains the URL that you use to download the report. To download the report, send an HTTP GET request to the specified URL.

For uncompressed reports, the GET response's Content-Type header contains text/csv. For compressed reports, the header contains application/zip.

If you asked the service to compress the report's data (see the report job's `Compression` field), the service places the file in a folder and uses ZIP compression to compress the report. Remember to uncompress the folder before accessing and reading the report. The name of the report file is auto-generated and has the form, performance-\<request ID\>.



## Filtering report data

To filter the data in the report, use the[ReportJob](reference.md#reportjob) object's `Filter` field. You may filter the report on the following dimension columns and any [measure column](#measure-columns). The column names are case sensitive.

- SubaccountId
- SubaccountName
- HotelGroupId
- HotelGroupName
- HotelId
- HotelName
- PartnerHotelId
- DeviceType

Using filters is an AND operation. For example, if you filter on HotelPartnerId equal to 123 and DeviceType equal to Mobile, the report contains data only where the partner's hotel ID is 123 AND the device type is mobile.

To filter a report's data, set `Filter` to an OData [$filter](http://www.odata.org/getting-started/basic-tutorial/#queryData) string. The following example shows how to filter the report for ads shown on desktops and tablets. The enumeration values that you use in the filter are case sensitive. For example, use Desktop instead of desktop.

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

In addition to using the `Filter` field, you can use the `SubaccountId` and `HotelGroupId` fields to limit the report to a specific subaccount or hotel group. Using these fields to limit the scope to a single subaccount or hotel group provides better performance than using `Filter`. If you use `SubaccountId` and `HotelGroupId`, don't also specify them in the filter.


## Including non-performing hotels in the report

By default, the performance report contains only hotels that have impressions during the reporting period. To include hotels that did not have impressions during the reporting period, set the [IncludeNonPerformingHotels](reference.md#includenonperforminghotels) field in the report request to **true**.

```json
{
    "ReportType":"Performance", 
    "StartDate":"2017-11-06", 
    "EndDate":"2017-11-13", 
    "Columns":[  
        "HotelId",
        "PartnerHotelId",
        "Clicks",
        "Impressions"
    ],
    "IncludeNonPerformingHotels" : true
}
```

If you request non-performing hotels in the report, the `columns` property must not include the following [dimension columns](#dimensioncolumns):

- Date
- DeviceType
- HotelCountry
- LengthOfStay
- SlotType
- UserCountry

If the `columns` property includes any of the above fields, the report jobs request fails.

### How does IncludeNonPerformingHotels affect reporting for hotels that moved groups?

By default, the report includes hotel performance data for the hotel no matter whether you segment the report by hotel, hotel group, or subaccount. Moving the hotel from one group to another does not impact the default reporting behavior. For example, if the report includes the hotel column, the report includes all performance data for the hotel during the specified time period. 

```
Date        Hotel ID   Clicks
1-1-2018    5678       12
```

If you include the hotel column and hotel group column, the report includes hotel performance data that occurred for each hotel group during the specified time period.

```
Date       Hotel group ID   Hotel ID   Clicks
1-1-2018   1234             5678       2
2-1-2018   9876             5678       10
```

But things change if you include the IncludeNonPerformingHotels request property. If true, the report includes performance data for only active hotel and hotel group associations. This means that the hotels report example above changes to:

```
Date        Hotel ID   Clicks
1-1-2018    5678       10
```

And the hotel group example changes to:

```
Date       Hotel group ID   Hotel ID   Clicks
2-1-2018   9876             5678       10
```



## Books closed

For information about when books close, see [Determining when books close](/advertising/guides/reports#booksclose). Determining when books close for Hotel Ads is the same as for Microsoft Advertising campaigns with the following exceptions:

- Hotel Ads' reporting service uses the account's time zone.
- Hotel Ads' reporting service doesn't support ReturnOnlyCompleteData.


## Performance report columns


Reports contain [dimension](#dimension-columns) columns and [measure](#measure-columns) columns (metrics). The metric data is segmented by the dimension columns. This means that the metric data rolls up to the lowest-level dimension in the dimension hierarchy that you specify in your report request.

The following is the dimension hierarchy for Performance Report.

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

<a name="dimensioncolumns" />

### Dimension columns

|Column name|Report column name|Description
|-|-|-
|AdvancedBookingWindow|Adv. booking window|The number of days before the check-in date that the user is asking to book the hotel room. For example, if today is 3 May and the user is asking to book a room for 8 May, the column's value is 5.
|CheckinDay|Checkin day|The day of the week (for example, Wednesday) the user is asking to check into the hotel.
|Date|Date|A date within the reporting period. This column is automatically added to the report if not specified. The format is YYYY-MM-dd (for example, 2017-11-16).
|DateType|Date type|Indicates whether the user searched for hotels using specific dates. The following are the possible values.<ul><li>DefaultDate&mdash;The user didn't search for hotels using specific dates</li><li>SelectedDate&mdash;The user searched for hotels using specific dates</li>
|DeviceType|Device type|The type of device that the ads were displayed on. The following are the possible values.<ul><li>Desktop</li><li>Mobile</li><li>Tablet</li></ul>
|HotelCountry|Hotel country|The two-letter ISO 3116 country code of the country where the hotel is located. For example, US for United States.
|HotelGroupId|Hotel group ID|The ID that uniquely identifies the hotel group.
|HotelGroupName|Hotel group name|The hotel group's display name.
|HotelId|Hotel ID|The ID that uniquely identifies the hotel.
|HotelName|Hotel name|The hotel's name.
|LengthOfStay|Length of stay|The itinerary's length of stay.
|PartnerHotelId|Partner hotel ID|The ID that the partner uses to uniquely identify the hotel.
|SiteType|Site type|The Bing site that users used to search for hotels. The following are the possible values.<ul><li>LocalUniversal&mdash;The user used Bing.com to search for hotels</li><li>MapResults&mdash;The user used Bing.com/maps to search for hotels</li> 
|SlotType|Slot type|The placement of the ads on the results page. The following are the possible values.<ul><li>A&mdash;The priority slot where ads are shown on the results page when it loads.</li><li>M&mdash;The secondary slot where ads are shown only after the user clicks *More rates*.</li></ul>
|SubAccountId|Subaccount ID|The ID that uniquely identifies the subaccount (hotel campaign).
|SubAccountName|Subaccount name|The subaccount's display name.
|UserCountry|User country|The two-letter ISO 3116 country code of the country where the user is located. For example, US for United States.<br /><br />**NOTE:** Prior to August 2, 2018, UserCountry contains the publisher's country. After August 2, 2018, UserCountry contains the user’s country.


<a name="measurecolumns" />

### Measure columns

|Column name|Report column name|Description
|-|-|-
|AverageCPC|Avg. CPC|The average cost per click, which is calculated by dividing the total cost of all clicks by the number of clicks. The cost is in the account's currency.  Data is available starting from December 6, 2017.
|AverageCPCUSD|Avg. CPC USD|The average cost per click, which is calculated by dividing the total cost of all clicks by the number of clicks. The cost is in US dollars.
|AveragePosition|Avg. pos.|The average position of ads on the results page. Position refers to the order of the ad on the page relative to all other ads across all slots.
|AverageSlotPosition|Avg. slot pos.|The average position of ads in the slot type. If you include this metric, you should also include the SlotType dimension column.
|Clicks|Clicks|The number of time ads were clicked.
|ClickShare|Click share|The percentage of clicks that went to your ads, out of the total number of clicks in the market you were targeting. For example, out of the estimated 1,000 clicks that occurred on this day in your targeted market, you had about 230, or 23%. The value is in the range 0.0 through 1.0. 
|CTR|CTR|The click-through-rate of the ads. CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.
|EligibleImpressions|Eligible impr.|The total number of realized and unrealized impressions (impressions plus missed impressions).
|Impressions|Impr.|The number of times ads were shown.
|ImpressionShare|Impr. share|The percentage of impressions, out of the total available impressions in the market you were targeting. For example, out of an estimated 59,000 impressions that occurred on this day in your targeted market, you received 2,300, or 3%. The value is in the range 0.0 through 1.0.
|MissedImpressions|Missed impr.|The total number of impressions lost. This is the sum of the following columns:<ul><li>MissedImpressionsInsufficientBid</li><li>MissedImpressionsNoTax</li><li>MissedImpressionsOther</li><li>MissedImpressionsSpendingCapReached</li></ul>
|MissedImpressionsInsufficientBid|Missed impr. insufficient bid|The number of impressions lost because your bids were low and not competing well in the auction marketplace. 
|MissedImpressionsNoTax|Missed impr. no tax|The number of impressions lost because the hotel didn't specify taxes.
|MissedImpressionsOther|Missed impr. other|The number of impressions lost for all other reasons. Typically, low ranking or your rate was available in the **More rates** section, but the user did not expand the section to view your rate.
|MissedImpressionsSpendingCapReached|Missed impr. spending cap reached|The number of impressions lost because you reached your daily spending limit.
|Spend|Spend|The total cost of all clicks. The cost is in the account's currency.  Data is available starting from December 6, 2017.
|SpendUSD|Spend USD|The total cost of all clicks. The cost is in US dollars.

<a name="sov" />

### Share of voice

In addition to the rule that requests must include at least one dimension column and one measure column, any report that includes share of voice (SOV) columns must include at least one of the following dimension columns.

- HotelGroupId
- HotelId
- PartnerHotelId
- SubAccountId

The following are the SOV columns:

- ClickShare
- EligibleImpressions
- ImpressionShare
- MissedImpressions
- MissedImpressionsInsufficientBid
- MissedImpressionsNoTax
- MissedImpressionsOther
- MissedImpressionsSpendingCapReached

> [!NOTE]
> SOV data is available beginning May 1, 2018. If you specify a reporting period that includes dates prior to May 1, 2018, the SOV fields will contain a zero (0) value for dates prior to 1 May.

## Sample Performance report

The following shows an example of the report's header rows and columns.

```
"Performance report (October 30, 2017 - November 29, 2017)"
Request Id: f11b6610-5b85-4d7f-97ad-69668eb9da11

Date,Subaccount ID,Hotel group ID,Clicks,CTR,Impr.,Spend,User country
```

The first header row contains the report's name and requested reporting period. The second header row contains the report's request ID. If there's a problem with the report, you'd use the ID when you contact support to get help with the issue.

> [!NOTE]
> IDs such as the hotel ID or ad group ID are enclosed in square brackets (for example, [1234567890]).
