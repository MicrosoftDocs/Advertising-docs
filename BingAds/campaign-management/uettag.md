---
title: UetTag Data Object
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# UetTag Data Object
Defines a Universal Event Tracking (UET) tag that you can add to your website to allow Bing Ads to collect actions people take on your website.

After you create a UET tag (e.g. via [AddUetTags](../campaign-management/adduettags.md)), the next step is to add the UET tag tracking code to your website. We recommend that you, or your website administrator, add it to your entire website in either the head or body sections. If your website has a master page, then that is the best place to add it because you add it once and it is included on all pages. For more information, see [How do I add the UET tag to my website?](https://help.bingads.microsoft.com/#apex/3/en/56688/2).

You can use one UET tag with all of your conversion goals and remarketing lists. Before you create multiple UET tags, see [Reasons for creating more than one UET tag](https://help.bingads.microsoft.com/#apex/3/en/56685/2).

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](~/guides/universal-event-tracking.md) technical guide.

## Syntax
```xml
<xs:complexType name="UetTag" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Description" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Id" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TrackingNoScript" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TrackingScript" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="TrackingStatus" nillable="true" type="tns:UetTagTrackingStatus" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="description"></a>Description|Text to help you identify the UET tag. We recommend that you set this to the related website page name or URL.<br /><br />**Add:** Optional<br />**Update:** Optional|**string**|
|<a name="id"></a>Id|The unique Bing Ads identifier of the UET tag.<br /><br />**Add:** Read-only<br />**Update:** Required and Read-only|**long**|
|<a name="name"></a>Name|The UET tag name.<br/><br/>The maximum length of the name is 100, and the name must be unique among all UET tags belonging to the same customer.<br /><br />**Add:** Required<br />**Update:** Optional|**string**|
|<a name="trackingnoscript"></a>TrackingNoScript|If your website doesn?t support JavaScript, you can use this Non-JavaScript representation of the UET tag. If you use Non-JavaScript, you can?t track custom events or variable revenue.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**string**|
|<a name="trackingscript"></a>TrackingScript|The tracking script that you can add to your website to allow Bing Ads to collect actions people take on your website.<br /><br />**Add:** Read-only<br />**Update:** Read-only|**string**|
|<a name="trackingstatus"></a>TrackingStatus|The system-determined status values of a UET tag, for example the system sets the status to *Unverified* if the UET tag has not yet been verified.<br /><br />**Add:** Read-only<br />**Update:** Read-only|[UetTagTrackingStatus](uettagtrackingstatus.md)|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[AddUetTags](adduettags.md)  
[GetUetTagsByIds](getuettagsbyids.md)  
[UpdateUetTags](updateuettags.md)  
