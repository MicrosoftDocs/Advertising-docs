---
title: AccountPropertyName Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the name of account level properties.
---
# AccountPropertyName Value Set - Campaign Management
Defines the name of account level properties.

## Syntax
```xml
<xs:simpleType name="AccountPropertyName" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="None" />
    <xs:enumeration value="TrackingUrlTemplate" />
    <xs:enumeration value="MSCLKIDAutoTaggingEnabled" />
    <xs:enumeration value="AdClickParallelTracking">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">4</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="FinalUrlSuffix">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">8</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="IncludeViewThroughConversions">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="ProfileExpansionEnabled">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">32</EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

The [AccountPropertyName](accountpropertyname.md) value set has the following values: [AdClickParallelTracking](#adclickparalleltracking), [FinalUrlSuffix](#finalurlsuffix), [IncludeViewThroughConversions](#includeviewthroughconversions), [MSCLKIDAutoTaggingEnabled](#msclkidautotaggingenabled), [None](#none), [ProfileExpansionEnabled](#profileexpansionenabled), [TrackingUrlTemplate](#trackingurltemplate).

|Value|Description|
|-----------|---------------|
|<a name="adclickparalleltracking"></a>AdClickParallelTracking|Used to get or set the property that determines whether you want to send customers directly to your final URL while click measurement runs in the background.<br/><br/>For more information see [AdClickParallelTracking](accountproperty.md#adclickparalleltracking).|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|Used to get or set the account's Final URL Suffix.<br/><br/>For more information see [FinalUrlSuffix](accountproperty.md#finalurlsuffix).|
|<a name="includeviewthroughconversions"></a>IncludeViewThroughConversions|Used to get or set the property that determines whether you want to include view-through conversions for campaigns in the account.<br/><br/>For more information see [IncludeViewThroughConversions](accountproperty.md#includeviewthroughconversions).|
|<a name="msclkidautotaggingenabled"></a>MSCLKIDAutoTaggingEnabled|Used to get or set the property that determines whether MSCLKID auto-tagging is enabled for the account.<br/><br/>For more information see [MSCLKIDAutoTaggingEnabled](accountproperty.md#msclkidautotaggingenabled).|
|<a name="none"></a>None|Reserved for internal use.|
|<a name="profileexpansionenabled"></a>ProfileExpansionEnabled|Used to get or set the property that determines whether LinkedIn profile targeting expansion is enabled for the account.<br/><br/>For more information see [ProfileExpansionEnabled](accountproperty.md#profileexpansionenabled).|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|Used to get or set the account's tracking template.<br/><br/>For more information see [TrackingUrlTemplate](accountproperty.md#trackingurltemplate).|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[AccountProperty](accountproperty.md)  
[GetAccountProperties](getaccountproperties.md)  
