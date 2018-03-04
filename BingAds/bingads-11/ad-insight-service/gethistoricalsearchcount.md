---
title: GetHistoricalSearchCount Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the number of times the normalized term was used in a search during the specified time period.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetHistoricalSearchCount Service Operation - Ad Insight
Gets the number of times the normalized term was used in a search during the specified time period. The results are aggregated by device type.

## <a name="request"></a>Request Elements
The *GetHistoricalSearchCountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="devices"></a>Devices|A list of one or more of the following device types: Computers, NonSmartphones, Smartphones, Tablets. The default is Computers.<br /><br />The response includes search counts for the device types that you specify only, if available.|**string** array|
|<a name="enddate"></a>EndDate|The end date of the date range that identifies the data that you want to use to determine the historical search count.<br /><br />The date cannot be later than today's date, and must be later than or the same as the specified start date.<br /><br />The effective *EndDate* may be adjusted if the specified *TimePeriodRollup* is Weekly or Monthly.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to determine the number of times that the keyword was used in a search query. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keywords are written.<br /><br />The countries/regions that you specify in the *PublisherCountries* element must support the specified language.<br /><br />For possible values, see [Ad Languages](../guides/ad-languages.md).|**string**|
|<a name="publishercountries"></a>PublisherCountries|The country codes of the countries/regions to use as the source of the historical data.<br /><br />You can specify one or more country codes. Each country/region that you specify must support the language specified in the *Language* element.<br /><br />For possible values, see [Geographical Location Codes](../guides/geographical-location-codes.md).<br /><br />If Null, the default is all countries/regions that support the specified language.|**string** array|
|<a name="startdate"></a>StartDate|The start date of the date range that identifies the data that you want to use to determine the historical search count.<br /><br />This date must be earlier than or the same as the specified end date. The date should be later than the maximum available historical data range corresponding to the specified *TimePeriodRollup* element.<br /><br />The effective *StartDate* may be adjusted if the specified *TimePeriodRollup* is Weekly or Monthly.|[DayMonthAndYear](daymonthandyear.md)|
|<a name="timeperiodrollup"></a>TimePeriodRollup|You may specify whether to return data aggregated daily, weekly, or monthly.<br /><br />For a list of supported values, see [Historical Data By Time Period](#timeperiodrollup).|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetHistoricalSearchCountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywordsearchcounts"></a>KeywordSearchCounts|An array of [KeywordSearchCount](keywordsearchcount.md) data objects. The array contains an item for each keyword specified in the request. If the keyword is not valid, the corresponding item in the array will be null.<br /><br />Each [KeywordSearchCount](keywordsearchcount.md) contains an array of [SearchCountsByAttributes](searchcountsbyattributes.md).  The array contains an item for each unique device specified in the request.|[KeywordSearchCount](keywordsearchcount.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
    <Action mustUnderstand="1">GetHistoricalSearchCount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetHistoricalSearchCountRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountries i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </PublisherCountries>
      <StartDate xmlns:e379="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e379:Day>ValueHere</e379:Day>
        <e379:Month>ValueHere</e379:Month>
        <e379:Year>ValueHere</e379:Year>
      </StartDate>
      <EndDate xmlns:e380="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" i:nil="false">
        <e380:Day>ValueHere</e380:Day>
        <e380:Month>ValueHere</e380:Month>
        <e380:Year>ValueHere</e380:Year>
      </EndDate>
      <TimePeriodRollup i:nil="false">ValueHere</TimePeriodRollup>
      <Devices i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Devices>
    </GetHistoricalSearchCountRequest>
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
    <GetHistoricalSearchCountResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V11">
      <KeywordSearchCounts xmlns:e381="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V11.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e381:KeywordSearchCount>
          <e381:Keyword d4p1:nil="false">ValueHere</e381:Keyword>
          <e381:SearchCountsByAttributes d4p1:nil="false">
            <e381:SearchCountsByAttributes>
              <e381:Device d4p1:nil="false">ValueHere</e381:Device>
              <e381:HistoricalSearchCounts d4p1:nil="false">
                <e381:HistoricalSearchCountPeriodic>
                  <e381:SearchCount>ValueHere</e381:SearchCount>
                  <e381:DayMonthAndYear d4p1:nil="false">
                    <e381:Day>ValueHere</e381:Day>
                    <e381:Month>ValueHere</e381:Month>
                    <e381:Year>ValueHere</e381:Year>
                  </e381:DayMonthAndYear>
                </e381:HistoricalSearchCountPeriodic>
              </e381:HistoricalSearchCounts>
            </e381:SearchCountsByAttributes>
          </e381:SearchCountsByAttributes>
        </e381:KeywordSearchCount>
      </KeywordSearchCounts>
    </GetHistoricalSearchCountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetHistoricalSearchCountResponse> GetHistoricalSearchCountAsync(
	IList<string> keywords,
	string language,
	IList<string> publisherCountries,
	DayMonthAndYear startDate,
	DayMonthAndYear endDate,
	string timePeriodRollup,
	IList<string> devices)
{
	var request = new GetHistoricalSearchCountRequest
	{
		Keywords = keywords,
		Language = language,
		PublisherCountries = publisherCountries,
		StartDate = startDate,
		EndDate = endDate,
		TimePeriodRollup = timePeriodRollup,
		Devices = devices
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetHistoricalSearchCountAsync(r), request));
}
```
```java
static GetHistoricalSearchCountResponse getHistoricalSearchCount(
	ArrayOfstring keywords,
	java.lang.String language,
	ArrayOfstring publisherCountries,
	DayMonthAndYear startDate,
	DayMonthAndYear endDate,
	java.lang.String timePeriodRollup,
	ArrayOfstring devices) throws RemoteException, Exception
{
	GetHistoricalSearchCountRequest request = new GetHistoricalSearchCountRequest();

	request.setKeywords(keywords);
	request.setLanguage(language);
	request.setPublisherCountries(publisherCountries);
	request.setStartDate(startDate);
	request.setEndDate(endDate);
	request.setTimePeriodRollup(timePeriodRollup);
	request.setDevices(devices);

	return AdInsightService.getService().getHistoricalSearchCount(request);
}
```
```php
static function GetHistoricalSearchCount(
	$keywords,
	$language,
	$publisherCountries,
	$startDate,
	$endDate,
	$timePeriodRollup,
	$devices)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetHistoricalSearchCountRequest();

	$request->Keywords = $keywords;
	$request->Language = $language;
	$request->PublisherCountries = $publisherCountries;
	$request->StartDate = $startDate;
	$request->EndDate = $endDate;
	$request->TimePeriodRollup = $timePeriodRollup;
	$request->Devices = $devices;

	return $GLOBALS['AdInsightProxy']->GetService()->GetHistoricalSearchCount($request);
}
```
```python
response=adinsight_service.GetHistoricalSearchCount(
	Keywords=Keywords,
	Language=Language,
	PublisherCountries=PublisherCountries,
	StartDate=StartDate,
	EndDate=EndDate,
	TimePeriodRollup=TimePeriodRollup,
	Devices=Devices)
```

## Requirements
Service: [AdInsightService.svc v11](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v11/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V11  

