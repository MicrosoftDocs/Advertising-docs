---
title: UpdateCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the details of the specified customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# UpdateCustomer Service Operation - Customer Management
Updates the details of the specified customer.

## <a name="request"></a>Request Elements
The *UpdateCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customer"></a>Customer|A customer object that contains the updated customer information.<br/><br/>This operation overwrites the existing customer data with the contents of the customer object that you pass. This operation performs a full update, and not a partial update. The *Customer* object must contain the time stamp value from the last time that the *Customer* object was written to. To ensure that the time stamp contains the correct value, call the [GetCustomer](getcustomer.md) operation. You can then update the customer data as appropriate, and call *UpdateCustomer*.|[Customer](customer.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the customer was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/>The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

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
      <Customer xmlns:e354="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e354:CustomerAddress i:nil="false">
          <e354:City i:nil="false">ValueHere</e354:City>
          <e354:CountryCode i:nil="false">ValueHere</e354:CountryCode>
          <e354:Id i:nil="false">ValueHere</e354:Id>
          <e354:Line1 i:nil="false">ValueHere</e354:Line1>
          <e354:Line2 i:nil="false">ValueHere</e354:Line2>
          <e354:Line3 i:nil="false">ValueHere</e354:Line3>
          <e354:Line4 i:nil="false">ValueHere</e354:Line4>
          <e354:PostalCode i:nil="false">ValueHere</e354:PostalCode>
          <e354:StateOrProvince i:nil="false">ValueHere</e354:StateOrProvince>
          <e354:TimeStamp i:nil="false">ValueHere</e354:TimeStamp>
        </e354:CustomerAddress>
        <e354:CustomerFinancialStatus i:nil="false">ValueHere</e354:CustomerFinancialStatus>
        <e354:Id i:nil="false">ValueHere</e354:Id>
        <e354:Industry i:nil="false">ValueHere</e354:Industry>
        <e354:LastModifiedByUserId i:nil="false">ValueHere</e354:LastModifiedByUserId>
        <e354:LastModifiedTime i:nil="false">ValueHere</e354:LastModifiedTime>
        <e354:MarketCountry i:nil="false">ValueHere</e354:MarketCountry>
        <ForwardCompatibilityMap xmlns:e355="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e355:KeyValuePairOfstringstring>
            <e355:key i:nil="false">ValueHere</e355:key>
            <e355:value i:nil="false">ValueHere</e355:value>
          </e355:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e354:MarketLanguage i:nil="false">ValueHere</e354:MarketLanguage>
        <e354:Name i:nil="false">ValueHere</e354:Name>
        <e354:ServiceLevel i:nil="false">ValueHere</e354:ServiceLevel>
        <e354:CustomerLifeCycleStatus i:nil="false">ValueHere</e354:CustomerLifeCycleStatus>
        <e354:TimeStamp i:nil="false">ValueHere</e354:TimeStamp>
        <e354:Number i:nil="false">ValueHere</e354:Number>
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
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
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
response=customermanagement_service.UpdateCustomer(
	Customer=Customer)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

