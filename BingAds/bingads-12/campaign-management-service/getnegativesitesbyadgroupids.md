---
title: GetNegativeSitesByAdGroupIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the negative site URLs of the specified ad groups.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetNegativeSitesByAdGroupIds Service Operation - Campaign Management
Gets the negative site URLs of the specified ad groups.

## <a name="request"></a>Request Elements
The *GetNegativeSitesByAdGroupIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupids"></a>AdGroupIds|An array of identifiers of the ad groups that contain the negative site URLs that you want to get.<br /><br />The call fails if the sum of all negative site URLs defined in the specified list of ad groups exceeds 30,000 URLs. To ensure that the call succeeds, consider limiting the number of ad groups to 15.|**long** array|
|<a name="campaignid"></a>CampaignId|The identifier of the campaign that contains the ad groups.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetNegativeSitesByAdGroupIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupnegativesites"></a>AdGroupNegativeSites|An array of [AdGroupNegativeSites](adgroupnegativesites.md) that corresponds directly to the ad group identifiers that you specified in the request. Items of the list may be returned as null. For each list index where an [AdGroupNegativeSites](adgroupnegativesites.md) was not retrieved, the corresponding element will be null.|[AdGroupNegativeSites](adgroupnegativesites.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetNegativeSitesByAdGroupIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetNegativeSitesByAdGroupIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <CampaignId>ValueHere</CampaignId>
      <AdGroupIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdGroupIds>
    </GetNegativeSitesByAdGroupIdsRequest>
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
    <GetNegativeSitesByAdGroupIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AdGroupNegativeSites d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <AdGroupNegativeSites>
          <AdGroupId>ValueHere</AdGroupId>
          <NegativeSites d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:string>ValueHere</a1:string>
          </NegativeSites>
        </AdGroupNegativeSites>
      </AdGroupNegativeSites>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1138="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1138:KeyValuePairOfstringstring>
              <e1138:key d4p1:nil="false">ValueHere</e1138:key>
              <e1138:value d4p1:nil="false">ValueHere</e1138:value>
            </e1138:KeyValuePairOfstringstring>
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
    </GetNegativeSitesByAdGroupIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetNegativeSitesByAdGroupIdsResponse> GetNegativeSitesByAdGroupIdsAsync(
	long campaignId,
	IList<long> adGroupIds)
{
	var request = new GetNegativeSitesByAdGroupIdsRequest
	{
		CampaignId = campaignId,
		AdGroupIds = adGroupIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetNegativeSitesByAdGroupIdsAsync(r), request));
}
```
```java
static GetNegativeSitesByAdGroupIdsResponse getNegativeSitesByAdGroupIds(
	java.lang.Long campaignId,
	ArrayOflong adGroupIds) throws RemoteException, Exception
{
	GetNegativeSitesByAdGroupIdsRequest request = new GetNegativeSitesByAdGroupIdsRequest();

	request.setCampaignId(campaignId);
	request.setAdGroupIds(adGroupIds);

	return CampaignManagementService.getService().getNegativeSitesByAdGroupIds(request);
}
```
```php
static function GetNegativeSitesByAdGroupIds(
	$campaignId,
	$adGroupIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetNegativeSitesByAdGroupIdsRequest();

	$request->CampaignId = $campaignId;
	$request->AdGroupIds = $adGroupIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetNegativeSitesByAdGroupIds($request);
}
```
```python
response=campaignmanagement_service.GetNegativeSitesByAdGroupIds(
	CampaignId=CampaignId,
	AdGroupIds=AdGroupIds)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

