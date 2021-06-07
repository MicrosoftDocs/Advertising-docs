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
      <Customer xmlns:e694="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e694:CustomerFinancialStatus i:nil="false">ValueHere</e694:CustomerFinancialStatus>
        <e694:Id i:nil="false">ValueHere</e694:Id>
        <e694:Industry i:nil="false">ValueHere</e694:Industry>
        <e694:LastModifiedByUserId i:nil="false">ValueHere</e694:LastModifiedByUserId>
        <e694:LastModifiedTime i:nil="false">ValueHere</e694:LastModifiedTime>
        <e694:MarketCountry i:nil="false">ValueHere</e694:MarketCountry>
        <e694:ForwardCompatibilityMap xmlns:e695="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e695:KeyValuePairOfstringstring>
            <e695:key i:nil="false">ValueHere</e695:key>
            <e695:value i:nil="false">ValueHere</e695:value>
          </e695:KeyValuePairOfstringstring>
        </e694:ForwardCompatibilityMap>
        <e694:MarketLanguage i:nil="false">ValueHere</e694:MarketLanguage>
        <e694:Name i:nil="false">ValueHere</e694:Name>
        <e694:ServiceLevel i:nil="false">ValueHere</e694:ServiceLevel>
        <e694:CustomerLifeCycleStatus i:nil="false">ValueHere</e694:CustomerLifeCycleStatus>
        <e694:TimeStamp i:nil="false">ValueHere</e694:TimeStamp>
        <e694:Number i:nil="false">ValueHere</e694:Number>
        <e694:CustomerAddress i:nil="false">
          <e694:City i:nil="false">ValueHere</e694:City>
          <e694:CountryCode i:nil="false">ValueHere</e694:CountryCode>
          <e694:Id i:nil="false">ValueHere</e694:Id>
          <e694:Line1 i:nil="false">ValueHere</e694:Line1>
          <e694:Line2 i:nil="false">ValueHere</e694:Line2>
          <e694:Line3 i:nil="false">ValueHere</e694:Line3>
          <e694:Line4 i:nil="false">ValueHere</e694:Line4>
          <e694:PostalCode i:nil="false">ValueHere</e694:PostalCode>
          <e694:StateOrProvince i:nil="false">ValueHere</e694:StateOrProvince>
          <e694:TimeStamp i:nil="false">ValueHere</e694:TimeStamp>
          <e694:BusinessName i:nil="false">ValueHere</e694:BusinessName>
        </e694:CustomerAddress>
      </Customer>
      <Account xmlns:e696="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e696:BillToCustomerId i:nil="false">ValueHere</e696:BillToCustomerId>
        <e696:CurrencyCode i:nil="false">ValueHere</e696:CurrencyCode>
        <e696:AccountFinancialStatus i:nil="false">ValueHere</e696:AccountFinancialStatus>
        <e696:Id i:nil="false">ValueHere</e696:Id>
        <e696:Language i:nil="false">ValueHere</e696:Language>
        <e696:LastModifiedByUserId i:nil="false">ValueHere</e696:LastModifiedByUserId>
        <e696:LastModifiedTime i:nil="false">ValueHere</e696:LastModifiedTime>
        <e696:Name i:nil="false">ValueHere</e696:Name>
        <e696:Number i:nil="false">ValueHere</e696:Number>
        <e696:ParentCustomerId>ValueHere</e696:ParentCustomerId>
        <e696:PaymentMethodId i:nil="false">ValueHere</e696:PaymentMethodId>
        <e696:PaymentMethodType i:nil="false">ValueHere</e696:PaymentMethodType>
        <e696:PrimaryUserId i:nil="false">ValueHere</e696:PrimaryUserId>
        <e696:AccountLifeCycleStatus i:nil="false">ValueHere</e696:AccountLifeCycleStatus>
        <e696:TimeStamp i:nil="false">ValueHere</e696:TimeStamp>
        <e696:TimeZone i:nil="false">ValueHere</e696:TimeZone>
        <e696:PauseReason i:nil="false">ValueHere</e696:PauseReason>
        <e696:ForwardCompatibilityMap xmlns:e697="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e697:KeyValuePairOfstringstring>
            <e697:key i:nil="false">ValueHere</e697:key>
            <e697:value i:nil="false">ValueHere</e697:value>
          </e697:KeyValuePairOfstringstring>
        </e696:ForwardCompatibilityMap>
        <e696:LinkedAgencies i:nil="false">
          <e696:CustomerInfo>
            <e696:Id i:nil="false">ValueHere</e696:Id>
            <e696:Name i:nil="false">ValueHere</e696:Name>
          </e696:CustomerInfo>
        </e696:LinkedAgencies>
        <e696:SalesHouseCustomerId i:nil="false">ValueHere</e696:SalesHouseCustomerId>
        <e696:TaxInformation xmlns:e698="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e698:KeyValuePairOfstringstring>
            <e698:key i:nil="false">ValueHere</e698:key>
            <e698:value i:nil="false">ValueHere</e698:value>
          </e698:KeyValuePairOfstringstring>
        </e696:TaxInformation>
        <e696:BackUpPaymentInstrumentId i:nil="false">ValueHere</e696:BackUpPaymentInstrumentId>
        <e696:BillingThresholdAmount i:nil="false">ValueHere</e696:BillingThresholdAmount>
        <e696:BusinessAddress i:nil="false">
          <e696:City i:nil="false">ValueHere</e696:City>
          <e696:CountryCode i:nil="false">ValueHere</e696:CountryCode>
          <e696:Id i:nil="false">ValueHere</e696:Id>
          <e696:Line1 i:nil="false">ValueHere</e696:Line1>
          <e696:Line2 i:nil="false">ValueHere</e696:Line2>
          <e696:Line3 i:nil="false">ValueHere</e696:Line3>
          <e696:Line4 i:nil="false">ValueHere</e696:Line4>
          <e696:PostalCode i:nil="false">ValueHere</e696:PostalCode>
          <e696:StateOrProvince i:nil="false">ValueHere</e696:StateOrProvince>
          <e696:TimeStamp i:nil="false">ValueHere</e696:TimeStamp>
          <e696:BusinessName i:nil="false">ValueHere</e696:BusinessName>
        </e696:BusinessAddress>
        <e696:AutoTagType i:nil="false">ValueHere</e696:AutoTagType>
        <e696:SoldToPaymentInstrumentId i:nil="false">ValueHere</e696:SoldToPaymentInstrumentId>
        <e696:TaxCertificate i:nil="false">
          <e696:TaxCertificateBlobContainerName i:nil="false">ValueHere</e696:TaxCertificateBlobContainerName>
          <e696:TaxCertificates xmlns:e699="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e699:KeyValuePairOfstringbase64Binary>
              <e699:key i:nil="false">ValueHere</e699:key>
              <e699:value i:nil="false">ValueHere</e699:value>
            </e699:KeyValuePairOfstringbase64Binary>
          </e696:TaxCertificates>
          <e696:Status i:nil="false">ValueHere</e696:Status>
        </e696:TaxCertificate>
        <e696:AccountMode i:nil="false">ValueHere</e696:AccountMode>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e700="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e700:Id>ValueHere</e700:Id>
        <e700:FirstName i:nil="false">ValueHere</e700:FirstName>
        <e700:LastName i:nil="false">ValueHere</e700:LastName>
        <e700:Email i:nil="false">ValueHere</e700:Email>
        <e700:CustomerId>ValueHere</e700:CustomerId>
        <e700:RoleId>ValueHere</e700:RoleId>
        <e700:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e700:AccountIds>
        <e700:ExpirationDate>ValueHere</e700:ExpirationDate>
        <e700:Lcid>ValueHere</e700:Lcid>
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

