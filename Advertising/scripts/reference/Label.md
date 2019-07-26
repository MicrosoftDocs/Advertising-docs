---
title: "Label object"
description: "Contains the methods for managing a Label."
author: "swhite-msft"
manager: ehansen

ms.author: "scottwhi"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Label

Contains the methods for managing a label. For information about labels, see [Labels](/advertising/guides/entity-hierarchy-limits#label).


## Methods
|Method Name|Return Type|Description|
|-|-|-
[getColor](#getcolor)|string|Gets the background color to use in the UX for this label.
[getDescription](#getdescription)|string|Gets the label's description.
[getEntityType](#getentitytype)|string|Gets this entity's type.
[getId](#getid)|string|Gets the ID that uniquely identifies this label.
[getName](#getname)|string|Gets label's name.
[remove](#remove)|void|Removes this label.
[setColor(string color)](#setdescription-string-color-)|void|Sets the background color to use in the UX for this label.
[setDescription(string description)](#setdescription-string-description-)|void|Sets the label's description.
[setName(string name)](#setname-string-name-)|void|Sets label's name.

<!-->
[getAds](#getads)|[AdIterator](AdIterator.md)|Gets an iterator that you use to loop through the ads that this label belongs to.
[getAdGroups](#getadgroups)|[AdGroupIterator](AdGroupIterator.md)|Gets an iterator that you use to loop through the ad groups that this label belongs to.
[getCampaigns](#getcampaigns)|[CampaignIterator](./CampaignIterator.md)|Gets an iterator that you use to loop through the campaigns that this label belongs to.
[getKeywords](#getkeywords)|[KeywordIterator](./KeywordIterator.md)|Gets an iterator that you use to loop through the campaigns that this label belongs to.
<-->


## <a name="getcolor"></a>getColor
Gets the background color to use in the UX for this label.

### Returns
|Type|Description|
|-|-
string|The background color to use in the UX for this label.


## <a name="getdescription"></a>getDescription
Gets the label's description.

### Returns
|Type|Description|
|-|-
string|The label's description.


## <a name="getname"></a>getName
Gets the label's name.

### Returns
|Type|Description|
|-|-
string|The label's name.


## <a name="setcolor-string-color-"></a>setColor(string color)
Sets the background color to use in the UX for this label.

### Arguments
|Name|Type|Description|
|-|-|-
color|The background color to use in the UX for this label.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="setdescription-string-description-"></a>setDescription(string description)
Sets the label's description.

### Arguments
|Name|Type|Description|
|-|-|-
description|The label's description.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="getentitytype"></a>getEntityType
Returns this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type, which is *Label*.


## <a name="getid"></a>getId
Gets the ID that uniquely identifies this label.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this label.


## <a name="setname-string-name-"></a>setName(string name)
Sets the label's name.

### Arguments
|Name|Type|Description|
|-|-|-
name|The label's name

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## <a name="remove"></a>remove
Removes this label.

### Returns
|Type|Description|
|-|-
void|Returns nothing.


## See also

- [LabelSelector](./LabelSelector.md)
- [LabelIterator](./LabelIterator.md)
- [AdsApp.createLabel](./AdsApp.md#createlabel-string-name-string-description-string-backgroundcolor-)
