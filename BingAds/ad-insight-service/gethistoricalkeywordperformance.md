---
title: GetHistoricalKeywordPerformance Service Operation
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the historical performance of the normalized search term.
---
# GetHistoricalKeywordPerformance Service Operation
Gets the historical performance of the normalized search term. The results are aggregated by device type.

## <a name="request"></a>Request Elements
The *GetHistoricalKeywordPerformanceRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get historical performance statistics. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string**|
|<a name="timeinterval"></a>TimeInterval|The time period that identifies the data to use to determine the key performance index of the specified keywords. For example, use data from the previous seven days or previous 30 days to determine the keyword performance.<br /><br />The default value is *Last7Days*.|[TimeInterval](timeinterval.md)|
|<a name="targetadposition"></a>TargetAdPosition|The position of the search results for which you want to get performance data.<br /><br />For example, to get performance data when ads appeared in the first position of the mainline by using the keyword and match type, set this element to MainLine1. To get performance data when ads appeared in any position of the search results by using the keyword and match type, set this element to All.<br /><br />The default value is *All*.<br /><br />**Note:** If you specify *All* for this element, the service will return multiple results per keyword for  each supported ad position. If you specify Aggregate, the service will return one aggregated result.|[AdPosition](adposition.md)|
|<a name="matchtypes"></a>MatchTypes|The match types for which you want to get historical data.<br /><br />You may not specify the Content match type.|[MatchType](matchtype.md) array|
|<a name="language"></a>Language|The language in which the keywords are written.<br /><br />The countries/regions that you specify in the *PublisherCountries* element must support the specified language.<br /><br />For possible values, see [Ad Languages](~/guides/ad-languages.md).|**string**|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries/regions to use as the source of the historical data.<br /><br />You can specify one or more country codes. Each country/region that you specify must support the language specified in the *Language* element.<br /><br />For possible values, see [Geographical Location Codes](~/guides/geographical-location-codes.md).<br /><br />If Null, the default is all countries/regions that support the specified language.|**string**|
|<a name="devices"></a>Devices|A list of one or more of the following device types: Computers, NonSmartphones, Smartphones, Tablets. The default is Computers.<br /><br />The response includes keyword performance data for the device types that you specify only, if available.<br />Used to determine a keyword?s performance on the specified device types.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetHistoricalKeywordPerformanceResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordhistoricalperformances"></a>KeywordHistoricalPerformances|An array of [KeywordHistoricalPerformance](../ad-insight-service/keywordhistoricalperformance.md) data objects. The array contains an item for each keyword, device, match type, and ad position specified in the request. If the keyword is not valid or has no data available, the corresponding item in the array will be null.|[KeywordHistoricalPerformance](keywordhistoricalperformance.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetHistoricalKeywordPerformance</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetHistoricalKeywordPerformanceRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <TimeInterval i:nil="false">ValueHere</TimeInterval>
      <TargetAdPosition i:nil="false">ValueHere</TargetAdPosition>
      <MatchTypes i:nil="false">
        <MatchType>ValueHere</MatchType>
      </MatchTypes>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </PublisherCountries>
      <Devices i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Devices>
    </GetHistoricalKeywordPerformanceRequest>
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
    <GetHistoricalKeywordPerformanceResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordHistoricalPerformances xmlns:e15="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e15:KeywordHistoricalPerformance>
          <e15:Keyword d4p1:nil="false">ValueHere</e15:Keyword>
          <e15:KeywordKPIs d4p1:nil="false">
            <e15:KeywordKPI>
              <e15:Device d4p1:nil="false">ValueHere</e15:Device>
              <e15:MatchType>ValueHere</e15:MatchType>
              <e15:AdPosition>ValueHere</e15:AdPosition>
              <e15:Clicks>ValueHere</e15:Clicks>
              <e15:Impressions>ValueHere</e15:Impressions>
              <e15:AverageCPC>ValueHere</e15:AverageCPC>
              <e15:CTR>ValueHere</e15:CTR>
              <e15:TotalCost>ValueHere</e15:TotalCost>
              <e15:AverageBid>ValueHere</e15:AverageBid>
            </e15:KeywordKPI>
          </e15:KeywordKPIs>
        </e15:KeywordHistoricalPerformance>
      </KeywordHistoricalPerformances>
    </GetHistoricalKeywordPerformanceResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetHistoricalKeywordPerformanceResponse> GetHistoricalKeywordPerformanceAsync(
	IList<string> keywords,
	TimeInterval? timeInterval,
	AdPosition? targetAdPosition,
	IList<MatchType> matchTypes,
	string language,
	IList<string> publisherCountries,
	IList<string> devices)
{
	var request = new GetHistoricalKeywordPerformanceRequest
	{
		Keywords = keywords,
		TimeInterval = timeInterval,
		TargetAdPosition = targetAdPosition,
		MatchTypes = matchTypes,
		Language = language,
		PublisherCountries = publisherCountries,
		Devices = devices
	};

	return (await AdInsight.CallAsync((s, r) => s.GetHistoricalKeywordPerformanceAsync(r), request));
}
```
```java
static GetHistoricalKeywordPerformanceResponse getHistoricalKeywordPerformance(
	ArrayOfstring keywords,
	TimeInterval timeInterval,
	AdPosition targetAdPosition,
	ArrayOfMatchType matchTypes,
	java.lang.String language,
	ArrayOfstring publisherCountries,
	ArrayOfstring devices) throws RemoteException, Exception
{
	GetHistoricalKeywordPerformanceRequest request = new GetHistoricalKeywordPerformanceRequest();

	request.setKeywords(keywords);
	request.setTimeInterval(timeInterval);
	request.setTargetAdPosition(targetAdPosition);
	request.setMatchTypes(matchTypes);
	request.setLanguage(language);
	request.setPublisherCountries(publisherCountries);
	request.setDevices(devices);

	return AdInsight.getService().getHistoricalKeywordPerformance(request);
}
```
```php
static function GetHistoricalKeywordPerformance(
	$keywords,
	$timeInterval,
	$targetAdPosition,
	$matchTypes,
	$language,
	$publisherCountries,
	$devices)

	$getHistoricalKeywordPerformanceRequest = new GetHistoricalKeywordPerformanceRequest();

	$request->Keywords = $keywords;
	$request->TimeInterval = $timeInterval;
	$request->TargetAdPosition = $targetAdPosition;
	$request->MatchTypes = $matchTypes;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->Devices = $devices;

	return $AdInsightProxy->GetService()->GetHistoricalKeywordPerformance($request);
}
```
```python
response=adinsight.GetHistoricalKeywordPerformance(
	Keywords=KeywordsHere,
	TimeInterval=TimeIntervalHere,
	TargetAdPosition=TargetAdPositionHere,
	MatchTypes=MatchTypesHere,
	Language=LanguageHere,
	PublisherCountries=PublisherCountriesHere,
	Devices=DevicesHere
)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

