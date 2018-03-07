---
title: GetAccount Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of an account.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetAccount Service Operation - Customer Management
Gets the details of an account.

## <a name="request"></a>Request Elements
The *GetAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountid"></a>AccountId|The identifier of the account to get.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An account object that contains information about the account, such as payment method, account type, and parent customer.|[AdvertiserAccount](advertiseraccount.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">GetAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <AccountId>ValueHere</AccountId>
    </GetAccountRequest>
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
    <GetAccountResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <Account xmlns:e1226="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1226:BillToCustomerId d4p1:nil="false">ValueHere</e1226:BillToCustomerId>
        <e1226:CountryCode d4p1:nil="false">ValueHere</e1226:CountryCode>
        <e1226:CurrencyCode d4p1:nil="false">ValueHere</e1226:CurrencyCode>
        <e1226:AccountFinancialStatus d4p1:nil="false">ValueHere</e1226:AccountFinancialStatus>
        <e1226:Id d4p1:nil="false">ValueHere</e1226:Id>
        <e1226:Language d4p1:nil="false">ValueHere</e1226:Language>
        <e1226:LastModifiedByUserId d4p1:nil="false">ValueHere</e1226:LastModifiedByUserId>
        <e1226:LastModifiedTime d4p1:nil="false">ValueHere</e1226:LastModifiedTime>
        <e1226:Name d4p1:nil="false">ValueHere</e1226:Name>
        <e1226:Number d4p1:nil="false">ValueHere</e1226:Number>
        <e1226:ParentCustomerId>ValueHere</e1226:ParentCustomerId>
        <e1226:PaymentMethodId d4p1:nil="false">ValueHere</e1226:PaymentMethodId>
        <e1226:PaymentMethodType d4p1:nil="false">ValueHere</e1226:PaymentMethodType>
        <e1226:PrimaryUserId d4p1:nil="false">ValueHere</e1226:PrimaryUserId>
        <e1226:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e1226:AccountLifeCycleStatus>
        <e1226:TimeStamp d4p1:nil="false">ValueHere</e1226:TimeStamp>
        <e1226:TimeZone d4p1:nil="false">ValueHere</e1226:TimeZone>
        <e1226:PauseReason d4p1:nil="false">ValueHere</e1226:PauseReason>
        <ForwardCompatibilityMap xmlns:e1227="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e1227:KeyValuePairOfstringstring>
            <e1227:key d4p1:nil="false">ValueHere</e1227:key>
            <e1227:value d4p1:nil="false">ValueHere</e1227:value>
          </e1227:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e1226:LinkedAgencies d4p1:nil="false">
          <e1226:CustomerInfo>
            <e1226:Id d4p1:nil="false">ValueHere</e1226:Id>
            <e1226:Name d4p1:nil="false">ValueHere</e1226:Name>
          </e1226:CustomerInfo>
        </e1226:LinkedAgencies>
        <e1226:SalesHouseCustomerId d4p1:nil="false">ValueHere</e1226:SalesHouseCustomerId>
        <TaxInformation xmlns:e1228="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e1228:KeyValuePairOfstringstring>
            <e1228:key d4p1:nil="false">ValueHere</e1228:key>
            <e1228:value d4p1:nil="false">ValueHere</e1228:value>
          </e1228:KeyValuePairOfstringstring>
        </TaxInformation>
        <e1226:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e1226:BackUpPaymentInstrumentId>
        <e1226:BillingThresholdAmount d4p1:nil="false">ValueHere</e1226:BillingThresholdAmount>
        <e1226:BusinessAddress d4p1:nil="false">
          <e1226:City d4p1:nil="false">ValueHere</e1226:City>
          <e1226:CountryCode d4p1:nil="false">ValueHere</e1226:CountryCode>
          <e1226:Id d4p1:nil="false">ValueHere</e1226:Id>
          <e1226:Line1 d4p1:nil="false">ValueHere</e1226:Line1>
          <e1226:Line2 d4p1:nil="false">ValueHere</e1226:Line2>
          <e1226:Line3 d4p1:nil="false">ValueHere</e1226:Line3>
          <e1226:Line4 d4p1:nil="false">ValueHere</e1226:Line4>
          <e1226:PostalCode d4p1:nil="false">ValueHere</e1226:PostalCode>
          <e1226:StateOrProvince d4p1:nil="false">ValueHere</e1226:StateOrProvince>
          <e1226:TimeStamp d4p1:nil="false">ValueHere</e1226:TimeStamp>
        </e1226:BusinessAddress>
        <e1226:AutoTagType d4p1:nil="false">ValueHere</e1226:AutoTagType>
      </Account>
    </GetAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetAccountResponse> GetAccountAsync(
	long accountId)
{
	var request = new GetAccountRequest
	{
		AccountId = accountId
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetAccountAsync(r), request));
}
```
```java
static GetAccountResponse getAccount(
	java.lang.Long accountId) throws RemoteException, Exception
{
	GetAccountRequest request = new GetAccountRequest();

	request.setAccountId(accountId);

	return CustomerManagementService.getService().getAccount(request);
}
```
```php
static function GetAccount(
	$accountId)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetAccountRequest();

	$request->AccountId = $accountId;

	return $GLOBALS['CustomerManagementProxy']->GetService()->GetAccount($request);
}
```
```python
response=customermanagement_service.GetAccount(
	AccountId=AccountId)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

