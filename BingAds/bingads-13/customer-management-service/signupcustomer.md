---
title: SignupCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Creates a new customer and account that rolls up to your reseller payment method.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# SignupCustomer Service Operation - Customer Management
Creates a new customer and account that rolls up to your reseller payment method.

> [!NOTE]
> You must be a reseller with aggregator user permissions to call this operation. For more details see [Management Model for Resellers](../guides/management-model-resellers.md).

Pass both [Customer](customer.md) and [AdvertiserAccount](advertiseraccount.md) objects in the request. The customer object includes the customer's name, the address where the customer is located, the market in which the customer operates, and the industry in which the customer participates. Although it is possible to add multiple customers with the same details, you should use unique customer names so that users can easily distinguish between customers in a user interface.

The account object must specify the name of the account; the type of currency to use to settle the account; and the payment method identifier, which must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the reseller's invoice. You are invoiced for all charges incurred by the customers that you manage.

If the operation succeeds, a new managed customer is created outside of the reseller customer and an account is created within the managed customer. 

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [AdvertiserAccount](advertiseraccount.md) that specifies the details of the customer's primary account.|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
|<a name="parentcustomerid"></a>ParentCustomerId|The customer identifier of the reseller that will manage this customer.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SignupCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|A system-generated account identifier corresponding to the new account specified in the request.<br/><br/>Use this identifier with operation requests that require an *AccountId* element and a *CustomerAccountId* SOAP header element.|**long**|
|<a name="accountnumber"></a>AccountNumber|A system-generated account number that is used to identify the account in the Bing Ads web application. The account number has the form, X*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|
|<a name="createtime"></a>CreateTime|The date and time that the account was added. The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="customerid"></a>CustomerId|A system-generated customer identifier corresponding to the new customer specified in the request.<br/><br/>Use this identifier with operation requests that require a *CustomerId* SOAP header element.|**long**|
|<a name="customernumber"></a>CustomerNumber|A system-generated customer number that is used in the Bing Ads web application. The customer number is of the form, C*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">SignupCustomer</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SignupCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <Customer xmlns:e1486="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e1486:CustomerFinancialStatus i:nil="false">ValueHere</e1486:CustomerFinancialStatus>
        <e1486:Id i:nil="false">ValueHere</e1486:Id>
        <e1486:Industry i:nil="false">ValueHere</e1486:Industry>
        <e1486:LastModifiedByUserId i:nil="false">ValueHere</e1486:LastModifiedByUserId>
        <e1486:LastModifiedTime i:nil="false">ValueHere</e1486:LastModifiedTime>
        <e1486:MarketCountry i:nil="false">ValueHere</e1486:MarketCountry>
        <e1486:ForwardCompatibilityMap xmlns:e1487="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1487:KeyValuePairOfstringstring>
            <e1487:key i:nil="false">ValueHere</e1487:key>
            <e1487:value i:nil="false">ValueHere</e1487:value>
          </e1487:KeyValuePairOfstringstring>
        </e1486:ForwardCompatibilityMap>
        <e1486:MarketLanguage i:nil="false">ValueHere</e1486:MarketLanguage>
        <e1486:Name i:nil="false">ValueHere</e1486:Name>
        <e1486:ServiceLevel i:nil="false">ValueHere</e1486:ServiceLevel>
        <e1486:CustomerLifeCycleStatus i:nil="false">ValueHere</e1486:CustomerLifeCycleStatus>
        <e1486:TimeStamp i:nil="false">ValueHere</e1486:TimeStamp>
        <e1486:Number i:nil="false">ValueHere</e1486:Number>
        <e1486:CustomerAddress i:nil="false">
          <e1486:City i:nil="false">ValueHere</e1486:City>
          <e1486:CountryCode i:nil="false">ValueHere</e1486:CountryCode>
          <e1486:Id i:nil="false">ValueHere</e1486:Id>
          <e1486:Line1 i:nil="false">ValueHere</e1486:Line1>
          <e1486:Line2 i:nil="false">ValueHere</e1486:Line2>
          <e1486:Line3 i:nil="false">ValueHere</e1486:Line3>
          <e1486:Line4 i:nil="false">ValueHere</e1486:Line4>
          <e1486:PostalCode i:nil="false">ValueHere</e1486:PostalCode>
          <e1486:StateOrProvince i:nil="false">ValueHere</e1486:StateOrProvince>
          <e1486:TimeStamp i:nil="false">ValueHere</e1486:TimeStamp>
          <e1486:BusinessName i:nil="false">ValueHere</e1486:BusinessName>
        </e1486:CustomerAddress>
      </Customer>
      <Account xmlns:e1488="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e1488:BillToCustomerId i:nil="false">ValueHere</e1488:BillToCustomerId>
        <e1488:CurrencyCode i:nil="false">ValueHere</e1488:CurrencyCode>
        <e1488:AccountFinancialStatus i:nil="false">ValueHere</e1488:AccountFinancialStatus>
        <e1488:Id i:nil="false">ValueHere</e1488:Id>
        <e1488:Language i:nil="false">ValueHere</e1488:Language>
        <e1488:LastModifiedByUserId i:nil="false">ValueHere</e1488:LastModifiedByUserId>
        <e1488:LastModifiedTime i:nil="false">ValueHere</e1488:LastModifiedTime>
        <e1488:Name i:nil="false">ValueHere</e1488:Name>
        <e1488:Number i:nil="false">ValueHere</e1488:Number>
        <e1488:ParentCustomerId>ValueHere</e1488:ParentCustomerId>
        <e1488:PaymentMethodId i:nil="false">ValueHere</e1488:PaymentMethodId>
        <e1488:PaymentMethodType i:nil="false">ValueHere</e1488:PaymentMethodType>
        <e1488:PrimaryUserId i:nil="false">ValueHere</e1488:PrimaryUserId>
        <e1488:AccountLifeCycleStatus i:nil="false">ValueHere</e1488:AccountLifeCycleStatus>
        <e1488:TimeStamp i:nil="false">ValueHere</e1488:TimeStamp>
        <e1488:TimeZone i:nil="false">ValueHere</e1488:TimeZone>
        <e1488:PauseReason i:nil="false">ValueHere</e1488:PauseReason>
        <e1488:ForwardCompatibilityMap xmlns:e1489="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1489:KeyValuePairOfstringstring>
            <e1489:key i:nil="false">ValueHere</e1489:key>
            <e1489:value i:nil="false">ValueHere</e1489:value>
          </e1489:KeyValuePairOfstringstring>
        </e1488:ForwardCompatibilityMap>
        <e1488:LinkedAgencies i:nil="false">
          <e1488:CustomerInfo>
            <e1488:Id i:nil="false">ValueHere</e1488:Id>
            <e1488:Name i:nil="false">ValueHere</e1488:Name>
          </e1488:CustomerInfo>
        </e1488:LinkedAgencies>
        <e1488:SalesHouseCustomerId i:nil="false">ValueHere</e1488:SalesHouseCustomerId>
        <e1488:TaxInformation xmlns:e1490="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1490:KeyValuePairOfstringstring>
            <e1490:key i:nil="false">ValueHere</e1490:key>
            <e1490:value i:nil="false">ValueHere</e1490:value>
          </e1490:KeyValuePairOfstringstring>
        </e1488:TaxInformation>
        <e1488:BackUpPaymentInstrumentId i:nil="false">ValueHere</e1488:BackUpPaymentInstrumentId>
        <e1488:BillingThresholdAmount i:nil="false">ValueHere</e1488:BillingThresholdAmount>
        <e1488:BusinessAddress i:nil="false">
          <e1488:City i:nil="false">ValueHere</e1488:City>
          <e1488:CountryCode i:nil="false">ValueHere</e1488:CountryCode>
          <e1488:Id i:nil="false">ValueHere</e1488:Id>
          <e1488:Line1 i:nil="false">ValueHere</e1488:Line1>
          <e1488:Line2 i:nil="false">ValueHere</e1488:Line2>
          <e1488:Line3 i:nil="false">ValueHere</e1488:Line3>
          <e1488:Line4 i:nil="false">ValueHere</e1488:Line4>
          <e1488:PostalCode i:nil="false">ValueHere</e1488:PostalCode>
          <e1488:StateOrProvince i:nil="false">ValueHere</e1488:StateOrProvince>
          <e1488:TimeStamp i:nil="false">ValueHere</e1488:TimeStamp>
          <e1488:BusinessName i:nil="false">ValueHere</e1488:BusinessName>
        </e1488:BusinessAddress>
        <e1488:AutoTagType i:nil="false">ValueHere</e1488:AutoTagType>
        <e1488:SoldToPaymentInstrumentId i:nil="false">ValueHere</e1488:SoldToPaymentInstrumentId>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
    </SignupCustomerRequest>
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
    <SignupCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v13">
      <CustomerId>ValueHere</CustomerId>
      <CustomerNumber d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</CustomerNumber>
      <AccountId d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</AccountId>
      <AccountNumber d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</AccountNumber>
      <CreateTime>ValueHere</CreateTime>
    </SignupCustomerResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SignupCustomerResponse> SignupCustomerAsync(
	Customer customer,
	AdvertiserAccount account,
	long? parentCustomerId)
{
	var request = new SignupCustomerRequest
	{
		Customer = customer,
		Account = account,
		ParentCustomerId = parentCustomerId
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SignupCustomerAsync(r), request));
}
```
```java
static SignupCustomerResponse signupCustomer(
	Customer customer,
	AdvertiserAccount account,
	java.lang.Long parentCustomerId) throws RemoteException, Exception
{
	SignupCustomerRequest request = new SignupCustomerRequest();

	request.setCustomer(customer);
	request.setAccount(account);
	request.setParentCustomerId(parentCustomerId);

	return CustomerManagementService.getService().signupCustomer(request);
}
```
```php
static function SignupCustomer(
	$customer,
	$account,
	$parentCustomerId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SignupCustomerRequest();

	$request->Customer = $customer;
	$request->Account = $account;
	$request->ParentCustomerId = $parentCustomerId;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SignupCustomer($request);
}
```
```python
response=customermanagement_service.SignupCustomer(
	Customer=Customer,
	Account=Account,
	ParentCustomerId=ParentCustomerId)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  
