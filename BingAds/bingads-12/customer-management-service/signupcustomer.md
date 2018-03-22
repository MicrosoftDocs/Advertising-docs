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
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# SignupCustomer Service Operation - Customer Management
Creates a new customer and account that rolls up to your reseller payment method.

> [!NOTE]
> You must be a reseller with aggregator user permissions to call this operation. For more details see [Management Model for Resellers](../guides/management-model-resellers.md).

Pass both [Customer](customer.md) and [AdvertiserAccount](advertiseraccount.md) objects in the request. The customer object includes the customer's name, the address where the customer is located, the market in which the customer operates, and the industry in which the customer participates. Although it is possible to add multiple customers with the same details, you should use unique customer names so that users can easily distinguish between customers in a user interface.

The account object must specify the name of the account; the type of currency to use to settle the account; and the payment method identifier, which must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the reseller's invoice. You are invoiced for all charges incurred by the customers that you manage.

If the operation succeeds, a new managed customer is created outside of the reseller customer and an account is created within the managed customer. 

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [AdvertiserAccount](advertiseraccount.md) that specifies the details of the customer's primary account.<br /><br /> Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](advertiseraccount.md) that derives from the *Account* data object.|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
|<a name="parentcustomerid"></a>ParentCustomerId|The customer identifier of the reseller that will manage this customer.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SignupCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|A system-generated account identifier corresponding to the new account specified in the request.<br /><br />Use this identifier with operation requests that require an *AccountId* element and a *CustomerAccountId* SOAP header element.|**long**|
|<a name="accountnumber"></a>AccountNumber|A system-generated account number that is used to identify the account in the Bing Ads web application. The account number has the form, X*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|
|<a name="createtime"></a>CreateTime|The date and time that the account was added. The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="customerid"></a>CustomerId|A system-generated customer identifier corresponding to the new customer specified in the request.<br /><br />Use this identifier with operation requests that require a *CustomerId* SOAP header element.|**long**|
|<a name="customernumber"></a>CustomerNumber|A system-generated customer number that is used in the Bing Ads web application. The customer number is of the form, C*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">SignupCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SignupCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Customer xmlns:e975="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e975:CustomerFinancialStatus i:nil="false">ValueHere</e975:CustomerFinancialStatus>
        <e975:Id i:nil="false">ValueHere</e975:Id>
        <e975:Industry i:nil="false">ValueHere</e975:Industry>
        <e975:LastModifiedByUserId i:nil="false">ValueHere</e975:LastModifiedByUserId>
        <e975:LastModifiedTime i:nil="false">ValueHere</e975:LastModifiedTime>
        <e975:MarketCountry i:nil="false">ValueHere</e975:MarketCountry>
        <ForwardCompatibilityMap xmlns:e976="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e976:KeyValuePairOfstringstring>
            <e976:key i:nil="false">ValueHere</e976:key>
            <e976:value i:nil="false">ValueHere</e976:value>
          </e976:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e975:MarketLanguage i:nil="false">ValueHere</e975:MarketLanguage>
        <e975:Name i:nil="false">ValueHere</e975:Name>
        <e975:ServiceLevel i:nil="false">ValueHere</e975:ServiceLevel>
        <e975:CustomerLifeCycleStatus i:nil="false">ValueHere</e975:CustomerLifeCycleStatus>
        <e975:TimeStamp i:nil="false">ValueHere</e975:TimeStamp>
        <e975:Number i:nil="false">ValueHere</e975:Number>
      </Customer>
      <Account xmlns:e977="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e977:BillToCustomerId i:nil="false">ValueHere</e977:BillToCustomerId>
        <e977:CurrencyCode i:nil="false">ValueHere</e977:CurrencyCode>
        <e977:AccountFinancialStatus i:nil="false">ValueHere</e977:AccountFinancialStatus>
        <e977:Id i:nil="false">ValueHere</e977:Id>
        <e977:Language i:nil="false">ValueHere</e977:Language>
        <e977:LastModifiedByUserId i:nil="false">ValueHere</e977:LastModifiedByUserId>
        <e977:LastModifiedTime i:nil="false">ValueHere</e977:LastModifiedTime>
        <e977:Name i:nil="false">ValueHere</e977:Name>
        <e977:Number i:nil="false">ValueHere</e977:Number>
        <e977:ParentCustomerId>ValueHere</e977:ParentCustomerId>
        <e977:PaymentMethodId i:nil="false">ValueHere</e977:PaymentMethodId>
        <e977:PaymentMethodType i:nil="false">ValueHere</e977:PaymentMethodType>
        <e977:PrimaryUserId i:nil="false">ValueHere</e977:PrimaryUserId>
        <e977:AccountLifeCycleStatus i:nil="false">ValueHere</e977:AccountLifeCycleStatus>
        <e977:TimeStamp i:nil="false">ValueHere</e977:TimeStamp>
        <e977:TimeZone i:nil="false">ValueHere</e977:TimeZone>
        <e977:PauseReason i:nil="false">ValueHere</e977:PauseReason>
        <ForwardCompatibilityMap xmlns:e978="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e978:KeyValuePairOfstringstring>
            <e978:key i:nil="false">ValueHere</e978:key>
            <e978:value i:nil="false">ValueHere</e978:value>
          </e978:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e977:LinkedAgencies i:nil="false">
          <e977:CustomerInfo>
            <e977:Id i:nil="false">ValueHere</e977:Id>
            <e977:Name i:nil="false">ValueHere</e977:Name>
          </e977:CustomerInfo>
        </e977:LinkedAgencies>
        <e977:SalesHouseCustomerId i:nil="false">ValueHere</e977:SalesHouseCustomerId>
        <TaxInformation xmlns:e979="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e979:KeyValuePairOfstringstring>
            <e979:key i:nil="false">ValueHere</e979:key>
            <e979:value i:nil="false">ValueHere</e979:value>
          </e979:KeyValuePairOfstringstring>
        </TaxInformation>
        <e977:BackUpPaymentInstrumentId i:nil="false">ValueHere</e977:BackUpPaymentInstrumentId>
        <e977:BillingThresholdAmount i:nil="false">ValueHere</e977:BillingThresholdAmount>
        <e977:BusinessAddress i:nil="false">
          <e977:City i:nil="false">ValueHere</e977:City>
          <e977:CountryCode i:nil="false">ValueHere</e977:CountryCode>
          <e977:Id i:nil="false">ValueHere</e977:Id>
          <e977:Line1 i:nil="false">ValueHere</e977:Line1>
          <e977:Line2 i:nil="false">ValueHere</e977:Line2>
          <e977:Line3 i:nil="false">ValueHere</e977:Line3>
          <e977:Line4 i:nil="false">ValueHere</e977:Line4>
          <e977:PostalCode i:nil="false">ValueHere</e977:PostalCode>
          <e977:StateOrProvince i:nil="false">ValueHere</e977:StateOrProvince>
          <e977:TimeStamp i:nil="false">ValueHere</e977:TimeStamp>
          <e977:BusinessName i:nil="false">ValueHere</e977:BusinessName>
        </e977:BusinessAddress>
        <e977:AutoTagType i:nil="false">ValueHere</e977:AutoTagType>
        <e977:SoldToPaymentInstrumentId i:nil="false">ValueHere</e977:SoldToPaymentInstrumentId>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
    </SignupCustomerRequest>
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
    <SignupCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v12">
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
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

