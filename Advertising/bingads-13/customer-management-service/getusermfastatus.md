---
title: GetUserMFAStatus Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Determines whether or not the user credentials have been obtained by passing through multi-factor authentication.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetUserMFAStatus Service Operation - Customer Management
Determines whether or not the user credentials have been obtained by passing through multi-factor authentication (MFA). 

> [!IMPORTANT]
> Starting April 1st, the Bing Ads API, Content API, and Hotel APIs will return an error (115; AuthenticationTokenNotAuthorized) for any user credentials that have not passed through MFA. All access and refresh tokens that were provisioned without passing through MFA will be invalid as soon as the MFA requirement is enforced. By this time you must have access and refresh tokens for a user who granted consent to your application via MFA.
> 
> Prior to enforcement of the MFA requirement, you should request all users to [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature). Optionally you can require that the user pass through MFA immediately by including the MFA parameter when prompting them for consent via the Microsoft Identity endpoint (recommended).
> 
> No action is required if the user granted consent to your application after they had set up MFA. Access and refresh tokens obtained after the user [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature) will continue to be honored even after the MFA requirement is enforced. 

If this operation returns *true*, the user credentials (current access token) had been obtained by passing through MFA. If this operation returns *false*, the user could have already [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature), but has not passed through MFA while granting consent to your application. For example, the user could have granted consent to your application before they had [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature). 

Here are example scenarios for arbitrary dates prior to enforcement of the MFA requirement:

- On January 1st the user [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature). On January 2nd your application requested access to their Microsoft Advertising accounts. Whether your application requests consent via Live connect or Microsoft Identity endpoint, they are automatically routed through the MFA consent flow. When you use the resulting access token this operation returns *true* and there is no further action required. 
- On January 1st the user had not yet [set up MFA](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time#who-decides-if-you-use-this-feature), and in the same state they granted consent for your application to access their Microsoft Advertising accounts. You can use the provisioned access token for any API request and this operation returns *false*. You can continue refreshing the access token and subsequent calls to the API will succeed until MFA is enforced. Even if contoso_two@outlook.com turns on MFA after February 1st, the access tokens that you obtained on their behalf will fail until they pass through MFA while granting consent to your application. 

## <a name="request"></a>Request Elements
The *GetUserMFAStatusRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements
There are not any elements in the operation's request body.

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetUserMFAStatusResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="mfastatus"></a>MFAStatus|Determines whether or not the user credentials have been obtained by passing through multi-factor authentication.<br/><br/>If this operation returns *true*, the user credentials (current access token) had been obtained by passing through multi-factor authentication. Otherwise this value is *false*.|**boolean**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">GetUserMFAStatus</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetUserMFAStatusRequest xmlns="https://bingads.microsoft.com/Customer/v13" />
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetUserMFAStatusResponse xmlns="https://bingads.microsoft.com/Customer/v13">
      <MFAStatus>ValueHere</MFAStatus>
    </GetUserMFAStatusResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetUserMFAStatusResponse> GetUserMFAStatusAsync()
{
	var request = new GetUserMFAStatusRequest
	{
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetUserMFAStatusAsync(r), request));
}
```
```java
static GetUserMFAStatusResponse getUserMFAStatus() throws RemoteException, Exception
{
	GetUserMFAStatusRequest request = new GetUserMFAStatusRequest();


	return CustomerManagementService.getService().getUserMFAStatus(request);
}
```
```php
static function GetUserMFAStatus()
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetUserMFAStatusRequest();


	return $GLOBALS['CustomerManagementProxy']->GetService()->GetUserMFAStatus($request);
}
```
```python
response=customermanagement_service.GetUserMFAStatus()
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

