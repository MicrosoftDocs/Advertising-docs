---
title: SignupCustomer Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# SignupCustomer Service Operation
Signs up a customer with Bing Ads.

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customer"></a>Customer|A [Customer](../customer-management/customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
|<a name="account"></a>Account|An [Account](../customer-management/account.md) that specifies the details of the customer?s primary account.<br /><br />**Note**: Do not instantiate the *Account* data object. Instead, instantiate the [AdvertiserAccount](../customer-management/advertiseraccount.md) that derives from the *Account* data object.|[Account](account.md)|
|<a name="parentcustomerid"></a>ParentCustomerId|The customer identifier of the reseller that will manage this customer.|**long**|
|<a name="applicationscope"></a>ApplicationScope|Determines  the type of customer application. The default is Advertiser.<br /><br />The scope of this customer and the scope of the parent customer must be the same; for example, they must both be set to Advertiser.|[ApplicationType](applicationtype.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SignupCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|A system-generated customer identifier corresponding to the new customer specified in the request.<br /><br />Use this identifier with operation requests that require a *CustomerId* SOAP header element.|**long**|
|<a name="customernumber"></a>CustomerNumber|A system-generated customer number that is used in the Bing Ads web application. The customer number is of the form, C*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|
|<a name="accountid"></a>AccountId|A system-generated account identifier corresponding to the new account specified in the request.<br /><br />Use this identifier with operation requests that require an *AccountId* element and a *CustomerAccountId* SOAP header element.|**long**|
|<a name="accountnumber"></a>AccountNumber|A system-generated account number that is used to identify the account in the Bing Ads web application. The account number has the form, X*nnnnnnn*, where *nnnnnnn* is a series of digits.|**string**|
|<a name="createtime"></a>CreateTime|The date and time that the account was added. The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

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
      <Customer xmlns:e442="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e442:CustomerAddress i:nil="false">
          <e442:City i:nil="false">ValueHere</e442:City>
          <e442:CountryCode i:nil="false">ValueHere</e442:CountryCode>
          <e442:Id i:nil="false">ValueHere</e442:Id>
          <e442:Line1 i:nil="false">ValueHere</e442:Line1>
          <e442:Line2 i:nil="false">ValueHere</e442:Line2>
          <e442:Line3 i:nil="false">ValueHere</e442:Line3>
          <e442:Line4 i:nil="false">ValueHere</e442:Line4>
          <e442:PostalCode i:nil="false">ValueHere</e442:PostalCode>
          <e442:StateOrProvince i:nil="false">ValueHere</e442:StateOrProvince>
          <e442:TimeStamp i:nil="false">ValueHere</e442:TimeStamp>
        </e442:CustomerAddress>
        <e442:CustomerFinancialStatus i:nil="false">ValueHere</e442:CustomerFinancialStatus>
        <e442:Id i:nil="false">ValueHere</e442:Id>
        <e442:Industry i:nil="false">ValueHere</e442:Industry>
        <e442:LastModifiedByUserId i:nil="false">ValueHere</e442:LastModifiedByUserId>
        <e442:LastModifiedTime i:nil="false">ValueHere</e442:LastModifiedTime>
        <e442:MarketCountry i:nil="false">ValueHere</e442:MarketCountry>
        <ForwardCompatibilityMap xmlns:e443="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e443:KeyValuePairOfstringstring>
            <e443:key i:nil="false">ValueHere</e443:key>
            <e443:value i:nil="false">ValueHere</e443:value>
          </e443:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e442:MarketLanguage i:nil="false">ValueHere</e442:MarketLanguage>
        <e442:Name i:nil="false">ValueHere</e442:Name>
        <e442:ServiceLevel i:nil="false">ValueHere</e442:ServiceLevel>
        <e442:CustomerLifeCycleStatus i:nil="false">ValueHere</e442:CustomerLifeCycleStatus>
        <e442:TimeStamp i:nil="false">ValueHere</e442:TimeStamp>
        <e442:Number i:nil="false">ValueHere</e442:Number>
      </Customer>
      <Account xmlns:e444="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e444:AccountType>ValueHere</e444:AccountType>
        <e444:BillToCustomerId i:nil="false">ValueHere</e444:BillToCustomerId>
        <e444:CountryCode i:nil="false">ValueHere</e444:CountryCode>
        <e444:CurrencyType i:nil="false">ValueHere</e444:CurrencyType>
        <e444:AccountFinancialStatus i:nil="false">ValueHere</e444:AccountFinancialStatus>
        <e444:Id i:nil="false">ValueHere</e444:Id>
        <e444:Language i:nil="false">ValueHere</e444:Language>
        <ForwardCompatibilityMap xmlns:e445="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e445:KeyValuePairOfstringstring>
            <e445:key i:nil="false">ValueHere</e445:key>
            <e445:value i:nil="false">ValueHere</e445:value>
          </e445:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e444:LastModifiedByUserId i:nil="false">ValueHere</e444:LastModifiedByUserId>
        <e444:LastModifiedTime i:nil="false">ValueHere</e444:LastModifiedTime>
        <e444:Name i:nil="false">ValueHere</e444:Name>
        <e444:Number i:nil="false">ValueHere</e444:Number>
        <e444:ParentCustomerId>ValueHere</e444:ParentCustomerId>
        <e444:PaymentMethodId i:nil="false">ValueHere</e444:PaymentMethodId>
        <e444:PaymentMethodType i:nil="false">ValueHere</e444:PaymentMethodType>
        <e444:PrimaryUserId i:nil="false">ValueHere</e444:PrimaryUserId>
        <e444:AccountLifeCycleStatus i:nil="false">ValueHere</e444:AccountLifeCycleStatus>
        <e444:TimeStamp i:nil="false">ValueHere</e444:TimeStamp>
        <e444:TimeZone i:nil="false">ValueHere</e444:TimeZone>
        <e444:PauseReason i:nil="false">ValueHere</e444:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e444:LinkedAgencies i:nil="false">
          <e444:CustomerInfo>
            <e444:Id i:nil="false">ValueHere</e444:Id>
            <e444:Name i:nil="false">ValueHere</e444:Name>
          </e444:CustomerInfo>
        </e444:LinkedAgencies>
        <e444:SalesHouseCustomerId i:nil="false">ValueHere</e444:SalesHouseCustomerId>
        <TaxInformation xmlns:e446="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e446:KeyValuePairOfstringstring>
            <e446:key i:nil="false">ValueHere</e446:key>
            <e446:value i:nil="false">ValueHere</e446:value>
          </e446:KeyValuePairOfstringstring>
        </TaxInformation>
        <e444:BackUpPaymentInstrumentId i:nil="false">ValueHere</e444:BackUpPaymentInstrumentId>
        <e444:BillingThresholdAmount i:nil="false">ValueHere</e444:BillingThresholdAmount>
        <e444:BusinessAddress i:nil="false">
          <e444:City i:nil="false">ValueHere</e444:City>
          <e444:CountryCode i:nil="false">ValueHere</e444:CountryCode>
          <e444:Id i:nil="false">ValueHere</e444:Id>
          <e444:Line1 i:nil="false">ValueHere</e444:Line1>
          <e444:Line2 i:nil="false">ValueHere</e444:Line2>
          <e444:Line3 i:nil="false">ValueHere</e444:Line3>
          <e444:Line4 i:nil="false">ValueHere</e444:Line4>
          <e444:PostalCode i:nil="false">ValueHere</e444:PostalCode>
          <e444:StateOrProvince i:nil="false">ValueHere</e444:StateOrProvince>
          <e444:TimeStamp i:nil="false">ValueHere</e444:TimeStamp>
        </e444:BusinessAddress>
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
```csharp
protected async Task<SignupCustomerResponse> SignupCustomerAsync(
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

	return (await CustomerManagement.CallAsync((s, r) => s.SignupCustomerAsync(r), request));
}
```
```java
static SignupCustomerResponse signupCustomer(
	Customer customer,
	Account account,
	long parentCustomerId,
	ApplicationType applicationScope)
{
	SignupCustomerRequest request = new SignupCustomerRequest();

	request.setCustomer(customer);
	request.setAccount(account);
	request.setParentCustomerId(parentCustomerId);
	request.setApplicationScope(applicationScope);

	return CustomerManagement.getService().signupCustomer(request);
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

