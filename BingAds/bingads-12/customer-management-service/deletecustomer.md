---
title: DeleteCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Deletes a customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DeleteCustomer Service Operation - Customer Management
Deletes a customer.

## <a name="request"></a>Request Elements
The *DeleteCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|The identifier of the customer to delete.|**long**|
|<a name="timestamp"></a>TimeStamp|The time-stamp value that the operation uses to reconcile the update. You must call  [GetCustomer](getcustomer.md) to get the time-stamp value. The delete operation fails if the customer object has a time-stamp value that differs from the one that you pass.|**base64Binary**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DeleteCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements
There are not any elements in the operation's response body.

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">DeleteCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DeleteCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <CustomerId>ValueHere</CustomerId>
      <TimeStamp i:nil="false">ValueHere</TimeStamp>
    </DeleteCustomerRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DeleteCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v12" />
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DeleteCustomerResponse> DeleteCustomerAsync(
	long customerId,
	base64Binary timeStamp)
{
	var request = new DeleteCustomerRequest
	{
		CustomerId = customerId,
		TimeStamp = timeStamp
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.DeleteCustomerAsync(r), request));
}
```
```java
static DeleteCustomerResponse deleteCustomer(
	java.lang.Long customerId,
	byte[] timeStamp) throws RemoteException, Exception
{
	DeleteCustomerRequest request = new DeleteCustomerRequest();

	request.setCustomerId(customerId);
	request.setTimeStamp(timeStamp);

	return CustomerManagementService.getService().deleteCustomer(request);
}
```
```php
static function DeleteCustomer(
	$customerId,
	$timeStamp)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new DeleteCustomerRequest();

	$request->CustomerId = $customerId;
	$request->TimeStamp = $timeStamp;

	return $GLOBALS['CustomerManagementProxy']->GetService()->DeleteCustomer($request);
}
```
```python
response=customermanagement_service.DeleteCustomer(
	CustomerId=CustomerId,
	TimeStamp=TimeStamp)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

