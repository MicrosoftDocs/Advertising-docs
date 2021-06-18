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
      <Customer xmlns:e449="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e449:CustomerFinancialStatus i:nil="false">ValueHere</e449:CustomerFinancialStatus>
        <e449:Id i:nil="false">ValueHere</e449:Id>
        <e449:Industry i:nil="false">ValueHere</e449:Industry>
        <e449:LastModifiedByUserId i:nil="false">ValueHere</e449:LastModifiedByUserId>
        <e449:LastModifiedTime i:nil="false">ValueHere</e449:LastModifiedTime>
        <e449:MarketCountry i:nil="false">ValueHere</e449:MarketCountry>
        <e449:ForwardCompatibilityMap xmlns:e450="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e450:KeyValuePairOfstringstring>
            <e450:key i:nil="false">ValueHere</e450:key>
            <e450:value i:nil="false">ValueHere</e450:value>
          </e450:KeyValuePairOfstringstring>
        </e449:ForwardCompatibilityMap>
        <e449:MarketLanguage i:nil="false">ValueHere</e449:MarketLanguage>
        <e449:Name i:nil="false">ValueHere</e449:Name>
        <e449:ServiceLevel i:nil="false">ValueHere</e449:ServiceLevel>
        <e449:CustomerLifeCycleStatus i:nil="false">ValueHere</e449:CustomerLifeCycleStatus>
        <e449:TimeStamp i:nil="false">ValueHere</e449:TimeStamp>
        <e449:Number i:nil="false">ValueHere</e449:Number>
        <e449:CustomerAddress i:nil="false">
          <e449:City i:nil="false">ValueHere</e449:City>
          <e449:CountryCode i:nil="false">ValueHere</e449:CountryCode>
          <e449:Id i:nil="false">ValueHere</e449:Id>
          <e449:Line1 i:nil="false">ValueHere</e449:Line1>
          <e449:Line2 i:nil="false">ValueHere</e449:Line2>
          <e449:Line3 i:nil="false">ValueHere</e449:Line3>
          <e449:Line4 i:nil="false">ValueHere</e449:Line4>
          <e449:PostalCode i:nil="false">ValueHere</e449:PostalCode>
          <e449:StateOrProvince i:nil="false">ValueHere</e449:StateOrProvince>
          <e449:TimeStamp i:nil="false">ValueHere</e449:TimeStamp>
          <e449:BusinessName i:nil="false">ValueHere</e449:BusinessName>
        </e449:CustomerAddress>
      </Customer>
      <Account xmlns:e451="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e451:BillToCustomerId i:nil="false">ValueHere</e451:BillToCustomerId>
        <e451:CurrencyCode i:nil="false">ValueHere</e451:CurrencyCode>
        <e451:AccountFinancialStatus i:nil="false">ValueHere</e451:AccountFinancialStatus>
        <e451:Id i:nil="false">ValueHere</e451:Id>
        <e451:Language i:nil="false">ValueHere</e451:Language>
        <e451:LastModifiedByUserId i:nil="false">ValueHere</e451:LastModifiedByUserId>
        <e451:LastModifiedTime i:nil="false">ValueHere</e451:LastModifiedTime>
        <e451:Name i:nil="false">ValueHere</e451:Name>
        <e451:Number i:nil="false">ValueHere</e451:Number>
        <e451:ParentCustomerId>ValueHere</e451:ParentCustomerId>
        <e451:PaymentMethodId i:nil="false">ValueHere</e451:PaymentMethodId>
        <e451:PaymentMethodType i:nil="false">ValueHere</e451:PaymentMethodType>
        <e451:PrimaryUserId i:nil="false">ValueHere</e451:PrimaryUserId>
        <e451:AccountLifeCycleStatus i:nil="false">ValueHere</e451:AccountLifeCycleStatus>
        <e451:TimeStamp i:nil="false">ValueHere</e451:TimeStamp>
        <e451:TimeZone i:nil="false">ValueHere</e451:TimeZone>
        <e451:PauseReason i:nil="false">ValueHere</e451:PauseReason>
        <e451:ForwardCompatibilityMap xmlns:e452="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e452:KeyValuePairOfstringstring>
            <e452:key i:nil="false">ValueHere</e452:key>
            <e452:value i:nil="false">ValueHere</e452:value>
          </e452:KeyValuePairOfstringstring>
        </e451:ForwardCompatibilityMap>
        <e451:LinkedAgencies i:nil="false">
          <e451:CustomerInfo>
            <e451:Id i:nil="false">ValueHere</e451:Id>
            <e451:Name i:nil="false">ValueHere</e451:Name>
          </e451:CustomerInfo>
        </e451:LinkedAgencies>
        <e451:SalesHouseCustomerId i:nil="false">ValueHere</e451:SalesHouseCustomerId>
        <e451:TaxInformation xmlns:e453="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e453:KeyValuePairOfstringstring>
            <e453:key i:nil="false">ValueHere</e453:key>
            <e453:value i:nil="false">ValueHere</e453:value>
          </e453:KeyValuePairOfstringstring>
        </e451:TaxInformation>
        <e451:BackUpPaymentInstrumentId i:nil="false">ValueHere</e451:BackUpPaymentInstrumentId>
        <e451:BillingThresholdAmount i:nil="false">ValueHere</e451:BillingThresholdAmount>
        <e451:BusinessAddress i:nil="false">
          <e451:City i:nil="false">ValueHere</e451:City>
          <e451:CountryCode i:nil="false">ValueHere</e451:CountryCode>
          <e451:Id i:nil="false">ValueHere</e451:Id>
          <e451:Line1 i:nil="false">ValueHere</e451:Line1>
          <e451:Line2 i:nil="false">ValueHere</e451:Line2>
          <e451:Line3 i:nil="false">ValueHere</e451:Line3>
          <e451:Line4 i:nil="false">ValueHere</e451:Line4>
          <e451:PostalCode i:nil="false">ValueHere</e451:PostalCode>
          <e451:StateOrProvince i:nil="false">ValueHere</e451:StateOrProvince>
          <e451:TimeStamp i:nil="false">ValueHere</e451:TimeStamp>
          <e451:BusinessName i:nil="false">ValueHere</e451:BusinessName>
        </e451:BusinessAddress>
        <e451:AutoTagType i:nil="false">ValueHere</e451:AutoTagType>
        <e451:SoldToPaymentInstrumentId i:nil="false">ValueHere</e451:SoldToPaymentInstrumentId>
        <e451:TaxCertificate i:nil="false">
          <e451:TaxCertificateBlobContainerName i:nil="false">ValueHere</e451:TaxCertificateBlobContainerName>
          <e451:TaxCertificates xmlns:e454="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e454:KeyValuePairOfstringbase64Binary>
              <e454:key i:nil="false">ValueHere</e454:key>
              <e454:value i:nil="false">ValueHere</e454:value>
            </e454:KeyValuePairOfstringbase64Binary>
          </e451:TaxCertificates>
          <e451:Status i:nil="false">ValueHere</e451:Status>
        </e451:TaxCertificate>
        <e451:AccountMode i:nil="false">ValueHere</e451:AccountMode>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e455="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e455:Id>ValueHere</e455:Id>
        <e455:FirstName i:nil="false">ValueHere</e455:FirstName>
        <e455:LastName i:nil="false">ValueHere</e455:LastName>
        <e455:Email i:nil="false">ValueHere</e455:Email>
        <e455:CustomerId>ValueHere</e455:CustomerId>
        <e455:RoleId>ValueHere</e455:RoleId>
        <e455:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e455:AccountIds>
        <e455:ExpirationDate>ValueHere</e455:ExpirationDate>
        <e455:Lcid>ValueHere</e455:Lcid>
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

