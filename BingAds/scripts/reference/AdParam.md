---
title: "AdParam object"
description: "Contains the methods used to manage the substitution parameter."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# AdParam

Contains the methods used to manage the substitution parameters used in the keyword.

## Methods
|Method Name|Return Type|Description|
|-|-|-
[getEntityType](#getentitytype)|string|Returns this entity's type.
[getIndex](#getindex)|int|Returns the index that identifies this substitution parameter.
[getInsertionText](#getinsertiontext)|string|Returns the substitution parameter's text.
[getKeyword](#getkeyword)|[Keyword](Keyword.md)|Returns the keyword that the substitution parameter applies to.
[remove](#remove)|void|Removes the substitution parameter from the keyword.
[setInsertionText(string insertionText)](#setinsertiontext~string-insertiontext~)|void|Sets the substitution parameter's text.


## <a name="getentitytype"></a>getEntityType
Returns this entity's type.

### Returns
|Type|Description|
|-|-
string|This entity's type (is set to AdParam).


## <a name="getindex"></a>getIndex
Returns the index that identifies this substitution parameter.

### Returns
|Type|Description|
|-|-
int|The index that identifies this substitution parameter.


## <a name="getinsertiontext"></a>getInsertionText
Returns the substitution parameter's text.

### Returns
|Type|Description|
|-|-
string|The substitution parameter's text.


## <a name="getkeyword"></a>getKeyword
Returns the keyword that the substitution parameter applies to.

### Returns
|Type|Description|
|-|-
[Keyword](Keyword.md)|The keyword that the substitution parameter applies to.


## <a name="remove"></a>remove
Removes the substitution parameter from the keyword.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

## <a name="setinsertiontext~string-insertiontext~"></a>setInsertionText(string insertionText)
Sets the substitution parameter's text.

### Arguments
|Name|Type|Description|
|-|-|-
insertionText|string|The text to set the substitution parameter to.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

