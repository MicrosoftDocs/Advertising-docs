---
title: "Product group script examples"
description: "Shows examples that get product groups and updates their bid amounts."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Script examples for product groups

[!INCLUDE[preview-note](../includes/preview-note.md)]

The following sections show examples of scripts that get product groups and update their bid amounts.

## Getting product groups

To get all product groups in an account, use the [AdsApp.productGroups()](../reference/AdsApp.md#productgroups) method. By default, the selector returns the product groups in order by product group IDs.

```javascript
function main() {

    var productGroups = AdsApp.productGroups().get();

    while (productGroups.hasNext()) {
        var productGroup = productGroups.next();

        Logger.log(`  campaign ID: ${productGroup.getCampaign().getId()}`);
        Logger.log(`  ad group ID: ${productGroup.getAdGroup().getId()}`);
        Logger.log(`  product group ID: ${productGroup.getId()}`);
        Logger.log(`  dimension: ${productGroup.getDimension()}`);
        Logger.log(`  cpc: ${productGroup.getMaxCpc()}`);
        Logger.log(`  other case: ${productGroup.isOtherCase()}`);
        Logger.log(`  excluded: ${productGroup.isExcluded()}`);
        Logger.log(`  children count: ${productGroup.children().get().totalNumEntities()}`);

        if (productGroup.parent() != null) {
            Logger.log(`  parent: ${productGroup.parent().getId()}`);
        }

        switch (productGroup.getDimension()) {
            case "ROOT": {
                Logger.log("\n");
                break;
            }
            case "CATEGORY": {
                Logger.log(`Entity type: ${productGroup.asCategory().getEntityType()}`);
                Logger.log(`Category name -> ${productGroup.asCategory().getName()}\n\n`);
                break;
            }
            case "BRAND": {
                Logger.log(`Entity type: ${productGroup.asBrand().getEntityType()}`);
                Logger.log(`Brand name -> ${productGroup.asBrand().getName()}\n\n`);
                break;
            }
            case "CONDITION": {
                Logger.log(`Entity type: ${productGroup.asCondition().getEntityType()}`);
                Logger.log(`Condition name -> ${productGroup.asCondition().getCondition()}\n\n`);
                break;
            }
            case "CUSTOM_LABEL": {
                Logger.log(`Entity type: ${productGroup.asCustomLabel().getEntityType()}`);
                Logger.log(`Custom label name -> ${productGroup.asCustomLabel().getType()}`);
                Logger.log(`Custom label value -> ${productGroup.asCustomLabel().getValue()}\n\n`);
                break;
            }
            case "ID": {
                Logger.log(`Entity type: ${productGroup.asItemId().getEntityType()}`);
                Logger.log(`Product item ID -> ${productGroup.asItemId().getValue()}\n\n`);
                break;
            }
            case "TYPE": {
                Logger.log(`Entity type: ${productGroup.asProductType().getEntityType()}`);
                Logger.log(`Product type name -> ${productGroup.asProductType().getType()}`);
                Logger.log(`Product type value -> ${productGroup.asProductType().getValue()}\n\n`);
                break;
            }
        }
    }
}
```

Another option is to get product groups by shopping campaigns or shopping ad groups. To get product groups by ad groups, first call the [AdsApp.shoppingAdGroups()](../reference/AdsApp.md#shoppingadgroups) method, and then call the [AdGroup.productGroups()](../reference/AdGroup.md#productgroups) method. For campaigns, you'd similarly call the [AdsApp.shoppingCampaigns()](../reference/AdsApp.md#shoppingcampaigns) and [Campaign.productGroups()](../reference/Campaign.md#productgroups) methods. 


```javascript
function main() {

    // Option 1 for getting all shopping ad groups
    var shoppingAdGroups = AdsApp.shoppingAdGroups()
        .get();  
    
    Logger.log(`shoppingAdGroups selector returned ${shoppingAdGroups.totalNumEntities()} ad groups that matched the selector's conditions`);

    // Option 2 for getting all shopping ad groups
    var shoppingAdGroups2 = AdsApp.adGroups()
        .withCondition('CampaignType = SHOPPING')
        .get()

    Logger.log(`adGroup selector returned ${shoppingAdGroups2.totalNumEntities()} ad groups that matched the selector's conditions\n\n`);

    while (shoppingAdGroups.hasNext()) {
        var adGroup = shoppingAdGroups.next();

        Logger.log(`Product groups for ad group, ${adGroup.getId()} of campaign ${adGroup.getCampaign().getId()}\n\n`);

        var productGroups = adGroup.productGroups().get();

        while (productGroups.hasNext()) {
            var productGroup = productGroups.next();

            Logger.log(`  product group ID: ${productGroup.getId()}`);
            Logger.log(`  dimension: ${productGroup.getDimension()}`);
            Logger.log(`  cpc: ${productGroup.getMaxCpc()}`);
            Logger.log(`  other case: ${productGroup.isOtherCase()}`);
            Logger.log(`  excluded: ${productGroup.isExcluded()}`);
            Logger.log(`  children count: ${productGroup.children().get().totalNumEntities()}`);

            if (productGroup.parent() != null) {
                Logger.log(`  parent: ${productGroup.parent().getId()}`);
            }

            switch (productGroup.getDimension()) {
                case "ROOT": {
                    Logger.log("\n");
                    break;
                }
                case "CATEGORY": {
                    Logger.log(`Entity type: ${productGroup.asCategory().getEntityType()}`);
                    Logger.log(`Category name -> ${productGroup.asCategory().getName()}\n\n`);
                    break;
                }
                case "BRAND": {
                    Logger.log(`Entity type: ${productGroup.asBrand().getEntityType()}`);
                    Logger.log(`Brand name -> ${productGroup.asBrand().getName()}\n\n`);
                    break;
                }
                case "CONDITION": {
                    Logger.log(`Entity type: ${productGroup.asCondition().getEntityType()}`);
                    Logger.log(`Condition name -> ${productGroup.asCondition().getCondition()}\n\n`);
                    break;
                }
                case "CUSTOM_LABEL": {
                    Logger.log(`Entity type: ${productGroup.asCustomLabel().getEntityType()}`);
                    Logger.log(`Custom label name -> ${productGroup.asCustomLabel().getType()}`);
                    Logger.log(`Custom label value -> ${productGroup.asCustomLabel().getValue()}\n\n`);
                    break;
                }
                case "ID": {
                    Logger.log(`Entity type: ${productGroup.asItemId().getEntityType()}`);
                    Logger.log(`Product item ID -> ${productGroup.asItemId().getValue()}\n\n`);
                    break;
                }
                case "TYPE": {
                    Logger.log(`Entity type: ${productGroup.asProductType().getEntityType()}`);
                    Logger.log(`Product type name -> ${productGroup.asProductType().getType()}`);
                    Logger.log(`Product type value -> ${productGroup.asProductType().getValue()}\n\n`);
                    break;
                }
            }
        }
    }
}
```

### Applying conditions

To filter the list of product groups, use the [withCondition](../reference/ProductGroupSelector.md#withcondition-string-condition-) method. By using `withCondition`, you can filter product groups by the standard metric values like clicks and conversions, but you can also filter by bid amount and product group.

The following example shows how to get the Skis product group if the path is 'All products > Sporting Goods > Winter Sports > Skiing > Skis > Refurbished > Cross-Country Skis'.

```javascript
function main() {
    var shoppingAdGroup = AdsApp.shoppingAdGroups().withIds(["123456789"]).get().next();

    var productGroups = shoppingAdGroup.productGroups()
        .withCondition("ProductGroup = skis")
        .get();

    while (productGroups.hasNext()) {
        var group = productGroups.next();

        Logger.log(`dimension ${group.getDimension()}`)
        Logger.log(`value ${group.getValue()}`)
        Logger.log(`cpc ${group.getMaxCpc()}`)

        if (group.parent() != null) {
            Logger.log(`parent ${group.parent().getId()}`)
        }

        Logger.log("\n");
    }
}
```

Because Skis is subdivided by Refurbished condition, the response includes the selected Skis product group and the OtherCase product group for Refurbished.

```
dimension CATEGORY
value Skis
cpc null
parent 4578503857653096

dimension CONDITION
value OtherCase
cpc 1
parent 4578503857653099
```

## Updating a product group's bid

This example shows how to get product groups with a specific bid and update the bid amount. Remember not to update the bid in the iterator (see [Best practices](../concepts/best-practices.md#)).

The bid amount for product groups that are subdivided (those that have children), is null. If the condition's operator uses less than ('<') (for example, `.withCondition("Bid < 1.0")`), the iterator includes all product groups whose bid is set to null (which includes all subdivided product groups). To prevent this, use `.withCondition("Bid < 1.0").withCondition("Bid > 0.0")`.

```javascript
function main() {
    var shoppingAdGroup = AdsApp.shoppingAdGroups().withIds(["123456789"]).get().next();

    var productGroups = shoppingAdGroup.productGroups()
        .withCondition("Bid = 1.0")
        .get();

    Logger.log(`${productGroups.totalNumEntities()} product groups to update\n\n`);

    var groupsToUpdate = [];

    while (productGroups.hasNext()) {
        groupsToUpdate.push(productGroups.next());
    }
    
    for (var group of groupsToUpdate) {

        Logger.log(`id ${group.getId()}`);
        Logger.log(`dimension ${group.getDimension()}`);
        Logger.log(`cpc before update ${group.getMaxCpc()}`);

        group.setMaxCpc(.35);

        Logger.log(`cpc after update ${group.getMaxCpc()}\n\n`);
    }
}
```
