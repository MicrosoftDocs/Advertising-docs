---
title: WebpageCondition Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Defines a condition or criterion that helps determine whether you want to show dynamic search ads.
---
# WebpageCondition Data Object - Campaign Management
Defines a condition or criterion that helps determine whether you want to show dynamic search ads.

## Syntax
```xml
<xs:complexType name="WebpageCondition" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Argument" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Operand" type="q2:WebpageConditionOperand" xmlns:q2="https://bingads.microsoft.com/CampaignManagement/v11" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="argument"></a>Argument|The webpage condition or criterion. The condition is met if the webpage property that is referenced by the operand contains or equals the argument's value.<br/><br/>For example you can set this string to the URL, category, page title, or page content for your site.<br/><br/>**Add:** Required<br/>**Update:** Not applicable. You cannot update the webpage conditions. To update the conditions you must delete the criterion and add a new criterion.|**string**|
|<a name="operand"></a>Operand|The webpage condition operand.<br/><br/>**Add:** Required<br/>**Update:** Not applicable. You cannot update the webpage conditions. To update the conditions you must delete the criterion and add a new criterion.|[WebpageConditionOperand](webpageconditionoperand.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11  

## Used By
[WebpageParameter](webpageparameter.md)  
