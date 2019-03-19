---
title: AccountProperty Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Maps an account level property name to a string value.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# AccountProperty Data Object - Campaign Management
Maps an account level property name to a string value.

## Syntax
```xml
<xs:complexType name="AccountProperty" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="Name" type="tns:AccountPropertyName" />
    <xs:element minOccurs="0" name="Value" nillable="true" type="xs:string" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="name"></a>Name|The name of the account property.|[AccountPropertyName](accountpropertyname.md)|
|<a name="value"></a>Value|The value of the named account property.<br/><br/>The value will vary by account property name. For more information, see [Account Property Values](#accountpropertyvalues) in the section below.|**string**|

## <a name="remarks"></a>Remarks
### <a name="accountpropertyvalues"></a>Account Property Values
#### <a name="adclickparalleltracking"></a>AdClickParallelTracking
Determines whether parallel tracking is enabled. Parallel tracking lets you send users directly to your final URL while click measurement runs in the background.

Parallel tracking reduces the time it takes for your landing page to load, increasing customer satisfaction with your ad and website (making conversions more likely!).

You need to have {lpurl] or one of its variants in your URL's tracking template for parallel tracking to work. For more information see [What tracking or URL parameters can I use?](https://help.bingads.microsoft.com/#apex/3/en/56799/2-500).

If the [Name](#name) element is set to *AdClickParallelTracking*, then the returned [Value](#value) can be either *true* or *false*. If the value is *true*, then parallel tracking is enabled. 

> [!IMPORTANT]
> Parallel tracking is only available for pilot customers ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 474), and currently all other customers are opted out. During pilot you can enable and disable the feature i.e., set the property to *true* or *false*. By the end of calendar year 2019 all customers will be enabled for parallel tracking, and the value can only be set to *true*. 

#### <a name="finalurlsuffix"></a>FinalUrlSuffix
If the [Name](#name) element is set to *FinalUrlSuffix*, then the [Value](#value) represents your account's Final URL Suffix. 

The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. 

> [!NOTE]
> This feature is only available for customers in the Final URL Suffix Phase 1 pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 533). If you are not in the pilot and attempt to set this property an error will be returned. During calendar year 2019 this feature will be enabled for all customers.

To delete the account's Final URL Suffix set the [Name](#name) to *FinalUrlSuffix* and the *Value* to *""* (empty string).

#### <a name="msclkidautotaggingenabled"></a>MSCLKIDAutoTaggingEnabled
Determines whether auto-tagging of the MSCLKID query string parameter is enabled. The MSCLKID is a 32-character GUID that is unique for each ad click.

If the [Name](#name) element is set to *MSCLKIDAutoTaggingEnabled*, then the [Value](#value) can be set to either *true* or *false*. If the value is *true*, then the MSCLKID auto tagging feature is enabled. You might want to enable auto-tagging of MSCLKID for tracking leads via offline conversion goals. If auto-tagging of MSCLKID is enabled, the MSCLKID is automatically appended to the landing page URL when a customer clicks on your ad. For example, *www.contoso.com/?msclkid={msclkid}*. The click ID is unique for each ad click and multiple clicks on the same ad from the same user will result in multiple click IDs.

> [!IMPORTANT]
> Every time you add or update a new [DurationGoal](durationgoal.md), [EventGoal](eventgoal.md), [OfflineConversionGoal](offlineconversiongoal.md), [PagesViewedPerVisitGoal](pagesviewedpervisitgoal.md) or [UrlGoal](urlgoal.md) via either the Bing Ads web application or Campaign Management API, the *MSCLKIDAutoTaggingEnabled* value of the corresponding [AccountProperty](accountproperty.md) is set to *true* automatically. If the Scope of the goal is set to *Customer* level, then the [AccountProperty](accountproperty.md) for all accounts under the Customer will be set. 

#### <a name="trackingurltemplate"></a>TrackingUrlTemplate
If the [Name](#name) element is set to *TrackingUrlTemplate*, then the [Value](#value) represents your account's tracking template to use as a default for all URLs in your account. The value of the *TrackingUrlTemplate* key can be set to any valid string as described below.

- Tracking templates defined for lower level entities e.g. keyword override those set for higher level entities e.g. campaign. For more information, see [Entity Hierarchy and Limits](https://go.microsoft.com/fwlink/?LinkID=627130).

- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.

- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.

- You must include at least one of the following landing page URL parameters: *{lpurl}*, *{lpurl+2}*, *{lpurl+3}*, *{unescapedlpurl}*, *{escapedlpurl}*. Additionally, you can use any dynamic parameter supported by Bing Ads. For a list of supported parameters, see the *Available parameters* sections within the Bing Ads help article [Set up a tracking template](https://help.bingads.microsoft.com/#apex/3/en/56772/-1).

- Bing Ads does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the final URL will include the key and value placeholders of your custom parameters without substitution. For example if your tracking template is  for example *http://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}*, and neither {_season} or {_promocode}  are defined at the campaign, ad group, keyword, or ad level, then the final URL will be the same.

To delete the account's tracking template set the [Name](#name) to *TrackingUrlTemplate* and the *Value* to *""* (empty string).

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

## Used By
[GetAccountProperties](getaccountproperties.md)  
[SetAccountProperties](setaccountproperties.md)  
