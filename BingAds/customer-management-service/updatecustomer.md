---
title: UpdateCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
ms.date: 11/1/2017
author: eric-urban
ms.author: eur
description: Updates the details of the specified customer.
---
# UpdateCustomer Service Operation - Customer Management
Updates the details of the specified customer.

## <a name="request"></a>Request Elements
The *UpdateCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customer"></a>Customer|A customer object that contains the updated customer information.<br /><br />This operation overwrites the existing customer data with the contents of the customer object that you pass. This operation performs a full update, and not a partial update. The *Customer* object must contain the time stamp value from the last time that the *Customer* object was written to. To ensure that the time stamp contains the correct value, call the [GetCustomer](../customer-management-service/getcustomer.md) operation. You can then update the customer data as appropriate, and call *UpdateCustomer*.|[Customer](customer.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the customer was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">UpdateCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Customer xmlns:e48="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e48:CustomerAddress i:nil="false">
          <e48:City i:nil="false">ValueHere</e48:City>
          <e48:CountryCode i:nil="false">ValueHere</e48:CountryCode>
          <e48:Id i:nil="false">ValueHere</e48:Id>
          <e48:Line1 i:nil="false">ValueHere</e48:Line1>
          <e48:Line2 i:nil="false">ValueHere</e48:Line2>
          <e48:Line3 i:nil="false">ValueHere</e48:Line3>
          <e48:Line4 i:nil="false">ValueHere</e48:Line4>
          <e48:PostalCode i:nil="false">ValueHere</e48:PostalCode>
          <e48:StateOrProvince i:nil="false">ValueHere</e48:StateOrProvince>
          <e48:TimeStamp i:nil="false">ValueHere</e48:TimeStamp>
        </e48:CustomerAddress>
        <e48:CustomerFinancialStatus i:nil="false">ValueHere</e48:CustomerFinancialStatus>
        <e48:Id i:nil="false">ValueHere</e48:Id>
        <e48:Industry i:nil="false">ValueHere</e48:Industry>
        <e48:LastModifiedByUserId i:nil="false">ValueHere</e48:LastModifiedByUserId>
        <e48:LastModifiedTime i:nil="false">ValueHere</e48:LastModifiedTime>
        <e48:MarketCountry i:nil="false">ValueHere</e48:MarketCountry>
        <ForwardCompatibilityMap xmlns:e49="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e49:KeyValuePairOfstringstring>
            <e49:key i:nil="false">ValueHere</e49:key>
            <e49:value i:nil="false">ValueHere</e49:value>
          </e49:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e48:MarketLanguage i:nil="false">ValueHere</e48:MarketLanguage>
        <e48:Name i:nil="false">ValueHere</e48:Name>
        <e48:ServiceLevel i:nil="false">ValueHere</e48:ServiceLevel>
        <e48:CustomerLifeCycleStatus i:nil="false">ValueHere</e48:CustomerLifeCycleStatus>
        <e48:TimeStamp i:nil="false">ValueHere</e48:TimeStamp>
        <e48:Number i:nil="false">ValueHere</e48:Number>
      </Customer>
    </UpdateCustomerRequest>
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
    <UpdateCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateCustomerResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateCustomerResponse> UpdateCustomerAsync(
	Customer customer)
{
	var request = new UpdateCustomerRequest
	{
		Customer = customer
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.UpdateCustomerAsync(r), request));
}
```
```java
static UpdateCustomerResponse updateCustomer(
	Customer customer) throws RemoteException, Exception
{
	UpdateCustomerRequest request = new UpdateCustomerRequest();

	request.setCustomer(customer);

	return CustomerManagementService.getService().updateCustomer(request);
}
```
```php
static function UpdateCustomer(
	$customer)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new UpdateCustomerRequest();

	$request->Customer = $customer;

	return $GLOBALS['CustomerManagementProxy']->GetService()->UpdateCustomer($request);
}
```
```python
response=customermanagement.UpdateCustomer(
	Customer=Customer)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

