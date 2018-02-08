# Keywords

## Add a keywrod to an existing ad group
```javascript
function addKeyword() {
  // If you have multiple adGroups with the same name, this snippet will
  // pick an arbitrary matching ad group each time. In such cases, just
  // filter on the campaign name as well:
  //
  // BingAdsApp.adGroups()
  //     .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
  //     .withCondition('CampaignName = "<CAMPAIGN_NAME_GOES_HERE>"')
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();

    adGroup.newKeywordBuilder()
        .withText('Hello world')
        .withCpc(1.25)                          // Optional
        .withFinalUrl('http://www.contoso.com') // Optional
        .build();

    // KeywordBuilder has a number of other options. For more details see
    // https://docs.microsoft.com/bingads/scripts/reference/keywordbuilder
  }
}
```

## Pause an existing keyword in an ad group
```javascript
function pauseKeywordInAdGroup() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords()
        .withCondition('Text="<KEYWORDS_GO_HERE>"').get();
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      keyword.pause();
    }
  }
}
```

## Get all keywords in an ad group
```javascript
function getKeywordsInAdGroup() {
  var keywordIterator = BingAdsApp.keywords()
      .withCondition('AdGroupName = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (keywordIterator.hasNext()) {
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      Logger.log(formatKeyword(keyword));
    }
  }
}

function formatKeyword(keyword) {
  return 'Text : ' + keyword.getText() + '\n' +
      'Match type : ' + keyword.getMatchType() + '\n' +
      'CPC : ' + keyword.bidding().getCpc() + '\n' +
      'Final URL : ' + keyword.urls().getFinalUrl() + '\n' +
      'Approval Status : ' + keyword.getApprovalStatus() + '\n' +
      'Enabled : ' + keyword.isEnabled() + '\n';
}
```

## Get stats for all keywords in an ad group
```javascript

function getKeywordStats() {
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "<ADGROUP_NAME_GOES_HERE>"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords().get();
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      var stats = keyword.getStatsFor('LAST_MONTH');
      Logger.log(adGroup.getName() + ', ' + keyword.getText() + ', ' +
          stats.getClicks() + ', ' + stats.getImpressions());
    }
  }
}
```