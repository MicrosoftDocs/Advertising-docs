---
title: How does ad language and location targeting affect who can see my ads?
description: When determining if your ads are eligible to be displayed, Microsoft Advertising uses both your ad language and location target settings. Both criteria must be met in order for an ad to display.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How does ad language and location targeting affect who can see my ads?

When determining if your ads are eligible to be shown to a particular search user, Microsoft Advertising first determines if your ad language allows for your ad to be shown in a particular country or region then considers the location target (and other target) settings you have configured. If the target criteria is met and the ad language is available in the country/region, the ad is eligible to display.

Here are the steps you'd take to determine where your ads are shown:

1. **Set ad language**: The language you set for your ads also determines where those ads can be shown. You can create different ad groups with different languages.
1. **Select location target settings**: When selecting your location targets, you can choose from:
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

> [!IMPORTANT]
> Microsoft Advertising will honor your location targeting settings and exclude locations you don’t want to target. However, location targeting and exclusions may not always work because of factors beyond the control of Microsoft Advertising, such as a customer’s device settings or the inherent limits of geolocation via GPS, IP addresses, Wi-Fi networks, and Bluetooth.

1. **Select advanced location targeting options**: In addition to selecting your location target settings, you can:
   - Show ads to people in your targeted location.
   - Show ads to people in, searching for, or viewing pages about your targeted location.

1. **Multiple language targeting**: If you are targeting countries/regions that speak different languages, you can also target different languages. In your campaign settings, below location targeting, you will see the option to target multiple languages. This allows you to have different ad groups in the same campaign show ads on websites in different languages. Remember that Microsoft Advertising doesn’t translate your ads. It's a good idea to write your ads in the language you are targeting.
> [!NOTE]
> When the feature is enabled, your campaign languages will match the languages of all the ad groups in that campaign by default. For example, if a campaign has three ad groups with language set to English, German, and French, then the campaign languages will be set to English, German, and French. You can subsequently change this setting. If you want the campaign to target multiple languages, you can update the ad groups, using the **Use the campaign settings** option. (Note: If all of the ad groups in a campaign are set to the same language, then enabling this feature will not affect the campaign's language setting.) You can still have an ad-group-level language setting if you want the ad group to target one specific language. The ad group language, if set, will override the campaign settings. If there is no ad group language, then all the campaign languages will apply to the ad groups.

Both the location targeting criteria and the language setting criteria must be met in order for an ad to be eligible for display.  Of course your other targeting settings, beyond location, will also have an impact on the determining if the ad should be shown to the searcher.

For an example, let’s say you set your ad language to German. Because the language you set for your ads also determines where the ads are shown, setting the language to German will show your ads in not only Germany, but Austria and Switzerland as well. But because your ads are specific to a market, you decide to select your location target to Berlin, and even more specifically, show your ads only to people in your targeted location. Now, your ads will only show to searchers physically located in Berlin.

## How does my ad language impact where my ads can be seen?
Your ad language setting determines what countries and regions your ad can be displayed in. For example, ads in German will not display in Italy.

This is true even if you have set location targeting to show your ads in “all available countries and regions.” German-language ads, for example, will still only show in countries/regions where German is supported. English-language ads will still only show in countries/regions where English is supported, and so on.

Here are the list of available languages and corresponding countries/regions where that language is supported:

|Ad language settings|Countries/regions where ads in this language can display|
|---|---|
|Danish|Denmark|
|Dutch|Belgium, Netherlands|
|English|Australia, Canada, France, Germany, India, Indonesia, Ireland, Italy, Malaysia, Netherlands, New Zealand, Philippines, Singapore, Spain, Sweden, Switzerland, Thailand, Vietnam, United Kingdom, United States|
|Finnish|Finland|
|French|Belgium, Canada, France, Switzerland|
|German|Austria, Germany, Switzerland|
|Italian|Italy|
|Norwegian|Norway|
|Portuguese|Brazil|
|Spanish|Argentina, Chile, Colombia, Mexico, Peru, Spain, Venezuela|
|Swedish|Sweden|
|Traditional Chinese|Hong Kong S.A.R., Taiwan|

Don’t see your country or region listed? Check back, because we are expanding to new markets on a regular basis.

> [!IMPORTANT]
> Shopping Campaigns and product ads are available only in the United States, United Kingdom, Australia, France, Germany, India, and Canada (English only and excluding Quebec).

For more information, see our  [article about targeting](./hlp_BA_CONC_Targeting.md).


