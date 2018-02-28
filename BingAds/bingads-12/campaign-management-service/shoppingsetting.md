---
title: ShoppingSetting Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the campaign level settings for a Bing Shopping Campaign.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ShoppingSetting Data Object - Campaign Management
Defines the campaign level settings for a Bing Shopping Campaign.

## Syntax
```xml
<xs:complexType name="ShoppingSetting" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Setting">
      <xs:sequence>
        <xs:element minOccurs="0" name="LocalInventoryAdsEnabled" nillable="true" type="xs:boolean" />
        <xs:element minOccurs="0" name="Priority" nillable="true" type="xs:int" />
        <xs:element minOccurs="0" name="SalesCountryCode" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="StoreId" nillable="true" type="xs:long" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="localinventoryadsenabled"></a>LocalInventoryAdsEnabled|Determines whether local inventory ads are enabled for the Bing Merchant Center store.<br/><br/> Not everyone has this feature yet. If you don't, don't worry. It's coming soon.<br/><br/>Set this property to *true* if you want to enable local inventory ads, and otherwise set it to *false*.<br/><br/>**Add:** Optional. If you do not specify this field or leave it empty, the default value of *false* will be set and local inventory ads will not be enabled.<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**boolean**|
|<a name="priority"></a>Priority|Helps determine which Bing Shopping campaign  serves ads, in the event that two or more campaigns use the product catalog feed from the same Bing Merchant Center store.<br /><br />You must specify one of the supported values: 0, 1, or 2. The higher numbers are given higher priority.<br /><br />If two shopping campaigns use the product catalog feed from same Bing Merchant Center store, then  ads will be delivered for the [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) with the highest bid.<br /><br /> In the Bing Ads web application, the default priority selected is "Low" which is the equivalent of '0'.<br/><br/>**Add:** Required<br/>**Update:** Optional|**int**|
|<a name="salescountrycode"></a>SalesCountryCode|The country code for the Bing Merchant Center store. To get the list of supported country codes use the [GetBSCCountries](../campaign-management-service/getbsccountries.md) operation.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**string**|
|<a name="storeid"></a>StoreId|The unique identifier for the Bing Merchant Center store that your product catalog feed belongs to.<br /><br />To get the *StoreId*, call the [GetBMCStoresByCustomerId](../campaign-management-service/getbmcstoresbycustomerid.md) operation. The *Id* element of a [BMCStore](../campaign-management-service/bmcstore.md) corresponds to this *StoreId*.<br/><br/>**Add:** Required<br/>**Update:** Read-only|**long**|

The [ShoppingSetting](shoppingsetting.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementssetting"></a>Inherited Elements from Setting
The [ShoppingSetting](shoppingsetting.md) object derives from the [Setting](setting.md) object, and inherits the following elements. The descriptions below are specific to [ShoppingSetting](shoppingsetting.md), and might not apply to other objects that inherit the same elements from the [Setting](setting.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="type"></a>Type|The type of the setting. This value is *Shopping* when you retrieve a shopping setting. For more information about setting types, see the [Setting Data Object Remarks](../campaign-management-service/setting.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**string**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

