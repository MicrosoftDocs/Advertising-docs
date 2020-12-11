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
      <Customer xmlns:e639="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e639:CustomerFinancialStatus i:nil="false">ValueHere</e639:CustomerFinancialStatus>
        <e639:Id i:nil="false">ValueHere</e639:Id>
        <e639:Industry i:nil="false">ValueHere</e639:Industry>
        <e639:LastModifiedByUserId i:nil="false">ValueHere</e639:LastModifiedByUserId>
        <e639:LastModifiedTime i:nil="false">ValueHere</e639:LastModifiedTime>
        <e639:MarketCountry i:nil="false">ValueHere</e639:MarketCountry>
        <e639:ForwardCompatibilityMap xmlns:e640="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e640:KeyValuePairOfstringstring>
            <e640:key i:nil="false">ValueHere</e640:key>
            <e640:value i:nil="false">ValueHere</e640:value>
          </e640:KeyValuePairOfstringstring>
        </e639:ForwardCompatibilityMap>
        <e639:MarketLanguage i:nil="false">ValueHere</e639:MarketLanguage>
        <e639:Name i:nil="false">ValueHere</e639:Name>
        <e639:ServiceLevel i:nil="false">ValueHere</e639:ServiceLevel>
        <e639:CustomerLifeCycleStatus i:nil="false">ValueHere</e639:CustomerLifeCycleStatus>
        <e639:TimeStamp i:nil="false">ValueHere</e639:TimeStamp>
        <e639:Number i:nil="false">ValueHere</e639:Number>
        <e639:CustomerAddress i:nil="false">
          <e639:City i:nil="false">ValueHere</e639:City>
          <e639:CountryCode i:nil="false">ValueHere</e639:CountryCode>
          <e639:Id i:nil="false">ValueHere</e639:Id>
          <e639:Line1 i:nil="false">ValueHere</e639:Line1>
          <e639:Line2 i:nil="false">ValueHere</e639:Line2>
          <e639:Line3 i:nil="false">ValueHere</e639:Line3>
          <e639:Line4 i:nil="false">ValueHere</e639:Line4>
          <e639:PostalCode i:nil="false">ValueHere</e639:PostalCode>
          <e639:StateOrProvince i:nil="false">ValueHere</e639:StateOrProvince>
          <e639:TimeStamp i:nil="false">ValueHere</e639:TimeStamp>
          <e639:BusinessName i:nil="false">ValueHere</e639:BusinessName>
        </e639:CustomerAddress>
      </Customer>
      <Account xmlns:e641="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e641:BillToCustomerId i:nil="false">ValueHere</e641:BillToCustomerId>
        <e641:CurrencyCode i:nil="false">ValueHere</e641:CurrencyCode>
        <e641:AccountFinancialStatus i:nil="false">ValueHere</e641:AccountFinancialStatus>
        <e641:Id i:nil="false">ValueHere</e641:Id>
        <e641:Language i:nil="false">ValueHere</e641:Language>
        <e641:LastModifiedByUserId i:nil="false">ValueHere</e641:LastModifiedByUserId>
        <e641:LastModifiedTime i:nil="false">ValueHere</e641:LastModifiedTime>
        <e641:Name i:nil="false">ValueHere</e641:Name>
        <e641:Number i:nil="false">ValueHere</e641:Number>
        <e641:ParentCustomerId>ValueHere</e641:ParentCustomerId>
        <e641:PaymentMethodId i:nil="false">ValueHere</e641:PaymentMethodId>
        <e641:PaymentMethodType i:nil="false">ValueHere</e641:PaymentMethodType>
        <e641:PrimaryUserId i:nil="false">ValueHere</e641:PrimaryUserId>
        <e641:AccountLifeCycleStatus i:nil="false">ValueHere</e641:AccountLifeCycleStatus>
        <e641:TimeStamp i:nil="false">ValueHere</e641:TimeStamp>
        <e641:TimeZone i:nil="false">ValueHere</e641:TimeZone>
        <e641:PauseReason i:nil="false">ValueHere</e641:PauseReason>
        <e641:ForwardCompatibilityMap xmlns:e642="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e642:KeyValuePairOfstringstring>
            <e642:key i:nil="false">ValueHere</e642:key>
            <e642:value i:nil="false">ValueHere</e642:value>
          </e642:KeyValuePairOfstringstring>
        </e641:ForwardCompatibilityMap>
        <e641:LinkedAgencies i:nil="false">
          <e641:CustomerInfo>
            <e641:Id i:nil="false">ValueHere</e641:Id>
            <e641:Name i:nil="false">ValueHere</e641:Name>
          </e641:CustomerInfo>
        </e641:LinkedAgencies>
        <e641:SalesHouseCustomerId i:nil="false">ValueHere</e641:SalesHouseCustomerId>
        <e641:TaxInformation xmlns:e643="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e643:KeyValuePairOfstringstring>
            <e643:key i:nil="false">ValueHere</e643:key>
            <e643:value i:nil="false">ValueHere</e643:value>
          </e643:KeyValuePairOfstringstring>
        </e641:TaxInformation>
        <e641:BackUpPaymentInstrumentId i:nil="false">ValueHere</e641:BackUpPaymentInstrumentId>
        <e641:BillingThresholdAmount i:nil="false">ValueHere</e641:BillingThresholdAmount>
        <e641:BusinessAddress i:nil="false">
          <e641:City i:nil="false">ValueHere</e641:City>
          <e641:CountryCode i:nil="false">ValueHere</e641:CountryCode>
          <e641:Id i:nil="false">ValueHere</e641:Id>
          <e641:Line1 i:nil="false">ValueHere</e641:Line1>
          <e641:Line2 i:nil="false">ValueHere</e641:Line2>
          <e641:Line3 i:nil="false">ValueHere</e641:Line3>
          <e641:Line4 i:nil="false">ValueHere</e641:Line4>
          <e641:PostalCode i:nil="false">ValueHere</e641:PostalCode>
          <e641:StateOrProvince i:nil="false">ValueHere</e641:StateOrProvince>
          <e641:TimeStamp i:nil="false">ValueHere</e641:TimeStamp>
          <e641:BusinessName i:nil="false">ValueHere</e641:BusinessName>
        </e641:BusinessAddress>
        <e641:AutoTagType i:nil="false">ValueHere</e641:AutoTagType>
        <e641:SoldToPaymentInstrumentId i:nil="false">ValueHere</e641:SoldToPaymentInstrumentId>
        <e641:TaxCertificate i:nil="false">
          <e641:TaxCertificateBlobContainerName i:nil="false">ValueHere</e641:TaxCertificateBlobContainerName>
          <e641:TaxCertificates xmlns:e644="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e644:KeyValuePairOfstringbase64Binary>
              <e644:key i:nil="false">ValueHere</e644:key>
              <e644:value i:nil="false">ValueHere</e644:value>
            </e644:KeyValuePairOfstringbase64Binary>
          </e641:TaxCertificates>
          <e641:Status i:nil="false">ValueHere</e641:Status>
        </e641:TaxCertificate>
      </Account>
      <ParentCustomerId i:nil="false">ValueHere</ParentCustomerId>
      <UserInvitation xmlns:e645="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e645:Id>ValueHere</e645:Id>
        <e645:FirstName i:nil="false">ValueHere</e645:FirstName>
        <e645:LastName i:nil="false">ValueHere</e645:LastName>
        <e645:Email i:nil="false">ValueHere</e645:Email>
        <e645:CustomerId>ValueHere</e645:CustomerId>
        <e645:RoleId>ValueHere</e645:RoleId>
        <e645:AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
          <a1:long>ValueHere</a1:long>
        </e645:AccountIds>
        <e645:ExpirationDate>ValueHere</e645:ExpirationDate>
        <e645:Lcid>ValueHere</e645:Lcid>
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

