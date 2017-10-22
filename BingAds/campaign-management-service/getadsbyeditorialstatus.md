---
title: GetAdsByEditorialStatus Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the ads that belong to the specified ad group and have the specified editorial review status.
---
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
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
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
    <GetAdsByEditorialStatusRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
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
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetAdsByEditorialStatusResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Ads d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Ad d4p1:type="-- derived type specified here with the appropriate prefix --">
          <AdFormatPreference d4p1:nil="false">ValueHere</AdFormatPreference>
          <DevicePreference d4p1:nil="false">ValueHere</DevicePreference>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls xmlns:e211="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e211:AppUrl>
              <e211:OsType d4p1:nil="false">ValueHere</e211:OsType>
              <e211:Url d4p1:nil="false">ValueHere</e211:Url>
            </e211:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ForwardCompatibilityMap xmlns:e212="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e212:KeyValuePairOfstringstring>
              <e212:key d4p1:nil="false">ValueHere</e212:key>
              <e212:value d4p1:nil="false">ValueHere</e212:value>
            </e212:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <Status d4p1:nil="false">ValueHere</Status>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <Type d4p1:nil="false">ValueHere</Type>
          <UrlCustomParameters xmlns:e213="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" d4p1:nil="false">
            <e213:Parameters d4p1:nil="false">
              <e213:CustomParameter>
                <e213:Key d4p1:nil="false">ValueHere</e213:Key>
                <e213:Value d4p1:nil="false">ValueHere</e213:Value>
              </e213:CustomParameter>
            </e213:Parameters>
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
        </Ad>
      </Ads>
    </GetAdsByEditorialStatusResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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
response=campaignmanagement.GetAdsByEditorialStatus(
	AdGroupId=AdGroupId,
	EditorialStatus=EditorialStatus,
	AdTypes=AdTypes)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

