---
title: PriceTableRow Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines pricing information by currency and unit that you can use with price ad extensions.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# PriceTableRow Data Object - Campaign Management
Defines pricing information by currency and unit that you can use with price ad extensions.

## Syntax
```xml
<xs:complexType name="PriceTableRow" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="CurrencyCode" nillable="true" type="xs:string" />
    <xs:element name="Description" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="FinalMobileUrls" nillable="true" type="q45:ArrayOfstring" xmlns:q45="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element name="FinalUrls" nillable="true" type="q46:ArrayOfstring" xmlns:q46="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element name="Header" nillable="true" type="xs:string" />
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
|<a name="currencycode"></a>CurrencyCode|The currency code for the listed price.<br/><br/>For more information, see [Currencies](../guides/currencies.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="description"></a>Description|The description must provide further information about the header that is also defined in this object.<br/><br/>The description can contain a maximum of 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.<br /><br />**Add:** Optional<br />**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br /><br />The following validation rules apply to Final URLs and Final Mobile URLs.- The length of the URL is limited to 2,048 characters.     The HTTP or HTTPS protocol string does count towards the 2,048 character limit.- You may specify up to 10 items for both *FinalUrls* and *FinalMobileUrls*; however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.- Usage of '{' and '}' is only allowed to delineate tags, for example "{lpurl}".- Final URLs must each be a well-formed URL starting with either http:// or https://.- If you specify *FinalMobileUrls*, you must also specify *FinalUrls*.- You may not specify *FinalMobileUrls* if the device preference is set to mobile.Also note that if the price ad extension's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br /><br />**Add:** Optional<br />**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string** array|
|<a name="header"></a>Header|The header that precedes the pricing data.<br/><br/>The header can contain a maximum of 25 characters.<br/><br/>The header must tie directly to the [priceextensiontype](priceextensiontype.md) that you defined for the [PriceAdExtension](priceadextension.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="price"></a>Price|The price that you are advertising.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**double**|
|<a name="pricequalifier"></a>PriceQualifier|The price qualifier.<br/><br/>Possible values include: *PerDay*, *PerHour*, *PerMonth*, *PerNight*, *PerWeek*, *PerYear*, *None*, and *Unknown*. <br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[PriceQualifier](pricequalifier.md)|
|<a name="priceunit"></a>PriceUnit|The price unit.<br/><br/>Possible values include: *Average*, *From*, *UpTo*, *None*, and *Unknown*.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|[PriceUnit](priceunit.md)|
|<a name="termsandconditions"></a>TermsAndConditions|Reserved for future use.|**string**|
|<a name="termsandconditionsurl"></a>TermsAndConditionsUrl|Reserved for future use.|**string**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

## Used By
[PriceAdExtension](priceadextension.md)  
