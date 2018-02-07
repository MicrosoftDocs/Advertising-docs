---
title: GetGeoLocationsFileUrl Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a temporary URL that you can use to download a file that contains the supported geographical location targeting codes.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetGeoLocationsFileUrl Service Operation - Campaign Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Gets a temporary URL that you can use to download a file that contains the supported geographical location targeting codes.

> [!NOTE]
> You must specify the account identifier in the *CustomerAccountId* header element.

## <a name="request"></a>Request Elements
The *GetGeoLocationsFileUrlRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="languagelocale"></a>LanguageLocale|The language and locale of the geographical location code descriptions. The supported language locale values are *zh-Hant* (Traditional Chinese), *en* (English), *fr* (French), *de* (German), *it* (Italian), *pt-BR* (Brazilian Portuguese), and *es* (Spanish).|**string**|
|<a name="version"></a>Version|The version of the location file that you want to download.<br/><br/>Currently the only supported version is 2.0. You must set this value to *2.0*. |**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetGeoLocationsFileUrlResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="fileurl"></a>FileUrl|The file URL that you can use to download the geographical location targeting codes for the version, language, and locale that you requested.<br/><br/>Before you download the file, check whether the date and time of the *LastModifiedTimeUtc* element is later than the date and time of your previous download. You should only download the file if necessary.|**string**|
|<a name="fileurlexpirytimeutc"></a>FileUrlExpiryTimeUtc|The date and time that the provided file URL will expire.<br/><br/>If you do not download the file prior to the expiration time, then you can call the operation again to request a new file URL. You might observe that the URL is set to expire 15 minutes from the time this operation completes; however, you should not depend on a fixed duration. Future calls to this operation might result in a shorter or longer expiration time. <br/><br/>The value is in Coordinated Universal Time (UTC). The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="lastmodifiedtimeutc"></a>LastModifiedTimeUtc|The date and time that the geographical locations file for the specified version, language, and locale was last updated.<br/><br/>As a best practice you should store this date and time, and going forward only download the file if this value is updated to a later date and time.<br/><br/>The value is in Coordinated Universal Time (UTC). The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetGeoLocationsFileUrl</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetGeoLocationsFileUrlRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Version i:nil="false">ValueHere</Version>
      <LanguageLocale i:nil="false">ValueHere</LanguageLocale>
    </GetGeoLocationsFileUrlRequest>
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
    <GetGeoLocationsFileUrlResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <FileUrl d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrl>
      <FileUrlExpiryTimeUtc d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrlExpiryTimeUtc>
      <LastModifiedTimeUtc>ValueHere</LastModifiedTimeUtc>
    </GetGeoLocationsFileUrlResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetGeoLocationsFileUrlResponse> GetGeoLocationsFileUrlAsync(
	string version,
	string languageLocale)
{
	var request = new GetGeoLocationsFileUrlRequest
	{
		Version = version,
		LanguageLocale = languageLocale
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetGeoLocationsFileUrlAsync(r), request));
}
```
```java
static GetGeoLocationsFileUrlResponse getGeoLocationsFileUrl(
	java.lang.String version,
	java.lang.String languageLocale) throws RemoteException, Exception
{
	GetGeoLocationsFileUrlRequest request = new GetGeoLocationsFileUrlRequest();

	request.setVersion(version);
	request.setLanguageLocale(languageLocale);

	return CampaignManagementService.getService().getGeoLocationsFileUrl(request);
}
```
```php
static function GetGeoLocationsFileUrl(
	$version,
	$languageLocale)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetGeoLocationsFileUrlRequest();

	$request->Version = $version;
	$request->LanguageLocale = $languageLocale;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetGeoLocationsFileUrl($request);
}
```
```python
response=campaignmanagement_service.GetGeoLocationsFileUrl(
	Version=Version,
	LanguageLocale=LanguageLocale)
```

## Requirements
Service: [CampaignManagementService.svc v12](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

