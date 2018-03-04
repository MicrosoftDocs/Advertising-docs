---
title: GetAdsByAdGroupId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the ads within an ad group.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAdsByAdGroupId Service Operation - Campaign Management
Retrieves the ads within an ad group.

## <a name="request"></a>Request Elements
The *GetAdsByAdGroupIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to retrieve the ads from.|**long**|
|<a name="adtypes"></a>AdTypes|One or more ad types to retrieve.|[AdType](adtype.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdsByAdGroupIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ads"></a>Ads|The list of ads that have been retrieved. If the ad group doesn't contain ads, this array is empty.|[Ad](ad.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetAdsByAdGroupId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdsByAdGroupIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroupId>ValueHere</AdGroupId>
      <AdTypes i:nil="false">
        <AdType>ValueHere</AdType>
      </AdTypes>
    </GetAdsByAdGroupIdRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdsByAdGroupIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Ads d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Ad d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdFormatPreference d4p1:nil="false">ValueHere</AdFormatPreference>
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls xmlns:e208="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e208:AppUrl>
              <e208:OsType d4p1:nil="false">ValueHere</e208:OsType>
              <e208:Url d4p1:nil="false">ValueHere</e208:Url>
            </e208:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ForwardCompatibilityMap xmlns:e209="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e209:KeyValuePairOfstringstring>
              <e209:key d4p1:nil="false">ValueHere</e209:key>
              <e209:value d4p1:nil="false">ValueHere</e209:value>
            </e209:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <Type d4p1:nil="false">ValueHere</Type>
          <UrlCustomParameters xmlns:e210="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e210:Parameters d4p1:nil="false">
              <e210:CustomParameter>
                <e210:Key d4p1:nil="false">ValueHere</e210:Key>
                <e210:Value d4p1:nil="false">ValueHere</e210:Value>
              </e210:CustomParameter>
            </e210:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to TextAd-->
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <DisplayUrl d4p1:nil="false">ValueHere</DisplayUrl>
          <Text d4p1:nil="false">ValueHere</Text>
          <Title d4p1:nil="false">ValueHere</Title>
          <!--This field is applicable if the derived type attribute is set to ProductAd-->
          <PromotionalText d4p1:nil="false">ValueHere</PromotionalText>
          <!--These fields are applicable if the derived type attribute is set to AppInstallAd-->
          <AppPlatform d4p1:nil="false">ValueHere</AppPlatform>
          <AppStoreId d4p1:nil="false">ValueHere</AppStoreId>
          <Text d4p1:nil="false">ValueHere</Text>
          <Title d4p1:nil="false">ValueHere</Title>
          <!--These fields are applicable if the derived type attribute is set to ExpandedTextAd-->
          <DisplayUrl d4p1:nil="false">ValueHere</DisplayUrl>
          <Path1 d4p1:nil="false">ValueHere</Path1>
          <Path2 d4p1:nil="false">ValueHere</Path2>
          <Text d4p1:nil="false">ValueHere</Text>
          <TitlePart1 d4p1:nil="false">ValueHere</TitlePart1>
          <TitlePart2 d4p1:nil="false">ValueHere</TitlePart2>
          <!--These fields are applicable if the derived type attribute is set to DynamicSearchAd-->
          <Path1 d4p1:nil="false">ValueHere</Path1>
          <Path2 d4p1:nil="false">ValueHere</Path2>
          <Text d4p1:nil="false">ValueHere</Text>
          <!--These fields are applicable if the derived type attribute is set to ResponsiveAd-->
          <BusinessName d4p1:nil="false">ValueHere</BusinessName>
          <CallToAction d4p1:nil="false">ValueHere</CallToAction>
          <Headline d4p1:nil="false">ValueHere</Headline>
          <LandscapeImageMediaId d4p1:nil="false">ValueHere</LandscapeImageMediaId>
          <LandscapeLogoMediaId d4p1:nil="false">ValueHere</LandscapeLogoMediaId>
          <LongHeadline d4p1:nil="false">ValueHere</LongHeadline>
          <SquareImageMediaId d4p1:nil="false">ValueHere</SquareImageMediaId>
          <SquareLogoMediaId d4p1:nil="false">ValueHere</SquareLogoMediaId>
          <Text d4p1:nil="false">ValueHere</Text>
        </Ad>
      </Ads>
    </GetAdsByAdGroupIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdsByAdGroupIdResponse> GetAdsByAdGroupIdAsync(
	long adGroupId,
	IList<AdType> adTypes)
{
	var request = new GetAdsByAdGroupIdRequest
	{
		AdGroupId = adGroupId,
		AdTypes = adTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdsByAdGroupIdAsync(r), request));
}
```
```java
static GetAdsByAdGroupIdResponse getAdsByAdGroupId(
	java.lang.Long adGroupId,
	ArrayOfAdType adTypes) throws RemoteException, Exception
{
	GetAdsByAdGroupIdRequest request = new GetAdsByAdGroupIdRequest();

	request.setAdGroupId(adGroupId);
	request.setAdTypes(adTypes);

	return CampaignManagementService.getService().getAdsByAdGroupId(request);
}
```
```php
static function GetAdsByAdGroupId(
	$adGroupId,
	$adTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdsByAdGroupIdRequest();

	$request->AdGroupId = $adGroupId;
	$request->AdTypes = $adTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdsByAdGroupId($request);
}
```
```python
response=campaignmanagement_service.GetAdsByAdGroupId(
	AdGroupId=AdGroupId,
	AdTypes=AdTypes)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

