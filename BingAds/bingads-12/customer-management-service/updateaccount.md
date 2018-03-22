---
title: UpdateAccount Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the details of the specified account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateAccount Service Operation - Customer Management
Updates the details of the specified account.

## <a name="request"></a>Request Elements
The *UpdateAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An *AdvertiserAccount* object that contains the updated account information.<br /><br />This operation overwrites the existing account data with the contents of the account object that you pass. This operation performs a full update, and not a partial update. The *Account* object must contain the time stamp value from the last time that the *Account* object was written to. To ensure that the time stamp contains the correct value, call the [GetAccount](getaccount.md) operation. You can then update the account data as appropriate, and call *UpdateAccount*.|[AdvertiserAccount](advertiseraccount.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">UpdateAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAccountRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <Account xmlns:e980="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e980:BillToCustomerId i:nil="false">ValueHere</e980:BillToCustomerId>
        <e980:CurrencyCode i:nil="false">ValueHere</e980:CurrencyCode>
        <e980:AccountFinancialStatus i:nil="false">ValueHere</e980:AccountFinancialStatus>
        <e980:Id i:nil="false">ValueHere</e980:Id>
        <e980:Language i:nil="false">ValueHere</e980:Language>
        <e980:LastModifiedByUserId i:nil="false">ValueHere</e980:LastModifiedByUserId>
        <e980:LastModifiedTime i:nil="false">ValueHere</e980:LastModifiedTime>
        <e980:Name i:nil="false">ValueHere</e980:Name>
        <e980:Number i:nil="false">ValueHere</e980:Number>
        <e980:ParentCustomerId>ValueHere</e980:ParentCustomerId>
        <e980:PaymentMethodId i:nil="false">ValueHere</e980:PaymentMethodId>
        <e980:PaymentMethodType i:nil="false">ValueHere</e980:PaymentMethodType>
        <e980:PrimaryUserId i:nil="false">ValueHere</e980:PrimaryUserId>
        <e980:AccountLifeCycleStatus i:nil="false">ValueHere</e980:AccountLifeCycleStatus>
        <e980:TimeStamp i:nil="false">ValueHere</e980:TimeStamp>
        <e980:TimeZone i:nil="false">ValueHere</e980:TimeZone>
        <e980:PauseReason i:nil="false">ValueHere</e980:PauseReason>
        <ForwardCompatibilityMap xmlns:e981="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e981:KeyValuePairOfstringstring>
            <e981:key i:nil="false">ValueHere</e981:key>
            <e981:value i:nil="false">ValueHere</e981:value>
          </e981:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e980:LinkedAgencies i:nil="false">
          <e980:CustomerInfo>
            <e980:Id i:nil="false">ValueHere</e980:Id>
            <e980:Name i:nil="false">ValueHere</e980:Name>
          </e980:CustomerInfo>
        </e980:LinkedAgencies>
        <e980:SalesHouseCustomerId i:nil="false">ValueHere</e980:SalesHouseCustomerId>
        <TaxInformation xmlns:e982="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e982:KeyValuePairOfstringstring>
            <e982:key i:nil="false">ValueHere</e982:key>
            <e982:value i:nil="false">ValueHere</e982:value>
          </e982:KeyValuePairOfstringstring>
        </TaxInformation>
        <e980:BackUpPaymentInstrumentId i:nil="false">ValueHere</e980:BackUpPaymentInstrumentId>
        <e980:BillingThresholdAmount i:nil="false">ValueHere</e980:BillingThresholdAmount>
        <e980:BusinessAddress i:nil="false">
          <e980:City i:nil="false">ValueHere</e980:City>
          <e980:CountryCode i:nil="false">ValueHere</e980:CountryCode>
          <e980:Id i:nil="false">ValueHere</e980:Id>
          <e980:Line1 i:nil="false">ValueHere</e980:Line1>
          <e980:Line2 i:nil="false">ValueHere</e980:Line2>
          <e980:Line3 i:nil="false">ValueHere</e980:Line3>
          <e980:Line4 i:nil="false">ValueHere</e980:Line4>
          <e980:PostalCode i:nil="false">ValueHere</e980:PostalCode>
          <e980:StateOrProvince i:nil="false">ValueHere</e980:StateOrProvince>
          <e980:TimeStamp i:nil="false">ValueHere</e980:TimeStamp>
          <e980:BusinessName i:nil="false">ValueHere</e980:BusinessName>
        </e980:BusinessAddress>
        <e980:AutoTagType i:nil="false">ValueHere</e980:AutoTagType>
        <e980:SoldToPaymentInstrumentId i:nil="false">ValueHere</e980:SoldToPaymentInstrumentId>
      </Account>
    </UpdateAccountRequest>
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
    <UpdateAccountResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAccountResponse> UpdateAccountAsync(
	AdvertiserAccount account)
{
	var request = new UpdateAccountRequest
	{
		Account = account
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.UpdateAccountAsync(r), request));
}
```
```java
static UpdateAccountResponse updateAccount(
	AdvertiserAccount account) throws RemoteException, Exception
{
	UpdateAccountRequest request = new UpdateAccountRequest();

	request.setAccount(account);

	return CustomerManagementService.getService().updateAccount(request);
}
```
```php
static function UpdateAccount(
	$account)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new UpdateAccountRequest();

	$request->Account = $account;

	return $GLOBALS['CustomerManagementProxy']->GetService()->UpdateAccount($request);
}
```
```python
response=customermanagement_service.UpdateAccount(
	Account=Account)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

