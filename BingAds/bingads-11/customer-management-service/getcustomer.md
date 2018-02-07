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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">GetCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <CustomerId>ValueHere</CustomerId>
    </GetCustomerRequest>
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
    <GetCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <Customer xmlns:e317="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e317:CustomerAddress d4p1:nil="false">
          <e317:City d4p1:nil="false">ValueHere</e317:City>
          <e317:CountryCode d4p1:nil="false">ValueHere</e317:CountryCode>
          <e317:Id d4p1:nil="false">ValueHere</e317:Id>
          <e317:Line1 d4p1:nil="false">ValueHere</e317:Line1>
          <e317:Line2 d4p1:nil="false">ValueHere</e317:Line2>
          <e317:Line3 d4p1:nil="false">ValueHere</e317:Line3>
          <e317:Line4 d4p1:nil="false">ValueHere</e317:Line4>
          <e317:PostalCode d4p1:nil="false">ValueHere</e317:PostalCode>
          <e317:StateOrProvince d4p1:nil="false">ValueHere</e317:StateOrProvince>
          <e317:TimeStamp d4p1:nil="false">ValueHere</e317:TimeStamp>
        </e317:CustomerAddress>
        <e317:CustomerFinancialStatus d4p1:nil="false">ValueHere</e317:CustomerFinancialStatus>
        <e317:Id d4p1:nil="false">ValueHere</e317:Id>
        <e317:Industry d4p1:nil="false">ValueHere</e317:Industry>
        <e317:LastModifiedByUserId d4p1:nil="false">ValueHere</e317:LastModifiedByUserId>
        <e317:LastModifiedTime d4p1:nil="false">ValueHere</e317:LastModifiedTime>
        <e317:MarketCountry d4p1:nil="false">ValueHere</e317:MarketCountry>
        <ForwardCompatibilityMap xmlns:e318="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e318:KeyValuePairOfstringstring>
            <e318:key d4p1:nil="false">ValueHere</e318:key>
            <e318:value d4p1:nil="false">ValueHere</e318:value>
          </e318:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e317:MarketLanguage d4p1:nil="false">ValueHere</e317:MarketLanguage>
        <e317:Name d4p1:nil="false">ValueHere</e317:Name>
        <e317:ServiceLevel d4p1:nil="false">ValueHere</e317:ServiceLevel>
        <e317:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e317:CustomerLifeCycleStatus>
        <e317:TimeStamp d4p1:nil="false">ValueHere</e317:TimeStamp>
        <e317:Number d4p1:nil="false">ValueHere</e317:Number>
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
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

