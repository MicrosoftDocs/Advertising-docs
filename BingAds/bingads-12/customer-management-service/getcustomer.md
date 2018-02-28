---
title: GetCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of a customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# GetCustomer Service Operation - Customer Management
Gets the details of a customer.

## <a name="request"></a>Request Elements
The *GetCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|The identifier of the customer whose information you want to get.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customer"></a>Customer|A *Customer* object that contains information about the customer.|[Customer](customer.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">GetCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <CustomerId>ValueHere</CustomerId>
    </GetCustomerRequest>
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
    <GetCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <Customer xmlns:e324="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e324:CustomerAddress d4p1:nil="false">
          <e324:City d4p1:nil="false">ValueHere</e324:City>
          <e324:CountryCode d4p1:nil="false">ValueHere</e324:CountryCode>
          <e324:Id d4p1:nil="false">ValueHere</e324:Id>
          <e324:Line1 d4p1:nil="false">ValueHere</e324:Line1>
          <e324:Line2 d4p1:nil="false">ValueHere</e324:Line2>
          <e324:Line3 d4p1:nil="false">ValueHere</e324:Line3>
          <e324:Line4 d4p1:nil="false">ValueHere</e324:Line4>
          <e324:PostalCode d4p1:nil="false">ValueHere</e324:PostalCode>
          <e324:StateOrProvince d4p1:nil="false">ValueHere</e324:StateOrProvince>
          <e324:TimeStamp d4p1:nil="false">ValueHere</e324:TimeStamp>
        </e324:CustomerAddress>
        <e324:CustomerFinancialStatus d4p1:nil="false">ValueHere</e324:CustomerFinancialStatus>
        <e324:Id d4p1:nil="false">ValueHere</e324:Id>
        <e324:Industry d4p1:nil="false">ValueHere</e324:Industry>
        <e324:LastModifiedByUserId d4p1:nil="false">ValueHere</e324:LastModifiedByUserId>
        <e324:LastModifiedTime d4p1:nil="false">ValueHere</e324:LastModifiedTime>
        <e324:MarketCountry d4p1:nil="false">ValueHere</e324:MarketCountry>
        <ForwardCompatibilityMap xmlns:e325="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e325:KeyValuePairOfstringstring>
            <e325:key d4p1:nil="false">ValueHere</e325:key>
            <e325:value d4p1:nil="false">ValueHere</e325:value>
          </e325:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e324:MarketLanguage d4p1:nil="false">ValueHere</e324:MarketLanguage>
        <e324:Name d4p1:nil="false">ValueHere</e324:Name>
        <e324:ServiceLevel d4p1:nil="false">ValueHere</e324:ServiceLevel>
        <e324:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e324:CustomerLifeCycleStatus>
        <e324:TimeStamp d4p1:nil="false">ValueHere</e324:TimeStamp>
        <e324:Number d4p1:nil="false">ValueHere</e324:Number>
      </Customer>
    </GetCustomerResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetCustomerResponse> GetCustomerAsync(
	long customerId)
{
	var request = new GetCustomerRequest
	{
		CustomerId = customerId
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetCustomerAsync(r), request));
}
```
```java
static GetCustomerResponse getCustomer(
	java.lang.Long customerId) throws RemoteException, Exception
{
	GetCustomerRequest request = new GetCustomerRequest();

	request.setCustomerId(customerId);

	return CustomerManagementService.getService().getCustomer(request);
}
```
```php
static function GetCustomer(
	$customerId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetCustomerRequest();

	$request->CustomerId = $customerId;

	return $GLOBALS['CustomerManagementProxy']->GetService()->GetCustomer($request);
}
```
```python
response=customermanagement_service.GetCustomer(
	CustomerId=CustomerId)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

