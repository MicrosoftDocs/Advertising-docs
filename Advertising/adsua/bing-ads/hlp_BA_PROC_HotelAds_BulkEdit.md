---
title: Making bulk changes in Hotel Ads
description: Learn how to make bulk changes in Hotel Ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Making bulk changes in Hotel Ads

> [!IMPORTANT]
> Hotel Ads is currently under beta testing and available to select advertisers only. Please contact your account manager for details on how you may be able to join.

You can update your bids, bid multipliers, and hotel group associations in bulk via the Microsoft Hotel Center UI, CSV upload, as well as [Hotels API](https://go.microsoft.com/fwlink?LinkId=862783).

## How to bulk edit bid and bid strategy in Microsoft Advertising

1. In the **Overview** tab, click **View by...** and select either **Hotel** or **Hotel group**.
1. Select the hotels or hotel groups you want to edit in bulk by selecting the checkbox in the table. You can also search for specific hotels or hotel groups in the search box above the table.
1. Click **Bulk edit** and select **Set bid and bid strategy**.
1. Enter the bid and bid strategy details.
1. Click **Save**.

## How to bulk edit bid multipliers in Microsoft Advertising

1. In the **Overview** tab, click **View by...** and select either **Hotel** or **Hotel group**.
1. Select the hotels or hotel groups you want to edit in bulk by selecting the checkbox in the table. You can also search for specific hotels or hotel groups in the search box above the table.
1. Click **Bulk edit** and select **Set bid multipliers**.
1. Enter the **Device type**, **User country**, **Length of stay**, and **Check-in day** details.
1. Optional: Check **Use parent multipliers** to use the subaccount bid multiplier setting.
1. Click **Save**.

## How to bulk edit hotel group associations in Microsoft Advertising

1. In the **Group Editor** tab, select or create the hotel group you would like to move hotels into or out of.
1. If moving hotels into the group, select the desired hotels under "Other hotels" and click "&lt;&lt;" to move them into the group. If moving hotels out of the group, select the desired hotels under your group and click "&gt;&gt;" to ungroup them.
1. You can increase the maximum number of hotels that can be grouped or ungrouped in one operation by changing the number of rows displayed.

## How to make bulk changes using a CSV upload

1. [Download the Hotel Ads bulk upload template](https://go.microsoft.com/fwlink?LinkId=863160). You can also download and edit a CSV list of your hotels by navigating to **Overview**&nbsp;&gt;&nbsp;**View by: hotel**&nbsp;&gt;&nbsp;**Download**. If making bulk changes to hotel group associations, you can similarly download a CSV list of your current associations by navigating to **Group Editor**&nbsp;&gt;&nbsp;**Download associations as CSV**.
1. Prepare your spreadsheet for upload using the below tables for guidance.
1. Navigate to **Accounts Summary**&nbsp;&gt;&nbsp;**Bulk Operations**&nbsp;&gt;&nbsp;**Uploads**.
1. Click **Browse** to locate your updated spreadsheet, then click **Upload and preview ** and finally **Apply changes** to complete your bulk changes.

> [!NOTE]
> When preparing your spreadsheet, the **FormatVersion** row and **Name** column should not be altered.

 
|I want to bulk edit...|Columns required|
|---|---|
|Hotel bids|Type, Account Id, Id, Bid, Bid type|
|Hotel bid multipliers|Type, Account Id, Id, Parent IdAlso required are one or more bid multiplier columns which are documented below.|
|Hotel group associations|Type, Account Id, Id, Parent Id|

 
<table type="type1">
  <tr>
    <th scope="col">Column(s)</th>
    <th scope="col">Description</th>
  </tr>
  <tr>
    <th scope="row">Type</th>
    <td>
              Defines the type of update being made. Possible values include: Hotel, Hotel Group, Hotel Association. 
            </td>
  </tr>
  <tr>
    <th scope="row">Name</th>
    <td>
				Used by the FormatVersion row only, do not edit.

            </td>
  </tr>
  <tr>
    <th scope="row">Account Id</th>
    <td>
              Your Microsoft Advertising account ID. 
            </td>
  </tr>
  <tr>
    <th scope="row">Id</th>
    <td>
              The ID of the entity being updated. For hotel group associations, this is the ID of the hotel to be grouped or ungrouped.  
            </td>
  </tr>
  <tr>
    <th scope="row">Parent Id</th>
    <td>
              The ID of the direct parent entity. For hotel group updates, this is the subaccount ID. For hotel group association updates, this is the ID of the group to move the hotel into.  
            </td>
  </tr>
  <tr>
    <th scope="row">Bid type</th>
    <td>
              Possible values: Percentage, Fixed.
            </td>
  </tr>
  <tr>
    <th scope="row">Bid</th>
    <td>
              The corresponding bid value. For both percentage and fixed bids, up to two decimal points of precision are supported. For example, 8.25 represents 8.25% if your bid type is percentage, or $8.25 if your bid type is fixed. Set to delete_value if you want the hotel or hotel group to inherit its bid from its parent.
            </td>
  </tr>
  <tr>
    <th scope="row">Device desktop  Device tablet  Device mobile</th>
    <td>
      <para>Adjust your bids based on the device the searcher is using. </para>
      <ul>
        <li>To increase a device's bid by 20%, you would enter 1.2</li>
        <li>To decrease a device's bid by 10.5%, you would enter .895</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row">Checkin monday   Checkin tuesday  Checkin wednesday  Checkin thursday  Checkin friday Checkin saturday  Checkin sunday</th>
    <td>
      <para>Adjust your bids based on the day of check in at the hotel. </para>
      <ul>
        <li>To increase a day's bid by 40%, you would enter 1.4</li>
        <li>To decrease a day's bid by 34.2%, you would enter .658 </li>
      </ul>
    </td>
  </tr>
  <tr>
    <th scope="row">Length of stay 1   Length of stay 2  ...   Length of stay 14</th>
    <td>
      <para>Adjust your bids based on how many nights are included in the reservation. This multiplier applies to all lengths of stay greater than or equal to the one currently being specified (up to a maximum of 14). </para>
      <para>For example, to increase bids by 10% for lengths of stay between 1 and 6 nights, and decrease bids by 20% for lengths of stay between 7 and 14 nights, you would set Length of stay 1 equal to 1.1 and Length of stay 7 equal to .8.</para>
    </td>
  </tr>
  <tr>
    <th scope="row">Country AR   Country AU ...   Country US  Country VE  Country VN</th>
    <td>
              Adjust your bids based on the country of the user.
            </td>
  </tr>
  <tr>
    <th scope="row">Advance booking window min days 1   Advance booking window multiplier 1 ...   Advance booking window min days 10  Advanced booking window multiplier 10</th>
    <td>
      <para>Adjust your bids based on how many days in advance the reservation is being made, also known as advanced booking window (ABW). The min days column specifies the minimum number of days in the ABW range to apply the multiplier to. The corresponding multiplier column defines the multiplier factor.
				</para>
      <para>For example:</para>
      <ul>
        <li>...min days 1   = 1 (0-1 days)</li>
        <li>...multiplier 1 = 1.2 </li>
        <li>...min days 2   = 9 (2-9 days)</li>
        <li>...multiplier 2 = 1.1 </li>
        <li>...min days 3   = 90 (10-90 days)</li>
        <li>...multiplier 3 = .9 </li>
      </ul>
      <para>The maximum advanced booking window allowed is 90 days.</para>
    </td>
  </tr>
</table>

> [!NOTE]
> To delete a bid multiplier, use "delete_value" where you normally specify the multiplier's value. In the case of deleting an advanced booking window multiplier, "delete_value" does not also need to be specified in the ** ...min days** column.


