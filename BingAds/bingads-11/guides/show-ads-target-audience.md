---
title: "Show Ads to Your Target Audience"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Get your ads in front of the right people.
---
# Show Ads to Your Target Audience
Getting your ad in front of the right people; that's what targeting is all about. With targeting, Bing Ads can help you focus a campaign or ad group on potential customers who meet specific criteria, so you can increase the chance that they see your ads. You may target your ads to display to users of a certain age group, display at a certain day and time of the week, or display to users in a particular geographical location.

> [!NOTE] 
> Bing Ads supports other criterion types e.g. product partition and webpage. This guide is limited to criterions that you can use to target your ads by age, day and time, device, gender, and location. Where necessary to distinguish from other criterion types the documentation may refer to these entities as *target criterions*.  

Here are a few tips to keep in mind before you begin:
*  When you first create a campaign or ad group using the Bing Ads API, it will not have any criterions. Effectively the brand new campaign and ad group target all ages, days, hours, devices, genders, and locations. You should specify your minimum target criterions at the campaign level and then use ad group level criterions to narrow or refine your targeting requirements. As a best practice you should consider at minimum adding a campaign location criterion corresponding to the customer market country. Its worth noting that when creating campaigns via the Bing Ads web application, the recommended [default criterions](#defaultcriterions) are added. 
*  If you specify the same [criterion types](#criteriontypes) at the ad group and campaign level, the ad group-level criterions will override the campaign-level criterions. For example, if the campaign location criterion is *US* and the ad group location criterion is *California*, the ads will display only to users in California. Or, if the campaign criterions are *Monday* and *Wednesday* and the ad group criterions are *Tuesday* and *Thursday*, the ads will display only on Tuesdays and Thursdays.
*  When a criterion type is not specified at the ad group level, that type is effectively inherited from the campaign if it exists in the campaign. For example, you can specify location criterions at the campaign level and day and time criterions at the ad group level. If the location criterion is set to U.S. and the day and time criterion is set to Monday from 11am - 3pm, then the ads will display to users in the U.S. on Mondays from 11am - 3pm. 
*  You must consider the location, negative location, and radius criterions as a set of *geo criterions*. If the ad group has any geo criterions, then none of the campaign's geo criterions are inherited. If the ad group doesn't have any geo criterions, then all of the campaign's geo criterions are inherited. The geo criterions can be inherited from the campaign even if the ad group has a location intent criterion. If the ad group's geo criterions are used, then the ad group's location intent criterion is used; if the campaign's geo criterions are inherited, then the campaign's location intent criterion is used and the ad group's location intent criterion is ignored. You cannot delete a campaign or ad group's location intent criterion, although it has no purpose without location or radius criterions. 
*  By default without any criterions you are effectively targeting *PeopleInOrSearchingForOrViewingPages*. When you create the campaign or ad group's first criterion, a location intent criterion set to *PeopleInOrSearchingForOrViewingPages* with a criterion identifier will be added automatically for the corresponding campaign or ad group. The default location intent criterion will be added whenever the first criterion was successfully added, whether or not you tried to explicitly set a location intent criterion in the same operation.  
*  Partial update is supported, so you can update each criterion individually. For example if you only want to update the bid adjustment for 1 location, only send that location criterion. There is no need to send all locations. 
*  Partial success is supported, such that if you add or update multiple criterions each can fail or succeed independently. 
*  If you delete the campaign or ad group, all of the criterions for the same campaign or ad group are also deleted. 
*  If you upload multiple records with the same criterion identifier, then the first record will succeed and the subsequent duplicates will fail. 
*  Individual criterions are validated first, and then system limits are enforced if the number of valid criterions would exceed the allowed limit of criterions per campaign or ad group. Partial success of criterions is allowed up to the system limit.

## <a name="criteriontypes"></a>Target Criterion Types
The following criterion types are supported for targeting.
*  [Age Criterion](#agecriterion)
*  [DayTime Criterion](#daytimecriterion)
*  [DeviceOS Criterion](#deviceoscriterion)
*  [Gender Criterion](#gendercriterion)
*  [Location Criterion](#locationcriterion)
*  [Location Intent Criterion](#locationintentcriterion)
*  [Negative Location Criterion](#negativelocationcriterion)
*  [Radius Criterion](#radiuscriterion)

### <a name="agecriterion"></a>Age Criterion
You can target customers by age so that your ads are displayed more frequently to people who will be interested in them. 

Each age criterion defines an age range for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *AgeCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Age Criterion](../bulk-service/campaign-age-criterion.md) or [Ad Group Age Criterion](../bulk-service/ad-group-age-criterion.md) records. 

The maximum number of age criterions that you can specify per campaign or ad group is five, i.e. one for each of the supported age ranges *EighteenToTwentyFour*, *TwentyFiveToThirtyFour*, *ThirtyFiveToFortyNine*, *FiftyToSixtyFour*, and *SixtyFiveAndAbove*.

### <a name="daytimecriterion"></a>DayTime Criterion
As your campaign progresses, you may find that your click-through rate and conversion rate are highest during certain times, for example, weeknights. This might be a perfect opportunity to use bid adjustments to improve your chances of displaying your ad Monday through Friday from 6:00 P.M. to 11:00 P.M.. When targeting by time, you are targeting the searcher's local time zone. For example, if you increase your bid by 10% for 6:00 P.M. to 11:00 P.M., that bid adjustment will be effective from 6:00 P.M. to 11:00 P.M. Eastern Time for searchers in New York, then be effective 6:00 P.M. to 11:00 P.M. Pacific Time for searchers in Seattle. Now you are showing your ads when your potential customers are online!

Each day and time criterion defines the day, from hour, from minute, to hour, and to minute requirements for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *DayTimeCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign DayTime Criterion](../bulk-service/campaign-daytime-criterion.md) or [Ad Group DayTime Criterion](../bulk-service/ad-group-daytime-criterion.md) records. 

The maximum number of day and time criterions that you can specify per campaign or ad group is 49. You may not specify any overlapping day and time ranges, for example Monday from 3:00AM to 5:00AM and Monday 4:00AM to 6:00AM are not allowed for the same campaign or ad group. Also for a given campaign or ad group, the maximum number of day and time criterions per day that you can specify is seven. For example you can specify up to 7 day and time criterions where the *Day* is set to Monday. 

### <a name="deviceoscriterion"></a>DeviceOS Criterion
When you target by device, you choose to show ads to potential customers when they're using desktops and tablets or smartphones. 

Each device criterion defines a device name for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *DeviceCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign DeviceOS Criterion](../bulk-service/campaign-deviceos-criterion.md) or [Ad Group DeviceOS Criterion](../bulk-service/ad-group-deviceos-criterion.md) records. 

The maximum number of device criterions that you can specify per campaign or ad group is three. You must either have three separate criterions for *Computers*, *Smartphones*, and *Tablets*, otherwise no device criterions can exist for the campaign or ad group.

### <a name="gendercriterion"></a>Gender Criterion
You can target customers by gender so that your ads are displayed more frequently to people who will be interested in them. 

Each gender criterion defines a gender for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *GenderCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Gender Criterion](../bulk-service/campaign-gender-criterion.md) or [Ad Group Gender Criterion](../bulk-service/ad-group-gender-criterion.md) records. 

The maximum number of gender criterions that you can specify per campaign or ad group is two i.e. one for *Male* and one for *Female*.

### <a name="locationcriterion"></a>Location Criterion
With location criterions, you can choose to show ads to potential customers in, searching for, or viewing pages about:
*  All available countries/regions
*  Selected cities, zip codes, metro areas (Nielsen DMA® in the United States), states/provinces, and countries/regions

Each location criterion defines a location code for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *LocationCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Location Criterion](../bulk-service/campaign-location-criterion.md) or [Ad Group Location Criterion](../bulk-service/ad-group-location-criterion.md) records. 

The maximum number of combined location and negative location criterions that you can specify per campaign or ad group is 10,000.  

> [!NOTE]
> Although location criterions are most often used to designate the specific locations where you want to show your ads, Bing Ads also lets you specify locations you want to exclude from seeing your ads. To exclude a location, see [Negative Location Criterion](#negativelocationcriterion).

### <a name="locationintentcriterion"></a>Location Intent Criterion
Set the location intent criterion to *PeopleInOrSearchingForOrViewingPages* if you want to show ads to people in, searching for, or viewing pages about your targeted location. For example if the [Location Criterion](#locationcriterion) includes London and the location intent criterion is *PeopleInOrSearchingForOrViewingPages*, then someone physically located in Florida searching for London hotels will see the ad. 

> [!NOTE]
> By default without any criterions you are effectively targeting *PeopleInOrSearchingForOrViewingPages*. When you create the campaign or ad group's first criterion, a location intent criterion set to *PeopleInOrSearchingForOrViewingPages* with a criterion identifier will be added automatically for the corresponding campaign or ad group. The default location intent criterion will be added whenever the first criterion was successfully added, whether or not you tried to explicitly set a location intent criterion in the same operation.

Set the location intent criterion to *PeopleIn* if you only want to show ads to people in your targeted location. For example if the [Location Criterion](#locationcriterion) is set to London and the location intent criterion is *PeopleIn*, then someone physically located in Florida searching for London hotels will not see the ad.

Set the location intent criterion to *PeopleSearchingForOrViewingPages* if you want to show ads to people searching for or viewing pages about your targeted location. For example if the [Location Criterion](#locationcriterion) includes London and the location intent criterion is *PeopleSearchingForOrViewingPages*, then someone physically located in Florida searching for London hotels will see the ad. Someone located in London who searches for your keywords, but does not search for or about the targeted location will not see the ads.

Each location intent criterion defines the intent option for all location and radius criterions of the campaign or ad group. There isn't any accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *LocationIntentCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md) or [Ad Group Location Intent Criterion](../bulk-service/ad-group-location-intent-criterion.md) records. 

The maximum number of location intent criterions that you can specify per campaign or ad group is one.

For more information and examples, please see [How can I get my ads in front of my customers?](https://help.bingads.microsoft.com/#apex/3/en/51029/0).

### <a name="negativelocationcriterion"></a>Negative Location Criterion
Although location criterions are most often used to designate the specific locations where you want to show your ads, Bing Ads also lets you specify locations you want to exclude from seeing your ads.

Each negative location criterion defines a location code where you do not want your ads to show. If you are using the Campaign Management service, add the *LocationCriterion* to either the *NegativeCampaignCriterion* or *NegativeAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Negative Location Criterion](../bulk-service/campaign-negative-location-criterion.md) or [Ad Group Negative Location Criterion](../bulk-service/ad-group-negative-location-criterion.md) records. 

The maximum number of combined location and negative location criterions that you can specify per campaign or ad group is 10,000. 

> [!NOTE]
> To designate the specific locations where you want to show your ads, see [Location Criterion](#locationcriterion).

### <a name="radiuscriterion"></a>Radius Criterion
With radius criterions, you can choose to show ads to potential customers in, searching for, or viewing pages about a specified radius around a zip code, coordinates, landmark, or area.

Each radius criterion defines a radius, latitude, and longitude for the accompanying criterion bid adjustment. If you are using the Campaign Management service, add the *RadiusCriterion* to either the *BiddableCampaignCriterion* or *BiddableAdGroupCriterion* objects. If you are using the Bulk service, use either the [Campaign Radius Criterion](../bulk-service/campaign-radius-criterion.md) or [Ad Group Radius Criterion](../bulk-service/ad-group-radius-criterion.md) records. 

The maximum number of radius criterions that you can specify per campaign or ad group is 2,000.

## <a name="bidadjust"></a>Criterion Bid Adjustments
The ad group or keyword bid is used as the default or base bid. When you define a criterion, you can choose to adjust the base bid by a specified percentage. This is known as a bid adjustment or bid multiplier. For example, if your business sells pet supplies on the Internet, and you also have a storefront in Seattle, you can set your base bid for the "pet supplies" keyword to $1, and create a location criterion for your campaign that adjusts the bid by 50% for users in the Seattle metropolitan area. If a user in Los Angeles searches for "pet supplies", your bid for that keyword will be the base bid of $1.00. If a user in Seattle searches for "pet supplies", your bid is adjusted by 50% to $1.50. Placing a bid adjustment increases the likelihood that your ad is displayed in a better position for customers who meet your targeting criteria.

The base bid is adjusted by multipliers of the bid adjustment percentage values that you specify for each criterion type that applies to the search user. For example, say you specify a day criterion for Saturday with a 20% bid adjustment, and a Seattle metropolitan area criterion with a 30% bid adjustment. If the user resides in Seattle and searches on a Saturday, the service increases the base bid by 56%. The example is calculated as follows.

`1.00` (base bid default) `* 1.20` (day bid adjustment) `* 1.30` (location bid adjustment)`= 1.56` (56 percent adjustment)

> [!NOTE]
> After calculation, bid adjustments are rounded to two decimals of precision. For example, 1.1749 is rounded to 1.17 (17%), or 1.175 is rounded to 1.18 (18%).  
> 
> Multiple bid adjustments across location criterions are not combined. If you specify geographically-related combinations of country/region, state/province, metropolitan area, or city criterions, the bid adjustment of the most refined criterion would apply.
> 
> For example, if the search user is located in Redmond and country is set to `US` with a 10% bid adjustment, state is set to *US-WA* with a 20% bid adjustment, metro area (Nielsen DMA® in the United States) is set to *Seattle-Tacoma, WA, WA US* with a 30% bid adjustment, and city is set to *Redmond, Seattle-Tacoma, WA WA US* with a 40% bid adjustment, then the bid would be adjusted by 40%. If the user is located elsewhere within the Seattle-Tacoma metropolitan area, for example in Bellevue, the bid would be increased by 30%.

## <a name="defaultcriterions"></a>Default Criterion Settings
When you first create a campaign or ad group using the Bing Ads API, it will not have any criterions. Effectively the brand new campaign and ad group target all ages, days, hours, devices, genders, and locations. You should specify your minimum target criterions at the campaign level and then use ad group level criterions to narrow or refine your targeting requirements. As a best practice you should consider at minimum adding a campaign location criterion corresponding to the customer market country. 

Its worth noting that when creating campaigns via the Bing Ads web application, the recommended default criterions are added. For example if you keep the default setting in the web application e.g. *United States, Canada*, the download will include the following campaign location and campaign location intent criterions. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Physical Intent,Bid Adjustment,Radius Target Id,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,,5,,,,,,,,
Account,,AcccountIdHere,CustomerIdHere,,,,,,,,,,,,,,,,,
Campaign Location Criterion,Active,101,CampaignIdHere,Country,CampaignNameHere,,41:34.8,32,,0,,Canada,,,,,,,,
Campaign Location Criterion,Active,102,CampaignIdHere,Country,CampaignNameHere,,41:34.8,190,,0,,United States,,,,,,,,
Campaign Location Intent Criterion,Active,CampaignIdHere,CampaignIdHere,,CampaignNameHere,,41:34.8,PeopleInOrSearchingForOrViewingPages,,,,,,,,,,,,
```

If you choose *All available countries/regions* in the Bing Ads web application, the download will only include the following campaign location intent criterion. This is the effective equivalent of targeting all ages, days, genders, hours, and locations worldwide.

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Physical Intent,Bid Adjustment,Radius Target Id,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,,5,,,,,,,,
Account,,AcccountIdHere,CustomerIdHere,,,,,,,,,,,,,,,,,
Campaign Location Intent Criterion,Active,CampaignIdHere,CampaignIdHere,,CampaignNameHere,,41:34.8,PeopleInOrSearchingForOrViewingPages,,,,,,,,,,,,
```

> [!NOTE]
> The above examples assume that you did not change any other defaults such as demographic or device settings. 

## <a name="usingcriterions"></a>Using Target Criterions
Bing Ads supports other criterion types e.g. product partition and webpage. This guide is limited to criterions that you can use to target your ads by age, day and time, device, gender, and location. Where necessary to distinguish from other criterion types the documentation may refer to these entities as *target criterions*.  

### <a name="synccriterions"></a>Sync Criterions
Sync the new criterions with campaigns and ad groups. For example you can use the Bulk service to download all criterions in the account and discover the mapping between criterions and campaigns and ad groups. Let's download the target criterions using Bing Ads API version 11, Bulk file format 5.0, and we can see that each criterion has its own identifier e.g. 101, 102, 103, and so on. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Physical Intent,Bid Adjustment,Radius Target Id,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,,5,,,,,,,,
Account,,AcccountIdHere,CustomerIdHere,,,,,,,,,,,,,,,,,
Campaign Age Criterion,Active,101,CampaignIdHere,,CampaignNameHere,,41:34.8,EighteenToTwentyFour,,20,,,,,,,,,,
Campaign Gender Criterion,Active,102,CampaignIdHere,,CampaignNameHere,,41:34.8,Female,,20,,,,,,,,,,
Campaign DeviceOS Criterion,Active,103,CampaignIdHere,,CampaignNameHere,,41:34.8,Computers,,20,,,,,,,,,,
Campaign DeviceOS Criterion,Active,104,CampaignIdHere,,CampaignNameHere,,41:34.8,Smartphones,,0,,,,,,,,,,
Campaign DeviceOS Criterion,Active,105,CampaignIdHere,,CampaignNameHere,,41:34.8,Tablets,,0,,,,,,,,,,
Campaign Location Criterion,Active,106,CampaignIdHere,Country,CampaignNameHere,,41:34.8,190,,20,,,,,,,,,,
Campaign Negative Location Criterion,Active,107,CampaignIdHere,PostalCode,CampaignNameHere,,41:34.8,79381,,,,,,,,,,,,
Campaign Location Intent Criterion,Active,CampaignIdHere,CampaignIdHere,,CampaignNameHere,,41:34.8,PeopleIn,,,,,,,,,,,,
Campaign Radius Criterion,Active,108,CampaignIdHere,,CampaignNameHere,,41:34.8,,,20,,RadiusName,10,Kilometers,,,,,10.5,40.5
Campaign DayTime Criterion,Active,109,CampaignIdHere,,CampaignNameHere,,41:34.8,Monday,,20,,,,,0,0,4,0,,
Ad Group Age Criterion,Active,201,AdGroupIdHere,,CampaignNameHere,,41:35.7,EighteenToTwentyFour,,20,,,,,,,,,,
Ad Group Gender Criterion,Active,202,AdGroupIdHere,,CampaignNameHere,,41:35.7,Female,,20,,,,,,,,,,
Ad Group DeviceOS Criterion,Active,203,AdGroupIdHere,,CampaignNameHere,,41:35.7,Computers,,20,,,,,,,,,,
Ad Group DeviceOS Criterion,Active,204,AdGroupIdHere,,CampaignNameHere,,41:35.7,Smartphones,,0,,,,,,,,,,
Ad Group DeviceOS Criterion,Active,205,AdGroupIdHere,,CampaignNameHere,,41:35.7,Tablets,,0,,,,,,,,,,
Ad Group Location Criterion,Active,206,AdGroupIdHere,Country,CampaignNameHere,,41:35.7,190,,20,,,,,,,,,,
Ad Group Negative Location Criterion,Active,207,AdGroupIdHere,PostalCode,CampaignNameHere,,41:35.7,79381,,,,,,,,,,,,
Ad Group Location Intent Criterion,Active,AdGroupIdHere,AdGroupIdHere,,CampaignNameHere,,41:35.7,PeopleIn,,,,,,,,,,,,
Ad Group Radius Criterion,Active,208,AdGroupIdHere,,CampaignNameHere,,41:35.7,,,20,,RadiusName,10,Kilometers,,,,,10.5,40.5
Ad Group DayTime Criterion,Active,209,AdGroupIdHere,,CampaignNameHere,,41:35.7,Monday,,20,,,,,0,0,4,0,,
```

### <a name="addcriterion"></a>Add or Update Criterions
Add new criterions directly to the campaign or ad group, or use the synced criterion identifiers to update or delete existing criterions. Let's assume we have already retrieved the criterion identifiers as described in [Sync Criterions](#synccriterions), and we attempt to upload the following criterions. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Physical Intent,Bid Adjustment,Radius Target Id,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,,5,,,,,,,,
Account,,AcccountIdHere,CustomerIdHere,,,,,,,,,,,,,,,,,
Campaign Location Criterion,Active,,CampaignIdHere,Country,,,,190,,20,,,,,,,,,,
Campaign Location Intent Criterion,Deleted,CampaignIdHere,CampaignIdHere,,,,,,,,,,,,,,,,,
Ad Group Age Criterion,Active,,AdGroupIdHere,,,,,EighteenToTwentyFour,,20,,,,,,,,,,
Ad Group DeviceOS Criterion,Deleted,203,AdGroupIdHere,,,,,Computers,,20,,,,,,,,,,
Ad Group DeviceOS Criterion,Deleted,204,AdGroupIdHere,,,,,Smartphones,,0,,,,,,,,,,
Ad Group DeviceOS Criterion,Deleted,205,AdGroupIdHere,,,,,Tablets,,0,,,,,,,,,,
```

As observed in the example upload results file below:
*  We successfully targeted Canada (LocationId = 32) by adding a new campaign location criterion.
*  Location intent criterions can never be deleted. The attempt to delete the location intent criterion from the campaign failed but did not cause other criterion updates to fail.
*  Without the assigned identifier for an existing age criterion, the upload attempt failed with code 1043 i.e. CampaignServiceEntityAlreadyExists. If the *EighteenToTwentyFour* age criterion had not existed already or if we had specified an age range that is not yet set for the campaign, then the upload would have succeeded and created a new criterion with unique identifier. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Physical Intent,Bid Adjustment,Radius Target Id,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude,Error,Error Number
Format Version,,,,,,,,,,,,5,,,,,,,,,,
Account,,AcccountIdHere,CustomerIdHere,,,,,,,,,,,,,,,,,,,
Campaign Location Criterion,Active,110,CampaignIdHere,Country,,,,190,,20,,,,,,,,,,,,
Campaign Location Intent Criterion,Deleted,CampaignIdHere,CampaignIdHere,,,,,,,,,,,,,,,,,,,
Campaign Location Intent Criterion Error,Deleted,CampaignIdHere,CampaignIdHere,,,,,,,,,,,,,,,,,,LocationIntentCriterionCannotBeDeleted,2965
Ad Group Age Criterion,Active,,AdGroupIdHere,,,,,EighteenToTwentyFour,,20,,,,,,,,,,,,
Ad Group Age Criterion Error,Active,,AdGroupIdHere,,,,,EighteenToTwentyFour,,20,,,,,,,,,,,CampaignServiceEntityAlreadyExists,1043
Ad Group DeviceOS Criterion,Deleted,203,AdGroupIdHere,,,,,Computers,,20,,,,,,,,,,,,
Ad Group DeviceOS Criterion,Deleted,204,AdGroupIdHere,,,,,Smartphones,,0,,,,,,,,,,,,
Ad Group DeviceOS Criterion,Deleted,205,AdGroupIdHere,,,,,Tablets,,0,,,,,,,,,,,,
```

