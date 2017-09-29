---
title: GetMediaMetaDataByIds Service Operation
ms.service: bing-ads-campaign-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# GetMediaMetaDataByIds Service Operation
Gets the specified media meta data from an account?s media library.

> [!NOTE]
> This operation does not return media meta data for location ad extensions. For getting location ad extension media, you should use [GetMediaByIds](../campaign-management/getmediabyids.md).

## <a name="request"></a>Request Elements
The *GetMediaMetaDataByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediaids"></a>MediaIds|The identifiers of the media to get.<br /><br />You can specify a maximum of 100 media identifiers in a single call.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetMediaMetaDataByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediametadata"></a>MediaMetaData|An array of [MediaMetaData](../campaign-management/mediametadata.md) objects that corresponds directly to the media identifiers that you specified in the request. Items of the list may be returned as null. For each list index where media meta data was not retrieved, the corresponding element will be null.<br /><br />The meta data includes download Urls for one or more media representations. The number of representations depends on the type of media. For example media for image ad extensions  have multiple height and width representations, and you can access each individually. For more information see [MediaEnabledEntityFilter](../campaign-management/mediaenabledentityfilter.md).|[MediaMetaData](mediametadata.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of [BatchError](../campaign-management/batcherror.md) objects that contain details for any request items that were not successful.<br /><br />The list of errors do not correspond directly to the list of items in the request. The list can be empty if there were no errors, or can include one or more error objects corresponding to each unsuccessful list item in the request.|[BatchError](batcherror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetMediaMetaDataByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetMediaMetaDataByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <MediaIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </MediaIds>
    </GetMediaMetaDataByIdsRequest>
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
    <GetMediaMetaDataByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <MediaMetaData d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <MediaMetaData>
          <Id>ValueHere</Id>
          <MediaType d4p1:nil="false">ValueHere</MediaType>
          <Representations d4p1:nil="false">
            <MediaRepresentation d4p1:type="-- derived type specified here with the appropriate prefix --">
              <Name d4p1:nil="false">ValueHere</Name>
              <Type d4p1:nil="false">ValueHere</Type>
              <Url d4p1:nil="false">ValueHere</Url>
              <!--These fields are applicable if the derived type attribute is set to ImageMediaRepresentation-->
              <Height>ValueHere</Height>
              <Width>ValueHere</Width>
            </MediaRepresentation>
          </Representations>
          <Type d4p1:nil="false">ValueHere</Type>
        </MediaMetaData>
      </MediaMetaData>
      <PartialErrors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <BatchError d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <FieldPath d4p1:nil="false">ValueHere</FieldPath>
          <ForwardCompatibilityMap xmlns:e656="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e656:KeyValuePairOfstringstring>
              <e656:key d4p1:nil="false">ValueHere</e656:key>
              <e656:value d4p1:nil="false">ValueHere</e656:value>
            </e656:KeyValuePairOfstringstring>
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
    </GetMediaMetaDataByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<GetMediaMetaDataByIdsResponse> GetMediaMetaDataByIdsAsync(
	IList<long> mediaIds)
{
	var request = new GetMediaMetaDataByIdsRequest
	{
		MediaIds = mediaIds
	};

	return (await CampaignManagement.CallAsync((s, r) => s.GetMediaMetaDataByIdsAsync(r), request));
}
```
```java
static GetMediaMetaDataByIdsResponse getMediaMetaDataByIds(
	ArrayOflong mediaIds)
{
	GetMediaMetaDataByIdsRequest request = new GetMediaMetaDataByIdsRequest();

	request.setMediaIds(mediaIds);

	return CampaignManagement.getService().getMediaMetaDataByIds(request);
}
```
```php
static function GetMediaMetaDataByIds(
	$mediaIds)

	$getMediaMetaDataByIdsRequest = new GetMediaMetaDataByIdsRequest();

	$request->MediaIds = $mediaIds;

	return $CampaignManagementProxy->GetService()->GetMediaMetaDataByIds($request);
}
```
```python
response=campaignmanagement.GetMediaMetaDataByIds(
	MediaIds=MediaIdsHere
)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

