---
title: SiteLinksAdExtension Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# SiteLinksAdExtension Data Object
Defines an object with *multiple* sitelinks per ad extension. You can use the sitelinks to promote certain products, services, or sections of your website and take potential customers to exactly the information they were searching for. This can increase both click-through-rate and conversions.

> [!NOTE]
> During calendar year 2017, Bing Ads upgraded all [SiteLinksAdExtension](../campaign-management/sitelinksadextension.md) objects (contains multiple sitelinks per ad extension) to [Sitelink2AdExtension](../campaign-management/sitelink2adextension.md) objects (contains one sitelink per ad extension).

## Syntax
```xml
<xs:complexType name="SiteLinksAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element name="SiteLinks" nillable="true" type="tns:ArrayOfSiteLink" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="sitelinks"></a>SiteLinks|A list of site links. Each object contains a link to a webpage on your website. You can specify a maximum of 10 site links, and the search engine determines a subset of links to include in the ad. If you specify the *Description1* and *Description2* elements of each site link, then up to four site links will be displayed.<br/><br/>**Add:** Required<br/>**Update:** Required|[SiteLink](sitelink.md) array|

The [SiteLinksAdExtension](sitelinksadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [SiteLinksAdExtension](sitelinksadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [SiteLinksAdExtension](sitelinksadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Not supported.<br/><br/>For *SiteLinksAdExtension* objects, you specify the *DevicePreference* for each [SiteLink](../campaign-management/sitelink.md), otherwise the operation will fail if you attempt to set the ad extension level *DevicePreference* element.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|This element is not supported at the parent site link ad extension level. <br/><br/>**Note:** Whereas this element is not applicable for the *SiteLinksAdExtension* object, you can specify a *Scheduling* element within each individual [SiteLink](../campaign-management/sitelink.md) object (nested list within the *SiteLinksAdExtension*). For most other ad extension types including [Sitelink2AdExtension](../campaign-management/sitelink2adextension.md), the [AdExtension](../campaign-management/adextension.md) object will include the *Scheduling* element.<br/><br/>**Add:** Not applicable.<br/>**Update:** Not applicable.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *SiteLinksAdExtension* when you retrieve a sitelinks ad extension. <br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](../campaign-management/adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it?s revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

