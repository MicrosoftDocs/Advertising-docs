---
title: GetAdsByEditorialStatus Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the ads that belong to the specified ad group and have the specified editorial review status.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdsByEditorialStatus Service Operation - Campaign Management
Retrieves the ads that belong to the specified ad group and have the specified editorial review status.

## <a name="request"></a>Request Elements
The *GetAdsByEditorialStatusRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to retrieve the ads from.|**long**|
|<a name="adtypes"></a>AdTypes|One or more types of ads to return.|[AdType](adtype.md) array|
|<a name="editorialstatus"></a>EditorialStatus|The editorial review status that the ads must have to be returned.|[AdEditorialStatus](adeditorialstatus.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdsByEditorialStatusResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ads"></a>Ads|The list of ads that have been retrieved. If the ad group doesn't contain ads that meet the criteria, this array is empty.|[Ad](ad.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdsByEditorialStatus</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdsByEditorialStatusRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupId>ValueHere</AdGroupId>
      <EditorialStatus>ValueHere</EditorialStatus>
      <AdTypes i:nil="false">
        <AdType>ValueHere</AdType>
      </AdTypes>
    </GetAdsByEditorialStatusRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdsByEditorialStatusResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Ads d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Ad d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdFormatPreference d4p1:nil="false">ValueHere</AdFormatPreference>
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls d4p1:nil="false">
            <AppUrl>
              <OsType d4p1:nil="false">ValueHere</OsType>
              <Url d4p1:nil="false">ValueHere</Url>
            </AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ForwardCompatibilityMap xmlns:e1112="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1112:KeyValuePairOfstringstring>
              <e1112:key d4p1:nil="false">ValueHere</e1112:key>
              <e1112:value d4p1:nil="false">ValueHere</e1112:value>
            </e1112:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <Type d4p1:nil="false">ValueHere</Type>
          <UrlCustomParameters d4p1:nil="false">
            <Parameters d4p1:nil="false">
              <CustomParameter>
                <Key d4p1:nil="false">ValueHere</Key>
                <Value d4p1:nil="false">ValueHere</Value>
              </CustomParameter>
            </Parameters>
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
          <Domain d4p1:nil="false">ValueHere</Domain>
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
    </GetAdsByEditorialStatusResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdsByEditorialStatusResponse> GetAdsByEditorialStatusAsync(
	long adGroupId,
	AdEditorialStatus editorialStatus,
	IList<AdType> adTypes)
{
	var request = new GetAdsByEditorialStatusRequest
	{
		AdGroupId = adGroupId,
		EditorialStatus = editorialStatus,
		AdTypes = adTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdsByEditorialStatusAsync(r), request));
}
```
```java
static GetAdsByEditorialStatusResponse getAdsByEditorialStatus(
	java.lang.Long adGroupId,
	AdEditorialStatus editorialStatus,
	ArrayOfAdType adTypes) throws RemoteException, Exception
{
	GetAdsByEditorialStatusRequest request = new GetAdsByEditorialStatusRequest();

	request.setAdGroupId(adGroupId);
	request.setEditorialStatus(editorialStatus);
	request.setAdTypes(adTypes);

	return CampaignManagementService.getService().getAdsByEditorialStatus(request);
}
```
```php
static function GetAdsByEditorialStatus(
	$adGroupId,
	$editorialStatus,
	$adTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdsByEditorialStatusRequest();

	$request->AdGroupId = $adGroupId;
	$request->EditorialStatus = $editorialStatus;
	$request->AdTypes = $adTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdsByEditorialStatus($request);
}
```
```python
response=campaignmanagement_service.GetAdsByEditorialStatus(
	AdGroupId=AdGroupId,
	EditorialStatus=EditorialStatus,
	AdTypes=AdTypes)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

