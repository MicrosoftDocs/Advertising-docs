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
|<a name="account"></a>Account|An account object that contains information about the account, such as payment method, account type, and parent customer.|[Account](account.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">GetAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <AccountId>ValueHere</AccountId>
    </GetAccountRequest>
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
    <GetAccountResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <Account xmlns:e313="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e313:AccountType>ValueHere</e313:AccountType>
        <e313:BillToCustomerId d4p1:nil="false">ValueHere</e313:BillToCustomerId>
        <e313:CountryCode d4p1:nil="false">ValueHere</e313:CountryCode>
        <e313:CurrencyType d4p1:nil="false">ValueHere</e313:CurrencyType>
        <e313:AccountFinancialStatus d4p1:nil="false">ValueHere</e313:AccountFinancialStatus>
        <e313:Id d4p1:nil="false">ValueHere</e313:Id>
        <e313:Language d4p1:nil="false">ValueHere</e313:Language>
        <ForwardCompatibilityMap xmlns:e314="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e314:KeyValuePairOfstringstring>
            <e314:key d4p1:nil="false">ValueHere</e314:key>
            <e314:value d4p1:nil="false">ValueHere</e314:value>
          </e314:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e313:LastModifiedByUserId d4p1:nil="false">ValueHere</e313:LastModifiedByUserId>
        <e313:LastModifiedTime d4p1:nil="false">ValueHere</e313:LastModifiedTime>
        <e313:Name d4p1:nil="false">ValueHere</e313:Name>
        <e313:Number d4p1:nil="false">ValueHere</e313:Number>
        <e313:ParentCustomerId>ValueHere</e313:ParentCustomerId>
        <e313:PaymentMethodId d4p1:nil="false">ValueHere</e313:PaymentMethodId>
        <e313:PaymentMethodType d4p1:nil="false">ValueHere</e313:PaymentMethodType>
        <e313:PrimaryUserId d4p1:nil="false">ValueHere</e313:PrimaryUserId>
        <e313:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e313:AccountLifeCycleStatus>
        <e313:TimeStamp d4p1:nil="false">ValueHere</e313:TimeStamp>
        <e313:TimeZone d4p1:nil="false">ValueHere</e313:TimeZone>
        <e313:PauseReason d4p1:nil="false">ValueHere</e313:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e313:LinkedAgencies d4p1:nil="false">
          <e313:CustomerInfo>
            <e313:Id d4p1:nil="false">ValueHere</e313:Id>
            <e313:Name d4p1:nil="false">ValueHere</e313:Name>
          </e313:CustomerInfo>
        </e313:LinkedAgencies>
        <e313:SalesHouseCustomerId d4p1:nil="false">ValueHere</e313:SalesHouseCustomerId>
        <TaxInformation xmlns:e315="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e315:KeyValuePairOfstringstring>
            <e315:key d4p1:nil="false">ValueHere</e315:key>
            <e315:value d4p1:nil="false">ValueHere</e315:value>
          </e315:KeyValuePairOfstringstring>
        </TaxInformation>
        <e313:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e313:BackUpPaymentInstrumentId>
        <e313:BillingThresholdAmount d4p1:nil="false">ValueHere</e313:BillingThresholdAmount>
        <e313:BusinessAddress d4p1:nil="false">
          <e313:City d4p1:nil="false">ValueHere</e313:City>
          <e313:CountryCode d4p1:nil="false">ValueHere</e313:CountryCode>
          <e313:Id d4p1:nil="false">ValueHere</e313:Id>
          <e313:Line1 d4p1:nil="false">ValueHere</e313:Line1>
          <e313:Line2 d4p1:nil="false">ValueHere</e313:Line2>
          <e313:Line3 d4p1:nil="false">ValueHere</e313:Line3>
          <e313:Line4 d4p1:nil="false">ValueHere</e313:Line4>
          <e313:PostalCode d4p1:nil="false">ValueHere</e313:PostalCode>
          <e313:StateOrProvince d4p1:nil="false">ValueHere</e313:StateOrProvince>
          <e313:TimeStamp d4p1:nil="false">ValueHere</e313:TimeStamp>
        </e313:BusinessAddress>
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
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

