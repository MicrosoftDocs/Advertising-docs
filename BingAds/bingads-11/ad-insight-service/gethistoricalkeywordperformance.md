---
title: GetHistoricalKeywordPerformance Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the historical performance of the normalized search term.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetHistoricalKeywordPerformance Service Operation - Ad Insight
Gets the historical performance of the normalized search term. The results are aggregated by device type.

## <a name="request"></a>Request Elements
The *GetHistoricalKeywordPerformanceRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devices"></a>Devices|A list of one or more of the following device types: Computers, NonSmartphones, Smartphones, Tablets. The default is Computers.<br /><br />The response includes keyword performance data for the device types that you specify only, if available.<br />Used to determine a keyword's performance on the specified device types.|**string** array|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get historical performance statistics. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keywords are written.<br /><br />The countries/regions that you specify in the [PublisherCountries](#publishercountries) element must support the specified language.<br /><br />Possible values include Danish, Dutch, English, Finnish, French, German, Italian, Norwegian, Portuguese, Spanish, Swedish, and TraditionalChinese.|**string**|
|<a name="matchtypes"></a>MatchTypes|The match types for which you want to get historical data.<br /><br />You may not specify the Content match type.|[MatchType](matchtype.md) array|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries/regions to use as the source of the historical data.<br /><br />You can specify one or more country codes. Each country/region that you specify must support the language specified in the [Language](#language) element.<br/><br/>The following language and country/region combinations are supported:<br/>Danish: DK<br/>Dutch: NL<br/>English: AU, CA, GB, ID, IN, MY, PH, SG, TH, US, VN<br/>Finnish: FI<br/>French: CA, FR<br/>German: AT, CH, DE<br/>Italian: IT<br/>Norwegian: NO<br/>Portuguese: BR<br/>Spanish: AR, CL, CO, ES, MX, PE, VE<br/>Swedish: SE<br/>TraditionalChinese: HK, TW<br/><br/>If this element is null, then by default the service includes all countries/regions that support the specified language.|**string** array|
|<a name="targetadposition"></a>TargetAdPosition|The position of the search results for which you want to get performance data.<br /><br />For example, to get performance data when ads appeared in the first position of the mainline by using the keyword and match type, set this element to MainLine1. To get performance data when ads appeared in any position of the search results by using the keyword and match type, set this element to All.<br /><br />The default value is *All*.<br /><br /> If you specify *All* for this element, the service will return multiple results per keyword for each supported ad position. If you specify Aggregate, the service will return one aggregated result.<br/><br/>Sidebar ads no longer serve on Bing owned and operated sites in the United States. If you only request first page data e.g., FirstPage1 for the United States (US), then the [KeywordKPIs](keywordhistoricalperformance.md#keywordkpis) element in the result will be nil/empty. If you include additional countries/regions e.g., US and CA in the same request, then any first page results are only attributed to countries/regions outside the United States.|[AdPosition](adposition.md)|
|<a name="timeinterval"></a>TimeInterval|The time period that identifies the data to use to determine the key performance index of the specified keywords. For example, use data from the previous seven days or previous 30 days to determine the keyword performance.<br /><br />The default value is *Last7Days*.|[TimeInterval](timeinterval.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetHistoricalKeywordPerformanceResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordhistoricalperformances"></a>KeywordHistoricalPerformances|An array of [KeywordHistoricalPerformance](keywordhistoricalperformance.md) data objects. The array contains an item for each keyword, device, match type, and ad position specified in the request. If the keyword is not valid or has no data available, the corresponding item in the array will be null.|[KeywordHistoricalPerformance](keywordhistoricalperformance.md) array|

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
      <KeywordHistoricalPerformances xmlns:e378="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e378:KeywordHistoricalPerformance>
          <e378:Keyword d4p1:nil="false">ValueHere</e378:Keyword>
          <e378:KeywordKPIs d4p1:nil="false">
            <e378:KeywordKPI>
              <e378:Device d4p1:nil="false">ValueHere</e378:Device>
              <e378:MatchType>ValueHere</e378:MatchType>
              <e378:AdPosition>ValueHere</e378:AdPosition>
              <e378:Clicks>ValueHere</e378:Clicks>
              <e378:Impressions>ValueHere</e378:Impressions>
              <e378:AverageCPC>ValueHere</e378:AverageCPC>
              <e378:CTR>ValueHere</e378:CTR>
              <e378:TotalCost>ValueHere</e378:TotalCost>
              <e378:AverageBid>ValueHere</e378:AverageBid>
            </e378:KeywordKPI>
          </e378:KeywordKPIs>
        </e378:KeywordHistoricalPerformance>
      </KeywordHistoricalPerformances>
    </GetHistoricalKeywordPerformanceResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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

	return (await AdInsightService.CallAsync((s, r) => s.GetHistoricalKeywordPerformanceAsync(r), request));
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

	return AdInsightService.getService().getHistoricalKeywordPerformance(request);
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
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetHistoricalKeywordPerformanceRequest();

	$request->Keywords = $keywords;
	$request->TimeInterval = $timeInterval;
	$request->TargetAdPosition = $targetAdPosition;
	$request->MatchTypes = $matchTypes;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->Devices = $devices;

	return $GLOBALS['AdInsightProxy']->GetService()->GetHistoricalKeywordPerformance($request);
}
```
```python
response=adinsight_service.GetHistoricalKeywordPerformance(
	Keywords=Keywords,
	TimeInterval=TimeInterval,
	TargetAdPosition=TargetAdPosition,
	MatchTypes=MatchTypes,
	Language=Language,
	PublisherCountries=PublisherCountries,
	Devices=Devices)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

