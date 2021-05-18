---
title: Understanding the Ad extension report
description: Want insight into which ad extensions are getting the most impressions and clicks? The different ad extension reports (on the reports page) and the call forwarding detail report (on both the reports page and dimensions tab) are where to look.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Understanding the Ad extension report

There are four types of ad extension reports:

- **Ad extension by keyword:**   This report shows performance metrics for all ad extension types and click types, which are ad components that can be clicked (for example, the ad title or driving directions).      You can see how many ad extension impressions you’re receiving for each keyword, and which click type is getting the most clicks and impressions.      When you include the click type column, this report shows you how your ad is performing relative to different ad extensions.
- **Ad extension by ad:**   This report contains the same information as Ad extension by keyword reports, sorted by ads rather than keywords.
- **Ad extension details:**   This report shows performance metrics measured when different ad extensions appear in the ad. That helps you analyze which ad extension gets better impressions and clicks results.
- **Call forwarding details:**   Shows the time and duration of each phone call that originated from a Call Extension that uses the Microsoft Advertising forwarding number. The report helps you understand how the accounts, campaigns, or ad groups are performing with Call Extensions.

## How to create an Ad extension report

1. From the global menu at the top of the page, click **Reports** > **Reports** > **Ad extensions**.
1. Click **Ad extensions**, and then the ad extension report type you want.
1. Select from each list the settings you want for **Show (unit of time)**, **Date range**, and download **Format**. At **What to report on**, if you select **Specific accounts and campaigns**, a box appears for you to select the campaign or account to report on.
1. For **What to report on**, you can choose to see how ad extensions are working on **All accounts and campaigns**, or, if you select **Specific accounts and campaigns**, pick the account you want in the **Available items** box that appears.
1. Under **Choose your columns**, add or remove the columns to set up your report to show what you want.
1. Optionally, you can select a **Filter** to apply to your report.
1. Click **Run** to run the report, or **Download** to download the report as CSV, TSV, or XLSX (Microsoft Excel) file.

> [!NOTE]
> Call forwarding detail reports can also be created on the **Campaigns** page, on the **Dimensions** tab. On the **All Campaigns** page, click the **Dimensions** tab, and then open the list at **Show** and click **Call forwarding detail** (or from the global menu at the top of the page, click **Reports** > **Dimensions** > **Basic** > **Call forwarding**).

## How to read the Ad extension report

Here's an example of some of the data provided in these reports (grouped by extension type), along with a short explanation of what the data means:

<table>
  <tr>
    <th colspan="5" scope="col">
        Report data
      </th>
    <th>
         
      </th>
    <th scope="col">
        What it means
      </th>
  </tr>
  <tr>
    <th scope="col">
        Keyword
      </th>
    <th scope="col">
        Ad extension type
        </th>
    <th scope="col">
       Click type
      </th>
    <th scope="col">
        Impressions
      </th>
    <th scope="col">
        Clicks
      </th>
    <th>
         
      </th>
    <th>
         
      </th>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Sitelink Extension
      </td>
    <td>
        Ad title (headline)
      </td>
    <td style="text-align:center">
        20
      </td>
    <td style="text-align:center">
        8
      </td>
    <td>
         
      </td>
    <td>
        Your Sitelink Extension was displayed with the ad title 20 times. The ad title was clicked 8 times.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Sitelink Extension
      </td>
    <td>
        Sitelink
      </td>
    <td style="text-align:center">
        20
      </td>
    <td style="text-align:center">
        2
      </td>
    <td>
         
      </td>
    <td>
        Your Sitelink Extension was clicked 2 times. Note: Ad title and sitelink are always shown together in an ad. Therefore, the two click types have the same number of impressions, in this case 20.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Sitelink Extension
      </td>
    <td>
        Driving directions
      </td>
    <td style="text-align:center">
        8
      </td>
    <td style="text-align:center">
        1
      </td>
    <td>
         
      </td>
    <td>
        Of the 20 times that your Sitelink Extension displayed with ad title, the driving directions link was displayed 8 times, and was clicked once.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Location Extension
      </td>
    <td>
        Ad title (headline)
      </td>
    <td style="text-align:center">
        15
      </td>
    <td style="text-align:center">
        5
      </td>
    <td>
         
      </td>
    <td>
        Your Location Extension was displayed with the ad title 15 times. The ad title was clicked 5 times.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Location Extension
      </td>
    <td>
      Driving direction
      </td>
    <td style="text-align:center">
        15
      </td>
    <td style="text-align:center">
        3
      </td>
    <td>
         
      </td>
    <td>
        The driving direction link was clicked 3 times. Note: Ad title and Location Extension are always shown together in an ad. Therefore, the two click types have the same number of impressions, in this case 15.
      </td>
  </tr>
  <tr>
    <th scope="row" style="background: transparent">Contoso</th>
    <td>
        Location Extension
      </td>
    <td>
        Sitelink
      </td>
    <td style="text-align:center">
        8
      </td>
    <td style="text-align:center">
        2
      </td>
    <td>
         
      </td>
    <td>
        Of the 15 times that your Location Extension displayed with ad title, the sitelink was also displayed 8 times, and was clicked twice.
		</td>
  </tr>
</table>

## Why don't I see clicks and impressions for Call Extensions in reports?

Call Extension data can show differently in different reports, depending on [how you set up Call Extensions in your ads](./hlp_BA_PROC_AddCallExtension.md).

|Option selected|Report|Data shown|What it costs|Where available|
|---|---|---|---|---|
|Bing forwarding number and Show a toll-free number|Ad extension by Ad/Keyword report|Ad extension type name =  Metered Extension|Click calls: Charge CPC bid          Manual calls: No Charge|US and UK only         All devices|
|Bing forwarding number and Show a toll-free number|Call forwarding details report|Call details information|Click calls: Charge CPC bid          Manual calls: No Charge|US and UK only         All devices|
|Bing forwarding number and Show a local number|Ad Extension by Ad/Keyword report|Ad Extension type name =  Metered Extension|Click calls: Charge CPC bid          Manual calls: No Charge|US and UK only         All devices|
|Bing forwarding number and Show a local number|Call forwarding details report|Call details information|Click calls: Charge CPC bid          Manual calls: No Charge|US and UK only         All devices|
|On smartphones using my own phone number|Ad Extension by Ad/Keyword report|Ad Extension type name =  Call Extension|Click calls only: Charge CPC bid|Global         Smartphones only|
|On smartphones using my own phone number|Call forwarding details report|Call details are not available for this selection|N/A|N/A|


