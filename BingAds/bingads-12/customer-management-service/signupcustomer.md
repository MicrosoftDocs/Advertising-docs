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
> This Bing Ads API Version 12 preview documentation is subject to change.
# SignupCustomer Service Operation - Customer Management
Creates a new customer and account that rolls up to your reseller payment method.

> [!NOTE]
> You must be a reseller with aggregator user permissions to call this operation. For more details see [Management Model for Resellers](../guides/management-model-resellers.md).

Pass both [Customer](../customer-management-service/customer.md) and [Account](../customer-management-service/account.md) objects in the request. The customer object includes the customer's name, the address where the customer is located, the market in which the customer operates, and the industry in which the customer participates. Although it is possible to add multiple customers with the same details, you should use unique customer names so that users can easily distinguish between customers in a user interface.

The account object must specify the name of the account; the type of currency to use to settle the account; and the payment method identifier, which must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the reseller's invoice. You are invoiced for all charges incurred by the customers that you manage.

If the operation succeeds, a new managed customer is created outside of the reseller customer and an account is created within the managed customer. 

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [Account](../customer-management-service/account.md) that specifies the details of the customer's primary account.<br /><br /> Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](../customer-management-service/advertiseraccount.md) that derives from the *Account* data object.|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](../customer-management-service/customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
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
      <Customer xmlns:e350="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e350:CustomerAddress i:nil="false">
          <e350:City i:nil="false">ValueHere</e350:City>
          <e350:CountryCode i:nil="false">ValueHere</e350:CountryCode>
          <e350:Id i:nil="false">ValueHere</e350:Id>
          <e350:Line1 i:nil="false">ValueHere</e350:Line1>
          <e350:Line2 i:nil="false">ValueHere</e350:Line2>
          <e350:Line3 i:nil="false">ValueHere</e350:Line3>
          <e350:Line4 i:nil="false">ValueHere</e350:Line4>
          <e350:PostalCode i:nil="false">ValueHere</e350:PostalCode>
          <e350:StateOrProvince i:nil="false">ValueHere</e350:StateOrProvince>
          <e350:TimeStamp i:nil="false">ValueHere</e350:TimeStamp>
        </e350:CustomerAddress>
        <e350:CustomerFinancialStatus i:nil="false">ValueHere</e350:CustomerFinancialStatus>
        <e350:Id i:nil="false">ValueHere</e350:Id>
        <e350:Industry i:nil="false">ValueHere</e350:Industry>
        <e350:LastModifiedByUserId i:nil="false">ValueHere</e350:LastModifiedByUserId>
        <e350:LastModifiedTime i:nil="false">ValueHere</e350:LastModifiedTime>
        <e350:MarketCountry i:nil="false">ValueHere</e350:MarketCountry>
        <ForwardCompatibilityMap xmlns:e351="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e351:KeyValuePairOfstringstring>
            <e351:key i:nil="false">ValueHere</e351:key>
            <e351:value i:nil="false">ValueHere</e351:value>
          </e351:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e350:MarketLanguage i:nil="false">ValueHere</e350:MarketLanguage>
        <e350:Name i:nil="false">ValueHere</e350:Name>
        <e350:ServiceLevel i:nil="false">ValueHere</e350:ServiceLevel>
        <e350:CustomerLifeCycleStatus i:nil="false">ValueHere</e350:CustomerLifeCycleStatus>
        <e350:TimeStamp i:nil="false">ValueHere</e350:TimeStamp>
        <e350:Number i:nil="false">ValueHere</e350:Number>
      </Customer>
      <Account xmlns:e352="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e352:BillToCustomerId i:nil="false">ValueHere</e352:BillToCustomerId>
        <e352:CountryCode i:nil="false">ValueHere</e352:CountryCode>
        <e352:CurrencyCode i:nil="false">ValueHere</e352:CurrencyCode>
        <e352:AccountFinancialStatus i:nil="false">ValueHere</e352:AccountFinancialStatus>
        <e352:Id i:nil="false">ValueHere</e352:Id>
        <e352:Language i:nil="false">ValueHere</e352:Language>
        <e352:LastModifiedByUserId i:nil="false">ValueHere</e352:LastModifiedByUserId>
        <e352:LastModifiedTime i:nil="false">ValueHere</e352:LastModifiedTime>
        <e352:Name i:nil="false">ValueHere</e352:Name>
        <e352:Number i:nil="false">ValueHere</e352:Number>
        <e352:ParentCustomerId>ValueHere</e352:ParentCustomerId>
        <e352:PaymentMethodId i:nil="false">ValueHere</e352:PaymentMethodId>
        <e352:PaymentMethodType i:nil="false">ValueHere</e352:PaymentMethodType>
        <e352:PrimaryUserId i:nil="false">ValueHere</e352:PrimaryUserId>
        <e352:AccountLifeCycleStatus i:nil="false">ValueHere</e352:AccountLifeCycleStatus>
        <e352:TimeStamp i:nil="false">ValueHere</e352:TimeStamp>
        <e352:TimeZone i:nil="false">ValueHere</e352:TimeZone>
        <e352:PauseReason i:nil="false">ValueHere</e352:PauseReason>
        <ForwardCompatibilityMap xmlns:e353="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e353:KeyValuePairOfstringstring>
            <e353:key i:nil="false">ValueHere</e353:key>
            <e353:value i:nil="false">ValueHere</e353:value>
          </e353:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e352:LinkedAgencies i:nil="false">
          <e352:CustomerInfo>
            <e352:Id i:nil="false">ValueHere</e352:Id>
            <e352:Name i:nil="false">ValueHere</e352:Name>
          </e352:CustomerInfo>
        </e352:LinkedAgencies>
        <e352:SalesHouseCustomerId i:nil="false">ValueHere</e352:SalesHouseCustomerId>
        <TaxInformation xmlns:e354="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e354:KeyValuePairOfstringstring>
            <e354:key i:nil="false">ValueHere</e354:key>
            <e354:value i:nil="false">ValueHere</e354:value>
          </e354:KeyValuePairOfstringstring>
        </TaxInformation>
        <e352:BackUpPaymentInstrumentId i:nil="false">ValueHere</e352:BackUpPaymentInstrumentId>
        <e352:BillingThresholdAmount i:nil="false">ValueHere</e352:BillingThresholdAmount>
        <e352:BusinessAddress i:nil="false">
          <e352:City i:nil="false">ValueHere</e352:City>
          <e352:CountryCode i:nil="false">ValueHere</e352:CountryCode>
          <e352:Id i:nil="false">ValueHere</e352:Id>
          <e352:Line1 i:nil="false">ValueHere</e352:Line1>
          <e352:Line2 i:nil="false">ValueHere</e352:Line2>
          <e352:Line3 i:nil="false">ValueHere</e352:Line3>
          <e352:Line4 i:nil="false">ValueHere</e352:Line4>
          <e352:PostalCode i:nil="false">ValueHere</e352:PostalCode>
          <e352:StateOrProvince i:nil="false">ValueHere</e352:StateOrProvince>
          <e352:TimeStamp i:nil="false">ValueHere</e352:TimeStamp>
        </e352:BusinessAddress>
        <e352:AutoTagType i:nil="false">ValueHere</e352:AutoTagType>
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
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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

