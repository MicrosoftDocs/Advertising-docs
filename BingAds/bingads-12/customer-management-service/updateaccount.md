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
      <Account xmlns:e1261="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e1261:BillToCustomerId i:nil="false">ValueHere</e1261:BillToCustomerId>
        <e1261:CountryCode i:nil="false">ValueHere</e1261:CountryCode>
        <e1261:CurrencyCode i:nil="false">ValueHere</e1261:CurrencyCode>
        <e1261:AccountFinancialStatus i:nil="false">ValueHere</e1261:AccountFinancialStatus>
        <e1261:Id i:nil="false">ValueHere</e1261:Id>
        <e1261:Language i:nil="false">ValueHere</e1261:Language>
        <e1261:LastModifiedByUserId i:nil="false">ValueHere</e1261:LastModifiedByUserId>
        <e1261:LastModifiedTime i:nil="false">ValueHere</e1261:LastModifiedTime>
        <e1261:Name i:nil="false">ValueHere</e1261:Name>
        <e1261:Number i:nil="false">ValueHere</e1261:Number>
        <e1261:ParentCustomerId>ValueHere</e1261:ParentCustomerId>
        <e1261:PaymentMethodId i:nil="false">ValueHere</e1261:PaymentMethodId>
        <e1261:PaymentMethodType i:nil="false">ValueHere</e1261:PaymentMethodType>
        <e1261:PrimaryUserId i:nil="false">ValueHere</e1261:PrimaryUserId>
        <e1261:AccountLifeCycleStatus i:nil="false">ValueHere</e1261:AccountLifeCycleStatus>
        <e1261:TimeStamp i:nil="false">ValueHere</e1261:TimeStamp>
        <e1261:TimeZone i:nil="false">ValueHere</e1261:TimeZone>
        <e1261:PauseReason i:nil="false">ValueHere</e1261:PauseReason>
        <ForwardCompatibilityMap xmlns:e1262="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1262:KeyValuePairOfstringstring>
            <e1262:key i:nil="false">ValueHere</e1262:key>
            <e1262:value i:nil="false">ValueHere</e1262:value>
          </e1262:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e1261:LinkedAgencies i:nil="false">
          <e1261:CustomerInfo>
            <e1261:Id i:nil="false">ValueHere</e1261:Id>
            <e1261:Name i:nil="false">ValueHere</e1261:Name>
          </e1261:CustomerInfo>
        </e1261:LinkedAgencies>
        <e1261:SalesHouseCustomerId i:nil="false">ValueHere</e1261:SalesHouseCustomerId>
        <TaxInformation xmlns:e1263="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e1263:KeyValuePairOfstringstring>
            <e1263:key i:nil="false">ValueHere</e1263:key>
            <e1263:value i:nil="false">ValueHere</e1263:value>
          </e1263:KeyValuePairOfstringstring>
        </TaxInformation>
        <e1261:BackUpPaymentInstrumentId i:nil="false">ValueHere</e1261:BackUpPaymentInstrumentId>
        <e1261:BillingThresholdAmount i:nil="false">ValueHere</e1261:BillingThresholdAmount>
        <e1261:BusinessAddress i:nil="false">
          <e1261:City i:nil="false">ValueHere</e1261:City>
          <e1261:CountryCode i:nil="false">ValueHere</e1261:CountryCode>
          <e1261:Id i:nil="false">ValueHere</e1261:Id>
          <e1261:Line1 i:nil="false">ValueHere</e1261:Line1>
          <e1261:Line2 i:nil="false">ValueHere</e1261:Line2>
          <e1261:Line3 i:nil="false">ValueHere</e1261:Line3>
          <e1261:Line4 i:nil="false">ValueHere</e1261:Line4>
          <e1261:PostalCode i:nil="false">ValueHere</e1261:PostalCode>
          <e1261:StateOrProvince i:nil="false">ValueHere</e1261:StateOrProvince>
          <e1261:TimeStamp i:nil="false">ValueHere</e1261:TimeStamp>
        </e1261:BusinessAddress>
        <e1261:AutoTagType i:nil="false">ValueHere</e1261:AutoTagType>
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

