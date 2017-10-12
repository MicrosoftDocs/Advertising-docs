---
title: "OAuth Code Example"
ms.service: "hotel-ads-hotel-service"
ms.topic: "article"
author: "swhite-msft"
ms.author: "scottwhi"
description: 
dev_langs:
  - csharp
---
# OAuth Code Example
The following topics break out a simple desktop implementation used to get an access and refresh token. The example does not support the recommended state query parameter.

If you use the Bing Ads C# SDK, you should use it to get your OAuth access and refresh tokens. For information, see [Get Started](../transaction-message/get-started.md).

|Module|Description
|-|-
|[CodeGrantFlow](../hotel-service/code-example-codegrantflow.md)|A browser control that gets the user's credentials, requests permissions for your application to access their resources, and returns the access and refresh tokens.
|[Call CodeGrantFlow](../hotel-service/code-example-call-codegrantflow.md)|A test app that shows how to call the CodeGrantFlow DLL to get an access and refresh token.
