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
      <Customer xmlns:e351="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e351:CustomerFinancialStatus i:nil="false">ValueHere</e351:CustomerFinancialStatus>
        <e351:Id i:nil="false">ValueHere</e351:Id>
        <e351:Industry i:nil="false">ValueHere</e351:Industry>
        <e351:LastModifiedByUserId i:nil="false">ValueHere</e351:LastModifiedByUserId>
        <e351:LastModifiedTime i:nil="false">ValueHere</e351:LastModifiedTime>
        <e351:MarketCountry i:nil="false">ValueHere</e351:MarketCountry>
        <ForwardCompatibilityMap xmlns:e352="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e352:KeyValuePairOfstringstring>
            <e352:key i:nil="false">ValueHere</e352:key>
            <e352:value i:nil="false">ValueHere</e352:value>
          </e352:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e351:MarketLanguage i:nil="false">ValueHere</e351:MarketLanguage>
        <e351:Name i:nil="false">ValueHere</e351:Name>
        <e351:ServiceLevel i:nil="false">ValueHere</e351:ServiceLevel>
        <e351:CustomerLifeCycleStatus i:nil="false">ValueHere</e351:CustomerLifeCycleStatus>
        <e351:TimeStamp i:nil="false">ValueHere</e351:TimeStamp>
        <e351:Number i:nil="false">ValueHere</e351:Number>
      </Customer>
      <Account xmlns:e353="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e353:BillToCustomerId i:nil="false">ValueHere</e353:BillToCustomerId>
        <e353:CurrencyCode i:nil="false">ValueHere</e353:CurrencyCode>
        <e353:AccountFinancialStatus i:nil="false">ValueHere</e353:AccountFinancialStatus>
        <e353:Id i:nil="false">ValueHere</e353:Id>
        <e353:Language i:nil="false">ValueHere</e353:Language>
        <e353:LastModifiedByUserId i:nil="false">ValueHere</e353:LastModifiedByUserId>
        <e353:LastModifiedTime i:nil="false">ValueHere</e353:LastModifiedTime>
        <e353:Name i:nil="false">ValueHere</e353:Name>
        <e353:Number i:nil="false">ValueHere</e353:Number>
        <e353:ParentCustomerId>ValueHere</e353:ParentCustomerId>
        <e353:PaymentMethodId i:nil="false">ValueHere</e353:PaymentMethodId>
        <e353:PaymentMethodType i:nil="false">ValueHere</e353:PaymentMethodType>
        <e353:PrimaryUserId i:nil="false">ValueHere</e353:PrimaryUserId>
        <e353:AccountLifeCycleStatus i:nil="false">ValueHere</e353:AccountLifeCycleStatus>
        <e353:TimeStamp i:nil="false">ValueHere</e353:TimeStamp>
        <e353:TimeZone i:nil="false">ValueHere</e353:TimeZone>
        <e353:PauseReason i:nil="false">ValueHere</e353:PauseReason>
        <ForwardCompatibilityMap xmlns:e354="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e354:KeyValuePairOfstringstring>
            <e354:key i:nil="false">ValueHere</e354:key>
            <e354:value i:nil="false">ValueHere</e354:value>
          </e354:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e353:LinkedAgencies i:nil="false">
          <e353:CustomerInfo>
            <e353:Id i:nil="false">ValueHere</e353:Id>
            <e353:Name i:nil="false">ValueHere</e353:Name>
          </e353:CustomerInfo>
        </e353:LinkedAgencies>
        <e353:SalesHouseCustomerId i:nil="false">ValueHere</e353:SalesHouseCustomerId>
        <TaxInformation xmlns:e355="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e355:KeyValuePairOfstringstring>
            <e355:key i:nil="false">ValueHere</e355:key>
            <e355:value i:nil="false">ValueHere</e355:value>
          </e355:KeyValuePairOfstringstring>
        </TaxInformation>
        <e353:BackUpPaymentInstrumentId i:nil="false">ValueHere</e353:BackUpPaymentInstrumentId>
        <e353:BillingThresholdAmount i:nil="false">ValueHere</e353:BillingThresholdAmount>
        <e353:BusinessAddress i:nil="false">
          <e353:City i:nil="false">ValueHere</e353:City>
          <e353:CountryCode i:nil="false">ValueHere</e353:CountryCode>
          <e353:Id i:nil="false">ValueHere</e353:Id>
          <e353:Line1 i:nil="false">ValueHere</e353:Line1>
          <e353:Line2 i:nil="false">ValueHere</e353:Line2>
          <e353:Line3 i:nil="false">ValueHere</e353:Line3>
          <e353:Line4 i:nil="false">ValueHere</e353:Line4>
          <e353:PostalCode i:nil="false">ValueHere</e353:PostalCode>
          <e353:StateOrProvince i:nil="false">ValueHere</e353:StateOrProvince>
          <e353:TimeStamp i:nil="false">ValueHere</e353:TimeStamp>
          <e353:BusinessName i:nil="false">ValueHere</e353:BusinessName>
        </e353:BusinessAddress>
        <e353:AutoTagType i:nil="false">ValueHere</e353:AutoTagType>
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

