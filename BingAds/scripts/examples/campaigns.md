# Campaigns

## Get all campaigns
```javascript
function getAllCampaigns() {
  // BingAdsApp.campaigns() will return all campaigns that are not removed by
  // default.
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
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "<CAMPAIGN_NAME_GOES_HERE>"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    Logger.log('Campaign Name: ' + campaign.getName());
    Logger.log('Enabled: ' + campaign.isEnabled());
    Logger.log('Bidding strategy: ' + campaign.getBiddingStrategyType());
    Logger.log('Ad rotation: ' + campaign.getAdRotationType());
    Logger.log('Start date: ' + formatDate(campaign.getStartDate()));
    Logger.log('End date: ' + formatDate(campaign.getEndDate()));
  }
}

function formatDate(date) {
  function zeroPad(number) { return Utilities.formatString('%02d', number); }
  return (date == null) ? 'None' : zeroPad(date.year) + zeroPad(date.month) +
      zeroPad(date.day);
}
```

## Get a campaign's stats
```javascript
function getCampaignStats() {
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "<CAMPAIGN_NAME_GOES_HERE>"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    // You can also request reports for pre-defined date ranges. See
    // https://docs.microsoft.com/bingads/scripts/reference/campaign?#getstatsfor~string-daterange~.
    var stats = campaign.getStatsFor('LAST_MONTH');
    Logger.log(campaign.getName() + ', ' + stats.getClicks() + 'clicks, ' +
        stats.getImpressions() + ' impressions');
  }
}
```

## Pause a campaign
```javascript
function pauseCampaign() {
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "<CAMPAIGN_NAME_GOES_HERE>"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    campaign.pause();
  }
}
```

## Get a campaign's device bid modifiers
```javascript
function getCampaignBidModifiers() {
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "<CAMPAIGN_NAME_GOES_HERE>"')
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
