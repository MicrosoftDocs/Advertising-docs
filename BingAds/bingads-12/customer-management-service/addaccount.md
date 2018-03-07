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
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# AddAccount Service Operation - Customer Management
Creates a new account within an existing customer. 

Only a user with Super Admin credentials can add accounts. 

> [!IMPORTANT]
> Resellers should call [SignupCustomer](signupcustomer.md) instead of *AddAccount*. For more details see [Management Model for Resellers](../guides/management-model-resellers.md).

## <a name="request"></a>Request Elements
The *AddAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|The account that you want to add to the existing customer.<br/><br/>You must specify the ParentCustomerId in the advertiser account object.|[AdvertiserAccount](advertiseraccount.md)|

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">AddAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddAccountRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Account xmlns:e1217="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1217:BillToCustomerId i:nil="false">ValueHere</e1217:BillToCustomerId>
        <e1217:CountryCode i:nil="false">ValueHere</e1217:CountryCode>
        <e1217:CurrencyCode i:nil="false">ValueHere</e1217:CurrencyCode>
        <e1217:AccountFinancialStatus i:nil="false">ValueHere</e1217:AccountFinancialStatus>
        <e1217:Id i:nil="false">ValueHere</e1217:Id>
        <e1217:Language i:nil="false">ValueHere</e1217:Language>
        <e1217:LastModifiedByUserId i:nil="false">ValueHere</e1217:LastModifiedByUserId>
        <e1217:LastModifiedTime i:nil="false">ValueHere</e1217:LastModifiedTime>
        <e1217:Name i:nil="false">ValueHere</e1217:Name>
        <e1217:Number i:nil="false">ValueHere</e1217:Number>
        <e1217:ParentCustomerId>ValueHere</e1217:ParentCustomerId>
        <e1217:PaymentMethodId i:nil="false">ValueHere</e1217:PaymentMethodId>
        <e1217:PaymentMethodType i:nil="false">ValueHere</e1217:PaymentMethodType>
        <e1217:PrimaryUserId i:nil="false">ValueHere</e1217:PrimaryUserId>
        <e1217:AccountLifeCycleStatus i:nil="false">ValueHere</e1217:AccountLifeCycleStatus>
        <e1217:TimeStamp i:nil="false">ValueHere</e1217:TimeStamp>
        <e1217:TimeZone i:nil="false">ValueHere</e1217:TimeZone>
        <e1217:PauseReason i:nil="false">ValueHere</e1217:PauseReason>
        <ForwardCompatibilityMap xmlns:e1218="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1218:KeyValuePairOfstringstring>
            <e1218:key i:nil="false">ValueHere</e1218:key>
            <e1218:value i:nil="false">ValueHere</e1218:value>
          </e1218:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e1217:LinkedAgencies i:nil="false">
          <e1217:CustomerInfo>
            <e1217:Id i:nil="false">ValueHere</e1217:Id>
            <e1217:Name i:nil="false">ValueHere</e1217:Name>
          </e1217:CustomerInfo>
        </e1217:LinkedAgencies>
        <e1217:SalesHouseCustomerId i:nil="false">ValueHere</e1217:SalesHouseCustomerId>
        <TaxInformation xmlns:e1219="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1219:KeyValuePairOfstringstring>
            <e1219:key i:nil="false">ValueHere</e1219:key>
            <e1219:value i:nil="false">ValueHere</e1219:value>
          </e1219:KeyValuePairOfstringstring>
        </TaxInformation>
        <e1217:BackUpPaymentInstrumentId i:nil="false">ValueHere</e1217:BackUpPaymentInstrumentId>
        <e1217:BillingThresholdAmount i:nil="false">ValueHere</e1217:BillingThresholdAmount>
        <e1217:BusinessAddress i:nil="false">
          <e1217:City i:nil="false">ValueHere</e1217:City>
          <e1217:CountryCode i:nil="false">ValueHere</e1217:CountryCode>
          <e1217:Id i:nil="false">ValueHere</e1217:Id>
          <e1217:Line1 i:nil="false">ValueHere</e1217:Line1>
          <e1217:Line2 i:nil="false">ValueHere</e1217:Line2>
          <e1217:Line3 i:nil="false">ValueHere</e1217:Line3>
          <e1217:Line4 i:nil="false">ValueHere</e1217:Line4>
          <e1217:PostalCode i:nil="false">ValueHere</e1217:PostalCode>
          <e1217:StateOrProvince i:nil="false">ValueHere</e1217:StateOrProvince>
          <e1217:TimeStamp i:nil="false">ValueHere</e1217:TimeStamp>
        </e1217:BusinessAddress>
        <e1217:AutoTagType i:nil="false">ValueHere</e1217:AutoTagType>
      </Account>
    </AddAccountRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <AddAccountResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <AccountId>ValueHere</AccountId>
      <AccountNumber d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</AccountNumber>
      <CreateTime>ValueHere</CreateTime>
    </AddAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddAccountResponse> AddAccountAsync(
	AdvertiserAccount account)
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
	AdvertiserAccount account) throws RemoteException, Exception
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
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

