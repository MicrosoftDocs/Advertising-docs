---
title: GetMediaMetaDataByAccountId Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the media meta data of the specified entity type from an account's media library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# GetMediaMetaDataByAccountId Service Operation - Campaign Management
Gets the media meta data of the specified entity type from an account's media library.

> [!NOTE]
> This operation does not return media meta data for location ad extensions. For getting location ad extension media, you should use [GetMediaByIds](getmediabyids.md).

## <a name="request"></a>Request Elements
The *GetMediaMetaDataByAccountIdRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediaenabledentities"></a>MediaEnabledEntities|Determines the type of media enabled entity to get meta data. Currently only ImageAdExtension is supported.|[MediaEnabledEntityFilter](mediaenabledentityfilter.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetMediaMetaDataByAccountIdResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediametadata"></a>MediaMetaData|The specified media meta data from the library.<br /><br />The meta data includes download Urls for one or more media representations. The number of representations depends on the type of media. For example media for image ad extensions  have multiple height and width representations, and you can access each individually. For more information see [MediaEnabledEntityFilter](mediaenabledentityfilter.md).|[MediaMetaData](mediametadata.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">GetMediaMetaDataByAccountId</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetMediaMetaDataByAccountIdRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <MediaEnabledEntities>ValueHere</MediaEnabledEntities>
    </GetMediaMetaDataByAccountIdRequest>
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
    <GetMediaMetaDataByAccountIdResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
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
    </GetMediaMetaDataByAccountIdResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetMediaMetaDataByAccountIdResponse> GetMediaMetaDataByAccountIdAsync(
	MediaEnabledEntityFilter mediaEnabledEntities)
{
	var request = new GetMediaMetaDataByAccountIdRequest
	{
		MediaEnabledEntities = mediaEnabledEntities
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetMediaMetaDataByAccountIdAsync(r), request));
}
```
```java
static GetMediaMetaDataByAccountIdResponse getMediaMetaDataByAccountId(
	ArrayList<MediaEnabledEntityFilter> mediaEnabledEntities) throws RemoteException, Exception
{
	GetMediaMetaDataByAccountIdRequest request = new GetMediaMetaDataByAccountIdRequest();

	request.setMediaEnabledEntities(mediaEnabledEntities);

	return CampaignManagementService.getService().getMediaMetaDataByAccountId(request);
}
```
```php
static function GetMediaMetaDataByAccountId(
	$mediaEnabledEntities)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetMediaMetaDataByAccountIdRequest();

	$request->MediaEnabledEntities = $mediaEnabledEntities;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetMediaMetaDataByAccountId($request);
}
```
```python
response=campaignmanagement_service.GetMediaMetaDataByAccountId(
	MediaEnabledEntities=MediaEnabledEntities)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

