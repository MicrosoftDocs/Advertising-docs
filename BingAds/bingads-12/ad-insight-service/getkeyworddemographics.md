---
title: GetKeywordDemographics Service Operation - Ad Insight
ms.service: bing-ads-ad-insight-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the age and gender of users who have searched for the specified keywords.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetKeywordDemographics Service Operation - Ad Insight
Gets the age and gender of users who have searched for the specified keywords.

## <a name="request"></a>Request Elements
The *GetKeywordDemographicsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="device"></a>Device|A list of one or more of the following device types: Computers, NonSmartphones, Smartphones, Tablets. The default is Computers.<br /><br />The response includes keyword demographics data for the device types that you specify only, if available.|**string** array|
|<a name="keywords"></a>Keywords|An array of keywords for which you want to get demographics data. The data is broken out by device type. The array can contain a maximum of 1,000 keywords, and each keyword can contain a maximum of 100 characters.|**string** array|
|<a name="language"></a>Language|The language in which the keywords are written.<br /><br />For possible values, see [Ad Languages](../guides/ad-languages.md).|**string**|
|<a name="publishercountry"></a>PublisherCountry|The country code of the country/region to use as the source of the demographics data.<br /><br />The country/region that you specify must support the language specified in the *Language* element.<br /><br />For possible values, see [Geographical Location Codes](../guides/ad-languages.md).|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordDemographicsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keyworddemographicresult"></a>KeywordDemographicResult|An array of [KeywordDemographicResult](keyworddemographicresult.md) data objects. The order of the items corresponds directly to the keywords specified in the request. If there is no demographic data available for a keyword, the keyword will be included in the list, but the *KeywordDemographics* element of the corresponding [KeywordDemographicResult](keyworddemographicresult.md) will be null.<br /><br />Each [KeywordDemographicResult](keyworddemographicresult.md)  contains an array of [KeywordDemographic](keyworddemographic.md) data objects.  The array contains an item for each device specified in the request. Each [KeywordDemographic](keyworddemographic.md) contains the percentage of time that users of a certain age and gender searched for the specified keyword.|[KeywordDemographicResult](keyworddemographicresult.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <Action mustUnderstand="1">GetKeywordDemographics</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordDemographicsRequest xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <Keywords i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Keywords>
      <Language i:nil="false">ValueHere</Language>
      <PublisherCountry i:nil="false">ValueHere</PublisherCountry>
      <Device i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:string>ValueHere</a1:string>
      </Device>
    </GetKeywordDemographicsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetKeywordDemographicsResponse xmlns="Microsoft.Advertiser.AdInsight.Api.Service.V12">
      <KeywordDemographicResult xmlns:e1659="http://schemas.datacontract.org/2004/07/Microsoft.BingAds.Advertiser.AdInsight.Api.DataContract.V12.Entity" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1659:KeywordDemographicResult>
          <e1659:Keyword d4p1:nil="false">ValueHere</e1659:Keyword>
          <e1659:KeywordDemographics d4p1:nil="false">
            <e1659:KeywordDemographic>
              <e1659:Device d4p1:nil="false">ValueHere</e1659:Device>
              <e1659:EighteenToTwentyFour>ValueHere</e1659:EighteenToTwentyFour>
              <e1659:TwentyFiveToThirtyFour>ValueHere</e1659:TwentyFiveToThirtyFour>
              <e1659:ThirtyFiveToFourtyNine>ValueHere</e1659:ThirtyFiveToFourtyNine>
              <e1659:FiftyToSixtyFour>ValueHere</e1659:FiftyToSixtyFour>
              <e1659:SixtyFiveAndAbove>ValueHere</e1659:SixtyFiveAndAbove>
              <e1659:AgeUnknown>ValueHere</e1659:AgeUnknown>
              <e1659:Female>ValueHere</e1659:Female>
              <e1659:Male>ValueHere</e1659:Male>
              <e1659:GenderUnknown>ValueHere</e1659:GenderUnknown>
            </e1659:KeywordDemographic>
          </e1659:KeywordDemographics>
        </e1659:KeywordDemographicResult>
      </KeywordDemographicResult>
    </GetKeywordDemographicsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordDemographicsResponse> GetKeywordDemographicsAsync(
	IList<string> keywords,
	string language,
	string publisherCountry,
	IList<string> device)
{
	var request = new GetKeywordDemographicsRequest
	{
		Keywords = keywords,
		Language = language,
		PublisherCountry = publisherCountry,
		Device = device
	};

	return (await AdInsightService.CallAsync((s, r) => s.GetKeywordDemographicsAsync(r), request));
}
```
```java
static GetKeywordDemographicsResponse getKeywordDemographics(
	ArrayOfstring keywords,
	java.lang.String language,
	java.lang.String publisherCountry,
	ArrayOfstring device) throws RemoteException, Exception
{
	GetKeywordDemographicsRequest request = new GetKeywordDemographicsRequest();

	request.setKeywords(keywords);
	request.setLanguage(language);
	request.setPublisherCountry(publisherCountry);
	request.setDevice(device);

	return AdInsightService.getService().getKeywordDemographics(request);
}
```
```php
static function GetKeywordDemographics(
	$keywords,
	$language,
	$publisherCountry,
	$device)
{

	$GLOBALS['Proxy'] = $GLOBALS['AdInsightProxy'];

	$request = new GetKeywordDemographicsRequest();

	$request->Keywords = $keywords;
	$request->Language = $language;
	$request->PublisherCountry = $publisherCountry;
	$request->Device = $device;

	return $GLOBALS['AdInsightProxy']->GetService()->GetKeywordDemographics($request);
}
```
```python
response=adinsight_service.GetKeywordDemographics(
	Keywords=Keywords,
	Language=Language,
	PublisherCountry=PublisherCountry,
	Device=Device)
```

## Requirements
Service: [AdInsightService.svc v12](https://adinsight.api.bingads.microsoft.com/Api/Advertiser/AdInsight/v12/AdInsightService.svc)  
Namespace: Microsoft.Advertiser.AdInsight.Api.Service.V12  

