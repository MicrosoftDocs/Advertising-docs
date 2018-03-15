---
title: GetKeywordsByEditorialStatus Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Retrieves the keywords with the specified editorial review status.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetKeywordsByEditorialStatus Service Operation - Campaign Management
Retrieves the keywords with the specified editorial review status.

## <a name="request"></a>Request Elements
The *GetKeywordsByEditorialStatusRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The identifier of the ad group that contains the keywords to retrieve.|**long**|
|<a name="editorialstatus"></a>EditorialStatus|The review status of the keywords to retrieve.|[KeywordEditorialStatus](keywordeditorialstatus.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetKeywordsByEditorialStatusResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="keywords"></a>Keywords|An array of [Keyword](keyword.md) objects that contains information about the keywords that were retrieved.|[Keyword](keyword.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetKeywordsByEditorialStatus</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetKeywordsByEditorialStatusRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupId>ValueHere</AdGroupId>
      <EditorialStatus>ValueHere</EditorialStatus>
    </GetKeywordsByEditorialStatusRequest>
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
    <GetKeywordsByEditorialStatusResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Keywords d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Keyword>
          <Bid d4p1:nil="false">
            <Amount d4p1:nil="false">ValueHere</Amount>
          </Bid>
          <BiddingScheme d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --">
            <Type d4p1:nil="false">ValueHere</Type>
            <!--This field is applicable if the derived type attribute is set to MaxClicksBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--This field is applicable if the derived type attribute is set to MaxConversionsBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <!--These fields are applicable if the derived type attribute is set to TargetCpaBiddingScheme-->
            <MaxCpc d4p1:nil="false">
              <Amount d4p1:nil="false">ValueHere</Amount>
            </MaxCpc>
            <TargetCpa d4p1:nil="false">ValueHere</TargetCpa>
            <!--No additional fields are applicable if the derived type attribute is set to ManualCpcBiddingScheme-->
            <!--No additional fields are applicable if the derived type attribute is set to EnhancedCpcBiddingScheme-->
            <!--This field is applicable if the derived type attribute is set to InheritFromParentBiddingScheme-->
            <InheritedBidStrategyType d4p1:nil="false">ValueHere</InheritedBidStrategyType>
          </BiddingScheme>
          <DestinationUrl d4p1:nil="false">ValueHere</DestinationUrl>
          <EditorialStatus d4p1:nil="false">ValueHere</EditorialStatus>
          <FinalAppUrls xmlns:e1814="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" d4p1:nil="false">
            <e1814:AppUrl>
              <e1814:OsType d4p1:nil="false">ValueHere</e1814:OsType>
              <e1814:Url d4p1:nil="false">ValueHere</e1814:Url>
            </e1814:AppUrl>
          </FinalAppUrls>
          <FinalMobileUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalMobileUrls>
          <FinalUrls d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </FinalUrls>
          <ForwardCompatibilityMap xmlns:e1815="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1815:KeyValuePairOfstringstring>
              <e1815:key d4p1:nil="false">ValueHere</e1815:key>
              <e1815:value d4p1:nil="false">ValueHere</e1815:value>
            </e1815:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
          <Id d4p1:nil="false">ValueHere</Id>
          <MatchType d4p1:nil="false">ValueHere</MatchType>
          <Param1 d4p1:nil="false">ValueHere</Param1>
          <Param2 d4p1:nil="false">ValueHere</Param2>
          <Param3 d4p1:nil="false">ValueHere</Param3>
          <Status d4p1:nil="false">ValueHere</Status>
          <Text d4p1:nil="false">ValueHere</Text>
          <TrackingUrlTemplate d4p1:nil="false">ValueHere</TrackingUrlTemplate>
          <UrlCustomParameters xmlns:e1816="http://schemas.datacontract.org/2004/07/Microsoft.AdCenter.Advertiser.CampaignManagement.Api.DataContracts.V12" d4p1:nil="false">
            <e1816:Parameters d4p1:nil="false">
              <e1816:CustomParameter>
                <e1816:Key d4p1:nil="false">ValueHere</e1816:Key>
                <e1816:Value d4p1:nil="false">ValueHere</e1816:Value>
              </e1816:CustomParameter>
            </e1816:Parameters>
          </UrlCustomParameters>
        </Keyword>
      </Keywords>
    </GetKeywordsByEditorialStatusResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetKeywordsByEditorialStatusResponse> GetKeywordsByEditorialStatusAsync(
	long adGroupId,
	KeywordEditorialStatus editorialStatus)
{
	var request = new GetKeywordsByEditorialStatusRequest
	{
		AdGroupId = adGroupId,
		EditorialStatus = editorialStatus
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetKeywordsByEditorialStatusAsync(r), request));
}
```
```java
static GetKeywordsByEditorialStatusResponse getKeywordsByEditorialStatus(
	java.lang.Long adGroupId,
	KeywordEditorialStatus editorialStatus) throws RemoteException, Exception
{
	GetKeywordsByEditorialStatusRequest request = new GetKeywordsByEditorialStatusRequest();

	request.setAdGroupId(adGroupId);
	request.setEditorialStatus(editorialStatus);

	return CampaignManagementService.getService().getKeywordsByEditorialStatus(request);
}
```
```php
static function GetKeywordsByEditorialStatus(
	$adGroupId,
	$editorialStatus)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetKeywordsByEditorialStatusRequest();

	$request->AdGroupId = $adGroupId;
	$request->EditorialStatus = $editorialStatus;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetKeywordsByEditorialStatus($request);
}
```
```python
response=campaignmanagement_service.GetKeywordsByEditorialStatus(
	AdGroupId=AdGroupId,
	EditorialStatus=EditorialStatus)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

