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

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

Signs up a customer with Bing Ads.

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [Account](/bingads/customer-management-service/account.md) that specifies the details of the customer's primary account.<br /><br /> Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](/bingads/customer-management-service/advertiseraccount.md) that derives from the *Account* data object.|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](/bingads/customer-management-service/customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
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
      <Customer xmlns:e707="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e707:CustomerAddress i:nil="false">
          <e707:City i:nil="false">ValueHere</e707:City>
          <e707:CountryCode i:nil="false">ValueHere</e707:CountryCode>
          <e707:Id i:nil="false">ValueHere</e707:Id>
          <e707:Line1 i:nil="false">ValueHere</e707:Line1>
          <e707:Line2 i:nil="false">ValueHere</e707:Line2>
          <e707:Line3 i:nil="false">ValueHere</e707:Line3>
          <e707:Line4 i:nil="false">ValueHere</e707:Line4>
          <e707:PostalCode i:nil="false">ValueHere</e707:PostalCode>
          <e707:StateOrProvince i:nil="false">ValueHere</e707:StateOrProvince>
          <e707:TimeStamp i:nil="false">ValueHere</e707:TimeStamp>
        </e707:CustomerAddress>
        <e707:CustomerFinancialStatus i:nil="false">ValueHere</e707:CustomerFinancialStatus>
        <e707:Id i:nil="false">ValueHere</e707:Id>
        <e707:Industry i:nil="false">ValueHere</e707:Industry>
        <e707:LastModifiedByUserId i:nil="false">ValueHere</e707:LastModifiedByUserId>
        <e707:LastModifiedTime i:nil="false">ValueHere</e707:LastModifiedTime>
        <e707:MarketCountry i:nil="false">ValueHere</e707:MarketCountry>
        <ForwardCompatibilityMap xmlns:e708="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e708:KeyValuePairOfstringstring>
            <e708:key i:nil="false">ValueHere</e708:key>
            <e708:value i:nil="false">ValueHere</e708:value>
          </e708:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e707:MarketLanguage i:nil="false">ValueHere</e707:MarketLanguage>
        <e707:Name i:nil="false">ValueHere</e707:Name>
        <e707:ServiceLevel i:nil="false">ValueHere</e707:ServiceLevel>
        <e707:CustomerLifeCycleStatus i:nil="false">ValueHere</e707:CustomerLifeCycleStatus>
        <e707:TimeStamp i:nil="false">ValueHere</e707:TimeStamp>
        <e707:Number i:nil="false">ValueHere</e707:Number>
      </Customer>
      <Account xmlns:e709="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e709:BillToCustomerId i:nil="false">ValueHere</e709:BillToCustomerId>
        <e709:CountryCode i:nil="false">ValueHere</e709:CountryCode>
        <e709:CurrencyType i:nil="false">ValueHere</e709:CurrencyType>
        <e709:AccountFinancialStatus i:nil="false">ValueHere</e709:AccountFinancialStatus>
        <e709:Id i:nil="false">ValueHere</e709:Id>
        <e709:Language i:nil="false">ValueHere</e709:Language>
        <e709:LastModifiedByUserId i:nil="false">ValueHere</e709:LastModifiedByUserId>
        <e709:LastModifiedTime i:nil="false">ValueHere</e709:LastModifiedTime>
        <e709:Name i:nil="false">ValueHere</e709:Name>
        <e709:Number i:nil="false">ValueHere</e709:Number>
        <e709:ParentCustomerId>ValueHere</e709:ParentCustomerId>
        <e709:PaymentMethodId i:nil="false">ValueHere</e709:PaymentMethodId>
        <e709:PaymentMethodType i:nil="false">ValueHere</e709:PaymentMethodType>
        <e709:PrimaryUserId i:nil="false">ValueHere</e709:PrimaryUserId>
        <e709:AccountLifeCycleStatus i:nil="false">ValueHere</e709:AccountLifeCycleStatus>
        <e709:TimeStamp i:nil="false">ValueHere</e709:TimeStamp>
        <e709:TimeZone i:nil="false">ValueHere</e709:TimeZone>
        <e709:PauseReason i:nil="false">ValueHere</e709:PauseReason>
        <ForwardCompatibilityMap xmlns:e710="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e710:KeyValuePairOfstringstring>
            <e710:key i:nil="false">ValueHere</e710:key>
            <e710:value i:nil="false">ValueHere</e710:value>
          </e710:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e709:LinkedAgencies i:nil="false">
          <e709:CustomerInfo>
            <e709:Id i:nil="false">ValueHere</e709:Id>
            <e709:Name i:nil="false">ValueHere</e709:Name>
          </e709:CustomerInfo>
        </e709:LinkedAgencies>
        <e709:SalesHouseCustomerId i:nil="false">ValueHere</e709:SalesHouseCustomerId>
        <TaxInformation xmlns:e711="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e711:KeyValuePairOfstringstring>
            <e711:key i:nil="false">ValueHere</e711:key>
            <e711:value i:nil="false">ValueHere</e711:value>
          </e711:KeyValuePairOfstringstring>
        </TaxInformation>
        <e709:BackUpPaymentInstrumentId i:nil="false">ValueHere</e709:BackUpPaymentInstrumentId>
        <e709:BillingThresholdAmount i:nil="false">ValueHere</e709:BillingThresholdAmount>
        <e709:BusinessAddress i:nil="false">
          <e709:City i:nil="false">ValueHere</e709:City>
          <e709:CountryCode i:nil="false">ValueHere</e709:CountryCode>
          <e709:Id i:nil="false">ValueHere</e709:Id>
          <e709:Line1 i:nil="false">ValueHere</e709:Line1>
          <e709:Line2 i:nil="false">ValueHere</e709:Line2>
          <e709:Line3 i:nil="false">ValueHere</e709:Line3>
          <e709:Line4 i:nil="false">ValueHere</e709:Line4>
          <e709:PostalCode i:nil="false">ValueHere</e709:PostalCode>
          <e709:StateOrProvince i:nil="false">ValueHere</e709:StateOrProvince>
          <e709:TimeStamp i:nil="false">ValueHere</e709:TimeStamp>
        </e709:BusinessAddress>
        <e709:AutoTagType i:nil="false">ValueHere</e709:AutoTagType>
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
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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

