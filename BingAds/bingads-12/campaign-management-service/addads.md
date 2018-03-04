---
title: AddAds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds one or more ads to an ad group.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddAds Service Operation - Campaign Management
Adds one or more ads to an ad group.

> [!IMPORTANT]
> Standard Text Ads have been deprecated in favor of Expanded Text Ads (EXTAs). Support for adding and updating standard text ads (STAs) ended on July 31, 2017. Now, advertisers can get and delete, but can no longer add new STAs or update existing standard text ads with Destination URLs. One exception to the rule, is that you can still update the STA status e.g. from *Active* to *Paused*. Otherwise attempts to add or update STAs will result in the *CampaignServiceAdTypeInvalid* error. 
> 
> It is important to note that all your existing STAs will continue to serve alongside EXTAs for the foreseeable future. While there is no date on when STAs will stop serving, you can expect an update to all of our customers well in advance once we make the decision to sunset serving STAs.

## <a name="request"></a>Request Elements
The *AddAdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group to add the ads to.|**long**|
|<a name="ads"></a>Ads|An array of up to 50 ads that you want added to the ad group.|[Ad](ad.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adids"></a>AdIds|A list of unique system identifiers corresponding to the ads that were added.<br /><br />The list of identifiers corresponds directly to the list of ads in the request. Items of the list may be returned as null. For each list index where an ad was not added, the corresponding element will be null.|**long** array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management-service/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddAds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroupId>ValueHere</AdGroupId>
      <Ads i:nil="false">
        <Ad i:type="-- derived type specified here with the appropriate prefix --">
          <AdFormatPreference i:nil="false">ValueHere</AdFormatPreference>
          <DevicePreference i:nil="false">ValueHere</DevicePreference>
          <EditorialStatus i:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls xmlns:e121="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e121:AppUrl>
              <e121:OsType i:nil="false">ValueHere</e121:OsType>
              <e121:Url i:nil="false">ValueHere</e121:Url>
            </e121:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ForwardCompatibilityMap xmlns:e122="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e122:KeyValuePairOfstringstring>
              <e122:key i:nil="false">ValueHere</e122:key>
              <e122:value i:nil="false">ValueHere</e122:value>
            </e122:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id i:nil="false">ValueHere</Id>
          <Status i:nil="false">ValueHere</Status>
          <TrackingUrlTemplate i:nil="false">ValueHere</TrackingUrlTemplate>
          <Type i:nil="false">ValueHere</Type>
          <UrlCustomParameters xmlns:e123="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V11" i:nil="false">
            <e123:Parameters i:nil="false">
              <e123:CustomParameter>
                <e123:Key i:nil="false">ValueHere</e123:Key>
                <e123:Value i:nil="false">ValueHere</e123:Value>
              </e123:CustomParameter>
            </e123:Parameters>
          </UrlCustomParameters>
          <!--These fields are applicable if the derived type attribute is set to TextAd-->
          <DestinationUrl i:nil="false">ValueHere</DestinationUrl>
          <DisplayUrl i:nil="false">ValueHere</DisplayUrl>
          <Text i:nil="false">ValueHere</Text>
          <Title i:nil="false">ValueHere</Title>
          <!--This field is applicable if the derived type attribute is set to ProductAd-->
          <PromotionalText i:nil="false">ValueHere</PromotionalText>
          <!--These fields are applicable if the derived type attribute is set to AppInstallAd-->
          <AppPlatform i:nil="false">ValueHere</AppPlatform>
          <AppStoreId i:nil="false">ValueHere</AppStoreId>
          <Text i:nil="false">ValueHere</Text>
          <Title i:nil="false">ValueHere</Title>
          <!--These fields are applicable if the derived type attribute is set to ExpandedTextAd-->
          <DisplayUrl i:nil="false">ValueHere</DisplayUrl>
          <Path1 i:nil="false">ValueHere</Path1>
          <Path2 i:nil="false">ValueHere</Path2>
          <Text i:nil="false">ValueHere</Text>
          <TitlePart1 i:nil="false">ValueHere</TitlePart1>
          <TitlePart2 i:nil="false">ValueHere</TitlePart2>
          <!--These fields are applicable if the derived type attribute is set to DynamicSearchAd-->
          <Path1 i:nil="false">ValueHere</Path1>
          <Path2 i:nil="false">ValueHere</Path2>
          <Text i:nil="false">ValueHere</Text>
          <!--These fields are applicable if the derived type attribute is set to ResponsiveAd-->
          <BusinessName i:nil="false">ValueHere</BusinessName>
          <CallToAction i:nil="false">ValueHere</CallToAction>
          <Headline i:nil="false">ValueHere</Headline>
          <LandscapeImageMediaId i:nil="false">ValueHere</LandscapeImageMediaId>
          <LandscapeLogoMediaId i:nil="false">ValueHere</LandscapeLogoMediaId>
          <LongHeadline i:nil="false">ValueHere</LongHeadline>
          <SquareImageMediaId i:nil="false">ValueHere</SquareImageMediaId>
          <SquareLogoMediaId i:nil="false">ValueHere</SquareLogoMediaId>
          <Text i:nil="false">ValueHere</Text>
        </Ad>
      </Ads>
    </AddAdsRequest>
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
    <AddAdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </AdIds>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e124="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e124:KeyValuePairOfstringstring>
              <e124:key d4p1:nil="false">ValueHere</e124:key>
              <e124:value d4p1:nil="false">ValueHere</e124:value>
            </e124:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Index>ValueHere</Index>
          <Message d4p1:nil="false">ValueHere</Message>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--These fields are applicable if the derived type attribute is set to EditorialError-->
          <Appealable d4p1:nil="false">ValueHere</Appealable>
          <DisapprovedText d4p1:nil="false">ValueHere</DisapprovedText>
          <Location d4p1:nil="false">ValueHere</Location>
          <PublisherCountry d4p1:nil="false">ValueHere</PublisherCountry>
          <ReasonCode>ValueHere</ReasonCode>
        </BatchError>
      </PartialErrors>
    </AddAdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<AddAdsResponse> AddAdsAsync(
	long adGroupId,
	IList<Ad> ads)
{
	var request = new AddAdsRequest
	{
		AdGroupId = adGroupId,
		Ads = ads
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddAdsAsync(r), request));
}
```
```java
static AddAdsResponse addAds(
	java.lang.Long adGroupId,
	ArrayOfAd ads) throws RemoteException, Exception
{
	AddAdsRequest request = new AddAdsRequest();

	request.setAdGroupId(adGroupId);
	request.setAds(ads);

	return CampaignManagementService.getService().addAds(request);
}
```
```php
static function AddAds(
	$adGroupId,
	$ads)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddAdsRequest();

	$request->AdGroupId = $adGroupId;
	$request->Ads = $ads;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddAds($request);
}
```
```python
response=campaignmanagement_service.AddAds(
	AdGroupId=AdGroupId,
	Ads=Ads)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

