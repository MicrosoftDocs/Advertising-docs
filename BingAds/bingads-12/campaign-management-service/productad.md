---
title: ProductAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a product ad.
---
# ProductAd Data Object - Campaign Management
Defines a product ad. A product ad is not used directly for delivered ad copy.  Instead, the delivery engine generates product ads from the product details that it finds in the customer's Bing Merchant Center store.

## Syntax
```xml
<xs:complexType name="ProductAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element minOccurs="0" name="PromotionalText" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="promotionaltext"></a>PromotionalText|The promotional text to display in a product ad. If you do not want to add promotional text to the product ads, set *PromotionalText* to null or an empty string.<br /><br />The text can contain a maximum of 45 characters. The promotional text of product ads within an ad group must be unique.<br /><br />**Add:** Optional<br/>**Update:** Optional|**string**|

The [ProductAd](productad.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [ProductAd](productad.md) object derives from the [Ad](ad.md) object, and inherits the following elements. The descriptions below are specific to [ProductAd](productad.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|This element is not applicable for product ads.|**string**|
|<a name="devicepreference"></a>DevicePreference|Not supported for product ads.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br /><br />**Add:** Read-only<br/>**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Not supported for product ads.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|Not supported for product ads.|**string** array|
|<a name="finalurls"></a>FinalUrls|Not supported for product ads.|**string** array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently not any ForwardCompatibilityMap key and value pairs that are applicable for product ads.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier for the ad.<br /><br />**Add:** Read-only<br/>**Update:** Required and Read-only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br /><br />**Add:** Optional<br/>**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Not supported for product ads.|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *Product* when you retrieve a product ad. For more information about ad types, see the [Ad Data Object Remarks](ad.md#remarks).<br /><br />**Add:** Read-only<br/>**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Not supported for product ads.|[CustomParameters](customparameters.md)|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

