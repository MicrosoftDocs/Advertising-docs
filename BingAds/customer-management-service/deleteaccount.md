---
title: DeleteAccount Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Deletes an account.
---
# DeleteAccount Service Operation - Customer Management
Deletes an account.

> [!NOTE]
> After deleting the account it will be searchable and show as inactive in the Bing Ads web application. You may or may not choose to surface inactive accounts in your application.

## <a name="request"></a>Request Elements
The *DeleteAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account to delete.|**long**|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the operation uses to reconcile the update. You must call  [GetAccount](../customer-management-service/getaccount.md) to get the time-stamp value. The delete operation fails if the account object has a time-stamp value that differs from the one that you pass.|**base64Binary**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements
There are not any elements in the operation's response body.

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">DeleteAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteAccountRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <AccountId>ValueHere</AccountId>
      <TimeStamp i:nil="false">ValueHere</TimeStamp>
    </DeleteAccountRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DeleteAccountResponse xmlns="https://bingads.microsoft.com/Customer/v11" />
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteAccountResponse> DeleteAccountAsync(
	long accountId,
	base64Binary timeStamp)
{
	var request = new DeleteAccountRequest
	{
		AccountId = accountId,
		TimeStamp = timeStamp
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.DeleteAccountAsync(r), request));
}
```
```java
static DeleteAccountResponse deleteAccount(
	java.lang.Long accountId,
	byte[] timeStamp) throws RemoteException, Exception
{
	DeleteAccountRequest request = new DeleteAccountRequest();

	request.setAccountId(accountId);
	request.setTimeStamp(timeStamp);

	return CustomerManagementService.getService().deleteAccount(request);
}
```
```php
static function DeleteAccount(
	$accountId,
	$timeStamp)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new DeleteAccountRequest();

	$request->AccountId = $accountId;
	$request->TimeStamp = $timeStamp;

	return $GLOBALS['CustomerManagementProxy']->GetService()->DeleteAccount($request);
}
```
```python
response=customermanagement_service.DeleteAccount(
	AccountId=AccountId,
	TimeStamp=TimeStamp)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

