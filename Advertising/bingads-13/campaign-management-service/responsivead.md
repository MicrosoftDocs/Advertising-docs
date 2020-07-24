---
title: ResponsiveAd Data Object - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: A responsive ad format for Audience ads in the Microsoft Audience Network.
---
# ResponsiveAd Data Object - Campaign Management
A responsive ad format for Audience ads in the Microsoft Audience Network.

Responsive ads automatically adjust to accommodate the sizes and shapes of audience ad formats. These ads work best with informative text rather than calls to action.

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

> [!NOTE]
> Duplicate responsive ads are allowed in the same ad group. 

## Syntax
```xml
<xs:complexType name="ResponsiveAd" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:complexContent mixed="false">
    <xs:extension base="tns:Ad">
      <xs:sequence>
        <xs:element minOccurs="0" name="BusinessName" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="CallToAction" nillable="true" type="tns:CallToAction" />
        <xs:element minOccurs="0" name="Descriptions" nillable="true" type="tns:ArrayOfAssetLink" />
        <xs:element minOccurs="0" name="Headline" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Headlines" nillable="true" type="tns:ArrayOfAssetLink" />
        <xs:element minOccurs="0" name="Images" nillable="true" type="tns:ArrayOfAssetLink" />
        <xs:element minOccurs="0" name="LongHeadline" nillable="true" type="tns:AssetLink" />
        <xs:element minOccurs="0" name="LongHeadlineString" nillable="true" type="xs:string" />
        <xs:element minOccurs="0" name="Text" nillable="true" type="xs:string" />
      </xs:sequence>
    </xs:extension>
  </xs:complexContent>
</xs:complexType>
```

## <a name="elements"></a>Elements

The [ResponsiveAd](responsivead.md) object has the following elements: [BusinessName](#businessname), [CallToAction](#calltoaction), [Descriptions](#descriptions), [Headline](#headline), [Headlines](#headlines), [Images](#images), [LongHeadline](#longheadline), [LongHeadlineString](#longheadlinestring), [Text](#text).

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="businessname"></a>BusinessName|The name of the business.<br/><br/>Depending on your audience ad's placement, your business's name may appear in your ad.<br/><br/>The length of the string is limited to 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="calltoaction"></a>CallToAction|A brief, punchy reason for customers to click your ad right now.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[CallToAction](calltoaction.md)|
|<a name="descriptions"></a>Descriptions|Reserved for future use.|[AssetLink](assetlink.md) array|
|<a name="headline"></a>Headline|This is one of two possible headlines that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements.<br/><br/>The length of the string is limited to 25 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="headlines"></a>Headlines|Reserved for future use.|[AssetLink](assetlink.md) array|
|<a name="images"></a>Images|Because audience ads are responsive, you can create multiple image assets with different sizes and aspect ratios so they can flexibly display across a variety of publishers and placements.<br/><br/>Include one or more [AssetLink](assetlink.md) objects that each contain an [ImageAsset](imageasset.md) with [SubType](imageasset.md#subtype) and crop settings that match the desired aspect ratio. For more information see the [remarks](#remarks) below.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you include images during update, any previously set images will be replaced.|[AssetLink](assetlink.md) array|
|<a name="longheadline"></a>LongHeadline|Reserved for future use.|[AssetLink](assetlink.md)|
|<a name="longheadlinestring"></a>LongHeadlineString|This is one of two possible headlines that could appear in your audience ads.<br/><br/>Because audience ads are responsive, we require multiple headlines so they can flexibly serve across a variety of publishers and placements.<br/><br/>The length of the string is limited to 90 characters.<br/><br/>**Add:** Required<br/>**Update:** Optional. If no value is set for the update, this setting is not changed.|**string**|
|<a name="text"></a>Text|Depending on your audience ad's placement, this text will appear below or adjacent to your ad's long or short headline.<br/><br/>You have more character space to work with in the ad text than in the headline. So once the imagery and headline have a potential customer's attention, the ad text needs to convince them to click it. What sets your product or service apart?<br/><br/>The text must contain at least one word.<br/><br/>The length of the string is limited to 90 characters.<br/><br/>The text cannot contain the newline (\n) character.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|

The [ResponsiveAd](responsivead.md) object has [Inherited Elements](#inheritedelements).

## <a name="inheritedelements"></a>Inherited Elements

### <a name="inheritedelementsad"></a>Inherited Elements from Ad
The [ResponsiveAd](responsivead.md) object derives from the [Ad](ad.md) object, and inherits the following elements: [AdFormatPreference](#adformatpreference), [DevicePreference](#devicepreference), [EditorialStatus](#editorialstatus), [FinalAppUrls](#finalappurls), [FinalMobileUrls](#finalmobileurls), [FinalUrls](#finalurls), [FinalUrlSuffix](#finalurlsuffix), [ForwardCompatibilityMap](#forwardcompatibilitymap), [Id](#id), [Status](#status), [TrackingUrlTemplate](#trackingurltemplate), [Type](#type), [UrlCustomParameters](#urlcustomparameters). The descriptions below are specific to [ResponsiveAd](responsivead.md), and might not apply to other objects that inherit the same elements from the [Ad](ad.md) object.  

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adformatpreference"></a>AdFormatPreference|Not supported for this ad type.|**string**|
|<a name="devicepreference"></a>DevicePreference|Not supported for this ad type.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status of the ad, which indicates whether the ad is pending review, has been approved, or has been disapproved.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdEditorialStatus](adeditorialstatus.md)|
|<a name="finalappurls"></a>FinalAppUrls|Not supported for this ad type.|[AppUrl](appurl.md) array|
|<a name="finalmobileurls"></a>FinalMobileUrls|The mobile landing page URL.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile.<br/><br/>This URL is used only if the keyword does not specify a final mobile URL.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty list, the previous setting will be deleted.|**string** array|
|<a name="finalurls"></a>FinalUrls|The landing page URL.<br/><br/>The domain portion of the URL in combination with the path 1 and path 2 strings cannot exceed 67 characters.<br/><br/>The following validation rules apply to Final URLs and Final Mobile URLs.<br/>- The length of the URL is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- You may specify up to 10 items for both [FinalUrls](#finalurls) and [FinalMobileUrls](#finalmobileurls); however, only the first item in each list is used for delivery. The service allows up to 10 for potential forward compatibility.<br/>- Usage of '{' and '}' is only allowed to delineate tags, for example *{lpurl}*.<br/>- Final URLs must each be a well-formed URL starting with either http:// or https://.<br/>- If you specify [FinalMobileUrls](#finalmobileurls), you must also specify [FinalUrls](#finalurls).<br/>- You may not specify [FinalMobileUrls](#finalmobileurls) if the device preference is set to mobile. Also note that if this ad's *TrackingUrlTemplate* or *UrlCustomParameters* element are set, then at least one final URL is required.<br/><br/>This URL is used only if the keyword does not specify a final URL.<br/><br/>**Add:** Required<br/>**Update:** Optional|**string** array|
|<a name="finalurlsuffix"></a>FinalUrlSuffix|The final URL suffix can include tracking parameters that will be appended to the end of your landing page URL. We recommend placing tracking parameters that your landing page requires in a final URL suffix so that your customers are always sent to your landing page. For more details and validation rules see [Final URL Suffix](../guides/url-tracking-upgraded-urls.md#finalurlsuffixvalidation) in the technical guides.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br/><br/>Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for this object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="id"></a>Id|The unique Microsoft Advertising identifier of the ad.<br/><br/>**Add:** Read-only<br/>**Update:** Required and Read-Only|**long**|
|<a name="status"></a>Status|The status of the ad.<br/><br/>You can set the ad status to Active or Paused.<br/><br/>**Add:** Optional<br/>**Update:** Optional|[AdStatus](adstatus.md)|
|<a name="trackingurltemplate"></a>TrackingUrlTemplate|The tracking template to use as a default for all landing page URLs.<br/><br/>The following validation rules apply to tracking templates. For more details about supported templates and parameters, see the Microsoft Advertising help article [What tracking or URL parameters can I use?](https://help.ads.microsoft.com/#apex/3/en/56799/2)<br/>- Tracking templates defined for lower level entities e.g. ads override those set for higher level entities e.g. campaign. For more information, see [Entity Limits](../guides/entity-hierarchy-limits.md).<br/>- The length of the tracking template is limited to 2,048 characters. The HTTP or HTTPS protocol string does count towards the 2,048 character limit.<br/>- The tracking template must be a well-formed URL beginning with one of the following: *http://*, *https://*, *{lpurl}*, or *{unescapedlpurl}*.<br/>- Microsoft Advertising does not validate whether custom parameters exist. If you use custom parameters in your tracking template and they do not exist, then the landing page URL will include the key and value placeholders of your custom parameters without substitution. For example, if your tracking template is *https://tracker.example.com/?season={_season}&promocode={_promocode}&u={lpurl}* and neither *{_season}* or *{_promocode}* are defined at the campaign, ad group, criterion, keyword, or ad level, then the landing page URL will be the same.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this element to an empty string (*""*), the previous setting will be deleted.|**string**|
|<a name="type"></a>Type|The type of the ad. This value is *ResponsiveAd* when you retrieve a responsive ad. For more information about ad types, see the [Ad Data Object Remarks](ad.md#remarks).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|[AdType](adtype.md)|
|<a name="urlcustomparameters"></a>UrlCustomParameters|Your custom collection of key and value parameters for URL tracking.<br/><br/>Microsoft Advertising will accept the first 8 [CustomParameter](customparameter.md) objects that you include within the [CustomParameters](customparameters.md) object, and if you include more than 8 custom parameters an error will be returned. Each [CustomParameter](customparameter.md) includes [Key](customparameter.md#key) and [Value](customparameter.md#value) elements.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is set for the update, this setting is not changed. Set the [UrlCustomParameters](#urlcustomparameters) element to null or empty to retain any existing custom parameters. To remove all custom parameters, set the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object to null or empty. To remove a subset of custom parameters, specify the custom parameters that you want to keep in the [Parameters](customparameters.md#parameters) element of the [CustomParameters](customparameters.md) object.|[CustomParameters](customparameters.md)|

## <a name="remarks"></a>Remarks
Because audience ads are responsive, you can create multiple image assets with different sizes and aspect ratios so they can flexibly display across a variety of publishers and placements. In the [Images](#images) element include one or more [AssetLink](assetlink.md) objects that each contain an [ImageAsset](imageasset.md) with [SubType](imageasset.md#subtype) set to one of the string values in the table below.

|Sub Type|Minimum dimensions in pixels|
|--------|--------|--------|
|LandscapeImageMedia|703 width x 368 height<br/>Aspect radio 1.91:1|
|SquareImageMedia|300 width x 300 height<br/>Aspect radio 1:1|
|ImageMedia169X100|622 width x 368 height<br/>Aspect radio 1.69:1|
|ImageMedia93X100|311 width x 333 height<br/>Aspect radio 0.93:1|
|ImageMedia15X10|300 width x 200 height<br/>Aspect radio 1.5:1|
|ImageMedia155X100|300 width x 194 height<br/>Aspect radio 1.55:1|
|ImageMedia133X100|100 width x 75 height<br/>Aspect radio 1.33:1|
|ImageMedia178X100|624 width x 350 height<br/>Aspect radio 1.78:1|
|ImageMedia172X100|300 width x 174 height<br/>Aspect radio 1.72:1|

> [!NOTE]
> Media for responsive ads are provisioned via the [Image](image.md) object using the [AddMedia](addmedia.md) operation. You can use the GIF, JPEG, or PNG MIME types. Images with animation are not supported. Although you can only add media with a few aspect ratios via the [AddMedia](addmedia.md) operation, you can use [ImageAsset](imageasset.md) crop settings to determine the effective aspect ratio in the context of each responsive ad [AssetLink](assetlink.md). The aspect ratio of the stored image would be unchanged in the account level media library.
> 
> The maximum file size is 5 MB. The maximum width and height in pixels are 2592 and 2048 independently, and you must still maintain one of the supported aspect ratios. For example if the image asset with sub type LandscapeImageMedia is 2592 in width, then the height must be 1357.

You are only required to provide a landscape image asset. In the [Images](#images) element include an [AssetLink](assetlink.md) that contains one [ImageAsset](imageasset.md) with [SubType](imageasset.md#subtype) set to LandscapeImageMedia. The recommended dimensions for the LandscapeImageMedia are 1200 width x 628 height. Optionally you can include additional asset links, i.e., one image asset for each supported sub type. For any image asset sub types that you do not explicitly set, Microsoft Advertising will automatically create image asset links by cropping the LandscapeImageMedia. 

Given the [GetAdsByAdGroupId](getadsbyadgroupid.md) response example below, please take note of the following:
- The same image asset identifier (e.g., 1234567890000) is used for all auto-generated image asset sub types. Whether or not you let Microsoft Advertising automatically generate the cropped images, the [Id](imageasset.md#id) does not need to be unique among the image assets linked to the same ad. 
- Because the ad in this example was created without crop settings for the LandscapeImageMedia image asset sub type, all image assets are cropped except for the original landscape image. 
- Whether or not the landscape image has its own crop settings, Microsoft Advertising uses the true height of the landscape image for all of the default crop settings. In this example the crop height for all system-generated image assets is 628, and we can infer that the landscape image (LandscapeImageMedia sub type) with 1.91:1 aspect ratio has width and height of 1200x628. Even if the landscape image asset link had been created with crop settings e.g., 703x368, the crop settings of the auto-generated image assets are based on the full dimensions of the landscape image (again that would be 1200x628 in this example). 

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
	<s:Header>
		<h:TrackingId xmlns:h="https://bingads.microsoft.com/CampaignManagement/v12">3acf4989-d6a3-405f-9fd1-a2e8dd1b09f8</h:TrackingId>
	</s:Header>
	<s:Body>
		<GetAdsByAdGroupIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
			<Ads xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
				<Ad i:type="ResponsiveAd">
					<AdFormatPreference i:nil="true"/>
					<DevicePreference>0</DevicePreference>
					<EditorialStatus>Inactive</EditorialStatus>
					<FinalAppUrls i:nil="true"/>
					<FinalMobileUrls xmlns:a="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
						<a:string>https://mobile.contoso.com/womenshoesale</a:string>
					</FinalMobileUrls>
					<FinalUrls xmlns:a="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
						<a:string>https://www.contoso.com/womenshoesale</a:string>
					</FinalUrls>
					<ForwardCompatibilityMap xmlns:a="http://schemas.datacontract.org/2004/07/System.Collections.Generic"/>
					<Id>9876543210000</Id>
					<Status>Active</Status>
					<TrackingUrlTemplate i:nil="true"/>
					<Type>ResponsiveAd</Type>
					<UrlCustomParameters i:nil="true"/>
					<BusinessName>Contoso</BusinessName>
					<CallToAction>AddToCart</CallToAction>
					<Headline>Fast &amp; Easy Setup</Headline>
					<Images>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight i:nil="true"/>
								<CropWidth i:nil="true"/>
								<CropX i:nil="true"/>
								<CropY i:nil="true"/>
								<SubType>LandscapeImageMedia</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>628</CropWidth>
								<CropX>286</CropX>
								<CropY>0</CropY>
								<SubType>SquareImageMedia</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>1061</CropWidth>
								<CropX>70</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia169X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>584</CropWidth>
								<CropX>308</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia93X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>942</CropWidth>
								<CropX>129</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia15X10</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>973</CropWidth>
								<CropX>114</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia155X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>835</CropWidth>
								<CropX>183</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia133X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>1118</CropWidth>
								<CropX>41</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia178X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
						<AssetLink>
							<Asset i:type="ImageAsset">
								<Id>1234567890000</Id>
								<Name i:nil="true"/>
								<Type>ImageAsset</Type>
								<CropHeight>628</CropHeight>
								<CropWidth>1080</CropWidth>
								<CropX>60</CropX>
								<CropY>0</CropY>
								<SubType>ImageMedia172X100</SubType>
							</Asset>
							<AssetPerformanceLabel i:nil="true"/>
							<EditorialStatus i:nil="true"/>
							<PinnedField i:nil="true"/>
						</AssetLink>
					</Images>
					<LandscapeImageMediaId>1234567890000</LandscapeImageMediaId>
					<LandscapeLogoMediaId i:nil="true"/>
					<LongHeadline>Find New Customers &amp; Increase Sales!</LongHeadline>
					<SquareImageMediaId>1234567890000</SquareImageMediaId>
					<SquareLogoMediaId i:nil="true"/>
					<Text>Find New Customers &amp; Increase Sales! Start Advertising on Contoso Today.</Text>
				</Ad>
			</Ads>
		</GetAdsByAdGroupIdResponse>
	</s:Body>
</s:Envelope>
```

## Requirements
Service: [CampaignManagementService.svc v13](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v13/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v13  

