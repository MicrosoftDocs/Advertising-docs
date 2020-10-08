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
      <Customer xmlns:e189="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e189:CustomerFinancialStatus i:nil="false">ValueHere</e189:CustomerFinancialStatus>
        <e189:Id i:nil="false">ValueHere</e189:Id>
        <e189:Industry i:nil="false">ValueHere</e189:Industry>
        <e189:LastModifiedByUserId i:nil="false">ValueHere</e189:LastModifiedByUserId>
        <e189:LastModifiedTime i:nil="false">ValueHere</e189:LastModifiedTime>
        <e189:MarketCountry i:nil="false">ValueHere</e189:MarketCountry>
        <e189:ForwardCompatibilityMap xmlns:e190="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e190:KeyValuePairOfstringstring>
            <e190:key i:nil="false">ValueHere</e190:key>
            <e190:value i:nil="false">ValueHere</e190:value>
          </e190:KeyValuePairOfstringstring>
        </e189:ForwardCompatibilityMap>
        <e189:MarketLanguage i:nil="false">ValueHere</e189:MarketLanguage>
        <e189:Name i:nil="false">ValueHere</e189:Name>
        <e189:ServiceLevel i:nil="false">ValueHere</e189:ServiceLevel>
        <e189:CustomerLifeCycleStatus i:nil="false">ValueHere</e189:CustomerLifeCycleStatus>
        <e189:TimeStamp i:nil="false">ValueHere</e189:TimeStamp>
        <e189:Number i:nil="false">ValueHere</e189:Number>
        <e189:CustomerAddress i:nil="false">
          <e189:City i:nil="false">ValueHere</e189:City>
          <e189:CountryCode i:nil="false">ValueHere</e189:CountryCode>
          <e189:Id i:nil="false">ValueHere</e189:Id>
          <e189:Line1 i:nil="false">ValueHere</e189:Line1>
          <e189:Line2 i:nil="false">ValueHere</e189:Line2>
          <e189:Line3 i:nil="false">ValueHere</e189:Line3>
          <e189:Line4 i:nil="false">ValueHere</e189:Line4>
          <e189:PostalCode i:nil="false">ValueHere</e189:PostalCode>
          <e189:StateOrProvince i:nil="false">ValueHere</e189:StateOrProvince>
          <e189:TimeStamp i:nil="false">ValueHere</e189:TimeStamp>
          <e189:BusinessName i:nil="false">ValueHere</e189:BusinessName>
        </e189:CustomerAddress>
      </Customer>
      <Account xmlns:e191="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e191:BillToCustomerId i:nil="false">ValueHere</e191:BillToCustomerId>
        <e191:CurrencyCode i:nil="false">ValueHere</e191:CurrencyCode>
        <e191:AccountFinancialStatus i:nil="false">ValueHere</e191:AccountFinancialStatus>
        <e191:Id i:nil="false">ValueHere</e191:Id>
        <e191:Language i:nil="false">ValueHere</e191:Language>
        <e191:LastModifiedByUserId i:nil="false">ValueHere</e191:LastModifiedByUserId>
        <e191:LastModifiedTime i:nil="false">ValueHere</e191:LastModifiedTime>
        <e191:Name i:nil="false">ValueHere</e191:Name>
        <e191:Number i:nil="false">ValueHere</e191:Number>
        <e191:ParentCustomerId>ValueHere</e191:ParentCustomerId>
        <e191:PaymentMethodId i:nil="false">ValueHere</e191:PaymentMethodId>
        <e191:PaymentMethodType i:nil="false">ValueHere</e191:PaymentMethodType>
        <e191:PrimaryUserId i:nil="false">ValueHere</e191:PrimaryUserId>
        <e191:AccountLifeCycleStatus i:nil="false">ValueHere</e191:AccountLifeCycleStatus>
        <e191:TimeStamp i:nil="false">ValueHere</e191:TimeStamp>
        <e191:TimeZone i:nil="false">ValueHere</e191:TimeZone>
        <e191:PauseReason i:nil="false">ValueHere</e191:PauseReason>
        <e191:ForwardCompatibilityMap xmlns:e192="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e192:KeyValuePairOfstringstring>
            <e192:key i:nil="false">ValueHere</e192:key>
            <e192:value i:nil="false">ValueHere</e192:value>
          </e192:KeyValuePairOfstringstring>
        </e191:ForwardCompatibilityMap>
        <e191:LinkedAgencies i:nil="false">
          <e191:CustomerInfo>
            <e191:Id i:nil="false">ValueHere</e191:Id>
            <e191:Name i:nil="false">ValueHere</e191:Name>
          </e191:CustomerInfo>
        </e191:LinkedAgencies>
        <e191:SalesHouseCustomerId i:nil="false">ValueHere</e191:SalesHouseCustomerId>
        <e191:TaxInformation xmlns:e193="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e193:KeyValuePairOfstringstring>
            <e193:key i:nil="false">ValueHere</e193:key>
            <e193:value i:nil="false">ValueHere</e193:value>
          </e193:KeyValuePairOfstringstring>
        </e191:TaxInformation>
        <e191:BackUpPaymentInstrumentId i:nil="false">ValueHere</e191:BackUpPaymentInstrumentId>
        <e191:BillingThresholdAmount i:nil="false">ValueHere</e191:BillingThresholdAmount>
        <e191:BusinessAddress i:nil="false">
          <e191:City i:nil="false">ValueHere</e191:City>
          <e191:CountryCode i:nil="false">ValueHere</e191:CountryCode>
          <e191:Id i:nil="false">ValueHere</e191:Id>
          <e191:Line1 i:nil="false">ValueHere</e191:Line1>
          <e191:Line2 i:nil="false">ValueHere</e191:Line2>
          <e191:Line3 i:nil="false">ValueHere</e191:Line3>
          <e191:Line4 i:nil="false">ValueHere</e191:Line4>
          <e191:PostalCode i:nil="false">ValueHere</e191:PostalCode>
          <e191:StateOrProvince i:nil="false">ValueHere</e191:StateOrProvince>
          <e191:TimeStamp i:nil="false">ValueHere</e191:TimeStamp>
          <e191:BusinessName i:nil="false">ValueHere</e191:BusinessName>
        </e191:BusinessAddress>
        <e191:AutoTagType i:nil="false">ValueHere</e191:AutoTagType>
        <e191:SoldToPaymentInstrumentId i:nil="false">ValueHere</e191:SoldToPaymentInstrumentId>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e194="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e194:Id>ValueHere</e194:Id>
        <e194:FirstName i:nil="false">ValueHere</e194:FirstName>
        <e194:LastName i:nil="false">ValueHere</e194:LastName>
        <e194:Email i:nil="false">ValueHere</e194:Email>
        <e194:CustomerId>ValueHere</e194:CustomerId>
        <e194:RoleId>ValueHere</e194:RoleId>
        <e194:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e194:AccountIds>
        <e194:ExpirationDate>ValueHere</e194:ExpirationDate>
        <e194:Lcid>ValueHere</e194:Lcid>
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

