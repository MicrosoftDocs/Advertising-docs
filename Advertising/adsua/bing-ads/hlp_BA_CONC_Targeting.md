---
title: How can I get my ads in front of my customers?
description: Use targeting to help focus your ads on potential customers who meet specific criteria (such as location or age), increasing the chance that they see your ads.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How can I get my ads in front of my customers?

Getting your ad in front of the right people—that's what targeting is all about. With targeting, Microsoft Advertising can help you focus a campaign or ad group on potential customers who meet specific criteria, so you can increase the chance that they see your ads. To learn how, see [How to target customers](./hlp_BA_PROC_TargetingAgeGender.md).

There are four ways to target your ads. You can use these individually or in combination:

## Geographic location
When you target by location, you can choose to show ads to potential customers in:

- United States and Canada
- All available countries/regions
- Selected countries/regions and states/provinces
- Selected counties within the United States
- Selected cities, metro areas, and postal codes\* within Australia, Canada, France, Germany, United Kingdom, and United States
**\*Note:	**
- **	Not all postal codes are supported for targeting exactly within their boundaries. If you target an unsupported postal code, it will be converted into a radius target (see below).**
- **	For Canadian and UK postal codes, only the first segment (for Canada, the first 3 characters; for UK, the first 2-to-4-character segment) is recognized. If you enter the second segment, you will only be able to use radius targeting.**
- **	The boundaries of some postal codes in Australia, Canada, France, Germany, and United Kingdom do not appear accurately on the map you see in Microsoft Advertising, but targeting within them will still function accurately.**

- A specified radius around a postal code, coordinates\*, landmark, or area
**\*Coordinates can be searched for in the format "[latitude], [longitude]" with the degrees in decimal form — for example, "44.590,-104.716". **

Although location targeting is most often used to designate the specific locations where you want to show your ads, Microsoft Advertising also lets you target locations you specifically want to **exclude** from seeing your ads. (Note: You cannot exclude using radius targeting. Also, keep in mind that Shopping Campaigns and product ads are available only in the United States, United Kingdom, Australia, France, Germany, India, and Canada (English only and excluding Quebec).)

> [!IMPORTANT]
> Microsoft Advertising will honor your location targeting settings and exclude locations you don’t want to target. However, location targeting and exclusions may not always work because of factors beyond the control of Microsoft Advertising, such as a customer’s device settings or the inherent limits of geolocation via GPS, IP addresses, Wi-Fi networks, and Bluetooth.

Not only does Microsoft Advertising let you target customers in a specific location, you can also show ads to customers searching **about** a specific location. Take a look at the following examples:

## Example 1

- **Who should see your ads?**             **People in your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**No** , **not** located in target location|
|London|Hotels|**Yes** , located **in** target location|
|London|New York hotels|**Yes** , located **in** target location|

## Example 2

- **Who should see your ads?**             **People searching for or viewing pages about your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**Yes** , searching **about** target location|
|London|Hotels|**No** , not searching for pages **about** target location|
|London|New York hotels|**No** , not searching for pages **about** target location|

## Example 3

- **Who should see your ads?**             Both **People in your targeted locations** and **People searching for or viewing pages about your targeted locations**
- **Target location defined in your campaign:**  London
- **Keyword:**  Hotels

|Searcher’s physical location|Search term|Ad eligible for display?|
|---|---|---|
|Florida|London hotels|**Yes** , searching **about** target location|
|London|Hotels|**Yes** , located **in** target location|
|London|New York hotels|**Yes** , located **in** target location|

## Day of the week or time of day
As your campaign progresses, you may find that your click-through rate and conversion rate are highest during certain times, for example, weeknights. This might be a perfect opportunity to use bid adjustments to improve your chances of displaying your ad Monday through Friday from 6:00 PM to 11:00 PM.

When targeting by time, you can choose to use **Your account's time zone** or the **Ad viewer's time zone**. For example, let's say you want to increase your bid by 10% for 6:00 PM to 11:00 PM.
- **Your account's time zone** : If your account location is New York, the bid adjustment will be effective for ad viewers in New York from 6:00 PM to 11:00 PM Eastern time, and simultaneously for ad viewers in Los Angeles, from 3:00 PM to 8:00 PM Pacific time.
- **Ad viewer's time zone** : The bid adjustment will be effective for ad viewers in New York from 6:00 PM to 11:00 PM Eastern time, and also from 6:00 PM to 11:00 PM Pacific Time for ad viewers in Los Angeles.

## Device type
You can target by the type of device your potential customer is using — desktop computer (which also includes laptop computers), tablet, or smartphone — giving you greater control over who sees your ads.

## Age and gender
You can also target customers by age and gender so that your ads are displayed more frequently to people who will be interested in them.

> [!NOTE]
> Ads will not be shown to customers under 18 years of age if the ad content is determined to deal with mature subjects such as gambling, tobacco, weapons, violence, alcohol, or hate speech.
> To opt out of showing ads to customers under 18 years of age regardless of your ads' content, just submit [this form](https://go.microsoft.com/fwlink?LinkId=875182) (when you click the link, you will need to sign in to Microsoft Advertising if you aren't currently signed in). You can opt back in using the same form.
> Age information from the customer's Microsoft account will be used to determine the customer's age.

When you select any of these targets, you can place an optional extra bid, known as an bid adjustment. Placing a bid adjustment increases the likelihood that your ad is displayed in a better position for customers who meet your targeting criteria. For more information about incremental bids, including a couple of examples, take a look at [How to target my customers by adjusting my bids](./hlp_BA_CONC_AboutAdvancedBidding.md).

If you use targeting, you should set your basic targets at the campaign level and then refine your targets at the ad group level. If there is no conflict between the targeting settings at both the campaign and ad group levels, Microsoft Advertising uses both. If there's a conflict, ad group targets take precedence. Campaign targets apply to all ad groups in that campaign. Ad group targets override campaign targets within that ad group.


