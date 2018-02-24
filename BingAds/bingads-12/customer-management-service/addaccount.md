---
title: AddAccount Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Creates a new account within an existing customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# AddAccount Service Operation - Customer Management
Creates a new account within an existing customer. 

Only a user with Super Admin credentials can add accounts. 

> [!IMPORTANT]
> Resellers should call [SignupCustomer](signupcustomer.md) instead of *AddAccount*. For more details see [Management Model for Resellers](bingads/guides/management-model-resellers.md).

## <a name="request"></a>Request Elements
The *AddAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|The account that you want to add to the existing customer.<br/><br/>You must specify the ParentCustomerId in the advertiser account object.|[Account](account.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
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
    <Action mustUnderstand="1">AddAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAccountRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Account xmlns:e1="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e1:AccountType>ValueHere</e1:AccountType>
        <e1:BillToCustomerId i:nil="false">ValueHere</e1:BillToCustomerId>
        <e1:CountryCode i:nil="false">ValueHere</e1:CountryCode>
        <e1:CurrencyType i:nil="false">ValueHere</e1:CurrencyType>
        <e1:AccountFinancialStatus i:nil="false">ValueHere</e1:AccountFinancialStatus>
        <e1:Id i:nil="false">ValueHere</e1:Id>
        <e1:Language i:nil="false">ValueHere</e1:Language>
        <ForwardCompatibilityMap xmlns:e2="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e2:KeyValuePairOfstringstring>
            <e2:key i:nil="false">ValueHere</e2:key>
            <e2:value i:nil="false">ValueHere</e2:value>
          </e2:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e1:LastModifiedByUserId i:nil="false">ValueHere</e1:LastModifiedByUserId>
        <e1:LastModifiedTime i:nil="false">ValueHere</e1:LastModifiedTime>
        <e1:Name i:nil="false">ValueHere</e1:Name>
        <e1:Number i:nil="false">ValueHere</e1:Number>
        <e1:ParentCustomerId>ValueHere</e1:ParentCustomerId>
        <e1:PaymentMethodId i:nil="false">ValueHere</e1:PaymentMethodId>
        <e1:PaymentMethodType i:nil="false">ValueHere</e1:PaymentMethodType>
        <e1:PrimaryUserId i:nil="false">ValueHere</e1:PrimaryUserId>
        <e1:AccountLifeCycleStatus i:nil="false">ValueHere</e1:AccountLifeCycleStatus>
        <e1:TimeStamp i:nil="false">ValueHere</e1:TimeStamp>
        <e1:TimeZone i:nil="false">ValueHere</e1:TimeZone>
        <e1:PauseReason i:nil="false">ValueHere</e1:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e1:LinkedAgencies i:nil="false">
          <e1:CustomerInfo>
            <e1:Id i:nil="false">ValueHere</e1:Id>
            <e1:Name i:nil="false">ValueHere</e1:Name>
          </e1:CustomerInfo>
        </e1:LinkedAgencies>
        <e1:SalesHouseCustomerId i:nil="false">ValueHere</e1:SalesHouseCustomerId>
        <TaxInformation xmlns:e3="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e3:KeyValuePairOfstringstring>
            <e3:key i:nil="false">ValueHere</e3:key>
            <e3:value i:nil="false">ValueHere</e3:value>
          </e3:KeyValuePairOfstringstring>
        </TaxInformation>
        <e1:BackUpPaymentInstrumentId i:nil="false">ValueHere</e1:BackUpPaymentInstrumentId>
        <e1:BillingThresholdAmount i:nil="false">ValueHere</e1:BillingThresholdAmount>
        <e1:BusinessAddress i:nil="false">
          <e1:City i:nil="false">ValueHere</e1:City>
          <e1:CountryCode i:nil="false">ValueHere</e1:CountryCode>
          <e1:Id i:nil="false">ValueHere</e1:Id>
          <e1:Line1 i:nil="false">ValueHere</e1:Line1>
          <e1:Line2 i:nil="false">ValueHere</e1:Line2>
          <e1:Line3 i:nil="false">ValueHere</e1:Line3>
          <e1:Line4 i:nil="false">ValueHere</e1:Line4>
          <e1:PostalCode i:nil="false">ValueHere</e1:PostalCode>
          <e1:StateOrProvince i:nil="false">ValueHere</e1:StateOrProvince>
          <e1:TimeStamp i:nil="false">ValueHere</e1:TimeStamp>
        </e1:BusinessAddress>
      </Account>
    </AddAccountRequest>
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
    <AddAccountResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <AccountId>ValueHere</AccountId>
      <AccountNumber d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</AccountNumber>
      <CreateTime>ValueHere</CreateTime>
    </AddAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](bingads/guides/client-libraries.md). See [Bing Ads Code Examples](bingads/guides/code-examples.md) for more examples.
```csharp
public async Task<AddAccountResponse> AddAccountAsync(
	Account account)
{
	var request = new AddAccountRequest
	{
		Account = account
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.AddAccountAsync(r), request));
}
```
```java
static AddAccountResponse addAccount(
	Account account) throws RemoteException, Exception
{
	AddAccountRequest request = new AddAccountRequest();

	request.setAccount(account);

	return CustomerManagementService.getService().addAccount(request);
}
```
```php
static function AddAccount(
	$account)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new AddAccountRequest();

	$request->Account = $account;

	return $GLOBALS['CustomerManagementProxy']->GetService()->AddAccount($request);
}
```
```python
response=customermanagement_service.AddAccount(
	Account=Account)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

