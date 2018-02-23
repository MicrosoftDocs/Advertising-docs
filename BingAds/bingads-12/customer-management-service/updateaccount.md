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

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

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
      <Account xmlns:e712="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e712:BillToCustomerId i:nil="false">ValueHere</e712:BillToCustomerId>
        <e712:CountryCode i:nil="false">ValueHere</e712:CountryCode>
        <e712:CurrencyType i:nil="false">ValueHere</e712:CurrencyType>
        <e712:AccountFinancialStatus i:nil="false">ValueHere</e712:AccountFinancialStatus>
        <e712:Id i:nil="false">ValueHere</e712:Id>
        <e712:Language i:nil="false">ValueHere</e712:Language>
        <e712:LastModifiedByUserId i:nil="false">ValueHere</e712:LastModifiedByUserId>
        <e712:LastModifiedTime i:nil="false">ValueHere</e712:LastModifiedTime>
        <e712:Name i:nil="false">ValueHere</e712:Name>
        <e712:Number i:nil="false">ValueHere</e712:Number>
        <e712:ParentCustomerId>ValueHere</e712:ParentCustomerId>
        <e712:PaymentMethodId i:nil="false">ValueHere</e712:PaymentMethodId>
        <e712:PaymentMethodType i:nil="false">ValueHere</e712:PaymentMethodType>
        <e712:PrimaryUserId i:nil="false">ValueHere</e712:PrimaryUserId>
        <e712:AccountLifeCycleStatus i:nil="false">ValueHere</e712:AccountLifeCycleStatus>
        <e712:TimeStamp i:nil="false">ValueHere</e712:TimeStamp>
        <e712:TimeZone i:nil="false">ValueHere</e712:TimeZone>
        <e712:PauseReason i:nil="false">ValueHere</e712:PauseReason>
        <ForwardCompatibilityMap xmlns:e713="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e713:KeyValuePairOfstringstring>
            <e713:key i:nil="false">ValueHere</e713:key>
            <e713:value i:nil="false">ValueHere</e713:value>
          </e713:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e712:LinkedAgencies i:nil="false">
          <e712:CustomerInfo>
            <e712:Id i:nil="false">ValueHere</e712:Id>
            <e712:Name i:nil="false">ValueHere</e712:Name>
          </e712:CustomerInfo>
        </e712:LinkedAgencies>
        <e712:SalesHouseCustomerId i:nil="false">ValueHere</e712:SalesHouseCustomerId>
        <TaxInformation xmlns:e714="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e714:KeyValuePairOfstringstring>
            <e714:key i:nil="false">ValueHere</e714:key>
            <e714:value i:nil="false">ValueHere</e714:value>
          </e714:KeyValuePairOfstringstring>
        </TaxInformation>
        <e712:BackUpPaymentInstrumentId i:nil="false">ValueHere</e712:BackUpPaymentInstrumentId>
        <e712:BillingThresholdAmount i:nil="false">ValueHere</e712:BillingThresholdAmount>
        <e712:BusinessAddress i:nil="false">
          <e712:City i:nil="false">ValueHere</e712:City>
          <e712:CountryCode i:nil="false">ValueHere</e712:CountryCode>
          <e712:Id i:nil="false">ValueHere</e712:Id>
          <e712:Line1 i:nil="false">ValueHere</e712:Line1>
          <e712:Line2 i:nil="false">ValueHere</e712:Line2>
          <e712:Line3 i:nil="false">ValueHere</e712:Line3>
          <e712:Line4 i:nil="false">ValueHere</e712:Line4>
          <e712:PostalCode i:nil="false">ValueHere</e712:PostalCode>
          <e712:StateOrProvince i:nil="false">ValueHere</e712:StateOrProvince>
          <e712:TimeStamp i:nil="false">ValueHere</e712:TimeStamp>
        </e712:BusinessAddress>
        <e712:AutoTagType i:nil="false">ValueHere</e712:AutoTagType>
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
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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

