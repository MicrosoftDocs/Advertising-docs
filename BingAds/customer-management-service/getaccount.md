---
title: GetAccount Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of an account.
---
# GetAccount Service Operation
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
      <Account xmlns:e619="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e619:AccountType>ValueHere</e619:AccountType>
        <e619:BillToCustomerId d4p1:nil="false">ValueHere</e619:BillToCustomerId>
        <e619:CountryCode d4p1:nil="false">ValueHere</e619:CountryCode>
        <e619:CurrencyType d4p1:nil="false">ValueHere</e619:CurrencyType>
        <e619:AccountFinancialStatus d4p1:nil="false">ValueHere</e619:AccountFinancialStatus>
        <e619:Id d4p1:nil="false">ValueHere</e619:Id>
        <e619:Language d4p1:nil="false">ValueHere</e619:Language>
        <ForwardCompatibilityMap xmlns:e620="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e620:KeyValuePairOfstringstring>
            <e620:key d4p1:nil="false">ValueHere</e620:key>
            <e620:value d4p1:nil="false">ValueHere</e620:value>
          </e620:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e619:LastModifiedByUserId d4p1:nil="false">ValueHere</e619:LastModifiedByUserId>
        <e619:LastModifiedTime d4p1:nil="false">ValueHere</e619:LastModifiedTime>
        <e619:Name d4p1:nil="false">ValueHere</e619:Name>
        <e619:Number d4p1:nil="false">ValueHere</e619:Number>
        <e619:ParentCustomerId>ValueHere</e619:ParentCustomerId>
        <e619:PaymentMethodId d4p1:nil="false">ValueHere</e619:PaymentMethodId>
        <e619:PaymentMethodType d4p1:nil="false">ValueHere</e619:PaymentMethodType>
        <e619:PrimaryUserId d4p1:nil="false">ValueHere</e619:PrimaryUserId>
        <e619:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e619:AccountLifeCycleStatus>
        <e619:TimeStamp d4p1:nil="false">ValueHere</e619:TimeStamp>
        <e619:TimeZone d4p1:nil="false">ValueHere</e619:TimeZone>
        <e619:PauseReason d4p1:nil="false">ValueHere</e619:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e619:LinkedAgencies d4p1:nil="false">
          <e619:CustomerInfo>
            <e619:Id d4p1:nil="false">ValueHere</e619:Id>
            <e619:Name d4p1:nil="false">ValueHere</e619:Name>
          </e619:CustomerInfo>
        </e619:LinkedAgencies>
        <e619:SalesHouseCustomerId d4p1:nil="false">ValueHere</e619:SalesHouseCustomerId>
        <TaxInformation xmlns:e621="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e621:KeyValuePairOfstringstring>
            <e621:key d4p1:nil="false">ValueHere</e621:key>
            <e621:value d4p1:nil="false">ValueHere</e621:value>
          </e621:KeyValuePairOfstringstring>
        </TaxInformation>
        <e619:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e619:BackUpPaymentInstrumentId>
        <e619:BillingThresholdAmount d4p1:nil="false">ValueHere</e619:BillingThresholdAmount>
        <e619:BusinessAddress d4p1:nil="false">
          <e619:City d4p1:nil="false">ValueHere</e619:City>
          <e619:CountryCode d4p1:nil="false">ValueHere</e619:CountryCode>
          <e619:Id d4p1:nil="false">ValueHere</e619:Id>
          <e619:Line1 d4p1:nil="false">ValueHere</e619:Line1>
          <e619:Line2 d4p1:nil="false">ValueHere</e619:Line2>
          <e619:Line3 d4p1:nil="false">ValueHere</e619:Line3>
          <e619:Line4 d4p1:nil="false">ValueHere</e619:Line4>
          <e619:PostalCode d4p1:nil="false">ValueHere</e619:PostalCode>
          <e619:StateOrProvince d4p1:nil="false">ValueHere</e619:StateOrProvince>
          <e619:TimeStamp d4p1:nil="false">ValueHere</e619:TimeStamp>
        </e619:BusinessAddress>
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

	$getAccountRequest = new GetAccountRequest();

	$request->AccountId = $accountId;

	return $CustomerManagementProxy->GetService()->GetAccount($request);
}
```
```python
response=customermanagement.GetAccount(
	AccountId=AccountIdHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

