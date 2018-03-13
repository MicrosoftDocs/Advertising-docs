---
title: AdExtensionsTypeFilter Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible ad extension types.
---
# AdExtensionsTypeFilter Value Set - Campaign Management
Defines the possible ad extension types.

## Syntax
```xml
<xs:simpleType name="AdExtensionsTypeFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="SiteLinksAdExtension" />
        <xs:enumeration value="LocationAdExtension" />
        <xs:enumeration value="CallAdExtension" />
        <xs:enumeration value="ImageAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="AppAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="ReviewAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">128</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="CalloutAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">512</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="Sitelink2AdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">1024</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="StructuredSnippetAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4096</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
        <xs:enumeration value="PriceAdExtension">
          <xs:annotation>
            <xs:appinfo>
              <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8192</EnumerationValue>
            </xs:appinfo>
          </xs:annotation>
        </xs:enumeration>
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="appadextension"></a>AppAdExtension|An ad extension that contains a link to install an application from a supported app store. For more information, see [AppAdExtension](appadextension.md).|
|<a name="calladextension"></a>CallAdExtension|An ad extension that contains a phone number and whether it's the only clickable item in an ad. For more information, see [CallAdExtension](calladextension.md).|
|<a name="calloutadextension"></a>CalloutAdExtension|An ad extension that contains additional text in the ad that can describe more about your business, products, or services. For more information, see [CalloutAdExtension](calloutadextension.md).|
|<a name="imageadextension"></a>ImageAdExtension|An ad extension that contains an image with alternative text. For more information, see [ImageAdExtension](imageadextension.md).|
|<a name="locationadextension"></a>LocationAdExtension|An ad extension that contains the address and phone number of the business. For more information, see [LocationAdExtension](locationadextension.md).|
|<a name="priceadextension"></a>PriceAdExtension|An ad extension that includes between 3 and 8 price table rows. For more information, see [PriceAdExtension](priceadextension.md).|
|<a name="reviewadextension"></a>ReviewAdExtension|An ad extension that contains third-party reviews (exact or paraphrased) about your business, products, or services. For more information, see [ReviewAdExtension](reviewadextension.md).|
|<a name="sitelink2adextension"></a>Sitelink2AdExtension|An ad extension that contains one site link. For more information, see [Sitelink2AdExtension](sitelink2adextension.md).|
|<a name="sitelinksadextension"></a>SiteLinksAdExtension|This value is deprecated in favor of Sitelink2AdExtension.|
|<a name="structuredsnippetadextension"></a>StructuredSnippetAdExtension|An ad extension that contains a header and values that tell customers more about your business. For more information, see [StructuredSnippetAdExtension](structuredsnippetadextension.md).|

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[GetAdExtensionIdsByAccountId](getadextensionidsbyaccountid.md)  
[GetAdExtensionsAssociations](getadextensionsassociations.md)  
[GetAdExtensionsByIds](getadextensionsbyids.md)  
