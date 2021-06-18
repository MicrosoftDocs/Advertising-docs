---
title: CampaignAdditionalField Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a list of optional campaign properties that you can request when calling GetCampaignsByAccountId and GetCampaignsByIds.
---
# CampaignAdditionalField Value Set - Campaign Management
Defines a list of optional campaign properties that you can request when calling [GetCampaignsByAccountId](getcampaignsbyaccountid.md) and [GetCampaignsByIds](getcampaignsbyids.md). The additional field values enable you to get the latest features using the current version of Campaign Management API, and in the next version the corresponding properties will be included in the campaign by default.  

## Syntax
```xml
<xs:simpleType name="CampaignAdditionalField" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="AdScheduleUseSearcherTimeZone" />
        <xs:enumeration value="MaxConversionValueBiddingScheme" />
        <xs:enumeration value="TargetImpressionShareBiddingScheme" />
        <xs:enumeration value="TargetSetting" />
        <xs:enumeration value="BidStrategyId" />
        <xs:enumeration value="CpvCpmBiddingScheme" />
        <xs:enumeration value="DynamicFeedSetting" />
        <xs:enumeration value="MultimediaAdsBidAdjustment" />
        <xs:enumeration value="VerifiedTrackingSetting" />
        <xs:enumeration value="DynamicDescriptionSetting" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

The [CampaignAdditionalField](campaignadditionalfield.md) value set has the following values: [AdScheduleUseSearcherTimeZone](#adscheduleusesearchertimezone), [BidStrategyId](#bidstrategyid), [CpvCpmBiddingScheme](#cpvcpmbiddingscheme), [DynamicDescriptionSetting](#dynamicdescriptionsetting), [DynamicFeedSetting](#dynamicfeedsetting), [MaxConversionValueBiddingScheme](#maxconversionvaluebiddingscheme), [MultimediaAdsBidAdjustment](#multimediaadsbidadjustment), [TargetImpressionShareBiddingScheme](#targetimpressionsharebiddingscheme), [TargetSetting](#targetsetting), [VerifiedTrackingSetting](#verifiedtrackingsetting).

|Value|Description|
|-----------|---------------|
|<a name="adscheduleusesearchertimezone"></a>AdScheduleUseSearcherTimeZone|Request that the [AdScheduleUseSearcherTimeZone](campaign.md#adscheduleusesearchertimezone) element be included within each returned [Campaign](campaign.md) object.|
|<a name="bidstrategyid"></a>BidStrategyId|Request that the [BidStrategyId](campaign.md#bidstrategyid) element be included within each returned [Campaign](campaign.md) object.|
|<a name="cpvcpmbiddingscheme"></a>CpvCpmBiddingScheme|Request that the [ManualCpmBiddingScheme](manualcpmbiddingscheme.md) or [ManualCpvBiddingScheme](manualcpvbiddingscheme.md) object be returned within the [BiddingScheme](campaign.md#biddingscheme) element of each returned [Campaign](campaign.md) object.|
|<a name="dynamicdescriptionsetting"></a>DynamicDescriptionSetting||Request that the [DynamicDescriptionEnabled](dynamicdescriptionenabled.md) element be returned within the [DynamicSearchAdsSetting](dynamicsearchadssetting.md)<br/><br/>A the [DynamicSearchAdsSetting](dynamicsearchadssetting.md) object can be returned within the [Settings](campaign.md#settings) element of a search [Campaign](campaign.md) object.|
|<a name="dynamicfeedsetting"></a>DynamicFeedSetting|Request that the [DynamicFeedSetting](dynamicfeedsetting.md) object be returned within the [Settings](campaign.md#settings) element of each returned [Campaign](campaign.md) object.|
|<a name="maxconversionvaluebiddingscheme"></a>MaxConversionValueBiddingScheme|Request that the [MaxConversionValueBiddingScheme](maxconversionvaluebiddingscheme.md) object be returned within the [BiddingScheme](campaign.md#biddingscheme) element of each returned [Campaign](campaign.md) object.|
|<a name="multimediaadsbidadjustment"></a>MultimediaAdsBidAdjustment|Request that the MultimediaAdsBidAdjustment element be included within each returned [Campaign](campaign.md) object.|
|<a name="targetimpressionsharebiddingscheme"></a>TargetImpressionShareBiddingScheme|Request that the [TargetImpressionShareBiddingScheme](targetimpressionsharebiddingscheme.md) object be returned within the [BiddingScheme](campaign.md#biddingscheme) element of each returned [Campaign](campaign.md) object.|
|<a name="targetsetting"></a>TargetSetting|Request that the [TargetSetting](targetsetting.md) object be returned within the [Settings](campaign.md#settings) element of each returned [Campaign](campaign.md) object.|
|<a name="verifiedtrackingsetting"></a>VerifiedTrackingSetting|Request that the [VerifiedTrackingSetting](verifiedtrackingsetting.md) object be returned within the [Settings](campaign.md#settings) element of each returned [Campaign](campaign.md) object.|

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetCampaignsByAccountId](getcampaignsbyaccountid.md)  
[GetCampaignsByIds](getcampaignsbyids.md)  
