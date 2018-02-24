---
title: UpdateLabels Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the labels within the account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# UpdateLabels Service Operation - Campaign Management
Updates the labels within the account.

## <a name="request"></a>Request Elements
The *UpdateLabelsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="labels"></a>Labels|The list of labels that you want to update.<br /><br />The maximum size of the list is 100 items per service request.|[Label](label.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateLabelsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">UpdateLabels</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateLabelsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Labels i:nil="false">
        <Label>
          <ColorCode i:nil="false">ValueHere</ColorCode>
          <Description i:nil="false">ValueHere</Description>
          <Id i:nil="false">ValueHere</Id>
          <Name i:nil="false">ValueHere</Name>
        </Label>
      </Labels>
    </UpdateLabelsRequest>
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
    <UpdateLabelsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e303="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e303:KeyValuePairOfstringstring>
              <e303:key d4p1:nil="false">ValueHere</e303:key>
              <e303:value d4p1:nil="false">ValueHere</e303:value>
            </e303:KeyValuePairOfstringstring>
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
    </UpdateLabelsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateLabelsResponse> UpdateLabelsAsync(
	IList<Label> labels)
{
	var request = new UpdateLabelsRequest
	{
		Labels = labels
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.UpdateLabelsAsync(r), request));
}
```
```java
static UpdateLabelsResponse updateLabels(
	ArrayOfLabel labels) throws RemoteException, Exception
{
	UpdateLabelsRequest request = new UpdateLabelsRequest();

	request.setLabels(labels);

	return CampaignManagementService.getService().updateLabels(request);
}
```
```php
static function UpdateLabels(
	$labels)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new UpdateLabelsRequest();

	$request->Labels = $labels;

	return $GLOBALS['CampaignManagementProxy']->GetService()->UpdateLabels($request);
}
```
```python
response=campaignmanagement_service.UpdateLabels(
	Labels=Labels)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

