---
title: "Logger object"
description: "Contains the methods for writing text messages to the log."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# Logger

Contains the methods for writing text messages to the console log.

## Methods
|Method Name|Return Type|Description|
|-|-|-
[log(string message)](#log-string-message-)|void|Writes a text string to the log.

## <a name="log-string-message-"></a>log(string message)
Writes a text string to the log. 

If the script is run in live mode, the log is found on the main Scripts page. If the script is run in preview mode, the log is found in the preview pane.

### Arguments
|Name|Type|Description|
|-|-|-
data|string|The text string to write to the log.

### Returns
|Type|Description|
|-|-
void|Returns nothing.

