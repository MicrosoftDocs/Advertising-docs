# Ad Groups

## Add an ad group
```javascript
function addAdGroup() {
  var campaignIterator = BingAdsApp.campaigns()
      .withCondition('Name = "<CAMPAIGN_NAME_GOES_HERE>"')
      .get();
  if (campaignIterator.hasNext()) {
    var campaign = campaignIterator.next();
    var adGroupOperation = campaign.newAdGroupBuilder()
        .withName('<ADGROUP_NAME_GOES_HERE>')
        .withCpc(1.2)
        .build();
  }
}
```

## Get all ad groups
```javascript
function getAlladGroups() {
  var adGroupIterator = BingAdsApp.adGroups().get();
  Logger.log('Total adGroups found : ' + adGroupIterator.totalNumEntities());
  while (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    Logger.log('AdGroup Name: ' + adGroup.getName());
  }
}
```

## Get an ad group by name
```javascript
function getAdGroupByName() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    Logger.log('AdGroup Name: ' + adGroup.getName());
    Logger.log('Enabled: ' + adGroup.isEnabled());
  }
}
```

## Get an ad group's stats
```javascript
function getadGroupstats() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var stats = adGroup.getStatsFor('LAST_MONTH');
    Logger.log(adGroup.getName() + ', ' + stats.getClicks() + ', ' +
        stats.getImpressions());
  }
}
```

## Pause an ad group
```javascript
function pauseAdGroup() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    adGroup.pause();
    Logger.log('AdGroup with name = ' + adGroup.getName() +
        ' has paused status : ' + adGroup.isPaused());
  }
}
```

## Enable an ad group
```javascript
function updateAdGroup() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    adGroup.enable();
  }
}
```

## Get an ad group's device bid modifiers
```javascript
function getAdGroupBidModifiers() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    Logger.log('AdGroup name: ' + adGroup.getName());
    Logger.log('Mobile bid modifier: ' +
        adGroup.devices().getMobileBidModifier());
    Logger.log('Tablet bid modifier: ' +
        adGroup.devices().getTabletBidModifier());
    Logger.log('Desktop bid modifier: ' +
        adGroup.devices().getDesktopBidModifier());
  }
}
```