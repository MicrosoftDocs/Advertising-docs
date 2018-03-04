---
title: UpdateUetTags Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the specified Universal Event Tracking (UET) tags.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# UpdateUetTags Service Operation - Campaign Management
Updates the specified Universal Event Tracking (UET) tags.

> [!TIP]
> For an implementation overview, see the [Universal Event Tracking](~/guides/universal-event-tracking.md) technical guide.

## <a name="request"></a>Request Elements
The *UpdateUetTagsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="uettags"></a>UetTags|An array of [UetTag](../campaign-management-service/uettag.md) objects to update within the customer's shared UET tag library.<br /><br />You can update a maximum of 100 UET tags in a single call.|[UetTag](uettag.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateUetTagsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management-service/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">UpdateUetTags</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateUetTagsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <UetTags i:nil="false">
        <UetTag>
          <Description i:nil="false">ValueHere</Description>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
          <TrackingNoScript i:nil="false">ValueHere</TrackingNoScript>
          <TrackingScript i:nil="false">ValueHere</TrackingScript>
          <TrackingStatus i:nil="false">ValueHere</TrackingStatus>
        </UetTag>
      </UetTags>
    </UpdateUetTagsRequest>
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
    <UpdateUetTagsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e306="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e306:KeyValuePairOfstringstring>
              <e306:key d4p1:nil="false">ValueHere</e306:key>
              <e306:value d4p1:nil="false">ValueHere</e306:value>
            </e306:KeyValuePairOfstringstring>
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
    </UpdateUetTagsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateUetTagsResponse> UpdateUetTagsAsync(
	IList<UetTag> uetTags)
{
	var request = new UpdateUetTagsRequest
	{
		UetTags = uetTags
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateUetTagsAsync(r), request));
}
```
```java
static UpdateUetTagsResponse updateUetTags(
	ArrayOfUetTag uetTags) throws RemoteException, Exception
{
	UpdateUetTagsRequest request = new UpdateUetTagsRequest();

	request.setUetTags(uetTags);

	return CampaignManagementService.getService().updateUetTags(request);
}
```
```php
static function UpdateUetTags(
	$uetTags)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateUetTagsRequest();

	$request->UetTags = $uetTags;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateUetTags($request);
}
```
```python
response=campaignmanagement_service.UpdateUetTags(
	UetTags=UetTags)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

