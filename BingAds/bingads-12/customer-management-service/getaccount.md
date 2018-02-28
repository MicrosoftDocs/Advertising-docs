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
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
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
      <Account xmlns:e320="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e320:BillToCustomerId d4p1:nil="false">ValueHere</e320:BillToCustomerId>
        <e320:CountryCode d4p1:nil="false">ValueHere</e320:CountryCode>
        <e320:CurrencyCode d4p1:nil="false">ValueHere</e320:CurrencyCode>
        <e320:AccountFinancialStatus d4p1:nil="false">ValueHere</e320:AccountFinancialStatus>
        <e320:Id d4p1:nil="false">ValueHere</e320:Id>
        <e320:Language d4p1:nil="false">ValueHere</e320:Language>
        <e320:LastModifiedByUserId d4p1:nil="false">ValueHere</e320:LastModifiedByUserId>
        <e320:LastModifiedTime d4p1:nil="false">ValueHere</e320:LastModifiedTime>
        <e320:Name d4p1:nil="false">ValueHere</e320:Name>
        <e320:Number d4p1:nil="false">ValueHere</e320:Number>
        <e320:ParentCustomerId>ValueHere</e320:ParentCustomerId>
        <e320:PaymentMethodId d4p1:nil="false">ValueHere</e320:PaymentMethodId>
        <e320:PaymentMethodType d4p1:nil="false">ValueHere</e320:PaymentMethodType>
        <e320:PrimaryUserId d4p1:nil="false">ValueHere</e320:PrimaryUserId>
        <e320:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e320:AccountLifeCycleStatus>
        <e320:TimeStamp d4p1:nil="false">ValueHere</e320:TimeStamp>
        <e320:TimeZone d4p1:nil="false">ValueHere</e320:TimeZone>
        <e320:PauseReason d4p1:nil="false">ValueHere</e320:PauseReason>
        <ForwardCompatibilityMap xmlns:e321="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e321:KeyValuePairOfstringstring>
            <e321:key d4p1:nil="false">ValueHere</e321:key>
            <e321:value d4p1:nil="false">ValueHere</e321:value>
          </e321:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e320:LinkedAgencies d4p1:nil="false">
          <e320:CustomerInfo>
            <e320:Id d4p1:nil="false">ValueHere</e320:Id>
            <e320:Name d4p1:nil="false">ValueHere</e320:Name>
          </e320:CustomerInfo>
        </e320:LinkedAgencies>
        <e320:SalesHouseCustomerId d4p1:nil="false">ValueHere</e320:SalesHouseCustomerId>
        <TaxInformation xmlns:e322="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e322:KeyValuePairOfstringstring>
            <e322:key d4p1:nil="false">ValueHere</e322:key>
            <e322:value d4p1:nil="false">ValueHere</e322:value>
          </e322:KeyValuePairOfstringstring>
        </TaxInformation>
        <e320:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e320:BackUpPaymentInstrumentId>
        <e320:BillingThresholdAmount d4p1:nil="false">ValueHere</e320:BillingThresholdAmount>
        <e320:BusinessAddress d4p1:nil="false">
          <e320:City d4p1:nil="false">ValueHere</e320:City>
          <e320:CountryCode d4p1:nil="false">ValueHere</e320:CountryCode>
          <e320:Id d4p1:nil="false">ValueHere</e320:Id>
          <e320:Line1 d4p1:nil="false">ValueHere</e320:Line1>
          <e320:Line2 d4p1:nil="false">ValueHere</e320:Line2>
          <e320:Line3 d4p1:nil="false">ValueHere</e320:Line3>
          <e320:Line4 d4p1:nil="false">ValueHere</e320:Line4>
          <e320:PostalCode d4p1:nil="false">ValueHere</e320:PostalCode>
          <e320:StateOrProvince d4p1:nil="false">ValueHere</e320:StateOrProvince>
          <e320:TimeStamp d4p1:nil="false">ValueHere</e320:TimeStamp>
        </e320:BusinessAddress>
        <e320:AutoTagType d4p1:nil="false">ValueHere</e320:AutoTagType>
      </Account>
    </GetAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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

