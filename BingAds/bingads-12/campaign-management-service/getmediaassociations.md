---
title: GetMediaAssociations Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the media associations of the specified entity type from an account's media library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetMediaAssociations Service Operation - Campaign Management
Gets the media associations of the specified entity type from an account's media library.

> [!NOTE]
> You must specify the account identifier in the *CustomerAccountId* header element.

## <a name="request"></a>Request Elements
The *GetMediaAssociationsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediaenabledentities"></a>MediaEnabledEntities|Filters the results to only return media associations with the specified type of media enabled entity.<br /><br />Currently only ImageAdExtension is supported.|[MediaEnabledEntityFilter](mediaenabledentityfilter.md)|
|<a name="mediaids"></a>MediaIds|The identifiers of the media to get corresponding entity associations.<br /><br />You can specify a maximum of 10 media identifiers in a single call.|**long** array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetMediaAssociationsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediaassociations"></a>MediaAssociations|An array of [MediaAssociation](mediaassociation.md) objects that corresponds directly to the media identifiers that you specified in the request. Items of the list may be returned as null. For each list index where media associations were not retrieved, the corresponding element will be null.|[MediaAssociation](mediaassociation.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetMediaAssociations</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetMediaAssociationsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <MediaEnabledEntities>ValueHere</MediaEnabledEntities>
      <MediaIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </MediaIds>
    </GetMediaAssociationsRequest>
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
    <GetMediaAssociationsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <MediaAssociations d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <ArrayOfMediaAssociation>
          <MediaAssociation>
            <EntityId>ValueHere</EntityId>
            <MediaEnabledEntity>ValueHere</MediaEnabledEntity>
            <MediaId>ValueHere</MediaId>
          </MediaAssociation>
        </ArrayOfMediaAssociation>
      </MediaAssociations>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e1135="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e1135:KeyValuePairOfstringstring>
              <e1135:key d4p1:nil="false">ValueHere</e1135:key>
              <e1135:value d4p1:nil="false">ValueHere</e1135:value>
            </e1135:KeyValuePairOfstringstring>
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
    </GetMediaAssociationsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetMediaAssociationsResponse> GetMediaAssociationsAsync(
	MediaEnabledEntityFilter mediaEnabledEntities,
	IList<long> mediaIds)
{
	var request = new GetMediaAssociationsRequest
	{
		MediaEnabledEntities = mediaEnabledEntities,
		MediaIds = mediaIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetMediaAssociationsAsync(r), request));
}
```
```java
static GetMediaAssociationsResponse getMediaAssociations(
	ArrayList<MediaEnabledEntityFilter> mediaEnabledEntities,
	ArrayOflong mediaIds) throws RemoteException, Exception
{
	GetMediaAssociationsRequest request = new GetMediaAssociationsRequest();

	request.setMediaEnabledEntities(mediaEnabledEntities);
	request.setMediaIds(mediaIds);

	return CampaignManagementService.getService().getMediaAssociations(request);
}
```
```php
static function GetMediaAssociations(
	$mediaEnabledEntities,
	$mediaIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetMediaAssociationsRequest();

	$request->MediaEnabledEntities = $mediaEnabledEntities;
	$request->MediaIds = $mediaIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetMediaAssociations($request);
}
```
```python
response=campaignmanagement_service.GetMediaAssociations(
	MediaEnabledEntities=MediaEnabledEntities,
	MediaIds=MediaIds)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

