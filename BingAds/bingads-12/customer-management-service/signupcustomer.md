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
# SignupCustomer Service Operation - Customer Management

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

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
      <Customer xmlns:e40="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e40:CustomerAddress i:nil="false">
          <e40:City i:nil="false">ValueHere</e40:City>
          <e40:CountryCode i:nil="false">ValueHere</e40:CountryCode>
          <e40:Id i:nil="false">ValueHere</e40:Id>
          <e40:Line1 i:nil="false">ValueHere</e40:Line1>
          <e40:Line2 i:nil="false">ValueHere</e40:Line2>
          <e40:Line3 i:nil="false">ValueHere</e40:Line3>
          <e40:Line4 i:nil="false">ValueHere</e40:Line4>
          <e40:PostalCode i:nil="false">ValueHere</e40:PostalCode>
          <e40:StateOrProvince i:nil="false">ValueHere</e40:StateOrProvince>
          <e40:TimeStamp i:nil="false">ValueHere</e40:TimeStamp>
        </e40:CustomerAddress>
        <e40:CustomerFinancialStatus i:nil="false">ValueHere</e40:CustomerFinancialStatus>
        <e40:Id i:nil="false">ValueHere</e40:Id>
        <e40:Industry i:nil="false">ValueHere</e40:Industry>
        <e40:LastModifiedByUserId i:nil="false">ValueHere</e40:LastModifiedByUserId>
        <e40:LastModifiedTime i:nil="false">ValueHere</e40:LastModifiedTime>
        <e40:MarketCountry i:nil="false">ValueHere</e40:MarketCountry>
        <ForwardCompatibilityMap xmlns:e41="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e41:KeyValuePairOfstringstring>
            <e41:key i:nil="false">ValueHere</e41:key>
            <e41:value i:nil="false">ValueHere</e41:value>
          </e41:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e40:MarketLanguage i:nil="false">ValueHere</e40:MarketLanguage>
        <e40:Name i:nil="false">ValueHere</e40:Name>
        <e40:ServiceLevel i:nil="false">ValueHere</e40:ServiceLevel>
        <e40:CustomerLifeCycleStatus i:nil="false">ValueHere</e40:CustomerLifeCycleStatus>
        <e40:TimeStamp i:nil="false">ValueHere</e40:TimeStamp>
        <e40:Number i:nil="false">ValueHere</e40:Number>
      </Customer>
      <Account xmlns:e42="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e42:BillToCustomerId i:nil="false">ValueHere</e42:BillToCustomerId>
        <e42:CountryCode i:nil="false">ValueHere</e42:CountryCode>
        <e42:CurrencyCode i:nil="false">ValueHere</e42:CurrencyCode>
        <e42:AccountFinancialStatus i:nil="false">ValueHere</e42:AccountFinancialStatus>
        <e42:Id i:nil="false">ValueHere</e42:Id>
        <e42:Language i:nil="false">ValueHere</e42:Language>
        <e42:LastModifiedByUserId i:nil="false">ValueHere</e42:LastModifiedByUserId>
        <e42:LastModifiedTime i:nil="false">ValueHere</e42:LastModifiedTime>
        <e42:Name i:nil="false">ValueHere</e42:Name>
        <e42:Number i:nil="false">ValueHere</e42:Number>
        <e42:ParentCustomerId>ValueHere</e42:ParentCustomerId>
        <e42:PaymentMethodId i:nil="false">ValueHere</e42:PaymentMethodId>
        <e42:PaymentMethodType i:nil="false">ValueHere</e42:PaymentMethodType>
        <e42:PrimaryUserId i:nil="false">ValueHere</e42:PrimaryUserId>
        <e42:AccountLifeCycleStatus i:nil="false">ValueHere</e42:AccountLifeCycleStatus>
        <e42:TimeStamp i:nil="false">ValueHere</e42:TimeStamp>
        <e42:TimeZone i:nil="false">ValueHere</e42:TimeZone>
        <e42:PauseReason i:nil="false">ValueHere</e42:PauseReason>
        <ForwardCompatibilityMap xmlns:e43="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e43:KeyValuePairOfstringstring>
            <e43:key i:nil="false">ValueHere</e43:key>
            <e43:value i:nil="false">ValueHere</e43:value>
          </e43:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e42:LinkedAgencies i:nil="false">
          <e42:CustomerInfo>
            <e42:Id i:nil="false">ValueHere</e42:Id>
            <e42:Name i:nil="false">ValueHere</e42:Name>
          </e42:CustomerInfo>
        </e42:LinkedAgencies>
        <e42:SalesHouseCustomerId i:nil="false">ValueHere</e42:SalesHouseCustomerId>
        <TaxInformation xmlns:e44="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e44:KeyValuePairOfstringstring>
            <e44:key i:nil="false">ValueHere</e44:key>
            <e44:value i:nil="false">ValueHere</e44:value>
          </e44:KeyValuePairOfstringstring>
        </TaxInformation>
        <e42:BackUpPaymentInstrumentId i:nil="false">ValueHere</e42:BackUpPaymentInstrumentId>
        <e42:BillingThresholdAmount i:nil="false">ValueHere</e42:BillingThresholdAmount>
        <e42:BusinessAddress i:nil="false">
          <e42:City i:nil="false">ValueHere</e42:City>
          <e42:CountryCode i:nil="false">ValueHere</e42:CountryCode>
          <e42:Id i:nil="false">ValueHere</e42:Id>
          <e42:Line1 i:nil="false">ValueHere</e42:Line1>
          <e42:Line2 i:nil="false">ValueHere</e42:Line2>
          <e42:Line3 i:nil="false">ValueHere</e42:Line3>
          <e42:Line4 i:nil="false">ValueHere</e42:Line4>
          <e42:PostalCode i:nil="false">ValueHere</e42:PostalCode>
          <e42:StateOrProvince i:nil="false">ValueHere</e42:StateOrProvince>
          <e42:TimeStamp i:nil="false">ValueHere</e42:TimeStamp>
        </e42:BusinessAddress>
        <e42:AutoTagType i:nil="false">ValueHere</e42:AutoTagType>
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

