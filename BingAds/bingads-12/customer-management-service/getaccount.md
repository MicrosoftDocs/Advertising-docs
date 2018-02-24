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

> [!IMPORTANT]
> This v12 preview documentation is subject to change.

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
      <Account xmlns:e678="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e678:BillToCustomerId d4p1:nil="false">ValueHere</e678:BillToCustomerId>
        <e678:CountryCode d4p1:nil="false">ValueHere</e678:CountryCode>
        <e678:CurrencyType d4p1:nil="false">ValueHere</e678:CurrencyType>
        <e678:AccountFinancialStatus d4p1:nil="false">ValueHere</e678:AccountFinancialStatus>
        <e678:Id d4p1:nil="false">ValueHere</e678:Id>
        <e678:Language d4p1:nil="false">ValueHere</e678:Language>
        <e678:LastModifiedByUserId d4p1:nil="false">ValueHere</e678:LastModifiedByUserId>
        <e678:LastModifiedTime d4p1:nil="false">ValueHere</e678:LastModifiedTime>
        <e678:Name d4p1:nil="false">ValueHere</e678:Name>
        <e678:Number d4p1:nil="false">ValueHere</e678:Number>
        <e678:ParentCustomerId>ValueHere</e678:ParentCustomerId>
        <e678:PaymentMethodId d4p1:nil="false">ValueHere</e678:PaymentMethodId>
        <e678:PaymentMethodType d4p1:nil="false">ValueHere</e678:PaymentMethodType>
        <e678:PrimaryUserId d4p1:nil="false">ValueHere</e678:PrimaryUserId>
        <e678:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e678:AccountLifeCycleStatus>
        <e678:TimeStamp d4p1:nil="false">ValueHere</e678:TimeStamp>
        <e678:TimeZone d4p1:nil="false">ValueHere</e678:TimeZone>
        <e678:PauseReason d4p1:nil="false">ValueHere</e678:PauseReason>
        <ForwardCompatibilityMap xmlns:e679="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e679:KeyValuePairOfstringstring>
            <e679:key d4p1:nil="false">ValueHere</e679:key>
            <e679:value d4p1:nil="false">ValueHere</e679:value>
          </e679:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e678:LinkedAgencies d4p1:nil="false">
          <e678:CustomerInfo>
            <e678:Id d4p1:nil="false">ValueHere</e678:Id>
            <e678:Name d4p1:nil="false">ValueHere</e678:Name>
          </e678:CustomerInfo>
        </e678:LinkedAgencies>
        <e678:SalesHouseCustomerId d4p1:nil="false">ValueHere</e678:SalesHouseCustomerId>
        <TaxInformation xmlns:e680="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e680:KeyValuePairOfstringstring>
            <e680:key d4p1:nil="false">ValueHere</e680:key>
            <e680:value d4p1:nil="false">ValueHere</e680:value>
          </e680:KeyValuePairOfstringstring>
        </TaxInformation>
        <e678:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e678:BackUpPaymentInstrumentId>
        <e678:BillingThresholdAmount d4p1:nil="false">ValueHere</e678:BillingThresholdAmount>
        <e678:BusinessAddress d4p1:nil="false">
          <e678:City d4p1:nil="false">ValueHere</e678:City>
          <e678:CountryCode d4p1:nil="false">ValueHere</e678:CountryCode>
          <e678:Id d4p1:nil="false">ValueHere</e678:Id>
          <e678:Line1 d4p1:nil="false">ValueHere</e678:Line1>
          <e678:Line2 d4p1:nil="false">ValueHere</e678:Line2>
          <e678:Line3 d4p1:nil="false">ValueHere</e678:Line3>
          <e678:Line4 d4p1:nil="false">ValueHere</e678:Line4>
          <e678:PostalCode d4p1:nil="false">ValueHere</e678:PostalCode>
          <e678:StateOrProvince d4p1:nil="false">ValueHere</e678:StateOrProvince>
          <e678:TimeStamp d4p1:nil="false">ValueHere</e678:TimeStamp>
        </e678:BusinessAddress>
        <e678:AutoTagType d4p1:nil="false">ValueHere</e678:AutoTagType>
      </Account>
    </GetAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](/bingads/guides/client-libraries.md). See [Bing Ads Code Examples](/bingads/guides/code-examples.md) for more examples.
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

