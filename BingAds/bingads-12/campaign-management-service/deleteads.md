---
title: DeleteAds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Deletes one or more ads from the specified ad group.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# DeleteAds Service Operation - Campaign Management
Deletes one or more ads from the specified ad group.

## <a name="request"></a>Request Elements
The *DeleteAdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="adgroupid"></a>AdGroupId|The ID of the ad group that contains the ads to delete.|**long**|
|<a name="adids"></a>AdIds|The IDs of the ads to delete. You can specify a maximum of 50 IDs.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteAdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">DeleteAds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteAdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AdGroupId>ValueHere</AdGroupId>
      <AdIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AdIds>
    </DeleteAdsRequest>
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
    <DeleteAdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e161="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e161:KeyValuePairOfstringstring>
              <e161:key d4p1:nil="false">ValueHere</e161:key>
              <e161:value d4p1:nil="false">ValueHere</e161:value>
            </e161:KeyValuePairOfstringstring>
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
    </DeleteAdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteAdsResponse> DeleteAdsAsync(
	long adGroupId,
	IList<long> adIds)
{
	var request = new DeleteAdsRequest
	{
		AdGroupId = adGroupId,
		AdIds = adIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.DeleteAdsAsync(r), request));
}
```
```java
static DeleteAdsResponse deleteAds(
	java.lang.Long adGroupId,
	ArrayOflong adIds) throws RemoteException, Exception
{
	DeleteAdsRequest request = new DeleteAdsRequest();

	request.setAdGroupId(adGroupId);
	request.setAdIds(adIds);

	return CampaignManagementService.getService().deleteAds(request);
}
```
```php
static function DeleteAds(
	$adGroupId,
	$adIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new DeleteAdsRequest();

	$request->AdGroupId = $adGroupId;
	$request->AdIds = $adIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->DeleteAds($request);
}
```
```python
response=campaignmanagement_service.DeleteAds(
	AdGroupId=AdGroupId,
	AdIds=AdIds)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

