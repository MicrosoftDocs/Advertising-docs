---
title: GetLabelsByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets labels by label identifiers.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetLabelsByIds Service Operation - Campaign Management
Gets labels by label identifiers.

## <a name="request"></a>Request Elements
The *GetLabelsByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="labelids"></a>LabelIds|The identifiers of the labels to get.<br /><br />The maximum size of the list is 1,000 items per service request. If this element is not specified, the operation will return all active labels in the account (1,000 results per page).|**long** array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of label results per page.<br /><br />If this element is not specified, the defaut page Index is *0* and the default Size is *1,000*.|[Paging](paging.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetLabelsByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="labels"></a>Labels|An array of [Label](label.md) objects that corresponds directly to the label identifiers that you specified in the request. Items of the list may be returned as null. For each list index where a label was not retrieved, the corresponding element will be null.|[Label](label.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetLabelsByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetLabelsByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <LabelIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </LabelIds>
      <PageInfo i:nil="false">
        <Index>ValueHere</Index>
        <Size>ValueHere</Size>
      </PageInfo>
    </GetLabelsByIdsRequest>
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
    <GetLabelsByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <Labels d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Label>
          <ColorCode d4p1:nil="false">ValueHere</ColorCode>
          <Description d4p1:nil="false">ValueHere</Description>
          <Id d4p1:nil="false">ValueHere</Id>
          <Name d4p1:nil="false">ValueHere</Name>
        </Label>
      </Labels>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1133="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1133:KeyValuePairOfstringstring>
              <e1133:key d4p1:nil="false">ValueHere</e1133:key>
              <e1133:value d4p1:nil="false">ValueHere</e1133:value>
            </e1133:KeyValuePairOfstringstring>
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
    </GetLabelsByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetLabelsByIdsResponse> GetLabelsByIdsAsync(
	IList<long> labelIds,
	Paging pageInfo)
{
	var request = new GetLabelsByIdsRequest
	{
		LabelIds = labelIds,
		PageInfo = pageInfo
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetLabelsByIdsAsync(r), request));
}
```
```java
static GetLabelsByIdsResponse getLabelsByIds(
	ArrayOflong labelIds,
	Paging pageInfo) throws RemoteException, Exception
{
	GetLabelsByIdsRequest request = new GetLabelsByIdsRequest();

	request.setLabelIds(labelIds);
	request.setPageInfo(pageInfo);

	return CampaignManagementService.getService().getLabelsByIds(request);
}
```
```php
static function GetLabelsByIds(
	$labelIds,
	$pageInfo)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetLabelsByIdsRequest();

	$request->LabelIds = $labelIds;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetLabelsByIds($request);
}
```
```python
response=campaignmanagement_service.GetLabelsByIds(
	LabelIds=LabelIds,
	PageInfo=PageInfo)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

