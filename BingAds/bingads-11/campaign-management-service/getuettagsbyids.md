---
title: GetUetTagsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the specified Universal Event Tracking (UET) tags.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetUetTagsByIds Service Operation - Campaign Management
Gets the specified Universal Event Tracking (UET) tags.

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](../guides/universal-event-tracking.md) technical guide.

## <a name="request"></a>Request Elements
The *GetUetTagsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="tagids"></a>TagIds|A maximum of 100 identifiers of the UET tags that you want to get. <br /><br />If *TagIds* is null or empty, then you are effectively requesting all UET tags that are available for the customer.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetUetTagsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|
|<a name="uettags"></a>UetTags|An array of [UetTag](uettag.md) objects that corresponds directly to the UET tag identifiers that you specified in the request. Items of the array may be returned as null. For each array index where a UET tag was not retrieved, the corresponding element will be null.|[UetTag](uettag.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetUetTagsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetUetTagsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <TagIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </TagIds>
    </GetUetTagsByIdsRequest>
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
    <GetUetTagsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <UetTags d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <UetTag>
          <Description d4p1:nil="false">ValueHere</Description>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
          <TrackingNoScript d4p1:nil="false">ValueHere</TrackingNoScript>
          <TrackingScript d4p1:nil="false">ValueHere</TrackingScript>
          <TrackingStatus d4p1:nil="false">ValueHere</TrackingStatus>
        </UetTag>
      </UetTags>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e257="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e257:KeyValuePairOfstringstring>
              <e257:key d4p1:nil="false">ValueHere</e257:key>
              <e257:value d4p1:nil="false">ValueHere</e257:value>
            </e257:KeyValuePairOfstringstring>
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
    </GetUetTagsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetUetTagsByIdsResponse> GetUetTagsByIdsAsync(
	IList<long> tagIds)
{
	var request = new GetUetTagsByIdsRequest
	{
		TagIds = tagIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetUetTagsByIdsAsync(r), request));
}
```
```java
static GetUetTagsByIdsResponse getUetTagsByIds(
	ArrayOflong tagIds) throws RemoteException, Exception
{
	GetUetTagsByIdsRequest request = new GetUetTagsByIdsRequest();

	request.setTagIds(tagIds);

	return CampaignManagementService.getService().getUetTagsByIds(request);
}
```
```php
static function GetUetTagsByIds(
	$tagIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetUetTagsByIdsRequest();

	$request->TagIds = $tagIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetUetTagsByIds($request);
}
```
```python
response=campaignmanagement_service.GetUetTagsByIds(
	TagIds=TagIds)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

