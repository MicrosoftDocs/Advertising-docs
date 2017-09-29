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
      <Account xmlns:e413="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" d4p1:type="-- derived type specified here with the appropriate prefix --" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e413:AccountType>ValueHere</e413:AccountType>
        <e413:BillToCustomerId d4p1:nil="false">ValueHere</e413:BillToCustomerId>
        <e413:CountryCode d4p1:nil="false">ValueHere</e413:CountryCode>
        <e413:CurrencyType d4p1:nil="false">ValueHere</e413:CurrencyType>
        <e413:AccountFinancialStatus d4p1:nil="false">ValueHere</e413:AccountFinancialStatus>
        <e413:Id d4p1:nil="false">ValueHere</e413:Id>
        <e413:Language d4p1:nil="false">ValueHere</e413:Language>
        <ForwardCompatibilityMap xmlns:e414="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e414:KeyValuePairOfstringstring>
            <e414:key d4p1:nil="false">ValueHere</e414:key>
            <e414:value d4p1:nil="false">ValueHere</e414:value>
          </e414:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e413:LastModifiedByUserId d4p1:nil="false">ValueHere</e413:LastModifiedByUserId>
        <e413:LastModifiedTime d4p1:nil="false">ValueHere</e413:LastModifiedTime>
        <e413:Name d4p1:nil="false">ValueHere</e413:Name>
        <e413:Number d4p1:nil="false">ValueHere</e413:Number>
        <e413:ParentCustomerId>ValueHere</e413:ParentCustomerId>
        <e413:PaymentMethodId d4p1:nil="false">ValueHere</e413:PaymentMethodId>
        <e413:PaymentMethodType d4p1:nil="false">ValueHere</e413:PaymentMethodType>
        <e413:PrimaryUserId d4p1:nil="false">ValueHere</e413:PrimaryUserId>
        <e413:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e413:AccountLifeCycleStatus>
        <e413:TimeStamp d4p1:nil="false">ValueHere</e413:TimeStamp>
        <e413:TimeZone d4p1:nil="false">ValueHere</e413:TimeZone>
        <e413:PauseReason d4p1:nil="false">ValueHere</e413:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e413:LinkedAgencies d4p1:nil="false">
          <e413:CustomerInfo>
            <e413:Id d4p1:nil="false">ValueHere</e413:Id>
            <e413:Name d4p1:nil="false">ValueHere</e413:Name>
          </e413:CustomerInfo>
        </e413:LinkedAgencies>
        <e413:SalesHouseCustomerId d4p1:nil="false">ValueHere</e413:SalesHouseCustomerId>
        <TaxInformation xmlns:e415="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e415:KeyValuePairOfstringstring>
            <e415:key d4p1:nil="false">ValueHere</e415:key>
            <e415:value d4p1:nil="false">ValueHere</e415:value>
          </e415:KeyValuePairOfstringstring>
        </TaxInformation>
        <e413:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e413:BackUpPaymentInstrumentId>
        <e413:BillingThresholdAmount d4p1:nil="false">ValueHere</e413:BillingThresholdAmount>
        <e413:BusinessAddress d4p1:nil="false">
          <e413:City d4p1:nil="false">ValueHere</e413:City>
          <e413:CountryCode d4p1:nil="false">ValueHere</e413:CountryCode>
          <e413:Id d4p1:nil="false">ValueHere</e413:Id>
          <e413:Line1 d4p1:nil="false">ValueHere</e413:Line1>
          <e413:Line2 d4p1:nil="false">ValueHere</e413:Line2>
          <e413:Line3 d4p1:nil="false">ValueHere</e413:Line3>
          <e413:Line4 d4p1:nil="false">ValueHere</e413:Line4>
          <e413:PostalCode d4p1:nil="false">ValueHere</e413:PostalCode>
          <e413:StateOrProvince d4p1:nil="false">ValueHere</e413:StateOrProvince>
          <e413:TimeStamp d4p1:nil="false">ValueHere</e413:TimeStamp>
        </e413:BusinessAddress>
      </Account>
    </GetAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
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

