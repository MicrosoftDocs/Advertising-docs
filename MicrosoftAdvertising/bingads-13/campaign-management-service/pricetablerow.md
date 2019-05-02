---
title: PriceTableRow Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines pricing information by currency and unit that you can use with price ad extensions.
---
# PriceTableRow Data Object - Campaign Management
Defines pricing information by currency and unit that you can use with price ad extensions.

## Syntax
```xml
<xs:complexType name="PriceTableRow" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="CurrencyCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q48:ArrayOfstring" xmlns:q48="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="FinalUrls" nillable="true" type="q49:ArrayOfstring" xmlns:q49="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="Header" nillable="true" type="xs:string" />
    <xs:element name="Price" type="xs:double" />
    <xs:element name="PriceQualifier" type="tns:PriceQualifier" />
    <xs:element name="PriceUnit" type="tns:PriceUnit" />
    <xs:element minOccurs="0" name="TermsAndConditions" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TermsAndConditionsUrl" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="currencycode"></a>CurrencyCode|The currency code for the listed price.<br/><br/>The supported currency codes are ARS, AUD, BRL, CAD, CHF, CLP, CNY, COP, DKK, EUR, GBP, HKD, INR, MXN, NZD, PEN, PHP, PLN, SEK, SGD, USD, TWD, and VEF.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="description"></a>Description|The description must provide further information about the header that is also defined in this object.<br/><br/>The description can contain a maximum of 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile. Also note that if the price ad extension's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string** array|
|<a name="header"></a>Header|The header that precedes the pricing data.<br/><br/>The header can contain a maximum of 25 characters.<br/><br/>The header must tie directly to the [priceextensiontype](priceextensiontype.md) that you defined for the [PriceAdExtension](priceadextension.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="price"></a>Price|The price that you are advertising.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**double**|
|<a name="pricequalifier"></a>PriceQualifier|The price qualifier for a given product or service e.g., starting from a specific price and up to a maximum price.<br/><br/>Possible values include: *Average*, *From*, *UpTo*, *None*, and *Unknown*.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[PriceQualifier](pricequalifier.md)|
|<a name="priceunit"></a>PriceUnit|The price unit allows you to specify the cost in terms of hour, day, week, etc. The price qualifier for a given product or service e.g., starting from a specific price and up to a maximum price.<br/><br/>Possible values include: *PerDay*, *PerHour*, *PerMonth*, *PerNight*, *PerWeek*, *PerYear*, *None*, and *Unknown*.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|[PriceUnit](priceunit.md)|
|<a name="termsandconditions"></a>TermsAndConditions|Reserved for future use.|**string**|
|<a name="termsandconditionsurl"></a>TermsAndConditionsUrl|Reserved for future use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[PriceAdExtension](priceadextension.md)  
