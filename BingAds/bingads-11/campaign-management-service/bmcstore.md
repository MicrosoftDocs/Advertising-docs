---
title: BMCStore Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a Bing Merchant Center store.
---
# BMCStore Data Object - Campaign Management
Defines a Bing Merchant Center store.

Elements of this object are defined in the Bing Merchant Center store, and read-only in Bing Ads.  Values of elements do not restrict Bing Ads features. For example, a Bing Shopping campaign and product ad may be added whether the *IsActive* element is set to true or false.

## Syntax
```xml
<xs:complexType name="BMCStore" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="HasCatalog" type="xs:boolean" />
    <xs:element minOccurs="0" name="Id" type="xs:long" />
    <xs:element minOccurs="0" name="IsActive" type="xs:boolean" />
    <xs:element minOccurs="0" name="IsProductAdsEnabled" type="xs:boolean" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="SubType" nillable="true" type="tns:BMCStoreSubType">
      <xs:annotation>
        <xs:appinfo>
          <DefaultValue EmitDefaultValue="false" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
        </xs:appinfo>
      </xs:annotation>
    </xs:element>
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="hascatalog"></a>HasCatalog|Value will be true if the store has a catalog of items, and otherwise the value is false.|**boolean**|
|<a name="id"></a>Id|The unique identifier for the  Bing Merchant Center store.|**long**|
|<a name="isactive"></a>IsActive|Value will be true if the store is active, and otherwise the value is false.|**boolean**|
|<a name="isproductadsenabled"></a>IsProductAdsEnabled|Reserved for internal use.|**boolean**|
|<a name="name"></a>Name|Defines the name of the store as defined in the Bing Merchant Center.|**string**|
|<a name="subtype"></a>SubType|The Bing Merchant Center store sub type.<br/><br/>This element is only applicable for Bing Merchant Center stores of subtype *CoOp*, and will be nil for all other stores. If the subtype is set to *CoOp* then you have linked from a partner's store. When your partner retrieves the same store via [GetBMCStoresByCustomerId](getbmcstoresbycustomerid.md) the subtype would be nil, since from their perspective the store is not restricted to cooperative bidding.<br /><br />This element is not returned in the *BMCStore* object by default. You must set the *ReturnCoOpStores* request element to *True* when calling [GetBMCStoresByCustomerId](getbmcstoresbycustomerid.md).|[BMCStoreSubType](bmcstoresubtype.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetBMCStoresByCustomerId](getbmcstoresbycustomerid.md)  
