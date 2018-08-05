---
title: SignupCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Signs up a customer with Bing Ads.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
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
|<a name="account"></a>Account|An [Account](account.md) that specifies the details of the customer's primary account.<br/><br/>Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](advertiseraccount.md) that derives from the *Account* data object.|[Account](account.md)|
|<a name="applicationscope"></a>ApplicationScope|Determines  the type of customer application. The default is Advertiser.<br/><br/>The scope of this customer and the scope of the parent customer must be the same; for example, they must both be set to Advertiser.|[ApplicationType](applicationtype.md)|
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
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">SignupCustomer</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <SignupCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Customer xmlns:e342="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e342:CustomerAddress i:nil="false">
          <e342:City i:nil="false">ValueHere</e342:City>
          <e342:CountryCode i:nil="false">ValueHere</e342:CountryCode>
          <e342:Id i:nil="false">ValueHere</e342:Id>
          <e342:Line1 i:nil="false">ValueHere</e342:Line1>
          <e342:Line2 i:nil="false">ValueHere</e342:Line2>
          <e342:Line3 i:nil="false">ValueHere</e342:Line3>
          <e342:Line4 i:nil="false">ValueHere</e342:Line4>
          <e342:PostalCode i:nil="false">ValueHere</e342:PostalCode>
          <e342:StateOrProvince i:nil="false">ValueHere</e342:StateOrProvince>
          <e342:TimeStamp i:nil="false">ValueHere</e342:TimeStamp>
        </e342:CustomerAddress>
        <e342:CustomerFinancialStatus i:nil="false">ValueHere</e342:CustomerFinancialStatus>
        <e342:Id i:nil="false">ValueHere</e342:Id>
        <e342:Industry i:nil="false">ValueHere</e342:Industry>
        <e342:LastModifiedByUserId i:nil="false">ValueHere</e342:LastModifiedByUserId>
        <e342:LastModifiedTime i:nil="false">ValueHere</e342:LastModifiedTime>
        <e342:MarketCountry i:nil="false">ValueHere</e342:MarketCountry>
        <ForwardCompatibilityMap xmlns:e343="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e343:KeyValuePairOfstringstring>
            <e343:key i:nil="false">ValueHere</e343:key>
            <e343:value i:nil="false">ValueHere</e343:value>
          </e343:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e342:MarketLanguage i:nil="false">ValueHere</e342:MarketLanguage>
        <e342:Name i:nil="false">ValueHere</e342:Name>
        <e342:ServiceLevel i:nil="false">ValueHere</e342:ServiceLevel>
        <e342:CustomerLifeCycleStatus i:nil="false">ValueHere</e342:CustomerLifeCycleStatus>
        <e342:TimeStamp i:nil="false">ValueHere</e342:TimeStamp>
        <e342:Number i:nil="false">ValueHere</e342:Number>
      </Customer>
      <Account xmlns:e344="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e344:AccountType>ValueHere</e344:AccountType>
        <e344:BillToCustomerId i:nil="false">ValueHere</e344:BillToCustomerId>
        <e344:CountryCode i:nil="false">ValueHere</e344:CountryCode>
        <e344:CurrencyType i:nil="false">ValueHere</e344:CurrencyType>
        <e344:AccountFinancialStatus i:nil="false">ValueHere</e344:AccountFinancialStatus>
        <e344:Id i:nil="false">ValueHere</e344:Id>
        <e344:Language i:nil="false">ValueHere</e344:Language>
        <ForwardCompatibilityMap xmlns:e345="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e345:KeyValuePairOfstringstring>
            <e345:key i:nil="false">ValueHere</e345:key>
            <e345:value i:nil="false">ValueHere</e345:value>
          </e345:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e344:LastModifiedByUserId i:nil="false">ValueHere</e344:LastModifiedByUserId>
        <e344:LastModifiedTime i:nil="false">ValueHere</e344:LastModifiedTime>
        <e344:Name i:nil="false">ValueHere</e344:Name>
        <e344:Number i:nil="false">ValueHere</e344:Number>
        <e344:ParentCustomerId>ValueHere</e344:ParentCustomerId>
        <e344:PaymentMethodId i:nil="false">ValueHere</e344:PaymentMethodId>
        <e344:PaymentMethodType i:nil="false">ValueHere</e344:PaymentMethodType>
        <e344:PrimaryUserId i:nil="false">ValueHere</e344:PrimaryUserId>
        <e344:AccountLifeCycleStatus i:nil="false">ValueHere</e344:AccountLifeCycleStatus>
        <e344:TimeStamp i:nil="false">ValueHere</e344:TimeStamp>
        <e344:TimeZone i:nil="false">ValueHere</e344:TimeZone>
        <e344:PauseReason i:nil="false">ValueHere</e344:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e344:LinkedAgencies i:nil="false">
          <e344:CustomerInfo>
            <e344:Id i:nil="false">ValueHere</e344:Id>
            <e344:Name i:nil="false">ValueHere</e344:Name>
          </e344:CustomerInfo>
        </e344:LinkedAgencies>
        <e344:SalesHouseCustomerId i:nil="false">ValueHere</e344:SalesHouseCustomerId>
        <TaxInformation xmlns:e346="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e346:KeyValuePairOfstringstring>
            <e346:key i:nil="false">ValueHere</e346:key>
            <e346:value i:nil="false">ValueHere</e346:value>
          </e346:KeyValuePairOfstringstring>
        </TaxInformation>
        <e344:BackUpPaymentInstrumentId i:nil="false">ValueHere</e344:BackUpPaymentInstrumentId>
        <e344:BillingThresholdAmount i:nil="false">ValueHere</e344:BillingThresholdAmount>
        <e344:BusinessAddress i:nil="false">
          <e344:City i:nil="false">ValueHere</e344:City>
          <e344:CountryCode i:nil="false">ValueHere</e344:CountryCode>
          <e344:Id i:nil="false">ValueHere</e344:Id>
          <e344:Line1 i:nil="false">ValueHere</e344:Line1>
          <e344:Line2 i:nil="false">ValueHere</e344:Line2>
          <e344:Line3 i:nil="false">ValueHere</e344:Line3>
          <e344:Line4 i:nil="false">ValueHere</e344:Line4>
          <e344:PostalCode i:nil="false">ValueHere</e344:PostalCode>
          <e344:StateOrProvince i:nil="false">ValueHere</e344:StateOrProvince>
          <e344:TimeStamp i:nil="false">ValueHere</e344:TimeStamp>
        </e344:BusinessAddress>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <ApplicationScope>ValueHere</ApplicationScope>
    </SignupCustomerRequest>
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
    <SignupCustomerResponse xmlns="https://bingads.microsoft.com/Customer/v11">
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
	Account account,
	long? parentCustomerId,
	ApplicationType applicationScope)
{
	var request = new SignupCustomerRequest
	{
		Customer = customer,
		Account = account,
		ParentCustomerId = parentCustomerId,
		ApplicationScope = applicationScope
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SignupCustomerAsync(r), request));
}
```
```java
static SignupCustomerResponse signupCustomer(
	Customer customer,
	Account account,
	java.lang.Long parentCustomerId,
	ApplicationType applicationScope) throws RemoteException, Exception
{
	SignupCustomerRequest request = new SignupCustomerRequest();

	request.setCustomer(customer);
	request.setAccount(account);
	request.setParentCustomerId(parentCustomerId);
	request.setApplicationScope(applicationScope);

	return CustomerManagementService.getService().signupCustomer(request);
}
```
```php
static function SignupCustomer(
	$customer,
	$account,
	$parentCustomerId,
	$applicationScope)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SignupCustomerRequest();

	$request->Customer = $customer;
	$request->Account = $account;
	$request->ParentCustomerId = $parentCustomerId;
	$request->ApplicationScope = $applicationScope;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SignupCustomer($request);
}
```
```python
response=customermanagement_service.SignupCustomer(
	Customer=Customer,
	Account=Account,
	ParentCustomerId=ParentCustomerId,
	ApplicationScope=ApplicationScope)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

