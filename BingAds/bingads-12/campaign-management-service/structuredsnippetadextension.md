---
title: StructuredSnippetAdExtension Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines an object that pairs one header with between 3 and 10 snippet values that tell customers more about your business.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# StructuredSnippetAdExtension Data Object - Campaign Management
Defines an object that pairs one header with between 3 and 10 snippet values that tell customers more about your business.

In the following example, *Courses* is the header, and *.NET*, *Java*, *Python*, and *PHP* are examples of individual values.

**Courses: .NET, Java, Python, PHP**

You can associate a structured snippet ad extension with the account or with campaigns and ad groups in the account. Each entity (account, campaign, or ad group) can be associated with up to 20 structured snippet ad extensions. An expanded text ad will only include one structured snippet (one headline with 3 - 10 values) per impression.

## Syntax
```xml
<xs:complexType name="StructuredSnippetAdExtension" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:AdExtension">
      <xs:sequence>
        <xs:element name="Header" nillable="true" type="xs:string" />
        <xs:element name="Values" nillable="true" type="q44:ArrayOfstring" xmlns:q44="http://schemas.microsoft.com/2003/10/Serialization/Arrays" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="header"></a>Header|The header that is appended with a colon (*:*) and precedes the snippet values. <br/><br/>Structured Snippet headers must be specified in the same language that you intend it to be shown. For example, if you want header *Amenities* in English you must specify the header as *Amenities*.  If you want header *Ausstattung* in German you must specify the header as *Ausstattung* (*Amenities* in German). For a list of supported headers per language, please see [Structured Snippet Header Languages](../guides/ad-languages.md#structuredsnippetheaders).<br/><br/>**Add:** Required<br/>**Update:** Required|**string**|
|<a name="values"></a>Values|The snippet values that follow after the *Header:* component. You can choose the values, and each value can have a maximum length of 25 characters. Note that for Traditional Chinese characters, each value can have a maximum length of 12 characters.<br/><br/>**Add:** Required<br/>**Update:** Required|**string** array|

The [StructuredSnippetAdExtension](structuredsnippetadextension.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsadextension"></a>Inherited Elements from AdExtension
The [StructuredSnippetAdExtension](structuredsnippetadextension.md) object derives from the [AdExtension](adextension.md) object, and inherits the following elements. The descriptions below are specific to [StructuredSnippetAdExtension](structuredsnippetadextension.md), and might not apply to other objects that inherit the same elements from the [AdExtension](adextension.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devicepreference"></a>DevicePreference|Reserved for future use.|**long**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br />There are currently no forward compatibility changes for the *AdExtension* object.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Bing Ads identifier of the ad extension.<br/><br/>**Add:** Read-only and Required<br/>**Update:** Read-only|**long**|
|<a name="scheduling"></a>Scheduling|Determines the calendar day and time ranges when the ad extension is eligible to be shown in ads.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If you set this element null, any existing scheduling set for the ad extension will remain unchanged. If you set this to any non-null [Schedule](schedule.md) object, you are effectively replacing existing scheduling settings for the ad extension. To remove all scheduling set this element to an empty [Schedule](schedule.md) object.|[Schedule](schedule.md)|
|<a name="status"></a>Status|The status of the ad extension. The value will always be *Active* because the Campaign Management service does not return deleted ad extensions.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdExtensionStatus](adextensionstatus.md)|
|<a name="type"></a>Type|The type of the ad extension. This value is *StructuredSnippetAdExtension* when you retrieve a structured snippet ad extension.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only<br/><br/>For more information about ad extension types, see the [Ad Extension Data Object Remarks](adextension.md#remarks).|**string**|
|<a name="version"></a>Version|The number of times the contents of the ad extension has been updated. The version is set to 1 when you add the extension and is incremented each time it's revised.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**int**|

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

