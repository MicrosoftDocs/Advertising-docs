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
|<a name="userid"></a>UserId|Reserved.|**long**|
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
      <Customer xmlns:e427="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e427:CustomerFinancialStatus i:nil="false">ValueHere</e427:CustomerFinancialStatus>
        <e427:Id i:nil="false">ValueHere</e427:Id>
        <e427:Industry i:nil="false">ValueHere</e427:Industry>
        <e427:LastModifiedByUserId i:nil="false">ValueHere</e427:LastModifiedByUserId>
        <e427:LastModifiedTime i:nil="false">ValueHere</e427:LastModifiedTime>
        <e427:MarketCountry i:nil="false">ValueHere</e427:MarketCountry>
        <e427:ForwardCompatibilityMap xmlns:e428="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e428:KeyValuePairOfstringstring>
            <e428:key i:nil="false">ValueHere</e428:key>
            <e428:value i:nil="false">ValueHere</e428:value>
          </e428:KeyValuePairOfstringstring>
        </e427:ForwardCompatibilityMap>
        <e427:MarketLanguage i:nil="false">ValueHere</e427:MarketLanguage>
        <e427:Name i:nil="false">ValueHere</e427:Name>
        <e427:ServiceLevel i:nil="false">ValueHere</e427:ServiceLevel>
        <e427:CustomerLifeCycleStatus i:nil="false">ValueHere</e427:CustomerLifeCycleStatus>
        <e427:TimeStamp i:nil="false">ValueHere</e427:TimeStamp>
        <e427:Number i:nil="false">ValueHere</e427:Number>
        <e427:CustomerAddress i:nil="false">
          <e427:City i:nil="false">ValueHere</e427:City>
          <e427:CountryCode i:nil="false">ValueHere</e427:CountryCode>
          <e427:Id i:nil="false">ValueHere</e427:Id>
          <e427:Line1 i:nil="false">ValueHere</e427:Line1>
          <e427:Line2 i:nil="false">ValueHere</e427:Line2>
          <e427:Line3 i:nil="false">ValueHere</e427:Line3>
          <e427:Line4 i:nil="false">ValueHere</e427:Line4>
          <e427:PostalCode i:nil="false">ValueHere</e427:PostalCode>
          <e427:StateOrProvince i:nil="false">ValueHere</e427:StateOrProvince>
          <e427:TimeStamp i:nil="false">ValueHere</e427:TimeStamp>
          <e427:BusinessName i:nil="false">ValueHere</e427:BusinessName>
        </e427:CustomerAddress>
      </Customer>
      <Account xmlns:e429="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e429:BillToCustomerId i:nil="false">ValueHere</e429:BillToCustomerId>
        <e429:CurrencyCode i:nil="false">ValueHere</e429:CurrencyCode>
        <e429:AccountFinancialStatus i:nil="false">ValueHere</e429:AccountFinancialStatus>
        <e429:Id i:nil="false">ValueHere</e429:Id>
        <e429:Language i:nil="false">ValueHere</e429:Language>
        <e429:LastModifiedByUserId i:nil="false">ValueHere</e429:LastModifiedByUserId>
        <e429:LastModifiedTime i:nil="false">ValueHere</e429:LastModifiedTime>
        <e429:Name i:nil="false">ValueHere</e429:Name>
        <e429:Number i:nil="false">ValueHere</e429:Number>
        <e429:ParentCustomerId>ValueHere</e429:ParentCustomerId>
        <e429:PaymentMethodId i:nil="false">ValueHere</e429:PaymentMethodId>
        <e429:PaymentMethodType i:nil="false">ValueHere</e429:PaymentMethodType>
        <e429:PrimaryUserId i:nil="false">ValueHere</e429:PrimaryUserId>
        <e429:AccountLifeCycleStatus i:nil="false">ValueHere</e429:AccountLifeCycleStatus>
        <e429:TimeStamp i:nil="false">ValueHere</e429:TimeStamp>
        <e429:TimeZone i:nil="false">ValueHere</e429:TimeZone>
        <e429:PauseReason i:nil="false">ValueHere</e429:PauseReason>
        <e429:ForwardCompatibilityMap xmlns:e430="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e430:KeyValuePairOfstringstring>
            <e430:key i:nil="false">ValueHere</e430:key>
            <e430:value i:nil="false">ValueHere</e430:value>
          </e430:KeyValuePairOfstringstring>
        </e429:ForwardCompatibilityMap>
        <e429:LinkedAgencies i:nil="false">
          <e429:CustomerInfo>
            <e429:Id i:nil="false">ValueHere</e429:Id>
            <e429:Name i:nil="false">ValueHere</e429:Name>
          </e429:CustomerInfo>
        </e429:LinkedAgencies>
        <e429:SalesHouseCustomerId i:nil="false">ValueHere</e429:SalesHouseCustomerId>
        <e429:TaxInformation xmlns:e431="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e431:KeyValuePairOfstringstring>
            <e431:key i:nil="false">ValueHere</e431:key>
            <e431:value i:nil="false">ValueHere</e431:value>
          </e431:KeyValuePairOfstringstring>
        </e429:TaxInformation>
        <e429:BackUpPaymentInstrumentId i:nil="false">ValueHere</e429:BackUpPaymentInstrumentId>
        <e429:BillingThresholdAmount i:nil="false">ValueHere</e429:BillingThresholdAmount>
        <e429:BusinessAddress i:nil="false">
          <e429:City i:nil="false">ValueHere</e429:City>
          <e429:CountryCode i:nil="false">ValueHere</e429:CountryCode>
          <e429:Id i:nil="false">ValueHere</e429:Id>
          <e429:Line1 i:nil="false">ValueHere</e429:Line1>
          <e429:Line2 i:nil="false">ValueHere</e429:Line2>
          <e429:Line3 i:nil="false">ValueHere</e429:Line3>
          <e429:Line4 i:nil="false">ValueHere</e429:Line4>
          <e429:PostalCode i:nil="false">ValueHere</e429:PostalCode>
          <e429:StateOrProvince i:nil="false">ValueHere</e429:StateOrProvince>
          <e429:TimeStamp i:nil="false">ValueHere</e429:TimeStamp>
          <e429:BusinessName i:nil="false">ValueHere</e429:BusinessName>
        </e429:BusinessAddress>
        <e429:AutoTagType i:nil="false">ValueHere</e429:AutoTagType>
        <e429:SoldToPaymentInstrumentId i:nil="false">ValueHere</e429:SoldToPaymentInstrumentId>
        <e429:TaxCertificate i:nil="false">
          <e429:TaxCertificateBlobContainerName i:nil="false">ValueHere</e429:TaxCertificateBlobContainerName>
          <e429:TaxCertificates xmlns:e432="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e432:KeyValuePairOfstringbase64Binary>
              <e432:key i:nil="false">ValueHere</e432:key>
              <e432:value i:nil="false">ValueHere</e432:value>
            </e432:KeyValuePairOfstringbase64Binary>
          </e429:TaxCertificates>
          <e429:Status i:nil="false">ValueHere</e429:Status>
        </e429:TaxCertificate>
        <e429:AccountMode i:nil="false">ValueHere</e429:AccountMode>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e433="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e433:Id>ValueHere</e433:Id>
        <e433:FirstName i:nil="false">ValueHere</e433:FirstName>
        <e433:LastName i:nil="false">ValueHere</e433:LastName>
        <e433:Email i:nil="false">ValueHere</e433:Email>
        <e433:CustomerId>ValueHere</e433:CustomerId>
        <e433:RoleId>ValueHere</e433:RoleId>
        <e433:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e433:AccountIds>
        <e433:ExpirationDate>ValueHere</e433:ExpirationDate>
        <e433:Lcid>ValueHere</e433:Lcid>
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

