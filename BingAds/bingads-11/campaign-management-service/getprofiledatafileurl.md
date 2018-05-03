---
title: GetProfileDataFileUrl Service Operation - Campaign Management
ms.service: bing-ads-campaign-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a temporary URL that you can use to download company name, industry, or job function profile data.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetProfileDataFileUrl Service Operation - Campaign Management
Gets a temporary URL that you can use to download company name, industry, or job function profile data.

For details about the file contents, see [Profile Data Files](../guides/profile-data-files.md).

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

> [!NOTE]
> You must specify the account identifier in the *CustomerAccountId* header element.

## <a name="request"></a>Request Elements
The *GetProfileDataFileUrlRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="languagelocale"></a>LanguageLocale|The language and locale of the profile display names.<br/><br/>Currently the only supported language is *en* (English).<br/><br/>This request element is required.|**string**|
|<a name="profiletype"></a>ProfileType|Determines whether you want company name, industry, or job function profile data.<br/><br/>This request element is required.|[ProfileType](profiletype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetProfileDataFileUrlResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="fileurl"></a>FileUrl|The file URL that you can use to download the profile data for the profile type, language, and locale that you requested.<br/><br/>Before you download the file, check whether the date and time of the *LastModifiedTimeUtc* element is later than the date and time of your previous download. You should only download the file if necessary.|**string**|
|<a name="fileurlexpirytimeutc"></a>FileUrlExpiryTimeUtc|The date and time that the provided file URL will expire.<br/><br/>If you do not download the file prior to the expiration time, then you can call the operation again to request a new file URL. You might observe that the URL is set to expire 15 minutes from the time this operation completes; however, you should not depend on a fixed duration. Future calls to this operation might result in a shorter or longer expiration time. <br/><br/>The value is in Coordinated Universal Time (UTC). The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="lastmodifiedtimeutc"></a>LastModifiedTimeUtc|The date and time that the profile data for the profile type, language, and locale was last updated.<br/><br/>As a best practice you should store this date and time, and going forward only download the file if this value is updated to a later date and time.<br/><br/>The value is in Coordinated Universal Time (UTC). The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetProfileDataFileUrl</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetProfileDataFileUrlRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <LanguageLocale i:nil="false">ValueHere</LanguageLocale>
      <ProfileType>ValueHere</ProfileType>
    </GetProfileDataFileUrlRequest>
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
    <GetProfileDataFileUrlResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <FileUrl d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrl>
      <FileUrlExpiryTimeUtc d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</FileUrlExpiryTimeUtc>
      <LastModifiedTimeUtc>ValueHere</LastModifiedTimeUtc>
    </GetProfileDataFileUrlResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetProfileDataFileUrlResponse> GetProfileDataFileUrlAsync(
	string languageLocale,
	ProfileType profileType)
{
	var request = new GetProfileDataFileUrlRequest
	{
		LanguageLocale = languageLocale,
		ProfileType = profileType
	};

	return (await CampaignManagementService.CallAsync((s, r) => s.GetProfileDataFileUrlAsync(r), request));
}
```
```java
static GetProfileDataFileUrlResponse getProfileDataFileUrl(
	java.lang.String languageLocale,
	ArrayList<ProfileType> profileType) throws RemoteException, Exception
{
	GetProfileDataFileUrlRequest request = new GetProfileDataFileUrlRequest();

	request.setLanguageLocale(languageLocale);
	request.setProfileType(profileType);

	return CampaignManagementService.getService().getProfileDataFileUrl(request);
}
```
```php
static function GetProfileDataFileUrl(
	$languageLocale,
	$profileType)
{

	$GLOBALS['Proxy'] = $GLOBALS['CampaignManagementProxy'];

	$request = new GetProfileDataFileUrlRequest();

	$request->LanguageLocale = $languageLocale;
	$request->ProfileType = $profileType;

	return $GLOBALS['CampaignManagementProxy']->GetService()->GetProfileDataFileUrl($request);
}
```
```python
response=campaignmanagement_service.GetProfileDataFileUrl(
	LanguageLocale=LanguageLocale,
	ProfileType=ProfileType)
```

## Requirements
Service: [CampaignManagementService.svc v11](https://campaign.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/CampaignManagementService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

