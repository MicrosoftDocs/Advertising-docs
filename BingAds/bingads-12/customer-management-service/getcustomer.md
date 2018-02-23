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

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

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
      <Customer xmlns:e682="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e682:CustomerAddress d4p1:nil="false">
          <e682:City d4p1:nil="false">ValueHere</e682:City>
          <e682:CountryCode d4p1:nil="false">ValueHere</e682:CountryCode>
          <e682:Id d4p1:nil="false">ValueHere</e682:Id>
          <e682:Line1 d4p1:nil="false">ValueHere</e682:Line1>
          <e682:Line2 d4p1:nil="false">ValueHere</e682:Line2>
          <e682:Line3 d4p1:nil="false">ValueHere</e682:Line3>
          <e682:Line4 d4p1:nil="false">ValueHere</e682:Line4>
          <e682:PostalCode d4p1:nil="false">ValueHere</e682:PostalCode>
          <e682:StateOrProvince d4p1:nil="false">ValueHere</e682:StateOrProvince>
          <e682:TimeStamp d4p1:nil="false">ValueHere</e682:TimeStamp>
        </e682:CustomerAddress>
        <e682:CustomerFinancialStatus d4p1:nil="false">ValueHere</e682:CustomerFinancialStatus>
        <e682:Id d4p1:nil="false">ValueHere</e682:Id>
        <e682:Industry d4p1:nil="false">ValueHere</e682:Industry>
        <e682:LastModifiedByUserId d4p1:nil="false">ValueHere</e682:LastModifiedByUserId>
        <e682:LastModifiedTime d4p1:nil="false">ValueHere</e682:LastModifiedTime>
        <e682:MarketCountry d4p1:nil="false">ValueHere</e682:MarketCountry>
        <ForwardCompatibilityMap xmlns:e683="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e683:KeyValuePairOfstringstring>
            <e683:key d4p1:nil="false">ValueHere</e683:key>
            <e683:value d4p1:nil="false">ValueHere</e683:value>
          </e683:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e682:MarketLanguage d4p1:nil="false">ValueHere</e682:MarketLanguage>
        <e682:Name d4p1:nil="false">ValueHere</e682:Name>
        <e682:ServiceLevel d4p1:nil="false">ValueHere</e682:ServiceLevel>
        <e682:CustomerLifeCycleStatus d4p1:nil="false">ValueHere</e682:CustomerLifeCycleStatus>
        <e682:TimeStamp d4p1:nil="false">ValueHere</e682:TimeStamp>
        <e682:Number d4p1:nil="false">ValueHere</e682:Number>
      </Customer>
    </GetCustomerResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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

