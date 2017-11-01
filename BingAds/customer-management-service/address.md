---
title: Address Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Defines a postal address.
---
# Address Data Object - Customer Management
Defines a postal address.

## Syntax
```xml
<xs:complexType name="Address" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="City" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="CountryCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Line1" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Line2" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Line3" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Line4" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="PostalCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="StateOrProvince" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TimeStamp" nillable="true" type="xs:base64Binary" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="city"></a>City|The city, which can contain a maximum of 35 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="countrycode"></a>CountryCode|The country/region code. For possible values, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="id"></a>Id|The system generated identifier of the address object.<br/><br/>**Add:** Read-only<br/>**Update:** Required|**long**|
|<a name="line1"></a>Line1|The first line of the address, which can contain a maximum of 35 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="line2"></a>Line2|The second line of the address, which can contain a maximum of 35 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="line3"></a>Line3|The third line of the address, which can contain a maximum of 35 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="line4"></a>Line4|The fourth line of the address, which can contain a maximum of 35 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="postalcode"></a>PostalCode|The Postal or ZIP Code, which can contain a maximum of 10 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="stateorprovince"></a>StateOrProvince|The state or province. This element is required for countries that define sub geographies, but should be set to null for countries that do not define sub geographies, such as Singapore.<br /><br />For possible values, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br /><br /> You must use the state or province code without country prefix. For example given US-WA, you should use only the WA suffix for Washington state.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="timestamp"></a>TimeStamp|The date and time that the address was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**base64Binary**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[AdvertiserAccount](advertiseraccount.md)  
[ContactInfo](contactinfo.md)  
[Customer](customer.md)  
