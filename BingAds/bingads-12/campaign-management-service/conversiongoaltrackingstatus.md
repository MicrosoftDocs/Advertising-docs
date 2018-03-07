---
title: ConversionGoalTrackingStatus Value Set - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible system-determined status values of a conversion goal.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ConversionGoalTrackingStatus Value Set - Campaign Management
Defines the possible system-determined status values of a conversion goal. These are the status values that can be set by the system, for example the system sets the status to *TagUnverified* if the UET tag has not yet been verified. 

> [!NOTE]
> For most goals (all except [AppInstallGoal](appinstallgoal.md)), the *ConversionGoalTrackingStatus* depends in part on the system-determined [UetTagTrackingStatus](uettagtrackingstatus.md) of the [UetTag](uettag.md) that is associated with the [ConversionGoal](conversiongoal.md). If the [UetTagTrackingStatus](uettagtrackingstatus.md) is *Active* then the conversion goal tracking status can be either *NoRecentConversions* or *RecordingConversions*, and otherwise the conversion goal tracking status mirrors the tag status. For details please see the descriptions below. 

For status values that a user can decide to set, for example setting the status to *Paused* if you no longer wish to track conversions for that goal, see [ConversionGoalStatus](conversiongoalstatus.md).   

## Syntax
```xml
<xs:simpleType name="ConversionGoalTrackingStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:restriction base="xs:string">
    <xs:enumeration value="TagUnverified" />
    <xs:enumeration value="NoRecentConversions" />
    <xs:enumeration value="RecordingConversions" />
    <xs:enumeration value="TagInactive" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="norecentconversions"></a>NoRecentConversions|The [UetTagTrackingStatus](uettagtrackingstatus.md) is *Active*, but we haven't recorded any conversions in the last 7 days. This is most likely because you either have created the goal incorrectly, have not tagged your entire website i.e. the pages that have the conversion action, or you don't have any users converting on your site. |
|<a name="recordingconversions"></a>RecordingConversions|The [UetTagTrackingStatus](uettagtrackingstatus.md) is *Active*, and we have recorded conversions within the last 7 days.|
|<a name="taginactive"></a>TagInactive|The [UetTagTrackingStatus](uettagtrackingstatus.md) is *Inactive*, and Bing Ads has not received any user activity data from the UET tag in the last 24 hours. Make sure that the UET tag tracking code is still on your website. |
|<a name="tagunverified"></a>TagUnverified|The [UetTagTrackingStatus](uettagtrackingstatus.md) is *Unverified*, and Bing Ads hasn't received any user activity data from the UET tag on your website. It can take up to 24 hours for Bing Ads to verify. If you still see this status, you either have not added the UET tag tracking code to your website or there is an issue with the setup that you need to fix. |

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

## Used By
[ConversionGoal](conversiongoal.md)  
