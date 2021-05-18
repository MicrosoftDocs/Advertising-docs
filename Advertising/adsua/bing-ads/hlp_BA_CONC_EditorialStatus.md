---
title: Delivery status
description: Learn about delivery statuses and how they affect your campaigns, ad groups, ads, keywords, ad extensions, ad customizers, or audience associations.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Delivery status

Delivery status tells you if your campaign, ad group, ad, keyword, ad extension, ad customizer, or audience association is operating correctly. The status **Eligible** indicates that your ad or ads are available to be displayed, unless there is [an error with your account](./hlp_BA_CONC_AccountErrors.md).

To determine the delivery status of your campaign, ad group, ad, keyword, ad extension, or audience association:

1. From the **Campaigns** page, click the **Campaigns**, **Ad Groups**, **Ads**, **Keywords**, **Ad Extensions**, or **Audiences** tab (or from the main menu on the left, click **All campaigns** and then either **Campaigns**, **Ad groups**, **Ads &amp; extensions**, **Keywords**, or **Audiences**).
1. Check the statuses of individual items in the **Delivery** column.
1. To make it easier to find non-**Eligible** statuses, you can sort the **Delivery** column by clicking the **Delivery** column header.

> [!NOTE]
> In the **Keywords** table, you can click the ellipsis icon ![More information icon](../images/BA_ScreenCap_DeliveryDetails.png) next to (or hover over) a keyword's delivery status to get an explanation of the problem and how to fix it.

 
## Possible delivery statuses

## Ad group expired
**What this means** : No ads are running for this ad group, ad, or keyword because the ad group's end date has passed.

**How to fix it** : To start running ads again, go to this ad group's Settings page, and, under **Advanced ad group settings** &nbsp;&gt;&nbsp; **Ad schedule**, adjust its **End date**.

## Ad group paused
**What this means** : No ads are running for this ad group, ad, or keyword because the ad group is set to **Pause**.

**How to fix it** : To start running ads again, go to the **Ad groups** table, select the checkbox next to the appropriate ad group, and click **Edit** &nbsp;&gt;&nbsp; **Enable**.

## Ad group targeting check pending
**What this means** : No ads are running for this ad group or ad because the ad group's targeting scope is under review.

**How to fix it** : We review an ad group's audience targeting scope every time you create or modify an ad group's audience. If the scope is wide enough, this status will change to **Eligible** (barring other issues). If the scope is **not** wide enough, this status will change to **Ad targeting too narrow**. Most reviews of targeting modifications are completed in less than an hour, but reviews of newly-created audience lists may take longer than a day.

## Ad group targeting too narrow
**What this means** : No ads are running for this ad group or ad because the ad group's targeting scope is not wide enough.

**How to fix it** : Adjust the targeting criteria for this ad group to make it less restrictive. After you modify the targeting, we will review it again.

## Ad paused
**What this means** : This ad isn't running because the ad is set to **Pause**.

**How to fix it** : To start running this ad again, go to the **Ads** table, select the checkbox next to the appropriate ad, and click **Edit** &nbsp;&gt;&nbsp; **Enable**.

## App not found
**What this means** : Your app cannot be found.

**How to fix it** : Try doing a manual search by entering your app ID or package name. Note that, if your app is brand-new, it can take up to 96 hours to sync.

## App URL incorrect
**What this means** : The link to your app is incorrect.

**How to fix it** : Check the link and make any necessary updates.

## Approved limited
**What this means** : The ad or keyword has been approved in at least one of your targeted locations, but has also been disapproved in at least one other targeted location.

**How to fix it** : For more information, see [What does Approved Limited status mean?](./hlp_BA_CONC_ApprovedLimited.md)

## Association deleted (ad extension)
**What this means** : This ad extension is not running because it is not associated with any campaigns.

**How to fix it** : Create one or more associations.

## Association excluded (audience)
**What this means** : The association for this audience has been excluded.

**How to fix it** : No action is required. Change the association status to **Enabled** if you want to start targeting this audience.

## Association paused (audience)
**What this means** : The association for this audience is set to **Pause**.

**How to fix it** : To start running the audience association again, change the association status to either **Enabled** or **Excluded**.

## Below first page bid
**What this means** : Your bid on this keyword is too low for ads associated with it to appear on the first page of search results. If you see this status even though your ads **are** appearing on the first page, it means that your keywords competed in only a small number of auctions in the marketplace. Increasing your bid to our estimated first page bid can help your ads gain more visibility on the Microsoft Search Network.

**How to fix it** : In the **Keywords** table, select the keyword, click **Edit**, select **Change current bid**, and then select either **Increase to estimated top of page bid** or **Increase to estimated first page bid**.

## Bid strategy is learning
**What this means** : You have recently turned on or switched to a new automated bid strategy. It takes some time for our algorithms to gather enough performance data to learn how to bid most effectively.

**How to fix it** : This issue will resolve itself when we gather enough performance data.

## Campaign out of budget
**What this means** : No ads are running for this campaign, ad group, ad, or keyword because your campaign budget has been used up.

**How to fix it** : Click the **Out of budget** status in the **Delivery** column to review our recommended budget increase. If there is no recommendation, you can increase your budget manually: Go to the **Campaigns** table, click in the **Budget** column for the campaign, increase the budget amount, and then click **Save**.

## Campaign paused
**What this means** : No ads are running for this campaign, ad group, ad, or keyword because the campaign is set to **Pause**.

**How to fix it** : To start running ads again, go to the **Campaigns** table, select the checkbox next to the appropriate campaign, and click **Edit** &nbsp;&gt;&nbsp; **Enable**.

## Campaign suspended
**What this means** : Your account has been suspended because of suspicious activity.

**How to fix it** : Please [contact support](https://go.microsoft.com/fwlink?LinkId=398371).

## Disapproved
**What this means** : We reviewed your ad or keyword and determined that it doesn't adhere to the [Microsoft Advertising policies](./hlp_BA_CONC_EditorialGuidelines.md).

**How to fix it** : For information about disapprovals, and how to fix them or request exceptions, see [How do I fix a Disapproved or Approved Limited status?](./hlp_BA_CONC_EditorialDisapprovalReasons.md)

## Draft ad group
**What this means** : No ads are running for this ad group, ad, or keyword because the associated ad group is still in draft form.

**How to fix it** : To start running ads, go to the **Ad groups** table, select the checkbox next to the appropriate ad group, and click **Edit** &nbsp;&gt;&nbsp; **Enable**.

## Eligible (Ads or Keywords tab)
**What this means** : Your ad or keyword passed the [editorial review](./hlp_BA_CONC_EditProcess.md).

**How to fix it** : As long as your active ad content has at least one active keyword associated with it (and there are no [errors with your account](./hlp_BA_CONC_AccountErrors.md)), your ad is available for people to see.

## Eligible (Campaigns or Ad groups tab)
**What this means** : Your campaign or ad group is functional.

**How to fix it** : There are no campaign-level or ad-group-level issues. If your campaign's delivery status is Eligible, you will also see a light bulb icon in the **Delivery** column. Clicking this will show you some recommendations for improving this campaign's performance. [Learn more about recommendations](./hlp_BA_CONC_Recommendations.md).

## Exception under review
**What this means** : This ad or keyword is not running because it is still pending [editorial review](./hlp_BA_CONC_EditProcess.md) after your [disapproval exception request](./hlp_BA_PROC_RequestException.md).

**How to fix it** : The Microsoft Advertising team responds to requests as quickly as possible -- most reviews are completed within a day. After we've reviewed your request, we'll change the status of the ad or keyword and send you an email summarizing any approvals or disapprovals.

## Extension and association deleted
**What this means** : This ad extension and all its associations are not running because the ad extension has been deleted.

**How to fix it** : You cannot undo a deletion, but you could re-create the ad extension and associations.

## Hold
**What this means** : We tried to charge your primary payment method five times (and, if you have one set, your backup payment method three times), but the charges were not authorized. All of your accounts have been paused, and none of your ads are displaying.

**How to fix it** : To fix this, see [Why is my account on hold?](./hlp_BA_PROC_AlertAcctHold.md)

## Keyword paused
**What this means** : No ads are running for this keyword because the keyword is set to **Pause**.

**How to fix it** : To start running ads for this keyword again, go to the **Keywords** table, select the checkbox next to the appropriate keyword, and click **Edit** &nbsp;&gt;&nbsp; **Enable**.

## Limited by budget
**What this means** : Your average daily budget is lower than the amount we recommend, so your ads aren't regularly showing as often as they could. This status means that your campaign ran out of budget at least once in the past 15 days or that we've determined that your campaign will run out of budget in the coming weeks.

A campaign that's limited by budget can still be successful and meet your business goals, but there might be opportunities to gain more exposure if you're able to increase your budget.

**Why it appears** : When your budget is below the recommended amount, it's possible that your budget can't accommodate all of the traffic available for your keywords and other campaign targeting settings. To make sure that your budget lasts throughout each day, Microsoft Advertising will reduce how often your ads appear.

**How to fix it** : Click the **Limited by budget** status in the **Delivery** column to review how your performance could be affected if you use a different budget.

## Low quality score
**What this means** : Your ads are running, but you may be missing potential traffic because the low quality score of one or more of your keywords is making your ads less competitive.

**How to fix it** : For more information, see [Quality score in depth](./hlp_BA_CONC_AboutQualityScore.md)

## Low search volume
**What this means** : This keyword has very little or no search history on the Microsoft Search Network. The keyword will be inactive until its search traffic increases, at which point it can start triggering your ads to appear. Our system checks and updates this status weekly.

**How to fix it** : You have a couple of options:
- You can choose to do nothing and wait for our system to check again in a week. If more people start searching for your keyword, we'll reactivate it. This option might be best if you're advertising a new brand, term, or product.
- You can remove the keyword and use [Keyword Planner](./hlp_BA_CONC_AboutKWResearch.md) to find additional keyword ideas.

## Negative keyword conflict
**What this means** : This keyword isn't in effect because it conflicts with a negative keyword.

**How to fix it** : To start showing ads for this keyword again, first [create a negative keyword conflicts report](./hlp_BA_PROC_CreateReport.md) by selecting **Negative keyword conflicts** in the **Targeting** report section. Then delete the conflicting negative keyword.

## Pending app verification
**What this means** : Your app is currently being verified.

**How to fix it** : It can take up to a business day for your app to be verified. For brand-new apps, it can take up to 96 hours to sync.

## Pending editorial review
**What this means** : This ad or keyword is not running because it is still under [editorial review](./hlp_BA_CONC_EditProcess.md).

**How to fix it** : The Microsoft Advertising team performs editorial reviews as quickly as possible -- most reviews are completed within a day. After we've completed the review, we'll change the status of the ad or keyword.

## Pending targeting review
**What this means** : The ad group is not serving ads yet because we are evaluating the scope of your ad group's targeting.

**How to fix it** : We are performing a review of your targeting to make sure it's broad enough to serve. Most reviews are completed within 15 minutes, but some ad groups can take a full day. After we've completed the review, we'll change the status of the ad group's ads and keywords:

- If your targeting is broad enough—and there are no other issues—the status will change to **Eligible**.
- If your targeting is not broad enough, the status will change to **Targeting too narrow**.

## Product offers not found
**What this means** : This campaign's product offers cannot be found.

**How to fix it** : Go to  Microsoft Merchant Center to make sure that the associated store contains approved offers.

## Store not found
**What this means** : This campaign's store cannot be found.

**How to fix it** : Go to  Microsoft Merchant Center to make sure that the associated store is active and contains approved offers.

## Targeting too narrow
**What this means** : The ad group is not serving ads because your ad group targeting is too narrow.

**How to fix it** : Update your ad group targeting to be more broad and/or increase the membership of your audiences. To avoid targeting too narrowly, we recommend expanding your ad group targeting to at least 1000 possible monthly impressions.

## URL is invalid
**What this means** : The URL is invalid.

**How to fix it** : Check the link and make any necessary updates.

 

