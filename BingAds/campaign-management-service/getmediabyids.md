---
title: GetMediaByIds Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Gets the specified media from an account's media library.
---
# GetMediaByIds Service Operation - Campaign Management
Gets the specified media from an account's media library.

> [!NOTE]
> This operation only supports media identifiers for location ad extensions. For getting image ad extension media, you should use [GetMediaMetaDataByIds](../campaign-management-service/getmediametadatabyids.md).

## <a name="request"></a>Request Elements
The *GetMediaByIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account that owns the media library.|**long**|
|<a name="mediaids"></a>MediaIds|The identifiers of the media to get.<br /><br />You can specify a maximum of 10 media identifiers in a single call.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetMediaByIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="media"></a>Media|The specified media from the library.|[Media](media.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetMediaByIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetMediaByIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <AccountId>ValueHere</AccountId>
      <MediaIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </MediaIds>
    </GetMediaByIdsRequest>
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
    <GetMediaByIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Media d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <Media d4p1:type="-- derived type specified here with the appropriate prefix --">
          <Id d4p1:nil="false">ValueHere</Id>
          <MediaType d4p1:nil="false">ValueHere</MediaType>
          <Type d4p1:nil="false">ValueHere</Type>
          <!--This field is applicable if the derived type attribute is set to Image-->
          <Data d4p1:nil="false">ValueHere</Data>
        </Media>
      </Media>
    </GetMediaByIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetMediaByIdsResponse> GetMediaByIdsAsync(
	long accountId,
	IList<long> mediaIds)
{
	var request = new GetMediaByIdsRequest
	{
		AccountId = accountId,
		MediaIds = mediaIds
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetMediaByIdsAsync(r), request));
}
```
```java
static GetMediaByIdsResponse getMediaByIds(
	java.lang.Long accountId,
	ArrayOflong mediaIds) throws RemoteException, Exception
{
	GetMediaByIdsRequest request = new GetMediaByIdsRequest();

	request.setAccountId(accountId);
	request.setMediaIds(mediaIds);

	return CampaignManagementService.getService().getMediaByIds(request);
}
```
```php
static function GetMediaByIds(
	$accountId,
	$mediaIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetMediaByIdsRequest();

	$request->AccountId = $accountId;
	$request->MediaIds = $mediaIds;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetMediaByIds($request);
}
```
```python
response=campaignmanagement_service.GetMediaByIds(
	AccountId=AccountId,
	MediaIds=MediaIds)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

