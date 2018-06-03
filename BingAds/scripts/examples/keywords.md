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
    var campaignName = 'YOUR CAMPAIGN NAME';
    var adGroupName = 'YOUR AD GROUP NAME';
    var adGroupIterator = BingAdsApp.adGroups()
        .withCondition('Name = "' + adGroupName + '"')
        .withCondition('CampaignName = "' + campaignName + '"')
        .get();

    if (adGroupIterator.hasNext()) {
        var adGroup = adGroupIterator.next();

        var operation = adGroup.newKeywordBuilder()
            .withText('Hello world')
            .withCpc(1.25)                          // Optional
            .withFinalUrl('http://www.contoso.com') // Optional
            .build();

        if (operation.isSuccessful()) {
            var keyword = operation.getResult();
            Logger.log(`Added keyword, ${keyword.getText()}.`);
        }
        else {
            var errors = operation.getErrors();
        }
    }
}
```

## Pause an existing keyword in an ad group
```javascript
function pauseKeywordInAdGroup() {
    var campaignName = 'YOUR CAMPAIGN NAME';
    var adGroupName = 'YOUR AD GROUP NAME';
    var keywordText = 'YOUR KEYWORD TEXT';

    var keywordIterator = BingAdsApp.keywords()
        .withCondition('Text = "' + keywordText + '"')
        .withCondition('AdGroupName = "' + adGroupName + '"')
        .withCondition('CampaignName = "' + campaignName + '"')
        .get();

    if (keywordIterator.hasNext()) {
        var keyword = keywordIterator.next();
        keyword.pause();
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

## Get performance data for all keywords in an ad group
```javascript
function getKeywordStats() {
    var campaignName = 'Big & Tall Men';
    var adGroupName = 'Tops > Shirt';
    var keywordText = 'formal business';

    var keywordIterator = BingAdsApp.keywords()
        .withCondition('Text = "' + keywordText + '"')
        .withCondition('AdGroupName = "' + adGroupName + '"')
        .withCondition('CampaignName = "' + campaignName + '"')
        .forDateRange('LAST_MONTH')
        .get();

    if (keywordIterator.hasNext()) {
        var keyword = keywordIterator.next();

        var stats = keyword.getStats();
        Logger.log('Ad group: ' + adGroupName + '\n' + 
            `Keyword: ${keyword.getText()} \nClicks: ${stats.getClicks()} \nImpressions: ${stats.getImpressions()}`);
    }
}
```