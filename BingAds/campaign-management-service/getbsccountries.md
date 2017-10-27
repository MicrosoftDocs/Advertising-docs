---
title: GetBSCCountries Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Gets the list of supported sales country codes for Bing Shopping campaigns.
---
# GetBSCCountries Service Operation - Campaign Management
Gets the list of supported sales country codes for Bing Shopping campaigns.

## <a name="request"></a>Request Elements
The *GetBSCCountriesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements
There are not any elements in the operation's request body.

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBSCCountriesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="countrycodes"></a>CountryCodes|The list of supported sales country codes for Bing Shopping campaigns. You can pass any one of the returned values in the *SalesCountryCode* element of a [ShoppingSetting](../campaign-management-service/shoppingsetting.md) object.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetBSCCountries</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBSCCountriesRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11" />
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
    <GetBSCCountriesResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <CountryCodes d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:string>ValueHere</a1:string>
      </CountryCodes>
    </GetBSCCountriesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetBSCCountriesResponse> GetBSCCountriesAsync()
{
	var request = new GetBSCCountriesRequest
	{
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetBSCCountriesAsync(r), request));
}
```
```java
static GetBSCCountriesResponse getBSCCountries() throws RemoteException, Exception
{
	GetBSCCountriesRequest request = new GetBSCCountriesRequest();


	return CampaignManagementService.getService().getBSCCountries(request);
}
```
```php
static function GetBSCCountries()
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetBSCCountriesRequest();


	return $GLOBALS['CampaignManagementProxy']->GetService()->GetBSCCountries($request);
}
```
```python
response=campaignmanagement_service.GetBSCCountries()
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

