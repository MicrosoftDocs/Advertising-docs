---
title: AccountTaxCertificate Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Reserved.
---
# AccountTaxCertificate Data Object - Customer Management
Reserved.

## Syntax
```xml
<xs:complexType name="AccountTaxCertificate" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="TaxCertificateBlobContainerName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TaxCertificates" nillable="true" type="q3:ArrayOfKeyValueOfstringbase64Binary" xmlns:q3="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:TaxCertificateStatus" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [AccountTaxCertificate](accounttaxcertificate.md) object has the following elements: [Status](#status), [TaxCertificateBlobContainerName](#taxcertificateblobcontainername), [TaxCertificates](#taxcertificates).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="status"></a>Status|Reserved.|[TaxCertificateStatus](taxcertificatestatus.md)|
|<a name="taxcertificateblobcontainername"></a>TaxCertificateBlobContainerName|Reserved.|**string**|
|<a name="taxcertificates"></a>TaxCertificates|Reserved.|[ArrayOfKeyValueOfstringbase64Binary](arrayofkeyvalueofstringbase64binary.md)|

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13/Entities  

## Used By
[AdvertiserAccount](advertiseraccount.md)  
