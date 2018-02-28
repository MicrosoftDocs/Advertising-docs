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
> This Bing Ads API Version 12 preview documentation is subject to change.

# UpdateAccount Service Operation - Customer Management
Updates the details of the specified account.

## <a name="request"></a>Request Elements
The *UpdateAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An *AdvertiserAccount* object that contains the updated account information.<br /><br />This operation overwrites the existing account data with the contents of the account object that you pass. This operation performs a full update, and not a partial update. The *Account* object must contain the time stamp value from the last time that the *Account* object was written to. To ensure that the time stamp contains the correct value, call the [GetAccount](../customer-management-service/getaccount.md) operation. You can then update the account data as appropriate, and call *UpdateAccount*.|[AdvertiserAccount](advertiseraccount.md)|

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
      <Account xmlns:e355="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e355:BillToCustomerId i:nil="false">ValueHere</e355:BillToCustomerId>
        <e355:CountryCode i:nil="false">ValueHere</e355:CountryCode>
        <e355:CurrencyCode i:nil="false">ValueHere</e355:CurrencyCode>
        <e355:AccountFinancialStatus i:nil="false">ValueHere</e355:AccountFinancialStatus>
        <e355:Id i:nil="false">ValueHere</e355:Id>
        <e355:Language i:nil="false">ValueHere</e355:Language>
        <e355:LastModifiedByUserId i:nil="false">ValueHere</e355:LastModifiedByUserId>
        <e355:LastModifiedTime i:nil="false">ValueHere</e355:LastModifiedTime>
        <e355:Name i:nil="false">ValueHere</e355:Name>
        <e355:Number i:nil="false">ValueHere</e355:Number>
        <e355:ParentCustomerId>ValueHere</e355:ParentCustomerId>
        <e355:PaymentMethodId i:nil="false">ValueHere</e355:PaymentMethodId>
        <e355:PaymentMethodType i:nil="false">ValueHere</e355:PaymentMethodType>
        <e355:PrimaryUserId i:nil="false">ValueHere</e355:PrimaryUserId>
        <e355:AccountLifeCycleStatus i:nil="false">ValueHere</e355:AccountLifeCycleStatus>
        <e355:TimeStamp i:nil="false">ValueHere</e355:TimeStamp>
        <e355:TimeZone i:nil="false">ValueHere</e355:TimeZone>
        <e355:PauseReason i:nil="false">ValueHere</e355:PauseReason>
        <ForwardCompatibilityMap xmlns:e356="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e356:KeyValuePairOfstringstring>
            <e356:key i:nil="false">ValueHere</e356:key>
            <e356:value i:nil="false">ValueHere</e356:value>
          </e356:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e355:LinkedAgencies i:nil="false">
          <e355:CustomerInfo>
            <e355:Id i:nil="false">ValueHere</e355:Id>
            <e355:Name i:nil="false">ValueHere</e355:Name>
          </e355:CustomerInfo>
        </e355:LinkedAgencies>
        <e355:SalesHouseCustomerId i:nil="false">ValueHere</e355:SalesHouseCustomerId>
        <TaxInformation xmlns:e357="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e357:KeyValuePairOfstringstring>
            <e357:key i:nil="false">ValueHere</e357:key>
            <e357:value i:nil="false">ValueHere</e357:value>
          </e357:KeyValuePairOfstringstring>
        </TaxInformation>
        <e355:BackUpPaymentInstrumentId i:nil="false">ValueHere</e355:BackUpPaymentInstrumentId>
        <e355:BillingThresholdAmount i:nil="false">ValueHere</e355:BillingThresholdAmount>
        <e355:BusinessAddress i:nil="false">
          <e355:City i:nil="false">ValueHere</e355:City>
          <e355:CountryCode i:nil="false">ValueHere</e355:CountryCode>
          <e355:Id i:nil="false">ValueHere</e355:Id>
          <e355:Line1 i:nil="false">ValueHere</e355:Line1>
          <e355:Line2 i:nil="false">ValueHere</e355:Line2>
          <e355:Line3 i:nil="false">ValueHere</e355:Line3>
          <e355:Line4 i:nil="false">ValueHere</e355:Line4>
          <e355:PostalCode i:nil="false">ValueHere</e355:PostalCode>
          <e355:StateOrProvince i:nil="false">ValueHere</e355:StateOrProvince>
          <e355:TimeStamp i:nil="false">ValueHere</e355:TimeStamp>
        </e355:BusinessAddress>
        <e355:AutoTagType i:nil="false">ValueHere</e355:AutoTagType>
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
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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

