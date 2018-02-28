---
title: GetKeywordLocations Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the geographical locations of users who have searched for the specified keywords.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# GetKeywordLocations Service Operation - Ad Insight
Gets the geographical locations of users who have searched for the specified keywords.

## <a name="request"></a>Request Elements
The *GetKeywordLocationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="device"></a>Device|A list of one or more of the following device types: Computers, NonSmartphones, Smartphones, Tablets. The default is Computers.<br /><br />The response includes keyword locations data for only the device types that you specify, if available.|**string** array|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get geographical location information. The data is broken out by device type. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keywords are written.<br /><br />For possible values, see [Ad Languages](../guides/ad-languages.md).|**string**|
|<a name="level"></a>Level|The level at which to aggregate the geographical location data. The following are the possible values:<br /><br />0 - Country<br /><br />1 - State/Province<br /><br />2 - Metropolitan area<br /><br />3 - City<br /><br />The default value is 1 (State/Province).|**int**|
|<a name="maxlocations"></a>MaxLocations|The maximum number of locations to return. You can request a maximum of 10 locations.<br /><br />The default value is 10.|**int**|
|<a name="parentcountry"></a>ParentCountry|The country from which the search originated.<br /><br />For possible values, see [Geographical Location Codes](../guides/geographical-location-codes.md).<br /><br />The default is US.|**string**|
|<a name="publishercountry"></a>PublisherCountry|The country code of the country/region to use as the source of the location data.<br /><br />The country/region that you specify must support the language specified in the *Language* element.<br /><br />For possible values, see [Geographical Location Codes](../guides/ad-languages.md).|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordLocationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordlocationresult"></a>KeywordLocationResult|An array of [KeywordLocationResult](../ad-insight-service/keywordlocationresult.md) data objects. The order of the items corresponds directly to the keywords specified in the request. If there is no location data available for a keyword, the keyword will be included in the list, but the *KeywordLocations* element of the corresponding [KeywordLocationResult](../ad-insight-service/keywordlocationresult.md) object will be null.<br /><br />Each [KeywordLocationResult](../ad-insight-service/keywordlocationresult.md) data object contains an array of [KeywordLocation](../ad-insight-service/keywordlocation.md).  The array contains an item for each device specified in the request. Each [KeywordLocation](../ad-insight-service/keywordlocation.md) contains the geographical location and percentage of time that users in the geographical location searched for the specified keyword.|[KeywordLocationResult](keywordlocationresult.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetKeywordLocations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordLocationsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountry i:nil="false">ValueHere</PublisherCountry>
      <Device i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Device>
      <Level i:nil="false">ValueHere</Level>
      <ParentCountry i:nil="false">ValueHere</ParentCountry>
      <MaxLocations i:nil="false">ValueHere</MaxLocations>
    </GetKeywordLocationsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordLocationsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordLocationResult xmlns:e395="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e395:KeywordLocationResult>
          <e395:Keyword d4p1:nil="false">ValueHere</e395:Keyword>
          <e395:KeywordLocations d4p1:nil="false">
            <e395:KeywordLocation>
              <e395:Device d4p1:nil="false">ValueHere</e395:Device>
              <e395:Location d4p1:nil="false">ValueHere</e395:Location>
              <e395:Percentage>ValueHere</e395:Percentage>
            </e395:KeywordLocation>
          </e395:KeywordLocations>
        </e395:KeywordLocationResult>
      </KeywordLocationResult>
    </GetKeywordLocationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordLocationsResponse> GetKeywordLocationsAsync(
	IList<string> keywords,
	string language,
	string publisherCountry,
	IList<string> device,
	int? level,
	string parentCountry,
	int? maxLocations)
{
	var request = new GetKeywordLocationsRequest
	{
		Keywords = keywords,
		Language = language,
		PublisherCountry = publisherCountry,
		Device = device,
		Level = level,
		ParentCountry = parentCountry,
		MaxLocations = maxLocations
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordLocationsAsync(r), request));
}
```
```java
static GetKeywordLocationsResponse getKeywordLocations(
	ArrayOfstring keywords,
	java.lang.String language,
	java.lang.String publisherCountry,
	ArrayOfstring device,
	int level,
	java.lang.String parentCountry,
	int maxLocations) throws RemoteException, Exception
{
	GetKeywordLocationsRequest request = new GetKeywordLocationsRequest();

	request.setKeywords(keywords);
	request.setLanguage(language);
	request.setPublisherCountry(publisherCountry);
	request.setDevice(device);
	request.setLevel(level);
	request.setParentCountry(parentCountry);
	request.setMaxLocations(maxLocations);

	return AdInsightService.getService().getKeywordLocations(request);
}
```
```php
static function GetKeywordLocations(
	$keywords,
	$language,
	$publisherCountry,
	$device,
	$level,
	$parentCountry,
	$maxLocations)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordLocationsRequest();

	$request->Keywords = $keywords;
	$request->Language = $language;
	$request->PublisherCountry = $publisherCountry;
	$request->Device = $device;
	$request->Level = $level;
	$request->ParentCountry = $parentCountry;
	$request->MaxLocations = $maxLocations;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordLocations($request);
}
```
```python
response=adinsight_service.GetKeywordLocations(
	Keywords=Keywords,
	Language=Language,
	PublisherCountry=PublisherCountry,
	Device=Device,
	Level=Level,
	ParentCountry=ParentCountry,
	MaxLocations=MaxLocations)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

