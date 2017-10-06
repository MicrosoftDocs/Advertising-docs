---
title: DeleteUser Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Deletes a user.
---
# DeleteUser Service Operation
Deletes a user.

## <a name="request"></a>Request Elements
The *DeleteUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="userid"></a>UserId|The identifier of the user to delete.|**long**|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the operation uses to reconcile the update. You must call  [GetUser](../customer-management-service/getuser.md) to get the time-stamp value. The delete operation fails if the user object has a time-stamp value that differs from the one that you pass.|**base64Binary**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">DeleteUser</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteUserRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <UserId>ValueHere</UserId>
      <TimeStamp i:nil="false">ValueHere</TimeStamp>
    </DeleteUserRequest>
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
    <DeleteUserResponse xmlns="https://bingads.microsoft.com/Customer/v11" />
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<DeleteUserResponse> DeleteUserAsync(
	long userId,
	base64Binary timeStamp)
{
	var request = new DeleteUserRequest
	{
		UserId = userId,
		TimeStamp = timeStamp
	};

	return (await CustomerManagement.CallAsync((s, r) => s.DeleteUserAsync(r), request));
}
```
```java
static DeleteUserResponse deleteUser(
	long userId,
	base64Binary timeStamp) throws RemoteException, Exception
{
	DeleteUserRequest request = new DeleteUserRequest();

	request.setUserId(userId);
	request.setTimeStamp(timeStamp);

	return CustomerManagement.getService().deleteUser(request);
}
```
```php
static function DeleteUser(
	$userId,
	$timeStamp)

	$deleteUserRequest = new DeleteUserRequest();

	$request->UserId = $userId;
	$request->TimeStamp = $timeStamp;

	return $CustomerManagementProxy->GetService()->DeleteUser($request);
}
```
```python
response=customermanagement.DeleteUser(
	UserId=UserIdHere,
	TimeStamp=TimeStampHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

