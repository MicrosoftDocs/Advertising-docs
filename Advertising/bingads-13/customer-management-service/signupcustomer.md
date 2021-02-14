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
      <Customer xmlns:e203="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e203:CustomerFinancialStatus i:nil="false">ValueHere</e203:CustomerFinancialStatus>
        <e203:Id i:nil="false">ValueHere</e203:Id>
        <e203:Industry i:nil="false">ValueHere</e203:Industry>
        <e203:LastModifiedByUserId i:nil="false">ValueHere</e203:LastModifiedByUserId>
        <e203:LastModifiedTime i:nil="false">ValueHere</e203:LastModifiedTime>
        <e203:MarketCountry i:nil="false">ValueHere</e203:MarketCountry>
        <e203:ForwardCompatibilityMap xmlns:e204="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e204:KeyValuePairOfstringstring>
            <e204:key i:nil="false">ValueHere</e204:key>
            <e204:value i:nil="false">ValueHere</e204:value>
          </e204:KeyValuePairOfstringstring>
        </e203:ForwardCompatibilityMap>
        <e203:MarketLanguage i:nil="false">ValueHere</e203:MarketLanguage>
        <e203:Name i:nil="false">ValueHere</e203:Name>
        <e203:ServiceLevel i:nil="false">ValueHere</e203:ServiceLevel>
        <e203:CustomerLifeCycleStatus i:nil="false">ValueHere</e203:CustomerLifeCycleStatus>
        <e203:TimeStamp i:nil="false">ValueHere</e203:TimeStamp>
        <e203:Number i:nil="false">ValueHere</e203:Number>
        <e203:CustomerAddress i:nil="false">
          <e203:City i:nil="false">ValueHere</e203:City>
          <e203:CountryCode i:nil="false">ValueHere</e203:CountryCode>
          <e203:Id i:nil="false">ValueHere</e203:Id>
          <e203:Line1 i:nil="false">ValueHere</e203:Line1>
          <e203:Line2 i:nil="false">ValueHere</e203:Line2>
          <e203:Line3 i:nil="false">ValueHere</e203:Line3>
          <e203:Line4 i:nil="false">ValueHere</e203:Line4>
          <e203:PostalCode i:nil="false">ValueHere</e203:PostalCode>
          <e203:StateOrProvince i:nil="false">ValueHere</e203:StateOrProvince>
          <e203:TimeStamp i:nil="false">ValueHere</e203:TimeStamp>
          <e203:BusinessName i:nil="false">ValueHere</e203:BusinessName>
        </e203:CustomerAddress>
      </Customer>
      <Account xmlns:e205="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e205:BillToCustomerId i:nil="false">ValueHere</e205:BillToCustomerId>
        <e205:CurrencyCode i:nil="false">ValueHere</e205:CurrencyCode>
        <e205:AccountFinancialStatus i:nil="false">ValueHere</e205:AccountFinancialStatus>
        <e205:Id i:nil="false">ValueHere</e205:Id>
        <e205:Language i:nil="false">ValueHere</e205:Language>
        <e205:LastModifiedByUserId i:nil="false">ValueHere</e205:LastModifiedByUserId>
        <e205:LastModifiedTime i:nil="false">ValueHere</e205:LastModifiedTime>
        <e205:Name i:nil="false">ValueHere</e205:Name>
        <e205:Number i:nil="false">ValueHere</e205:Number>
        <e205:ParentCustomerId>ValueHere</e205:ParentCustomerId>
        <e205:PaymentMethodId i:nil="false">ValueHere</e205:PaymentMethodId>
        <e205:PaymentMethodType i:nil="false">ValueHere</e205:PaymentMethodType>
        <e205:PrimaryUserId i:nil="false">ValueHere</e205:PrimaryUserId>
        <e205:AccountLifeCycleStatus i:nil="false">ValueHere</e205:AccountLifeCycleStatus>
        <e205:TimeStamp i:nil="false">ValueHere</e205:TimeStamp>
        <e205:TimeZone i:nil="false">ValueHere</e205:TimeZone>
        <e205:PauseReason i:nil="false">ValueHere</e205:PauseReason>
        <e205:ForwardCompatibilityMap xmlns:e206="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e206:KeyValuePairOfstringstring>
            <e206:key i:nil="false">ValueHere</e206:key>
            <e206:value i:nil="false">ValueHere</e206:value>
          </e206:KeyValuePairOfstringstring>
        </e205:ForwardCompatibilityMap>
        <e205:LinkedAgencies i:nil="false">
          <e205:CustomerInfo>
            <e205:Id i:nil="false">ValueHere</e205:Id>
            <e205:Name i:nil="false">ValueHere</e205:Name>
          </e205:CustomerInfo>
        </e205:LinkedAgencies>
        <e205:SalesHouseCustomerId i:nil="false">ValueHere</e205:SalesHouseCustomerId>
        <e205:TaxInformation xmlns:e207="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e207:KeyValuePairOfstringstring>
            <e207:key i:nil="false">ValueHere</e207:key>
            <e207:value i:nil="false">ValueHere</e207:value>
          </e207:KeyValuePairOfstringstring>
        </e205:TaxInformation>
        <e205:BackUpPaymentInstrumentId i:nil="false">ValueHere</e205:BackUpPaymentInstrumentId>
        <e205:BillingThresholdAmount i:nil="false">ValueHere</e205:BillingThresholdAmount>
        <e205:BusinessAddress i:nil="false">
          <e205:City i:nil="false">ValueHere</e205:City>
          <e205:CountryCode i:nil="false">ValueHere</e205:CountryCode>
          <e205:Id i:nil="false">ValueHere</e205:Id>
          <e205:Line1 i:nil="false">ValueHere</e205:Line1>
          <e205:Line2 i:nil="false">ValueHere</e205:Line2>
          <e205:Line3 i:nil="false">ValueHere</e205:Line3>
          <e205:Line4 i:nil="false">ValueHere</e205:Line4>
          <e205:PostalCode i:nil="false">ValueHere</e205:PostalCode>
          <e205:StateOrProvince i:nil="false">ValueHere</e205:StateOrProvince>
          <e205:TimeStamp i:nil="false">ValueHere</e205:TimeStamp>
          <e205:BusinessName i:nil="false">ValueHere</e205:BusinessName>
        </e205:BusinessAddress>
        <e205:AutoTagType i:nil="false">ValueHere</e205:AutoTagType>
        <e205:SoldToPaymentInstrumentId i:nil="false">ValueHere</e205:SoldToPaymentInstrumentId>
        <e205:TaxCertificate i:nil="false">
          <e205:TaxCertificateBlobContainerName i:nil="false">ValueHere</e205:TaxCertificateBlobContainerName>
          <e205:TaxCertificates xmlns:e208="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e208:KeyValuePairOfstringbase64Binary>
              <e208:key i:nil="false">ValueHere</e208:key>
              <e208:value i:nil="false">ValueHere</e208:value>
            </e208:KeyValuePairOfstringbase64Binary>
          </e205:TaxCertificates>
          <e205:Status i:nil="false">ValueHere</e205:Status>
        </e205:TaxCertificate>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e209="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e209:Id>ValueHere</e209:Id>
        <e209:FirstName i:nil="false">ValueHere</e209:FirstName>
        <e209:LastName i:nil="false">ValueHere</e209:LastName>
        <e209:Email i:nil="false">ValueHere</e209:Email>
        <e209:CustomerId>ValueHere</e209:CustomerId>
        <e209:RoleId>ValueHere</e209:RoleId>
        <e209:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e209:AccountIds>
        <e209:ExpirationDate>ValueHere</e209:ExpirationDate>
        <e209:Lcid>ValueHere</e209:Lcid>
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

