---
title: "Keyword script examples"
description: "Shows examples that perform various actions against keywords."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Script examples for managing keywords

[!INCLUDE[preview-note](../includes/preview-note.md)]

The following sections show examples of scripts that perform various actions against keywords.


## Add a keyword to an existing ad group
```javascript
function addKeyword() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();

    adGroup.newKeywordBuilder()
        .withText('Hello world')
        .withCpc(1.25)                          // Optional
        .withFinalUrl('http://www.contoso.com') // Optional
        .build();
  }
}
```

## Pause an existing keyword in an ad group
```javascript
function pauseKeywordInAdGroup() {
  var adGroupName = 'YOUR AD GROUP NAME';
  var keywordText = 'YOUR KEYWORD TEXT';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords()
        .withCondition('Text="' + keywordText + '"').get();
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
  var adGroupName = 'YOUR AD GROUP NAME';
  var keywordIterator = BingAdsApp.keywords()
      .withCondition('AdGroupName = "' + adGroupName + '"')
      .get();
  while (keywordIterator.hasNext()) {
    var keyword = keywordIterator.next();
    Logger.log(formatKeyword(keyword));
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
  var adGroupName = 'YOUR AD GROUP NAME';
  var adGroupIterator = BingAdsApp.adGroups()
      .withCondition('Name = "' + adGroupName + '"')
      .get();
  if (adGroupIterator.hasNext()) {
    var adGroup = adGroupIterator.next();
    var keywordIterator = adGroup.keywords().get();
    while (keywordIterator.hasNext()) {
      var keyword = keywordIterator.next();
      var stats = keyword.getStats();
      Logger.log(adGroup.getName() + ', ' + keyword.getText() + ', ' +
          stats.getClicks() + ', ' + stats.getImpressions());
    }
  }
}
```