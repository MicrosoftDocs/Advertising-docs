---
title: "Labels"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Labels
Labels let you organize campaigns, ad groups, ads, and keywords into groups based on whatever is important to you. You can then filter and run reports on your labels to get the data that is most meaningful to you.

> [!NOTE]
> Not everyone has this feature yet. If you don?t, don?t worry. It's coming soon.
> 
> Reporting for labels is not yet available via Bing Ads API. You can use Reporting in the Bing Ads web applicationn. 

With labels, you could:
* Run a report to compare "Holiday 2016" and "Holiday 2017" performance, across campaigns, ad groups, ads, and keywords.
* Run a report to compare ads and keywords that include brand names against ads and keywords that use generic terms.
* Quickly filter and view performance for keywords labeled "Suggested by Bing Ads."
* Create an automated rule to change bids on keywords labeled "CPA bidding."

The important thing is that it's all up to you. You decide what your labels mean and how to apply them to your campaigns, ad groups, ads, and keywords.

![Labels in the Bing Ads Web Application](../guides/media/labels-bing-ads-web-application.png)

## <a name="bulkservice"></a>Managing Labels with the Bulk Service
You can use the [Bulk Service](~/bulk/bulk-service-reference.md) i.e., [Bulk Download and Upload](../guides/bulk-download-upload.md) to create, get, update, and delete both labels and label associations. 

The following Bulk records are available for managing labels and label associations. 

-   [Label](~/bulk/label.md)  
-   [Campaign Label](~/bulk/campaign-label.md)  
-   [Ad Group Label](~/bulk/ad-group-label.md)  
-   [Keyword Label](~/bulk/keyword-label.md)  
-   [App Install Ad Label](~/bulk/app-install-ad-label.md)  
-   [Dynamic Search Ad Label](~/bulk/dynamic-search-ad-label.md)  
-   [Expanded Text Ad Label](~/bulk/expanded-text-ad-label.md)  
-   [Product Ad Label](~/bulk/product-ad-label.md)  
-   [Text Ad Label](~/bulk/text-ad-label.md)  

For example, the following Bulk CSV example would apply a label to the campaign, ad group, keyword, and expanded text ad if the valid *Id* and *Parent Id* are provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Name,Description,Label,Color
Format Version,,,,,,,,5,,,
Label,Active,-22,,,,ClientIdGoesHere,,,Label Description,Label Name 7/27/2017 6:50:54 PM,#FFFFFF
Campaign Label,Active,-22,-111,,,ClientIdGoesHere,,,,,
Ad Group Label,Active,-22,-1111,,,ClientIdGoesHere,,,,,
Expanded Text Ad Label,Active,-22,-11112,,,ClientIdGoesHere,,,,,
Keyword Label,Active,-22,-11113,,,ClientIdGoesHere,,,,,
```

## <a name="campaignservice"></a>Managing Labels with the Campaign Management Service
You can use the [Campaign Management Service](~/campaign-management/campaign-management-service-reference.md) to create, get, update, and delete both labels and label associations. 

You can add, delete, get, and update labels ([Label](~/campaign-management/label.md) objects) with the corresponding operations.
-  [AddLabels](~/campaign-management/addlabels.md)  
-  [DeleteLabels](~/campaign-management/deletelabels.md)  
-  [GetLabelsByIds](~/campaign-management/getlabelsbyids.md)  
-  [UpdateLabels](~/campaign-management/updatelabels.md)  

You can set, get, and delete label associations ([LabelAssociation](~/campaign-management/labelassociation.md) objects) with the corresponding operations.
-  [DeleteLabelAssociations](~/campaign-management/deletelabelassociations.md)  
-  [GetLabelAssociationsByEntityIds](~/campaign-management/getlabelassociationsbyentityids.md)  
-  [GetLabelAssociationsByLabelIds](~/campaign-management/getlabelassociationsbylabelids.md)  
-  [SetLabelAssociations](~/campaign-management/setlabelassociations.md)  



