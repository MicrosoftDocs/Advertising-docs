---
title: "Campaign script examples"
description: "Shows examples that perform various actions against campaigns."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Script examples for managing campaigns

[!INCLUDE[preview-note](../includes/preview-note.md)]

The following sections show examples of scripts that perform various actions against campaigns.


## Get all campaigns
```javascript
function getAllCampaigns() {
  var campaignIterator = BingAdsApp.campaigns().get();
  Logger.log('Total campaigns found : ' +
      campaignIterator.totalNumEntities());
  while (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log(campaign.getName());
  }
}
```

## Get a campaign by name
```javascript
function getCampaignsByName() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log('Campaign Name: ' + campaign.getName());
    Logger.log('Enabled: ' + campaign.isEnabled());
    Logger.log('Bidding strategy: ' + campaign.getBiddingStrategyType());
  }
}
```

## Get a campaign's performance data
```javascript
function getCampaignStats() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var stats = campaign.getStatsFor('LAST_MONTH');
    Logger.log(campaign.getName() + ', ' + stats.getClicks() + 'clicks, ' +
        stats.getImpressions() + ' impressions');
  }
}
```

## Pause a campaign
```javascript
function pauseCampaign() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    campaign.pause();
  }
}
```

<!--
## Get a campaign's device bid modifiers
```javascript
function getCampaignBidModifiers() {
  var campaignName = 'YOUR CAMPAIGN NAME';
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "' + campaignName + '"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log('Campaign name: ' + campaign.getName());

    var platformIterator = campaign.targeting().platforms().get();
    while (platformIterator.hasNext()) {
      var platform = platformIterator.next();
      Logger.log(platform.getName() + ' bid modifier: ' +
          platform.getBidModifier());
    }
  }
```
-->