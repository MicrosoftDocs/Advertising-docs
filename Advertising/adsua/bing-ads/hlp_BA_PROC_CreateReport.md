---
title: Create a report
description: Use report information to help improve your campaign's relevance and the conversion rates for your ads. Here’s how you create a new report and schedule regular reports to be emailed to you.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Create a report

Microsoft Advertising provides several types of reports to help you monitor, manage and improve your campaign's performance. Get deeper looks into data such as visibility, click-through rate, and conversion rates for your ads, in reports such as:

- The **Keyword**, **Campaign**, **Ad** and **Ad group** reports tell you which campaigns are performing well and how your keywords are contributing to campaign performance.
- The **Search term** report shows which words customers enter into search to cause your ads to display.
- The **Share of voice** report gives you an estimate on where you might be losing to competitors in the marketplace.

> [!NOTE]
> Reports will not include campaigns, ad groups, keywords, or other entities with zero impressions.
> Reporting data is kept for limited periods of time. If you want to learn how far back hourly, daily, weekly, monthly, yearly and summary aggregated data can be retrieved for a report type, see [this Bing Ads API doc](https://go.microsoft.com/fwlink?LinkId=734729).

<anchor id="standard_report" />

## Choose the report you want
Each report type breaks out your data in different ways, to help you see deeper into your campaigns' performance. Choose the report type that shows the data most interesting to you:

## Performance

<table>
  <tr>
    <th colspan="2" scope="col">Account</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The impressions, impression share (%), clicks, spend, and average cost-per-click for individual accounts. This data can be sorted by individual accounts, currency, bid match type, and delivered match type.
            </td>
    <td>
              <strong>Why run it: </strong>To observe long-term Microsoft Advertising account performance and trends.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Campaign</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, impression share (%), clicks, spend, and average cost-per-click for each campaign or account. This data can be sorted by campaign, campaign status, and quality score.
            </td>
    <td>
              <strong>Why run it:</strong> To view high-level performance statistics and quality attributes for each campaign or account. This is also a quick way to flag any major campaign or account problems.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Ad group</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, impression share (%), clicks, spend, and average cost-per-click of your ad groups. This data can be sorted by ad group, ad group status, language, and network.
            </td>
    <td>
              <strong>Why run it:</strong> To more broadly compare delivery performance statistics by ad group, campaign, or account attributes, rather than at the keyword level.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Ad</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The impressions, clicks, spend, and average cost-per-click for each ad. This data can be sorted by ad ID, ad status, ad title(s), display URL, and destination URL.
            </td>
    <td>
              <strong>Why run it: </strong>To help you determine which ads lead to clicks and conversions, and which are not performing. Having underperforming ads in your account can pull down the quality of your campaigns.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Keyword</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The impressions, clicks, click-through rate, quality score, bid, cost-per-click, position, and conversions for each individual keyword within your campaign.
            </td>
    <td>
              <strong>Why run it: </strong>To find out which keywords are triggering your ads and getting clicks. You can also identify keywords that aren’t performing well, to determine if you want to delete them.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Negative keyword conflicts</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> Negative keywords that conflict with some of your keywords, and block your ad from showing.
            </td>
    <td>
              <strong>Why run it:</strong> This report tells you which keywords and negative keywords are in conflict, and whether the conflict is at the campaign or ad group level. Use this list to figure out which negative keywords to delete.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Search term</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The impressions, clicks, and click-through rate based on the search terms that have triggered your ads. This data can be filtered for search campaigns and for shopping campaigns.
            </td>
    <td>
              <strong>Why run it: </strong>To get insight into what your audience is searching for when your ads are shown, as well as ensure that your product titles are relevant to search queries.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Share of voice</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, impression share (%), impression share lost to budget (%), and impression share lost to bid. This data can be sorted by keyword, keyword ID, landing page experience, and quality score.
            </td>
    <td>
              <strong>Why run it:</strong> To view impression share (%) of successful bids for each keyword, and identify opportunities to increase impression share.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Destination URL</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click for your landing pages. This data can be sorted by destination URL, account, campaign, and ad group. Note that only the first URL in the list (ad, keyword, or criterion) is reported.
            </td>
    <td>
              <strong>Why run it:</strong> To identify landing pages that met audience expectations, resulting in high click or conversion ratios.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Website URL (publisher)</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and conversions for websites on the Microsoft Search Network and the Microsoft Audience Network. This data can be sorted by website URL, account, campaign, and ad group.
            </td>
    <td>
              <strong>Why run it:</strong> To see which website URLs are or aren’t performing well enough for your campaign or ad group target settings. For example, if ad impressions at those URLs yield a low click-through-rate, then you might decide to exclude those websites from your campaign.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Ad dynamic text</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click of your dynamic text strings. This data can be sorted by ad title, destination URL, or the param dynamic text placeholders.
            </td>
    <td>
              <strong>Why run it:</strong> To identify which dynamic text strings are performing well and which strings you might consider changing.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Rich ad component</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The component clicks and component click-through rate of your rich ads. This data can be sorted by rich ad subtype, ad title, and component.
            </td>
    <td>
              <strong>Why run it:</strong> To view delivery performance of your Rich Ads in Search (RAIS) campaigns.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Audiences</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, revenue, and conversions for your audiences.
            </td>
    <td>
              <strong>Why run it:</strong> To evaluate performance of remarketing campaigns.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Goals</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The spend, revenue, assists, conversions, and conversion steps of your websites. This data can be sorted by account, ad group, campaign, keyword, and goal.
            </td>
    <td>
              <strong>Why run it:</strong> To discover whether visitors who arrive at your website via an Ad click, complete the steps on conversion pages of your website. This report provides data for your conversions’ goals, including UET tags, App Install Ads, offline conversions, and historical campaign data.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Conversions</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The conversions, assists, revenue, and revenue per conversion for your campaigns. This data can be sorted by account, ad group, campaign, keyword, and device type.
            </td>
    <td>
              <strong>Why run it:</strong> To understand which campaigns and keywords are leading customers to complete conversion actions. This report provides data for your conversions’ goals, including UET tags, App Install Ads, offline conversions, and historical campaign data.
            </td>
  </tr>
</table>

## Ad extensions

<table>
  <tr>
    <th colspan="2" scope="col">Ad extension by keyword</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click of your extensions for each keyword. This data can be sorted by keyword, keyword ID, ad extension type, and ad extension version.
            </td>
    <td>
              <strong>Why run it:</strong> To compare how well different versions of your ad extensions are performing for each keyword.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Ad extension by ad</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The aggregated extension impressions, clicks, spend, and average cost-per-click by ad. This data can be sorted by ad ID, ad title, ad extension type, and ad extension version.
            </td>
    <td>
              <strong>Why run it:</strong> To compare how well different versions of your ad extensions are performing with each ad. 
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Ad extension details</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click of individual extension items. This data can be sorted by the individual ad extension property value, ad extension ID, and ad extension type.
            </td>
    <td>
              <strong>Why run it:</strong> To discover the effectiveness of individual ad extension items, for example, each link of a sitelink extension.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Call forwarding detail</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> Duration for each forwarded call that originated from a call ad extension.
            </td>
    <td>
              <strong>Why run it:</strong> To discover which accounts, campaigns, or ad groups are driving the most completed phone calls.
            </td>
  </tr>
</table>

## Product ads

<table>
  <tr>
    <th colspan="2" scope="col">Product partition</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click and average conversion for each product group in your Microsoft Shopping Campaigns. 
            </td>
    <td>
              <strong>Why run it:</strong> To see the performance data for the product groups in your shopping campaigns and to optimize your campaigns accordingly.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product partition unit</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click, and average conversions for each product group in your Microsoft Shopping Campaigns. Depending on the report time and columns you choose, the report may include more than one row per product group.
            </td>
    <td>
              <strong>Why run it:</strong> To see product partition unit data of your Product Groups in Microsoft Shopping Campaigns.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product dimension</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, average cost-per-click and conversion for each product in your catalog (each line item in Microsoft Merchant Center catalog).
            </td>
    <td>
              <strong>Why run it:</strong> To figure out which of your products are triggering ads and getting the most clicks, and optimize the ones not performing so well.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product match count</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The number of products that are matched and targeted at the campaign, ad group, and product group level.
            </td>
    <td>
              <strong>Why run it: </strong>To see if you covered your bidding across the Microsoft Shopping Campaigns inventory.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product negative keyword conflicts</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>Shopping negative keywords that conflict with some of your products, and block your ad from showing.
            </td>
    <td>
              <strong>Why run it: </strong>This report tells you which products and negative keywords are in conflict, and whether the conflict is at the campaign or ad group level. Use this list to figure out which negative keywords to delete.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Product search term report</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows: </strong>The impressions, clicks, click-through rate, and average position for search terms that have triggered your ads.
            </td>
    <td>
              <strong>Why run it: </strong>To see what your audience is searching for when your ads are shown. You can use this information to make informed additions, removals, or edits to both your keyword and negative keyword lists.
            </td>
  </tr>
</table>

## Change history

<table>
  <tr>
    <th colspan="2" scope="col">Change history</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> A record of changes made to an account, including keyword bid changes, landing page changes, new campaign creations, or when new account budgets are added to the account.
            </td>
    <td>
              <strong>Why run it:</strong> To discover when changes to an account were made, as well as which user made them.
            </td>
  </tr>
</table>

## Targeting

<table>
  <tr>
    <th colspan="2" scope="col">Age and gender</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click for each ad group, organized by gender and age group. 
            </td>
    <td>
              <strong>Why run it:</strong> To discover how your campaigns and ad groups are resonating with audiences of diverse age and gender.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">User location</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click for each ad group, organized by city, country, metro area, radius, state, and account.
            </td>
    <td>
              <strong>Why run it:</strong> To see which locations your traffic is coming from. You can then validate whether your location targeting strategy is successful, and identify opportunities to improve.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Geographic</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The impressions, clicks, spend, and average cost-per-click for each ad group, organized into columns that show the location used to serve ads. The location can be where the customers were physically located (location type is physical location) or the location that customers showed interest in (location type is location of interest.)
            </td>
    <td>
              <strong>Why run it:</strong> To see which locations your traffic is coming from. You can then validate whether your location targeting strategy is successful, and identify opportunities to improve.
            </td>
  </tr>
</table>

## Billing and budget

<table>
  <tr>
    <th colspan="2" scope="col">Budget</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> Your monthly budget, how much you have spent to date, and whether you are on target to spend your monthly budget.
            </td>
    <td>
              <strong>Why run it:</strong> To help control and manage your advertising spend for a particular month.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Billing statement</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> Billing documents, including invoices and credit memos.
            </td>
    <td>
              <strong>Why run it:</strong> To view an overall summary of your billing information.
            </td>
  </tr>
</table>

## Dynamic search ads

<table>
  <tr>
    <th colspan="2" scope="col">Dynamic search ad auto target</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The clicks, impressions, and other performance metrics of each of your dynamic ad targets.
            </td>
    <td>
              <strong>Why run it:</strong> To understand how your dynamic ad targets are performing and where bid adjustments may be useful.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Dynamic search ad category</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> The clicks, impressions, and other performance generated from your website.
            </td>
    <td>
              <strong>Why run it:</strong> To check the performance of your existing category targets or to find new categories worth targeting.
            </td>
  </tr>
  <tr>
    <th colspan="2" scope="col">Dynamic search ad search term</th>
  </tr>
  <tr>
    <td>
              <strong>What it shows:</strong> Search terms that triggered your dynamic search ads and their corresponding headlines, final URLs, and associated performance metrics.
            </td>
    <td>
              <strong>Why run it:</strong> To see how your ads perform against search terms. The data can help you find negative keywords (so that you're not spending money targeting the wrong customer), as well as the right keywords that create conversions.
            </td>
  </tr>
</table>

## Create a report
1. From the global menu at the top of the page, click **Reports** and then click **Reports**.
1. Select either **Performance**, **Ad extensions**, **Product ads**, **Change history**, **Targeting**, **Billing and budget**, or **Dynamic search ads**.
1. Select the report you want.
1. Select from each list the settings you want for **Show (unit of time)**, **Date range**, and download **Format**. At **What to report on**, if you select **Specific accounts and campaigns**, a box appears for you to select the campaign or account to report on.
1. Under **Choose your columns**, add or remove the columns to set up your report to show what you want.
1. Optionally, you can select a **Filter** to apply to your report.
1. Click **Run** to run the report, or **Download** to download the report as CSV, TSV, or XLSX (Microsoft Excel) file.

> [!NOTE]
> Remember, effects of any updates you make to campaigns can take up to a couple of weeks to show in report data. So, consider running performance reports in two- to four-week intervals.
> You can regularly run reports either manually using those saved in **Reports History**, or by scheduling reports to automatically run on a regular basis.

## Create a custom report
You can customize and save a standard report, to run it again in the future.

1. From the global menu at the top of the page, click **Reports** and then click **Reports**.
1. Select either **Performance**, **Ad extensions**, **Product ads**, **Change history**, **Targeting**, **Billing and budget**, or **Dynamic search ads**.
1. Select the report you want.
1. Select the  **Show (unit of time)**, **Date range**, download **Format** and **What to report on** either all accounts or specific ones.
1. Under **Choose your columns**, add or remove the columns to set up your report to show what you want.
1. Optionally, you can select a **Filter** to apply to your report.
1. Click **My report settings** and then select the **Save as custom report** check box.
1. Click **Run**.
1. In the left pane, click **Saved custom reports** and you will see the report you just created. You can click this report anytime to run the report again.
Please note that Report history, Saved campaign reports, and Saved account reports are no longer available in the Microsoft Advertising redesign. From the global menu at the top of the page, click **Reports** to create and save customized reports on any level of Microsoft Advertising.

> [!NOTE]
> To help you more easily find and reuse your custom report, at the top of the page, enter a distinctive name in the **Report name** box.

## Set up a regularly scheduled report
1. From the global menu at the top of the page, click **Reports** and then click **Reports**.
1. Select either **Performance**, **Ad extensions**, **Product ads**, **Change history**, **Targeting**, **Billing and budget**, **Campaign analytics**, or **Dynamic search ads**.
1. Select the report you want.
1. Select the  **Show (unit of time)**, **Date range**, download **Format** and **What to report on** either all accounts or specific ones.
1. Under **Choose your columns**, add or remove the columns to set up your report to show what you want.
1. Optionally, you can select a **Filter** to apply to your report.
1. Click **My report settings** and then select the **Schedule this report** check box.
1. Select the frequency, day of the week, time of day, start date, and end date for the scheduled report.
1. Enter the email address where you want the report sent to, and indicate if you want the report sent as an email attachment. Please note that reports larger than 4MB will not be included as email attachments.
1. Click **Run**.

> [!NOTE]
> As of August 1st, 2019 all new reports must be scheduled to run on one of the first 28 days of the month and set to one of the following frequencies: **Daily**, **Weekly**, or **Monthly**. Please note that this will not impact your existing scheduled reports.

## Cancel a scheduled report
1. From the global menu at the top of the page, click **Reports** > **Reports** > **Saved custom reports**
1. Select the report you want to delete and then click **Delete.**

## Unsubscribe from report notifications
You can always opt out of receiving scheduled report notifications, even if you created the report yourself. There are two ways to do so.

**Option 1**:
In the footer of a scheduled report email, click **Unsubscribe from this scheduled report**.

**Option 2**:

1. From the global menu at the top of the page, click **Reports** > **Reports** **Saved custom reports**.
1. Select the report from which you wish to unsubscribe.
1. Click **My report settings**.
1. In the **Send report to** text box, remove the email addresses for which you wish to unsubscribe.
1. Click **Save** or **Save and run**.

## Email and schedule reports
> [!IMPORTANT]
> Not everyone has this feature yet. If you don't, don't worry — it's coming soon!

1. From the global menu at the top of the page, click **Reports** and then click **Reports**.
1. Select either **Performance**, **Ad extensions**, **Product ads**, **Change history**, **Targeting**, **Billing and budget**, **Campaign analytics**, or **Dynamic search ads**.
1. Select the report you want.
1. Click **Download**.
1. Select the **Format** or **Segment** for the report.
1. You can also select **Email and schedule report**, **Save as custom report**, or both.
1. Click **Download**.
1. To access saved Account Summary reports on the **Accounts Summary** page, from global menu at the top of the page, click **Reports** > **Saved custom reports**).
1. To access saved Campaign reports on the **Campaigns** page, from global menu at the top of the page, click **Reports** > **Saved custom reports**).


