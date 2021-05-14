---
title: Welcome to pubCenter!
description: Learn all about the reports you can run using pubCenter.
ms.service: "bing-ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Welcome to pubCenter!

Microsoft pubCenter lets you run and download reports on a variety of performance metrics. You can use these reports to determine which of your accounts, ad units, and websites are performing well, and which need attention.

> [!NOTE]
> For a list of the latest features and known issues, see the [pubCenter release notes](./hlp_PCv3_CONC_WhatsNew.md).

## Types of reports

There are five types of reports you can run on your pubCenter dashboard. They are listed under **New report** in the upper-left corner of the screen:

- **Account performance**: This report aggregates your ad unit performance metrics at the account level. It is useful as a summary report or for comparing the performance of one or more accounts.
- **Site performance**: This report aggregates ad unit performance metrics at the website level. It is useful as a site summary report or for comparing the performance of one or more websites.
- **Ad unit performance**: This report shows performance metrics of individual ad units. It is useful for comparing the performance of ad units, and for getting a more granular view of performance -- for example, which ad units are getting the most impressions on specific device types.
- **Type tag performance**: This report provides the most granular view of performance, as determined by the web publisher. Type tags are text strings that publishers send along with each ad request for the purpose of data classification. For example, a publisher could use a browser name or a content category as a type tag, and with these reports, you could compare browser or content category performance. Note that, depending on how type tags are created and used by publishers, the aggregated metrics in the chart and the summary boxes above the chart area may not be completely accurate.
> [!NOTE]
> Each publisher can have up to 20,000 unique type tags per month.

- **PTQS** (Publisher Traffic Quality Score): This score helps rank how well your ad units are performing over time.

## Working with reports

With any report, you can:

## Set up filters
Use the **Filter by** selector above the left side of the chart area to scope your report. Different reports have different filters -- see below for more information.
- In the **Filter by** selector, you can find the fields that can be filtered on for the given report type.
- You can type or paste in a list of entities to filter on in the search field. Note: For type tag filters, you just need to type or paste the tags instead of searching.
- Select all the entities you want to filter on.
- When a filter is in place, you'll see the number of entities being filtered on top of the chart. For example, if you filter on two specific accounts, you'll see **Accounts : 2**. You can click the x next to the number to remove the filter.

## Define a date range
Use the date range selector above the right side of the chart area to specify the time period to report on and the unit of time to report by (in other words, the granularity).
- The granularity options change based on your date range selection to show you only the applicable options:
  - Hour and Day are only applicable for date ranges of 92 days or fewer.
  - Week is only applicable for date ranges of 644 days or fewer.
  - Month is only applicable for date ranges of 2,760 days or fewer.
  - Year is only applicable for date ranges of 3,653 days or fewer.

- If your defined date range only covers part of the unit of time you selected, you will see data for the entire unit of time. For example, if you select Month granularity and your date range is Oct 10 to Nov 9, then you will see data from Oct 1 to Oct 31 and from Nov 1 to Nov 30.
- Note that the PTQS report's only applicable unit of time (granularity) is Day.

## Choose and order columns
Use the **Columns** selector above the table area to choose and order the columns in the table.
- On the left, select the checkboxes for the columns you want to see.
- On the right, you can drag and drop the columns into your preferred order.
- When you have it set, click **Apply**. This may reload the report.

## Sort columns
Sort on a column by clicking a column header. For example, in an ad unit report, you could click the **Estimated revenue** column header to see your top-earning ad units. An arrow in the column header indicates which column the table is sorted by.
## Save and schedule reports
If you'd like to save a report to refer to -- or run again -- at a later date:

1. Click the **Save** button in the upper-right corner of the screen.
1. In the **Save my report** window, enter a unique name in the **Report name** field. The name can be up to 100 characters long.
1. If you want to run the report regularly, select Daily, Weekly, Monthly, or Yearly in the **Auto-run** dropdown.
1. If you want to have this report sent to you or other stakeholders, enter the appropriate email addresses in the **Send these people a link to the report** field.
  - The email addresses in total cannot exceed 1024 characters.
  - Email addresses must be in the format alias@domain.xxx (.xxx can be replaced with .com, .net, .org, etc.).

1. Click **Save** in the **Save my report** window. The report will appear in the **My reports** list on the left side of the screen.
  - To see this report again, click its name in the **My reports** list.
  - If you make changes and want to save them:
    1. Click **Save** again in the upper-right corner of the screen.
    1. Review your selections and choose whether to save it as a new report or update the existing report.
    1. Click **Save** in the **Save my report** window.

  - To delete a report, click the garbage-can icon next to the report's name in the **My reports** list.

## Download the report
Click the **Download to Excel** button above the table area to download the current report as a zipped .csv-format file.

## Report filters and columns

Here are each report's specific filters and available columns:

## Account performance report
## Filters

Filter by account.

## Available columns

<table>
  <tr>
    <th style="text-align:left">Column name</th>
    <th style="text-align:left">What does it mean?</th>
    <th style="text-align:left">Setting or metric?</th>
    <th style="text-align:left">Optional or required?</th>
  </tr>
  <tr>
    <td><strong>Account ID</strong></td>
    <td>An ID that uniquely identifies the account. </td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Account name</strong></td>
    <td>The name of the account.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Account number</strong></td>
    <td>The number associated with the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad CTR</strong></td>
    <td>The click-through rate based on all ads that were shown to a user. It is calculated as (clicks * 100) / ad impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad density</strong></td>
    <td>The average number of ads served on each query where Bing Ads returned at least one ad (impression or bidded SRPV). The formula is: ad density = ad impressions / impressions.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impressions</strong></td>
    <td>The total number of ads served. For a single query (or SRPV), there could be multiple ads served.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Clicks</strong></td>
    <td>The number of clicks the ad unit received during the specified reporting period.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>CPC</strong></td>
    <td>The cost per click. CPC is calculated by dividing estimated revenue by clicks.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CTR</strong></td>
    <td>The click-through rate of the ad unit. The CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Currency</strong></td>
    <td>The currency that the revenue-related columns are specified in. The column contains the ISO 4217 code of the currency (for example, USD for US Dollar). Because currency is specified in your account, you should include this column if your accounts use different currencies.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Date</strong></td>
    <td>The time period for the data in the report, in the unit of time you have selected.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>eCPM</strong></td>
    <td>The estimated revenue per one thousand impressions. The effective revenue is calculated after fraud detection and traffic filtering is applied. </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Estimated revenue</strong></td>
    <td>The estimated amount of gross revenue before revenue sharing is applied..</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Impressions</strong></td>
    <td>The number of times Bing Ads responds to a search query with an ad. For example, if a user searches on one keyword and navigates to three pages of search results -- but Bing Ads only displays ads on the first two pages -- then this will count as two impressions.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Language</strong></td>
    <td>The language used by the ads requests. For example, English.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Market</strong></td>
    <td>The market (country/region) used by the ads requests. For example, United States.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher ID</strong></td>
    <td>An ID that uniquely identifies the publisher.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher name</strong></td>
    <td>The name of the publisher. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
</table>

## Site performance report
## Filters

Filter by account and by specific website.

## Available columns

<table>
  <tr>
    <th style="text-align:left">Column name</th>
    <th style="text-align:left">What does it mean?</th>
    <th style="text-align:left">Setting or metric?</th>
    <th style="text-align:left">Optional or required?</th>
  </tr>
  <tr>
    <td><strong>Account ID</strong></td>
    <td>An ID that uniquely identifies the account. </td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Account name</strong></td>
    <td>The name of the account.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Account number</strong></td>
    <td>The number associated with the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad CTR</strong></td>
    <td>The click-through rate based on all ads that were shown to a user. It is calculated as (clicks * 100) / ad impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad density</strong></td>
    <td>The average number of ads served on each query where Bing Ads returned at least one ad (impression or bidded SRPV). The formula is: ad density = ad impressions / impressions.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impressions</strong></td>
    <td>The total number of ads served. For a single query (or SRPV), there could be multiple ads served.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Clicks</strong></td>
    <td>The number of clicks the ad unit received during the specified reporting period.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>CPC</strong></td>
    <td>The cost per click. CPC is calculated by dividing estimated revenue by clicks.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CTR</strong></td>
    <td>The click-through rate of the ad unit. The CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Currency</strong></td>
    <td>The currency that the revenue-related columns are specified in. The column contains the ISO 4217 code of the currency (for example, USD for US Dollar). Because currency is specified in your account, you should include this column if your accounts use different currencies.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Date</strong></td>
    <td>The time period for the data in the report, in the unit of time you have selected</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Device type</strong></td>
    <td>The type of device that the ads were displayed on. The following are the possible values: HiFi Phone, LoFi Phone, PC, Tablet. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>eCPM</strong></td>
    <td>The estimated revenue per one thousand impressions. The effective revenue is calculated after fraud detection and traffic filtering is applied. </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Estimated revenue</strong></td>
    <td>The estimated amount of gross revenue before revenue sharing is applied..</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Impressions</strong></td>
    <td>The number of times Bing Ads responds to a search query with an ad. For example, if a user searches on one keyword and navigates to three pages of search results -- but Bing Ads only displays ads on the first two pages -- then this will count as two impressions.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Publisher ID</strong></td>
    <td>An ID that uniquely identifies the publisher.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher name</strong></td>
    <td>The name of the publisher. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Site ID</strong></td>
    <td>An ID that uniquely identifies the website.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Site name</strong></td>
    <td>The name of the website property where the ad was placed.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Site URL</strong></td>
    <td>The URL of the website.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
</table>

## Ad unit performance report
## Filters

Filter by account and by specific ad unit.

## Available columns

<table>
  <tr>
    <th style="text-align:left">Column name</th>
    <th style="text-align:left">What does it mean?</th>
    <th style="text-align:left">Setting or metric?</th>
    <th style="text-align:left">Optional or required?</th>
  </tr>
  <tr>
    <td><strong>Account ID</strong></td>
    <td>An ID that uniquely identifies the account. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account name</strong></td>
    <td>The name of the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account number</strong></td>
    <td>The number associated with the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad CTR</strong></td>
    <td>The click-through rate based on all ads that were shown to a user. It is calculated as (clicks * 100) / ad impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad density</strong></td>
    <td>The average number of ads served on each query where Bing Ads returned at least one ad (impression or bidded SRPV). The formula is: ad density = ad impressions / impressions.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impression yield</strong></td>
    <td>The average number of ads served on each query (raw SRPV). The formula is: ad impression yield = ad impressions / raw SRPV.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impressions</strong></td>
    <td>The total number of ads served. For a single query (or SRPV), there could be multiple ads served.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad unit ID</strong></td>
    <td>An ID that uniquely identifies the ad unit.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Ad unit name</strong></td>
    <td>The display name of the ad unit. </td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Click yield</strong></td>
    <td>The average number of ads that Bing returned per request (only requests that returned at least one ad are used). It is calculated as clicks / raw SRPV.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Clicks</strong></td>
    <td>The number of clicks the ad unit received during the specified reporting period.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Coverage</strong></td>
    <td>The percentage of queries for which at least one ad was shown.  </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CPC</strong></td>
    <td>The cost per click. CPC is calculated by dividing estimated revenue by clicks.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CTR</strong></td>
    <td>The click-through rate of the ad unit. The CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Currency</strong></td>
    <td>The currency that the revenue-related columns are specified in. The column contains the ISO 4217 code of the currency (for example, USD for US Dollar). Because currency is specified in your account, you should include this column if your accounts use different currencies.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Date</strong></td>
    <td>The time period for the data in the report, in the unit of time you have selected.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Device type</strong></td>
    <td>The type of device that the ads were displayed on. The following are the possible values: HiFi Phone, LoFi Phone, PC, Tablet. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>eCPM</strong></td>
    <td>The estimated revenue per one thousand impressions. The effective revenue is calculated after fraud detection and traffic filtering is applied. </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Estimated revenue</strong></td>
    <td>The estimated amount of gross revenue before revenue sharing is applied..</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Impressions</strong></td>
    <td>The number of times Bing Ads responds to a search query with an ad. For example, if a user searches on one keyword and navigates to three pages of search results -- but Bing Ads only displays ads on the first two pages -- then this will count as two impressions.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Language</strong></td>
    <td>The language used by the ads requests. For example, English.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Market</strong></td>
    <td>The market (country/region) used by the ads requests. For example, United States.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher ID</strong></td>
    <td>An ID that uniquely identifies the publisher.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher name</strong></td>
    <td>The name of the publisher. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Queries</strong></td>
    <td>The number of distinct search queries from a given user. For example, if a user searches for two different keywords and navigates to three pages of search results, this counts as two queries.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Raw SRPV</strong></td>
    <td>Raw search results page views — the number of times a search request is received by the Bing Ads platform. Note that each page request for the same keyword/query is counted as an independent raw SRPV. For example, if a user searches for "camera" and then navigates to the second and third pages of search results, there are three requests made (one per page) to the Bing Ads platform, so the raw SRPV count will be three.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>RPM</strong></td>
    <td>The estimated revenue per thousand raw SRPV. It is calculated as (estimated revenue * 1,000) / raw SRPV.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Site ID</strong></td>
    <td>An ID that uniquely identifies the website.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Site name</strong></td>
    <td>The name of the website property where the ad was placed.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>User country</strong></td>
    <td>The country/region where the user was located when the ads were requested.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
</table>

## Type tag performance report
## Filters

Filter by account, by specific ad unit, and by type tag.

## Available columns

<table>
  <tr>
    <th style="text-align:left">Column name</th>
    <th style="text-align:left">What does it mean?</th>
    <th style="text-align:left">Setting or metric?</th>
    <th style="text-align:left">Optional or required?</th>
  </tr>
  <tr>
    <td><strong>Account ID</strong></td>
    <td>An ID that uniquely identifies the account. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account name</strong></td>
    <td>The name of the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account number</strong></td>
    <td>The number associated with the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad CTR</strong></td>
    <td>The click-through rate based on all ads that were shown to a user. It is calculated as (clicks * 100) / ad impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad density</strong></td>
    <td>The average number of ads served on each query where Bing Ads returned at least one ad (impression or bidded SRPV). The formula is: ad density = ad impressions / impressions.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impression yield</strong></td>
    <td>The average number of ads served on each query (raw SRPV). The formula is: ad impression yield = ad impressions / raw SRPV.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impressions</strong></td>
    <td>The total number of ads served. For a single query (or SRPV), there could be multiple ads served.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad unit ID</strong></td>
    <td>An ID that uniquely identifies the ad unit.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Ad unit name</strong></td>
    <td>The display name of the ad unit. </td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Click yield</strong></td>
    <td>The average number of ads that Bing returned per request (only requests that returned at least one ad are used). It is calculated as clicks / raw SRPV.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Clicks</strong></td>
    <td>The number of clicks the ad unit received during the specified reporting period.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Coverage</strong></td>
    <td>The percentage of queries for which at least one ad was shown. </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CPC</strong></td>
    <td>The cost per click. CPC is calculated by dividing estimated revenue by clicks.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>CTR</strong></td>
    <td>The click-through rate of the ad unit. The CTR is calculated by dividing the number of times the ads were clicked by the number of impressions.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Currency</strong></td>
    <td>The currency that the revenue-related columns are specified in. The column contains the ISO 4217 code of the currency (for example, USD for US Dollar). Because currency is specified in your account, you should include this column if your accounts use different currencies.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Date</strong></td>
    <td>The time period for the data in the report, in the unit of time you have selected.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Device type</strong></td>
    <td>The type of device that the ads were displayed on. The following are the possible values: HiFi Phone, LoFi Phone, PC, Tablet. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>eCPM</strong></td>
    <td>The estimated revenue per one thousand impressions. The effective revenue is calculated after fraud detection and traffic filtering is applied. </td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Estimated revenue</strong></td>
    <td>The estimated amount of gross revenue before revenue sharing is applied..</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Impressions</strong></td>
    <td>The number of times Bing Ads responds to a search query with an ad. For example, if a user searches on one keyword and navigates to three pages of search results -- but Bing Ads only displays ads on the first two pages -- then this will count as two impressions.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Language</strong></td>
    <td>The language used by the ads requests. For example, English.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Market</strong></td>
    <td>The market (country/region) used by the ads requests. For example, United States.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>PTQS</strong></td>
    <td>The publisher's traffic quality score. Publishers can use the score to compare traffic trends and gain insight into the quality of their site traffic and either improve efficiencies or remove poorly performing traffic. The score is calculated by analyzing an ad unit's performance using its impressions, clicks, and conversions metrics, among others. The possible scores are 0.5 through 10.0, with 10 being the highest. The score is specified in increments of 0.5. If the ad unit does not have a quality score, the value is -1. A higher score indicates better traffic quality. The score is one factor that determines the cost per click (CPC) that advertisers pay. The lower the quality score, the lower the CPC.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher ID</strong></td>
    <td>An ID that uniquely identifies the publisher.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher name</strong></td>
    <td>The name of the publisher. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Queries</strong></td>
    <td>The number of distinct search queries from a given user. For example, if a user searches for two different keywords and navigates to three pages of search results, this counts as two queries.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Raw SRPV</strong></td>
    <td>Raw search results page views — the number of times a search request is received by the Bing Ads platform. Note that each page request for the same keyword/query is counted as an independent raw SRPV. For example, if a user searches for "camera" and then navigates to the second and third pages of search results, there are three requests made (one per page) to the Bing Ads platform, so the raw SRPV count will be three.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>RPM</strong></td>
    <td>The estimated revenue per thousand raw SRPV. It is calculated as (estimated revenue * 1,000) / raw SRPV.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Type tag</strong></td>
    <td>Type tags are text strings that publishers send along with each ad request for the purpose of data classification. For example, a publisher could use a browser name or a content category as a type tag, and with these reports, you could compare browser or content category performance.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
</table>

## PTQS (Publisher Traffic Quality Score) report
## Filters

Filter by account and by specific ad unit.

## Available columns

<table>
  <tr>
    <th style="text-align:left">Column name</th>
    <th style="text-align:left">What does it mean?</th>
    <th style="text-align:left">Setting or metric?</th>
    <th style="text-align:left">Optional or required?</th>
  </tr>
  <tr>
    <td><strong>Account ID</strong></td>
    <td>An ID that uniquely identifies the account. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account name</strong></td>
    <td>The name of the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Account number</strong></td>
    <td>The number associated with the account.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad CTR</strong></td>
    <td>The click-through rate based on all ads that were shown to a user. It is calculated as (clicks * 100) / ad impressions.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad density</strong></td>
    <td>The average number of ads served on each query where Bing Ads returned at least one ad (impression or bidded SRPV). The formula is: ad density = ad impressions / impressions.
			</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad impressions</strong></td>
    <td>The total number of ads served. For a single query (or SRPV), there could be multiple ads served.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Ad unit ID</strong></td>
    <td>An ID that uniquely identifies the ad unit.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Ad unit name</strong></td>
    <td>The display name of the ad unit. </td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Clicks</strong></td>
    <td>The number of clicks the ad unit received during the specified reporting period.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Currency</strong></td>
    <td>The currency that the revenue-related columns are specified in. The column contains the ISO 4217 code of the currency (for example, USD for US Dollar). Because currency is specified in your account, you should include this column if your accounts use different currencies.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Date</strong></td>
    <td>The time period for the data in the report, in the unit of time you have selected.</td>
    <td>Setting</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Estimated revenue</strong></td>
    <td>The estimated amount of gross revenue before revenue sharing is applied.</td>
    <td>Metric</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Impressions</strong></td>
    <td>The number of times Bing Ads responds to a search query with an ad. For example, if a user searches on one keyword and navigates to three pages of search results -- but Bing Ads only displays ads on the first two pages -- then this will count as two impressions.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>PTQS</strong></td>
    <td>The publisher's traffic quality score. Publishers can use the score to compare traffic trends and gain insight into the quality of their site traffic and either improve efficiencies or remove poorly performing traffic. The score is calculated by analyzing an ad unit's performance using its impressions, clicks, and conversions metrics, among others. The possible scores are 0.5 through 10.0, with 10 being the highest. The score is specified in increments of 0.5. If the ad unit does not have a quality score, the value is -1. A higher score indicates better traffic quality. The score is one factor that determines the cost per click (CPC) that advertisers pay. The lower the quality score, the lower the CPC.</td>
    <td>Metric</td>
    <td>Required</td>
  </tr>
  <tr>
    <td><strong>Publisher ID</strong></td>
    <td>An ID that uniquely identifies the publisher.</td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
  <tr>
    <td><strong>Publisher name</strong></td>
    <td>The name of the publisher. </td>
    <td>Setting</td>
    <td>Optional</td>
  </tr>
</table>

> [!IMPORTANT]
> This help content applies only to paid search Bing Ads partners who are registered through pubCenter.


