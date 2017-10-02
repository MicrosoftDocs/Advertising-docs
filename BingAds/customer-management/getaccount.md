---
title: GetAccount Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
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
      <Account xmlns:e7="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e7:AccountType>ValueHere</e7:AccountType>
        <e7:BillToCustomerId d4p1:nil="false">ValueHere</e7:BillToCustomerId>
        <e7:CountryCode d4p1:nil="false">ValueHere</e7:CountryCode>
        <e7:CurrencyType d4p1:nil="false">ValueHere</e7:CurrencyType>
        <e7:AccountFinancialStatus d4p1:nil="false">ValueHere</e7:AccountFinancialStatus>
        <e7:Id d4p1:nil="false">ValueHere</e7:Id>
        <e7:Language d4p1:nil="false">ValueHere</e7:Language>
        <ForwardCompatibilityMap xmlns:e8="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e8:KeyValuePairOfstringstring>
            <e8:key d4p1:nil="false">ValueHere</e8:key>
            <e8:value d4p1:nil="false">ValueHere</e8:value>
          </e8:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e7:LastModifiedByUserId d4p1:nil="false">ValueHere</e7:LastModifiedByUserId>
        <e7:LastModifiedTime d4p1:nil="false">ValueHere</e7:LastModifiedTime>
        <e7:Name d4p1:nil="false">ValueHere</e7:Name>
        <e7:Number d4p1:nil="false">ValueHere</e7:Number>
        <e7:ParentCustomerId>ValueHere</e7:ParentCustomerId>
        <e7:PaymentMethodId d4p1:nil="false">ValueHere</e7:PaymentMethodId>
        <e7:PaymentMethodType d4p1:nil="false">ValueHere</e7:PaymentMethodType>
        <e7:PrimaryUserId d4p1:nil="false">ValueHere</e7:PrimaryUserId>
        <e7:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e7:AccountLifeCycleStatus>
        <e7:TimeStamp d4p1:nil="false">ValueHere</e7:TimeStamp>
        <e7:TimeZone d4p1:nil="false">ValueHere</e7:TimeZone>
        <e7:PauseReason d4p1:nil="false">ValueHere</e7:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e7:LinkedAgencies d4p1:nil="false">
          <e7:CustomerInfo>
            <e7:Id d4p1:nil="false">ValueHere</e7:Id>
            <e7:Name d4p1:nil="false">ValueHere</e7:Name>
          </e7:CustomerInfo>
        </e7:LinkedAgencies>
        <e7:SalesHouseCustomerId d4p1:nil="false">ValueHere</e7:SalesHouseCustomerId>
        <TaxInformation xmlns:e9="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e9:KeyValuePairOfstringstring>
            <e9:key d4p1:nil="false">ValueHere</e9:key>
            <e9:value d4p1:nil="false">ValueHere</e9:value>
          </e9:KeyValuePairOfstringstring>
        </TaxInformation>
        <e7:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e7:BackUpPaymentInstrumentId>
        <e7:BillingThresholdAmount d4p1:nil="false">ValueHere</e7:BillingThresholdAmount>
        <e7:BusinessAddress d4p1:nil="false">
          <e7:City d4p1:nil="false">ValueHere</e7:City>
          <e7:CountryCode d4p1:nil="false">ValueHere</e7:CountryCode>
          <e7:Id d4p1:nil="false">ValueHere</e7:Id>
          <e7:Line1 d4p1:nil="false">ValueHere</e7:Line1>
          <e7:Line2 d4p1:nil="false">ValueHere</e7:Line2>
          <e7:Line3 d4p1:nil="false">ValueHere</e7:Line3>
          <e7:Line4 d4p1:nil="false">ValueHere</e7:Line4>
          <e7:PostalCode d4p1:nil="false">ValueHere</e7:PostalCode>
          <e7:StateOrProvince d4p1:nil="false">ValueHere</e7:StateOrProvince>
          <e7:TimeStamp d4p1:nil="false">ValueHere</e7:TimeStamp>
        </e7:BusinessAddress>
      </Account>
    </GetAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
protected async Task<GetAccountResponse> GetAccountAsync(
	long accountId)
{
	var request = new GetAccountRequest
	{
		AccountId = accountId
	};

	return (await CustomerManagement.CallAsync((s, r) => s.GetAccountAsync(r), request));
}
```
```java
static GetAccountResponse getAccount(
	long accountId)
{
	GetAccountRequest request = new GetAccountRequest();

	request.setAccountId(accountId);

	return CustomerManagement.getService().getAccount(request);
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

