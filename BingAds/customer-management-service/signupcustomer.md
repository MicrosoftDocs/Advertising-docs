---
title: SignupCustomer Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Signs up a customer with Bing Ads.
---
# SignupCustomer Service Operation
Signs up a customer with Bing Ads.

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [Account](../customer-management-service/account.md) that specifies the details of the customer's primary account.<br /><br /> Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](../customer-management-service/advertiseraccount.md) that derives from the *Account* data object.|[Account](account.md)|
|<a name="applicationscope"></a>ApplicationScope|Determines  the type of customer application. The default is Advertiser.<br /><br />The scope of this customer and the scope of the parent customer must be the same; for example, they must both be set to Advertiser.|[ApplicationType](applicationtype.md)|
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
      <Customer xmlns:e648="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e648:CustomerAddress i:nil="false">
          <e648:City i:nil="false">ValueHere</e648:City>
          <e648:CountryCode i:nil="false">ValueHere</e648:CountryCode>
          <e648:Id i:nil="false">ValueHere</e648:Id>
          <e648:Line1 i:nil="false">ValueHere</e648:Line1>
          <e648:Line2 i:nil="false">ValueHere</e648:Line2>
          <e648:Line3 i:nil="false">ValueHere</e648:Line3>
          <e648:Line4 i:nil="false">ValueHere</e648:Line4>
          <e648:PostalCode i:nil="false">ValueHere</e648:PostalCode>
          <e648:StateOrProvince i:nil="false">ValueHere</e648:StateOrProvince>
          <e648:TimeStamp i:nil="false">ValueHere</e648:TimeStamp>
        </e648:CustomerAddress>
        <e648:CustomerFinancialStatus i:nil="false">ValueHere</e648:CustomerFinancialStatus>
        <e648:Id i:nil="false">ValueHere</e648:Id>
        <e648:Industry i:nil="false">ValueHere</e648:Industry>
        <e648:LastModifiedByUserId i:nil="false">ValueHere</e648:LastModifiedByUserId>
        <e648:LastModifiedTime i:nil="false">ValueHere</e648:LastModifiedTime>
        <e648:MarketCountry i:nil="false">ValueHere</e648:MarketCountry>
        <ForwardCompatibilityMap xmlns:e649="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e649:KeyValuePairOfstringstring>
            <e649:key i:nil="false">ValueHere</e649:key>
            <e649:value i:nil="false">ValueHere</e649:value>
          </e649:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e648:MarketLanguage i:nil="false">ValueHere</e648:MarketLanguage>
        <e648:Name i:nil="false">ValueHere</e648:Name>
        <e648:ServiceLevel i:nil="false">ValueHere</e648:ServiceLevel>
        <e648:CustomerLifeCycleStatus i:nil="false">ValueHere</e648:CustomerLifeCycleStatus>
        <e648:TimeStamp i:nil="false">ValueHere</e648:TimeStamp>
        <e648:Number i:nil="false">ValueHere</e648:Number>
      </Customer>
      <Account xmlns:e650="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e650:AccountType>ValueHere</e650:AccountType>
        <e650:BillToCustomerId i:nil="false">ValueHere</e650:BillToCustomerId>
        <e650:CountryCode i:nil="false">ValueHere</e650:CountryCode>
        <e650:CurrencyType i:nil="false">ValueHere</e650:CurrencyType>
        <e650:AccountFinancialStatus i:nil="false">ValueHere</e650:AccountFinancialStatus>
        <e650:Id i:nil="false">ValueHere</e650:Id>
        <e650:Language i:nil="false">ValueHere</e650:Language>
        <ForwardCompatibilityMap xmlns:e651="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e651:KeyValuePairOfstringstring>
            <e651:key i:nil="false">ValueHere</e651:key>
            <e651:value i:nil="false">ValueHere</e651:value>
          </e651:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e650:LastModifiedByUserId i:nil="false">ValueHere</e650:LastModifiedByUserId>
        <e650:LastModifiedTime i:nil="false">ValueHere</e650:LastModifiedTime>
        <e650:Name i:nil="false">ValueHere</e650:Name>
        <e650:Number i:nil="false">ValueHere</e650:Number>
        <e650:ParentCustomerId>ValueHere</e650:ParentCustomerId>
        <e650:PaymentMethodId i:nil="false">ValueHere</e650:PaymentMethodId>
        <e650:PaymentMethodType i:nil="false">ValueHere</e650:PaymentMethodType>
        <e650:PrimaryUserId i:nil="false">ValueHere</e650:PrimaryUserId>
        <e650:AccountLifeCycleStatus i:nil="false">ValueHere</e650:AccountLifeCycleStatus>
        <e650:TimeStamp i:nil="false">ValueHere</e650:TimeStamp>
        <e650:TimeZone i:nil="false">ValueHere</e650:TimeZone>
        <e650:PauseReason i:nil="false">ValueHere</e650:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e650:LinkedAgencies i:nil="false">
          <e650:CustomerInfo>
            <e650:Id i:nil="false">ValueHere</e650:Id>
            <e650:Name i:nil="false">ValueHere</e650:Name>
          </e650:CustomerInfo>
        </e650:LinkedAgencies>
        <e650:SalesHouseCustomerId i:nil="false">ValueHere</e650:SalesHouseCustomerId>
        <TaxInformation xmlns:e652="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e652:KeyValuePairOfstringstring>
            <e652:key i:nil="false">ValueHere</e652:key>
            <e652:value i:nil="false">ValueHere</e652:value>
          </e652:KeyValuePairOfstringstring>
        </TaxInformation>
        <e650:BackUpPaymentInstrumentId i:nil="false">ValueHere</e650:BackUpPaymentInstrumentId>
        <e650:BillingThresholdAmount i:nil="false">ValueHere</e650:BillingThresholdAmount>
        <e650:BusinessAddress i:nil="false">
          <e650:City i:nil="false">ValueHere</e650:City>
          <e650:CountryCode i:nil="false">ValueHere</e650:CountryCode>
          <e650:Id i:nil="false">ValueHere</e650:Id>
          <e650:Line1 i:nil="false">ValueHere</e650:Line1>
          <e650:Line2 i:nil="false">ValueHere</e650:Line2>
          <e650:Line3 i:nil="false">ValueHere</e650:Line3>
          <e650:Line4 i:nil="false">ValueHere</e650:Line4>
          <e650:PostalCode i:nil="false">ValueHere</e650:PostalCode>
          <e650:StateOrProvince i:nil="false">ValueHere</e650:StateOrProvince>
          <e650:TimeStamp i:nil="false">ValueHere</e650:TimeStamp>
        </e650:BusinessAddress>
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
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<SignupCustomerResponse> SignupCustomerAsync(
	Customer customer,
	Account account,
	long parentCustomerId,
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

	$signupCustomerRequest = new SignupCustomerRequest();

	$request->Customer = $customer;
	$request->Account = $account;
	$request->ParentCustomerId = $parentCustomerId;
	$request->ApplicationScope = $applicationScope;

	return $CustomerManagementProxy->GetService()->SignupCustomer($request);
}
```
```python
response=customermanagement.SignupCustomer(
	Customer=CustomerHere,
	Account=AccountHere,
	ParentCustomerId=ParentCustomerIdHere,
	ApplicationScope=ApplicationScopeHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

