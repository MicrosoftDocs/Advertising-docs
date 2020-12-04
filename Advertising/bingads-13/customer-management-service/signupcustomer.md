---
title: SignupCustomer Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Creates a new customer and account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SignupCustomer Service Operation - Customer Management
Creates a new customer and account.  

Typically you must be a user with aggregator [credentials](../guides/account-hierarchy-permissions.md#user-roles) to call this operation. In that case, the operation creates a new customer and account that roll up to your aggregator payment method. The [AdvertiserAccount](advertiseraccount.md) object must include the name of the account, the type of currency to use to settle the account, and the payment method identifier must be set to null. The operation generates an invoice account and sets the payment method identifier to the identifier associated with the aggregator's invoice. You are invoiced for all charges incurred by the customers that you manage.

> [!NOTE]
> Agency customers in the Create Accounts on Behalf of Client pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 793) can sign up a new customer on behalf of a client and optionally link to the new account as an agency. In this case a [UserInvitation](userinvitation.md) is sent and the client must complete sign up steps via the Microsoft Advertising UI e.g., accept the terms and conditions.  

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [AdvertiserAccount](advertiseraccount.md) that specifies the details of the customer's primary account.|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
|<a name="parentcustomerid"></a>ParentCustomerId|The customer identifier of the aggregator that will manage the new child customer.<br/><br/>This element is required for aggregators but ignored for agencies when the [UserInvitation](#userinvitation) request element is set.|**long**|
|<a name="userinvitation"></a>UserInvitation|The user invitation to send if you want to sign up a new customer on behalf of a client and optionally link to the new account as an agency.<br/><br/>A client Super Admin user must complete sign up steps via the Microsoft Advertising UI e.g., accept the terms and conditions.<br/><br/>This element is optional and only available for agency customers in the Create Accounts on Behalf of Client pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 793).|[UserInvitation](userinvitation.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SignupCustomerResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|A system-generated account identifier corresponding to the new account specified in the request.<br/><br/>Use this identifier with operation requests that require an *AccountId* body element and a *CustomerAccountId* SOAP header element.|**long**|
|<a name="accountnumber"></a>AccountNumber|The system-generated account number that is used to identify the account in the Microsoft Advertising web application.<br/><br/>The account number has the form *xxxxxxxx*, where *xxxxxxxx* is a series of any eight alphanumeric characters.|**string**|
|<a name="createtime"></a>CreateTime|The date and time that the account was added. The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|
|<a name="customerid"></a>CustomerId|A system-generated customer identifier corresponding to the new customer specified in the request.<br/><br/>Use this identifier with operation requests that require a *CustomerId* SOAP header element.|**long**|
|<a name="customernumber"></a>CustomerNumber|A system-generated customer number that is used in the Microsoft Advertising web application.<br/><br/>The customer number has the form *xxxxxxxxxx*, where *xxxxxxxxxx* is a series of any ten alphanumeric characters.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">SignupCustomer</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SignupCustomerRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <Customer xmlns:e199="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e199:CustomerFinancialStatus i:nil="false">ValueHere</e199:CustomerFinancialStatus>
        <e199:Id i:nil="false">ValueHere</e199:Id>
        <e199:Industry i:nil="false">ValueHere</e199:Industry>
        <e199:LastModifiedByUserId i:nil="false">ValueHere</e199:LastModifiedByUserId>
        <e199:LastModifiedTime i:nil="false">ValueHere</e199:LastModifiedTime>
        <e199:MarketCountry i:nil="false">ValueHere</e199:MarketCountry>
        <e199:ForwardCompatibilityMap xmlns:e200="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e200:KeyValuePairOfstringstring>
            <e200:key i:nil="false">ValueHere</e200:key>
            <e200:value i:nil="false">ValueHere</e200:value>
          </e200:KeyValuePairOfstringstring>
        </e199:ForwardCompatibilityMap>
        <e199:MarketLanguage i:nil="false">ValueHere</e199:MarketLanguage>
        <e199:Name i:nil="false">ValueHere</e199:Name>
        <e199:ServiceLevel i:nil="false">ValueHere</e199:ServiceLevel>
        <e199:CustomerLifeCycleStatus i:nil="false">ValueHere</e199:CustomerLifeCycleStatus>
        <e199:TimeStamp i:nil="false">ValueHere</e199:TimeStamp>
        <e199:Number i:nil="false">ValueHere</e199:Number>
        <e199:CustomerAddress i:nil="false">
          <e199:City i:nil="false">ValueHere</e199:City>
          <e199:CountryCode i:nil="false">ValueHere</e199:CountryCode>
          <e199:Id i:nil="false">ValueHere</e199:Id>
          <e199:Line1 i:nil="false">ValueHere</e199:Line1>
          <e199:Line2 i:nil="false">ValueHere</e199:Line2>
          <e199:Line3 i:nil="false">ValueHere</e199:Line3>
          <e199:Line4 i:nil="false">ValueHere</e199:Line4>
          <e199:PostalCode i:nil="false">ValueHere</e199:PostalCode>
          <e199:StateOrProvince i:nil="false">ValueHere</e199:StateOrProvince>
          <e199:TimeStamp i:nil="false">ValueHere</e199:TimeStamp>
          <e199:BusinessName i:nil="false">ValueHere</e199:BusinessName>
        </e199:CustomerAddress>
      </Customer>
      <Account xmlns:e201="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e201:BillToCustomerId i:nil="false">ValueHere</e201:BillToCustomerId>
        <e201:CurrencyCode i:nil="false">ValueHere</e201:CurrencyCode>
        <e201:AccountFinancialStatus i:nil="false">ValueHere</e201:AccountFinancialStatus>
        <e201:Id i:nil="false">ValueHere</e201:Id>
        <e201:Language i:nil="false">ValueHere</e201:Language>
        <e201:LastModifiedByUserId i:nil="false">ValueHere</e201:LastModifiedByUserId>
        <e201:LastModifiedTime i:nil="false">ValueHere</e201:LastModifiedTime>
        <e201:Name i:nil="false">ValueHere</e201:Name>
        <e201:Number i:nil="false">ValueHere</e201:Number>
        <e201:ParentCustomerId>ValueHere</e201:ParentCustomerId>
        <e201:PaymentMethodId i:nil="false">ValueHere</e201:PaymentMethodId>
        <e201:PaymentMethodType i:nil="false">ValueHere</e201:PaymentMethodType>
        <e201:PrimaryUserId i:nil="false">ValueHere</e201:PrimaryUserId>
        <e201:AccountLifeCycleStatus i:nil="false">ValueHere</e201:AccountLifeCycleStatus>
        <e201:TimeStamp i:nil="false">ValueHere</e201:TimeStamp>
        <e201:TimeZone i:nil="false">ValueHere</e201:TimeZone>
        <e201:PauseReason i:nil="false">ValueHere</e201:PauseReason>
        <e201:ForwardCompatibilityMap xmlns:e202="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e202:KeyValuePairOfstringstring>
            <e202:key i:nil="false">ValueHere</e202:key>
            <e202:value i:nil="false">ValueHere</e202:value>
          </e202:KeyValuePairOfstringstring>
        </e201:ForwardCompatibilityMap>
        <e201:LinkedAgencies i:nil="false">
          <e201:CustomerInfo>
            <e201:Id i:nil="false">ValueHere</e201:Id>
            <e201:Name i:nil="false">ValueHere</e201:Name>
          </e201:CustomerInfo>
        </e201:LinkedAgencies>
        <e201:SalesHouseCustomerId i:nil="false">ValueHere</e201:SalesHouseCustomerId>
        <e201:TaxInformation xmlns:e203="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e203:KeyValuePairOfstringstring>
            <e203:key i:nil="false">ValueHere</e203:key>
            <e203:value i:nil="false">ValueHere</e203:value>
          </e203:KeyValuePairOfstringstring>
        </e201:TaxInformation>
        <e201:BackUpPaymentInstrumentId i:nil="false">ValueHere</e201:BackUpPaymentInstrumentId>
        <e201:BillingThresholdAmount i:nil="false">ValueHere</e201:BillingThresholdAmount>
        <e201:BusinessAddress i:nil="false">
          <e201:City i:nil="false">ValueHere</e201:City>
          <e201:CountryCode i:nil="false">ValueHere</e201:CountryCode>
          <e201:Id i:nil="false">ValueHere</e201:Id>
          <e201:Line1 i:nil="false">ValueHere</e201:Line1>
          <e201:Line2 i:nil="false">ValueHere</e201:Line2>
          <e201:Line3 i:nil="false">ValueHere</e201:Line3>
          <e201:Line4 i:nil="false">ValueHere</e201:Line4>
          <e201:PostalCode i:nil="false">ValueHere</e201:PostalCode>
          <e201:StateOrProvince i:nil="false">ValueHere</e201:StateOrProvince>
          <e201:TimeStamp i:nil="false">ValueHere</e201:TimeStamp>
          <e201:BusinessName i:nil="false">ValueHere</e201:BusinessName>
        </e201:BusinessAddress>
        <e201:AutoTagType i:nil="false">ValueHere</e201:AutoTagType>
        <e201:SoldToPaymentInstrumentId i:nil="false">ValueHere</e201:SoldToPaymentInstrumentId>
        <e201:TaxCertificate i:nil="false">
          <e201:TaxCertificateBlobContainerName i:nil="false">ValueHere</e201:TaxCertificateBlobContainerName>
          <e201:TaxCertificates xmlns:e204="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="false">
            <e204:KeyValueOfstringbase64Binary>ValueHere</e204:KeyValueOfstringbase64Binary>
            <e204:Key i:nil="false">ValueHere</e204:Key>
            <e204:Value i:nil="false">ValueHere</e204:Value>
          </e201:TaxCertificates>
          <e201:Status i:nil="false">ValueHere</e201:Status>
        </e201:TaxCertificate>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e205="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e205:Id>ValueHere</e205:Id>
        <e205:FirstName i:nil="false">ValueHere</e205:FirstName>
        <e205:LastName i:nil="false">ValueHere</e205:LastName>
        <e205:Email i:nil="false">ValueHere</e205:Email>
        <e205:CustomerId>ValueHere</e205:CustomerId>
        <e205:RoleId>ValueHere</e205:RoleId>
        <e205:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e205:AccountIds>
        <e205:ExpirationDate>ValueHere</e205:ExpirationDate>
        <e205:Lcid>ValueHere</e205:Lcid>
      </UserInvitation>
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
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SignupCustomerResponse> SignupCustomerAsync(
	Customer customer,
	AdvertiserAccount account,
	long? parentCustomerId,
	UserInvitation userInvitation)
{
	var request = new SignupCustomerRequest
	{
		Customer = customer,
		Account = account,
		ParentCustomerId = parentCustomerId,
		UserInvitation = userInvitation
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SignupCustomerAsync(r), request));
}
```
```java
static SignupCustomerResponse signupCustomer(
	Customer customer,
	AdvertiserAccount account,
	java.lang.Long parentCustomerId,
	UserInvitation userInvitation) throws RemoteException, Exception
{
	SignupCustomerRequest request = new SignupCustomerRequest();

	request.setCustomer(customer);
	request.setAccount(account);
	request.setParentCustomerId(parentCustomerId);
	request.setUserInvitation(userInvitation);

	return CustomerManagementService.getService().signupCustomer(request);
}
```
```php
static function SignupCustomer(
	$customer,
	$account,
	$parentCustomerId,
	$userInvitation)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SignupCustomerRequest();

	$request->Customer = $customer;
	$request->Account = $account;
	$request->ParentCustomerId = $parentCustomerId;
	$request->UserInvitation = $userInvitation;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SignupCustomer($request);
}
```
```python
response=customermanagement_service.SignupCustomer(
	Customer=Customer,
	Account=Account,
	ParentCustomerId=ParentCustomerId,
	UserInvitation=UserInvitation)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

