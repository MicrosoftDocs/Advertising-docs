---
title: AddMedia Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Adds the specified media to an account's media library.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# AddMedia Service Operation - Campaign Management
Adds the specified media to an account's media library. Depending on the type of [Media](../campaign-management-service/media.md), you can then add the media to one or more [ImageAdExtension](../campaign-management-service/imageadextension.md) or [LocationAdExtension](../campaign-management-service/locationadextension.md) objects.

## <a name="request"></a>Request Elements
The *AddMediaRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the media library.|**long**|
|<a name="media"></a>Media|An array of *Media* to add to the account's media library.<br /><br />You can add a maximum of 10 media in a single call.|[Media](media.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddMediaResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mediaids"></a>MediaIds|The identifiers of the media that you added to the library. You use the identifier to set the appropriate media ID field in the [ImageAdExtension](../campaign-management-service/imageadextension.md) or [LocationAdExtension](../campaign-management-service/locationadextension.md) object.<br /><br />You can get the media for image ad extensions with the [GetMediaMetaDataByAccountId](../campaign-management-service/getmediametadatabyaccountid.md) and [GetMediaMetaDataByIds](../campaign-management-service/getmediametadatabyids.md) operations.<br /><br />You can get the media for location ad extensions with the [GetMediaByIds](../campaign-management-service/getmediabyids.md). operation.|**long** array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">AddMedia</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddMediaRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <Media i:nil="false">
        <Media i:type="-- derived type specified here with the appropriate prefix --">
          <Id i:nil="false">ValueHere</Id>
          <MediaType i:nil="false">ValueHere</MediaType>
          <Type i:nil="false">ValueHere</Type>
          <!--This field is applicable if the derived type attribute is set to Image-->
          <Data i:nil="false">ValueHere</Data>
        </Media>
      </Media>
    </AddMediaRequest>
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
    <AddMediaResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <MediaIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <a1:long>ValueHere</a1:long>
      </MediaIds>
    </AddMediaResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddMediaResponse> AddMediaAsync(
	long accountId,
	IList<Media> media)
{
	var request = new AddMediaRequest
	{
		AccountId = accountId,
		Media = media
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.AddMediaAsync(r), request));
}
```
```java
static AddMediaResponse addMedia(
	java.lang.Long accountId,
	ArrayOfMedia media) throws RemoteException, Exception
{
	AddMediaRequest request = new AddMediaRequest();

	request.setAccountId(accountId);
	request.setMedia(media);

	return CampaignManagementService.getService().addMedia(request);
}
```
```php
static function AddMedia(
	$accountId,
	$media)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new AddMediaRequest();

	$request->AccountId = $accountId;
	$request->Media = $media;

	return $GLOBALS['CampaignManagementProxy']->GetService()->AddMedia($request);
}
```
```python
response=campaignmanagement_service.AddMedia(
	AccountId=AccountId,
	Media=Media)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

