---
title: "Ad script examples"
description: "Shows examples that perform various actions against ads."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Script examples for managing ads

[!INCLUDE[preview-note](../includes/preview-note.md)]

The following sections show examples of scripts that perform various actions against ads.


## Add ads

To add an ad, first get the ad group to add the ad to. Use the [AdGroupSelector](../reference/AdGroupSelector.md) object to select the ad group. Using the `withIds` method provides better performance than passing the ad group's name in the `withCondition` method.

Next, call the ad group's [newAd](../reference/AdGroup.md#newad) method to get a builder that you use to specify the ad's properties. Unlike with other entity types, the `newAd` method returns an [AdBuilderSpace](../reference/AdBuilderSpace.md) object that contains methods for getting the builder for the type of ad you want to create. This example adds an expanded text ad, so it calls the `expandedTextAdBuilder` method to get an expanded text ad builder.

For expanded text ads, you must specify the following properties:

- Description
- FinalUrl
- HeadlinePart1
- HeadlinePart2

The combination of these properties uniquely defines an expanded text ad.

Calling the builder's `build` method creates the ad asynchronously; Bing adds the ad at some point before the script terminates or if you call one of the build operation's methods. For information about this process, see [What is a builder?](../concepts/builders.md)



```javascript
function main() {
    var adGroupId = "AD GROUP ID GOES HERE";
    var adGroup = getAdGroup(adGroupId);

    if (adGroup != null) {

        // Get an expanded text ad builder, specify the ad's 
        // properties, an add the ad to the build queue.
        var operation = adGroup.newAd().expandedTextAdBuilder()
            .withDescription("AD COPY GOES HERE")
            .withFinalUrl("https://contoso.com")
            .withHeadlinePart1("AD TITLE PART 1 GOES HERE")
            .withHeadlinePart2("AD TITLE PART 2 GOES HERE")
            .build();

        if (operation.isSuccessful()) {
            var ad = operation.getResult();
            logAdContents(ad);
        }
        else {
            for (var error of operation.getErrors()) {
                Logger.log(error);
            }
        }
    }
    else {
        Logger.log(`Failed to get ad group, ${adGroupId}.`);
    }
}

function getAdGroup(id) {
    var adGroups = BingAdsApp.adGroups()
        .withIds([id])
        .get();

    if (adGroups.hasNext()) {
        return adGroups.next();
    }
    else {
        return null;
    }
}

function logAdContents(ad) {
    if (ad.isType().expandedTextAd()) {
        var expandedAd = ad.asType().expandedTextAd();
        Logger.log(`Id: ${expandedAd.getId()}
            copy:${expandedAd.getDescription()}
            title part 1: ${expandedAd.getHeadlinePart1()}
            title part 2: ${expandedAd.getHeadlinePart2()}
            final URL: ${expandedAd.urls().getFinalUrl()}\n\n`);
    }
}
```


If a previously added ad with the same values for the combination of required fields exists, the service does not add the ad but instead returns the previously added ad and ID. However, if the same ads are processed in the same build queue, the second ad fails with CampaignServiceDuplicateAd. For example, in th

```javascript
    if (adGroup != null) {
        var adOperation = adGroup.newAd().expandedTextAdBuilder()
            .withDescription("ad copy")
            .withFinalUrl("https://contoso.com")
            .withHeadlinePart1("title part 1")
            .withHeadlinePart2("title part 2")
            .build();

        operations.push(adOperation);

        adOperation = adGroup.newAd().expandedTextAdBuilder()
            .withDescription("ad copy")
            .withFinalUrl("https://contoso.com")
            .withHeadlinePart1("title part 1")
            .withHeadlinePart2("title part 2")
            .build();

        operations.push(adOperation);
        
        for (var operation of operations) {
            if (operation.isSuccessful()) {
                var ad = operation.getResult();
                logAdContents(ad);
            }
            else {
                for (var error of operation.getErrors()) {
                    Logger.log(error);
                }
            }
        }
    }
```