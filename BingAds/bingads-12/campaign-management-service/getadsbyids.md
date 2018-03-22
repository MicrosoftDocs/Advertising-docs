---
title: GetAdsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the specified ads from the specified ad group.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetAdsByIds Service Operation - Campaign Management
Retrieves the specified ads from the specified ad group.

## <a name="request"></a>Request Elements
The *GetAdsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that contains the ads to get.|**long**|
|<a name="adids"></a>AdIds|A maximum of 20 identifiers of the requested ads.<br/><br/> If the ad identifiers do not match the requested ad types, then the operation will return a batch error for each requested ad.|**long** array|
|<a name="adtypes"></a>AdTypes|One or more types of ads to return.|[AdType](adtype.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAdsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ads"></a>Ads|An array of [Ad](ad.md) objects that corresponds directly to the ad identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an ad was not retrieved, the corresponding element will be null.|[Ad](ad.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetAdsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAdsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupId>ValueHere</AdGroupId>
      <AdIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdIds>
      <AdTypes i:nil="false">
        <AdType>ValueHere</AdType>
      </AdTypes>
    </GetAdsByIdsRequest>
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
    <GetAdsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
          <ForwardCompatibilityMap xmlns:e1113="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1113:KeyValuePairOfstringstring>
              <e1113:key d4p1:nil="false">ValueHere</e1113:key>
              <e1113:value d4p1:nil="false">ValueHere</e1113:value>
            </e1113:KeyValuePairOfstringstring>
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
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1114="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1114:KeyValuePairOfstringstring>
              <e1114:key d4p1:nil="false">ValueHere</e1114:key>
              <e1114:value d4p1:nil="false">ValueHere</e1114:value>
            </e1114:KeyValuePairOfstringstring>
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
    </GetAdsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAdsByIdsResponse> GetAdsByIdsAsync(
	long adGroupId,
	IList<long> adIds,
	IList<AdType> adTypes)
{
	var request = new GetAdsByIdsRequest
	{
		AdGroupId = adGroupId,
		AdIds = adIds,
		AdTypes = adTypes
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetAdsByIdsAsync(r), request));
}
```
```java
static GetAdsByIdsResponse getAdsByIds(
	java.lang.Long adGroupId,
	ArrayOflong adIds,
	ArrayOfAdType adTypes) throws RemoteException, Exception
{
	GetAdsByIdsRequest request = new GetAdsByIdsRequest();

	request.setAdGroupId(adGroupId);
	request.setAdIds(adIds);
	request.setAdTypes(adTypes);

	return CampaignManagementService.getService().getAdsByIds(request);
}
```
```php
static function GetAdsByIds(
	$adGroupId,
	$adIds,
	$adTypes)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetAdsByIdsRequest();

	$request->AdGroupId = $adGroupId;
	$request->AdIds = $adIds;
	$request->AdTypes = $adTypes;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetAdsByIds($request);
}
```
```python
response=campaignmanagement_service.GetAdsByIds(
	AdGroupId=AdGroupId,
	AdIds=AdIds,
	AdTypes=AdTypes)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

