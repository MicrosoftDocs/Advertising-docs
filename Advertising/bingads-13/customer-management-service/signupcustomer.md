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

> [!NOTE]
> Customers in the closed Unified smart campaigns pilot can sign up a new customer with an account for Unified smart campaigns. Optionally they can link to the new account as an agency. The super admin is provisioned by either setting the [UserId](#userid) or [UserInvitation](#userinvitation) element.

## <a name="request"></a>Request Elements
The *SignupCustomerRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An [AdvertiserAccount](advertiseraccount.md) that specifies the details of the customer's primary account.<br/><br/>Customers in the closed Unified smart campaigns pilot must set the [AccountMode](advertiseraccount.md#accountmode) element to "UnifiedSmart".|[AdvertiserAccount](advertiseraccount.md)|
|<a name="customer"></a>Customer|A [Customer](customer.md) that specifies the details of the customer that you are adding.|[Customer](customer.md)|
|<a name="parentcustomerid"></a>ParentCustomerId|The customer identifier of the aggregator or agency that will manage the new child customer.<br/><br/>This element is required for aggregators but ignored for agencies when the [UserInvitation](#userinvitation) request element is set. Customers in the closed Unified smart campaigns pilot can link the new customer to the parent agency ID or leave this element empty.|**long**|
|<a name="userid"></a>UserId|The identifier of an existing user who will be added as Super Admin in the new customer.<br/><br/>This element is only available for customers in the closed Unified smart campaigns pilot. One or more of the [UserId](#userid) or [UserInvitation](#userinvitation) element must be set.|**long**|
|<a name="userinvitation"></a>UserInvitation|The user invitation to send if you want to sign up a new customer on behalf of a client and optionally link to the new account as an agency.<br/><br/>A client Super Admin user must complete sign up steps via the Microsoft Advertising UI e.g., accept the terms and conditions.<br/><br/>This element is optional for agency customers in the Create Accounts on Behalf of Client pilot.<br/><br/>Customers in the closed Unified smart campaigns pilot must set one or more of the [UserId](#userid) or [UserInvitation](#userinvitation) element.|[UserInvitation](userinvitation.md)|

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
      <Customer xmlns:e210="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e210:CustomerFinancialStatus i:nil="false">ValueHere</e210:CustomerFinancialStatus>
        <e210:Id i:nil="false">ValueHere</e210:Id>
        <e210:Industry i:nil="false">ValueHere</e210:Industry>
        <e210:LastModifiedByUserId i:nil="false">ValueHere</e210:LastModifiedByUserId>
        <e210:LastModifiedTime i:nil="false">ValueHere</e210:LastModifiedTime>
        <e210:MarketCountry i:nil="false">ValueHere</e210:MarketCountry>
        <e210:ForwardCompatibilityMap xmlns:e211="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e211:KeyValuePairOfstringstring>
            <e211:key i:nil="false">ValueHere</e211:key>
            <e211:value i:nil="false">ValueHere</e211:value>
          </e211:KeyValuePairOfstringstring>
        </e210:ForwardCompatibilityMap>
        <e210:MarketLanguage i:nil="false">ValueHere</e210:MarketLanguage>
        <e210:Name i:nil="false">ValueHere</e210:Name>
        <e210:ServiceLevel i:nil="false">ValueHere</e210:ServiceLevel>
        <e210:CustomerLifeCycleStatus i:nil="false">ValueHere</e210:CustomerLifeCycleStatus>
        <e210:TimeStamp i:nil="false">ValueHere</e210:TimeStamp>
        <e210:Number i:nil="false">ValueHere</e210:Number>
        <e210:CustomerAddress i:nil="false">
          <e210:City i:nil="false">ValueHere</e210:City>
          <e210:CountryCode i:nil="false">ValueHere</e210:CountryCode>
          <e210:Id i:nil="false">ValueHere</e210:Id>
          <e210:Line1 i:nil="false">ValueHere</e210:Line1>
          <e210:Line2 i:nil="false">ValueHere</e210:Line2>
          <e210:Line3 i:nil="false">ValueHere</e210:Line3>
          <e210:Line4 i:nil="false">ValueHere</e210:Line4>
          <e210:PostalCode i:nil="false">ValueHere</e210:PostalCode>
          <e210:StateOrProvince i:nil="false">ValueHere</e210:StateOrProvince>
          <e210:TimeStamp i:nil="false">ValueHere</e210:TimeStamp>
          <e210:BusinessName i:nil="false">ValueHere</e210:BusinessName>
        </e210:CustomerAddress>
      </Customer>
      <Account xmlns:e212="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e212:BillToCustomerId i:nil="false">ValueHere</e212:BillToCustomerId>
        <e212:CurrencyCode i:nil="false">ValueHere</e212:CurrencyCode>
        <e212:AccountFinancialStatus i:nil="false">ValueHere</e212:AccountFinancialStatus>
        <e212:Id i:nil="false">ValueHere</e212:Id>
        <e212:Language i:nil="false">ValueHere</e212:Language>
        <e212:LastModifiedByUserId i:nil="false">ValueHere</e212:LastModifiedByUserId>
        <e212:LastModifiedTime i:nil="false">ValueHere</e212:LastModifiedTime>
        <e212:Name i:nil="false">ValueHere</e212:Name>
        <e212:Number i:nil="false">ValueHere</e212:Number>
        <e212:ParentCustomerId>ValueHere</e212:ParentCustomerId>
        <e212:PaymentMethodId i:nil="false">ValueHere</e212:PaymentMethodId>
        <e212:PaymentMethodType i:nil="false">ValueHere</e212:PaymentMethodType>
        <e212:PrimaryUserId i:nil="false">ValueHere</e212:PrimaryUserId>
        <e212:AccountLifeCycleStatus i:nil="false">ValueHere</e212:AccountLifeCycleStatus>
        <e212:TimeStamp i:nil="false">ValueHere</e212:TimeStamp>
        <e212:TimeZone i:nil="false">ValueHere</e212:TimeZone>
        <e212:PauseReason i:nil="false">ValueHere</e212:PauseReason>
        <e212:ForwardCompatibilityMap xmlns:e213="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e213:KeyValuePairOfstringstring>
            <e213:key i:nil="false">ValueHere</e213:key>
            <e213:value i:nil="false">ValueHere</e213:value>
          </e213:KeyValuePairOfstringstring>
        </e212:ForwardCompatibilityMap>
        <e212:LinkedAgencies i:nil="false">
          <e212:CustomerInfo>
            <e212:Id i:nil="false">ValueHere</e212:Id>
            <e212:Name i:nil="false">ValueHere</e212:Name>
          </e212:CustomerInfo>
        </e212:LinkedAgencies>
        <e212:SalesHouseCustomerId i:nil="false">ValueHere</e212:SalesHouseCustomerId>
        <e212:TaxInformation xmlns:e214="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e214:KeyValuePairOfstringstring>
            <e214:key i:nil="false">ValueHere</e214:key>
            <e214:value i:nil="false">ValueHere</e214:value>
          </e214:KeyValuePairOfstringstring>
        </e212:TaxInformation>
        <e212:BackUpPaymentInstrumentId i:nil="false">ValueHere</e212:BackUpPaymentInstrumentId>
        <e212:BillingThresholdAmount i:nil="false">ValueHere</e212:BillingThresholdAmount>
        <e212:BusinessAddress i:nil="false">
          <e212:City i:nil="false">ValueHere</e212:City>
          <e212:CountryCode i:nil="false">ValueHere</e212:CountryCode>
          <e212:Id i:nil="false">ValueHere</e212:Id>
          <e212:Line1 i:nil="false">ValueHere</e212:Line1>
          <e212:Line2 i:nil="false">ValueHere</e212:Line2>
          <e212:Line3 i:nil="false">ValueHere</e212:Line3>
          <e212:Line4 i:nil="false">ValueHere</e212:Line4>
          <e212:PostalCode i:nil="false">ValueHere</e212:PostalCode>
          <e212:StateOrProvince i:nil="false">ValueHere</e212:StateOrProvince>
          <e212:TimeStamp i:nil="false">ValueHere</e212:TimeStamp>
          <e212:BusinessName i:nil="false">ValueHere</e212:BusinessName>
        </e212:BusinessAddress>
        <e212:AutoTagType i:nil="false">ValueHere</e212:AutoTagType>
        <e212:SoldToPaymentInstrumentId i:nil="false">ValueHere</e212:SoldToPaymentInstrumentId>
        <e212:TaxCertificate i:nil="false">
          <e212:TaxCertificateBlobContainerName i:nil="false">ValueHere</e212:TaxCertificateBlobContainerName>
          <e212:TaxCertificates xmlns:e215="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e215:KeyValuePairOfstringbase64Binary>
              <e215:key i:nil="false">ValueHere</e215:key>
              <e215:value i:nil="false">ValueHere</e215:value>
            </e215:KeyValuePairOfstringbase64Binary>
          </e212:TaxCertificates>
          <e212:Status i:nil="false">ValueHere</e212:Status>
        </e212:TaxCertificate>
        <e212:AccountMode i:nil="false">ValueHere</e212:AccountMode>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e216="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e216:Id>ValueHere</e216:Id>
        <e216:FirstName i:nil="false">ValueHere</e216:FirstName>
        <e216:LastName i:nil="false">ValueHere</e216:LastName>
        <e216:Email i:nil="false">ValueHere</e216:Email>
        <e216:CustomerId>ValueHere</e216:CustomerId>
        <e216:RoleId>ValueHere</e216:RoleId>
        <e216:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e216:AccountIds>
        <e216:ExpirationDate>ValueHere</e216:ExpirationDate>
        <e216:Lcid>ValueHere</e216:Lcid>
      </UserInvitation>
      <UserId i:nil="false">ValueHere</UserId>
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
	UserInvitation userInvitation,
	long? userId)
{
	var request = new SignupCustomerRequest
	{
		Customer = customer,
		Account = account,
		ParentCustomerId = parentCustomerId,
		UserInvitation = userInvitation,
		UserId = userId
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SignupCustomerAsync(r), request));
}
```
```java
static SignupCustomerResponse signupCustomer(
	Customer customer,
	AdvertiserAccount account,
	java.lang.Long parentCustomerId,
	UserInvitation userInvitation,
	java.lang.Long userId) throws RemoteException, Exception
{
	SignupCustomerRequest request = new SignupCustomerRequest();

	request.setCustomer(customer);
	request.setAccount(account);
	request.setParentCustomerId(parentCustomerId);
	request.setUserInvitation(userInvitation);
	request.setUserId(userId);

	return CustomerManagementService.getService().signupCustomer(request);
}
```
```php
static function SignupCustomer(
	$customer,
	$account,
	$parentCustomerId,
	$userInvitation,
	$userId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SignupCustomerRequest();

	$request->Customer = $customer;
	$request->Account = $account;
	$request->ParentCustomerId = $parentCustomerId;
	$request->UserInvitation = $userInvitation;
	$request->UserId = $userId;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SignupCustomer($request);
}
```
```python
response=customermanagement_service.SignupCustomer(
	Customer=Customer,
	Account=Account,
	ParentCustomerId=ParentCustomerId,
	UserInvitation=UserInvitation,
	UserId=UserId)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

