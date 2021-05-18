---
title: Show a countdown to an event in your ad
description: Countdown customizers are tags you can insert into your ad title, body, or paths that show an automatically-updated countdown to an event.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Show a countdown to an event in your ad

Countdown customizers let you easily add a countdown — by day, hour, and then minute — to an event in expanded text ads, dynamic search ads, and responsive search ads. The countdown, which automatically updates as the event draws nearer, is eye-catching and gives potential customers greater incentive to click your ad.

For example, you can use a countdown to draw attention to a sale that is ending:

![Ad with a countdown in hours](../images/BA_CONC_CountdownExample1.png)

...or to promote an upcoming event:

![Ad with a countdown in days](../images/BA_CONC_CountdownExample2.png)

Ads with countdowns only run while the countdown is relevant — they won't start running until a specific day and time that you set, and they'll stop running when the countdown timer expires.

## How to create an ad with a countdown
1. [!INCLUDE [AdsExtensionsAds](./includes/AdsExtensionsAds.md)]
1. Select **Create ad**, and then select an **ad group** that contains expanded search, dynamic search, or responsive search ads.
1. You can insert a countdown as you are entering your ad copy. Simply enter an open curly bracket ( { ), and then select **Countdown** from the drop-down list that appears under the field.
1. **Countdown ends**: select the date and enter the time you want the countdown to end. When this date and time is reached, the ad will stop running. If you leave the time box empty, it will default to midnight at the very beginning of the date you selected.
1. **Countdown starts**: enter how many days before the **Countdown ends** date/time you want this ad to start running (the maximum is 999). Note: If you leave this empty, the countdown will start five days before your **Countdown ends** date/time.
1. **Time zone**: You can choose to have the **Countdown ends** date/time in the viewer's local time zone or your account's time zone. Note: If you use the ad viewer's time zone, your countdown's syntax will start with "=COUNTDOWN"; if you use your account's time zone, it will start with "=GLOBAL_COUNTDOWN".
1. **Language**: For dynamic search and expanded text ads, the countdown will appear in English (for example, "```3 days```"), unless you change it here. To display the countdown in a different language (for example, "```3 jours```" or "```3 Tage```"), select the appropriate language from the drop-down list. Note: The countdown language for responsive search ads will be determined by the language the ad copy is served in.
> [!NOTE]
> The maximum character length of the countdown will vary depending on the language you select. This will affect how long the rest of your title, description, and path can be. Take a look at [this table](https://go.microsoft.com/fwlink?LinkId=855971) to see the supported languages and the countdown character length for each.

1. Select **Set**. You will see this countdown's syntax appear where you typed the { .
1. [!INCLUDE [SelectSave](./includes/SelectSave.md)]

> [!NOTE]
> When considering character length, keep in mind that your text will be determined to be too long if any possible countdown makes it go over the maximum character length for that piece of text. For example, the maximum character length for ad text is 80 characters. Watch what happens here:
> - The ad text "```Take a big first step towards a brighter future. **30 days** to Application Deadline```" is 80 characters long — the maximum length.
> - But the ad text "```Take a big first step towards a brighter future. **17 hours** to Application Deadline```" is 81 characters long — more than the maximum.

## How to create a countdown manually
You can also create a countdown manually, either by typing directly in the **Create ad** input boxes, by using a [bulk upload](./hlp_BA_CONC_AboutBulk.md) spreadsheet, or by using [Microsoft Advertising Editor](./hlp_BA_CONC_AboutDesktop.md).

To make sure you enter it correctly, let's look at the components of a countdown's syntax using this example:

**{=COUNTDOWN("2018/02/17 00:00:00","en-us",3)}**

|Component|What you need to know|
|---|---|
|{ ... }|**Mandatory** . The entire countdown syntax must be within a pair of braces (also called curly brackets).|
|=COUNTDOWN|**Mandatory** . This component determines whether the countdown is based on the ad viewer's local time zone or on your account's time zone. The possible values are "=COUNTDOWN" (the ad viewer's local time zone) or "=GLOBAL_COUNTDOWN" (your account's time zone).|
|( ... )|**Mandatory** . The other components of the syntax must be within a pair of parentheses.**Note** : Individual components within the parentheses must be separated by commas.|
|"2018/02/17 00:00:00"|This is the countdown end date and time (must be within a pair of double quotation marks). **The date is mandatory, but the time is optional** . If you do not specify the time, it will default to midnight (00:00:00) at the very beginning of the date you specified.|
|"en-us"|This is the language the countdown will appear in (must be within a pair of double quotation marks). For example, "```3 days```", "```3 jours```", or "```3 Tage```"). **This component is only mandatory if you define how many days before the countdown end date/time you want the ad to start running**  (see next component). If you do not specify the language, it will default to English.**Note** : The maximum character length of the countdown will vary depending on the language you select. This will affect how long the rest of your title part, path, or ad text can be. Take a look at [this table](https://go.microsoft.com/fwlink?LinkId=855971) to see the supported languages and the countdown character length for each.|
|3|**Optional** . This is how many days before the countdown end date/time you want the ad to start running (the maximum is 999). If you do not specify the number of days, it will default to 5.|

## Example of a countdown in action
Let's say you're going to have a big online sale. You pick 12:00 AM on February 17 as your **Countdown ends** date/time, enter 3 for **Countdown starts**, and base the date/time on the ad viewer's time zone. Here's when your ad would run and examples of how it would look:
![Timeline showing when the ad would appear](../images/BA_CONC_Countdown.png)

With the countdown syntax, this ad's **Title Part 2** would look like this when you create it: "Sale ends in {=COUNTDOWN("2018/02/17 00:00:00","en-us",3)}!".

> [!NOTE]
> After an ad's countdown ends, the ad will stop running but will retain the status **Enabled**. You can make the ad start running again by either:
> - Updating the ad's **Countdown ends** date to a point in the future, or
> - Removing the ad's countdown syntax entirely.

## Best practices for ads with countdowns
<table type="type1">
  <tr>
    <th scope="col">Don't have all of the ads in an ad group use countdowns</th>
  </tr>
  <tr>
    <td>
                  Having a countdown in an ad means that the ad won't start running until a certain date and time, and then will stop running a few days later. If all of the ads in an ad group use countdowns, it's easy to end up having no ads running for some periods of time. To ensure that you always have ads running, we recommend having at least one ad without a countdown in each ad group.
                </td>
  </tr>
  <tr>
    <th scope="col">Don't have multiple countdowns in a single ad if they have different date ranges</th>
  </tr>
  <tr>
    <td>
                  It is possible to have more than one countdown in an ad. However, if they are based on different time ranges, the ad will only appear when the two time ranges overlap. We recommend avoiding this scenario.
                </td>
  </tr>
  <tr>
    <th scope="col">Choose the right time zone setting</th>
  </tr>
  <tr>
    <td>
      <ul>
        <li>If you're counting down to an event that will take place at a specific location — such as an in-store appearance, sporting event, or convention — it's probably best to base the countdown on your account time zone.</li>
        <li>If you're counting down to an event that isn't tied to a specific location (like an online sale), it's probably best to base the countdown on the ad viewer's time zone.</li>
      </ul>
    </td>
  </tr>
</table>


