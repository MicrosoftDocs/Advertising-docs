---
title: "NegativeKeywordList object"
description: "Contains the methods for adding keywords to a negative keywords list."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# NegativeKeywordList

Contains the methods for adding keywords to a negative keywords list. For information about negative keyword lists, see [Negative Keywords](/bingads/guides/entity-hierarchy-limits#negativekeywords).

## Methods
|Method Name|Return Type|Description|
|-|-|-
[addNegativeKeyword(string keywordText)](#addnegativekeyword~string-keywordtext~)|void|Adds a keyword to the negative keywords list.
[addNegativeKeywords(string[] keywordTexts)](#addnegativekeywords~string-keywordtexts~)|void|Adds a list of keywords to the negative keywords list.
[getEntityType](#getentitytype)|String|Returns the entity's type.
[getId](#getid)|string|Returns the ID that uniquely identifies this negative keyword list.
[getName](#getname)|String|Returns the name of this negative keyword list.
[setName(String name)](#setname~string-name~)|void|Sets the name of this negative keyword list.

## <a name="addnegativekeyword~string-keywordtext~"></a>addNegativeKeyword(string keywordText)
Adds a keyword to the negative keywords list. To specify the match type for negative keywords:

- Use no syntax around keyword for **broad match**. For example, `negativeKeywordList.addNegativeKeyword("shoes")`.
- Use quotes around keyword for **phrase match**. For example, `negativeKeywordList.addNegativeKeyword("\"shoes\"")`.
- Use square brackets around keyword for **exact match**. For example, `negativeKeywordList.addNegativeKeyword("[leather shoes]")`.

### Arguments
|Name|Type|Description|
|-|-|-
keywordText|String|The negative keyword's text.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="addnegativekeywords~string-keywordtexts~"></a>addNegativeKeywords(string[] keywordTexts)
Adds a list of keywords to the negative keywords list. To specify the match type for negative keywords:

- - Use no syntax around keyword for **broad match**. For example, `negativeKeywordsList.addNegativeKeywords(["planes", "trains"])`.
- Use quotes around keyword for **phrase match**. For example, `negativeKeywordsList.addNegativeKeywords(["\"planes\"", "\"trains\""])`.
- Use square brackets around keyword for **exact match**. For example, `negativeKeywordsList.addNegativeKeywords(["[model planes]", "[toy trains]"])`.

### Arguments
|Name|Type|Description|
|-|-|-
keywordTexts|string[]|An array of keyword strings.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="getentitytype"></a>getEntityType
Returns the entity's type. 

### Returns
|Type|Description|
|-|-
string|This entity's type, which is NegativeKeywordList.

## <a name="getid"></a>getId
Returns the ID that uniquely identifies this negative keyword list.

### Returns
|Type|Description|
|-|-
string|The ID that uniquely identifies this negative keyword list.

## <a name="getname"></a>getName
Returns the name of this negative keyword list.

### Returns
|Type|Description|
|-|-
string|The name of this negative keyword list.

## <a name="setname~string-name~"></a>setName(string name)
Sets the name of this negative keyword list.

### Arguments
|Name|Type|Description|
|-|-|-
name|string|The name for this negative keyword list.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

