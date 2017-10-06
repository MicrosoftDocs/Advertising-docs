---
title: Address Data Object
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a postal address.
---
# Address Data Object
Defines a postal address.

## Syntax
```xml
<xs:complexType name="Address" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element name="CityName" nillable="true" type="xs:string" />
    <xs:element name="CountryCode" nillable="true" type="xs:string" />
    <xs:element name="PostalCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ProvinceCode" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ProvinceName" nillable="true" type="xs:string" />
    <xs:element name="StreetAddress" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="StreetAddress2" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="cityname"></a>CityName|The name of the city where the street address is located. The name can contain a maximum of 80 characters.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="countrycode"></a>CountryCode|The country where the street address is located. The country code must contain a 2 character country code. For a list of possible country codes that you can specify, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="postalcode"></a>PostalCode|The postal or zip code. The postal code can contain a maximum of 80 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|
|<a name="provincecode"></a>ProvinceCode|A code that identifies the state or province where the street address is located. For example, WA. The code can contain a maximum of 50 characters.<br /><br />You must specify either *ProvinceName* or *ProvinceCode*.<br /><br />**Note:** The *ProvinceCode* and *ProvinceName* are not required if the *CountryCode* element is set to either *FR*, *IE*, or *SG*.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="provincename"></a>ProvinceName|The name of the state or province where the street address is located. For example, Washington. The name can contain a maximum of 50 characters.<br /><br />You must specify either *ProvinceName* or *ProvinceCode*.<br /><br />**Note:** The*ProvinceCode* and *ProvinceName* are not required if the *CountryCode* element is set to either *FR*, *IE*, or *SG*.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="streetaddress"></a>StreetAddress|The first line of the address. The first line can contain a maximum of 80 characters.<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="streetaddress2"></a>StreetAddress2|The second line of the address. The second line can contain a maximum of 80 characters.<br/><br/>**Add:** Optional<br/>**Update:** Optional|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[LocationAdExtension](locationadextension.md)  
