---
title: Truncation of Expanded Text Ads
description: Learn about how Microsoft Advertising may truncate Expanded Text Ads, depending on screen size and display format of the search results page.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Truncation of Expanded Text Ads

Depending on screen size, layout of the search result page, length of the ad creative, and the width of the letters used in the ad copy, Microsoft Advertising may truncate the ad titles, URLs, ad text, and certain ad extensions of [Expanded Text Ads](./hlp_BA_CONC_EXTA_FAQ.md). This is most likely to happen in Extended Text Ads whose titles, URLs, and ad text are all close to the character limit.

Below are the possible ways Microsoft Advertising may truncate ad titles, URLs, ad text, and certain ad extensions. If truncation is necessary, we will pick the optimal way, based on screen size, search result page layout, and ad copy.

## Ad titles
In these examples, the ad title is constructed like this:

|Ad title part 1:|All the Sports data you want|
|---|---|
|Ad title part 2:|Baseball, football, hoops, etc|
|Complete title:|All the Sports data you want - Baseball, football, hoops, etc|

## Possible ways of truncating an ad title:

- Truncate at a word break in ad title part 2. Example: **All the Sports data you want - Baseball, football...**
- Remove ad title part 2 entirely. Example: **All the Sports data you want...**

## URLs
In these examples, the URL is constructed like this:

|Final URL:|www.ConsolidatedMessenger.com|
|---|---|
|Path 1:|Top4MajorSports|
|Path 2:|PerformanceData|
|Complete URL:|www.ConsolidatedMessenger.com/Top4MajorSports/PerformanceData|

## Possible ways of truncating a URL:

- Remove the URL's prefix. Example: **ConsolidatedMessenger.com/Top4MajorSports/PerformanceData**
- Replace path 1 with an ellipsis. Example: **www.ConsolidatedMessenger.com/.../PerformanceData** or  **ConsolidatedMessenger.com/.../PerformanceData**
- Remove path 2. Example: **www.ConsolidatedMessenger.com/Top4MajorSports** or **ConsolidatedMessenger.com/Top4MajorSports**
- Remove both path 1 and path 2. Example: **www.ConsolidatedMessenger.com** or **ConsolidatedMessenger.com**
- Truncate your URL. Example: **www.ConsolidatedMesseng...**

## Ad text
## 

In this example, the complete ad text is:

|Ad text:|Up-to-the-minute sports data at your fingertips! We crunch the numbers, you win!|
|---|---|

## Possible ways of truncating ad text:

- Truncate at a word break. Example: **Up-to-the-minute sports data at your fingertips! We crunch the numbers...**

## Ad extension
Callout Extensions or Structured Snippet Extensions may not display, based on the availability of horizontal space. Smaller screen sizes will display fewer items.

For more information on Expanded Text Ads, check out our [Expanded Text Ads FAQ](./hlp_BA_CONC_EXTA_FAQ.md).

> [!NOTE]
> If a Long Ad Title (LAT) annotation is served with an Expanded Text Ad, the LAT could replace the ad title part 2.


