---
title: UpdateAccount Service Operation
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the details of the specified account.
---
# UpdateAccount Service Operation
Updates the details of the specified account.

## <a name="request"></a>Request Elements
The *UpdateAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An *AdvertiserAccount* object that contains the updated account information.<br /><br />This operation overwrites the existing account data with the contents of the account object that you pass. This operation performs a full update, and not a partial update. The *Account* object must contain the time stamp value from the last time that the *Account* object was written to. To ensure that the time stamp contains the correct value, call the [GetAccount](../customer-management-service/getaccount.md) operation. You can then update the account data as appropriate, and call *UpdateAccount*.|[Account](account.md)|

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">UpdateAccount</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateAccountRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <Account xmlns:e653="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e653:AccountType>ValueHere</e653:AccountType>
        <e653:BillToCustomerId i:nil="false">ValueHere</e653:BillToCustomerId>
        <e653:CountryCode i:nil="false">ValueHere</e653:CountryCode>
        <e653:CurrencyType i:nil="false">ValueHere</e653:CurrencyType>
        <e653:AccountFinancialStatus i:nil="false">ValueHere</e653:AccountFinancialStatus>
        <e653:Id i:nil="false">ValueHere</e653:Id>
        <e653:Language i:nil="false">ValueHere</e653:Language>
        <ForwardCompatibilityMap xmlns:e654="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e654:KeyValuePairOfstringstring>
            <e654:key i:nil="false">ValueHere</e654:key>
            <e654:value i:nil="false">ValueHere</e654:value>
          </e654:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e653:LastModifiedByUserId i:nil="false">ValueHere</e653:LastModifiedByUserId>
        <e653:LastModifiedTime i:nil="false">ValueHere</e653:LastModifiedTime>
        <e653:Name i:nil="false">ValueHere</e653:Name>
        <e653:Number i:nil="false">ValueHere</e653:Number>
        <e653:ParentCustomerId>ValueHere</e653:ParentCustomerId>
        <e653:PaymentMethodId i:nil="false">ValueHere</e653:PaymentMethodId>
        <e653:PaymentMethodType i:nil="false">ValueHere</e653:PaymentMethodType>
        <e653:PrimaryUserId i:nil="false">ValueHere</e653:PrimaryUserId>
        <e653:AccountLifeCycleStatus i:nil="false">ValueHere</e653:AccountLifeCycleStatus>
        <e653:TimeStamp i:nil="false">ValueHere</e653:TimeStamp>
        <e653:TimeZone i:nil="false">ValueHere</e653:TimeZone>
        <e653:PauseReason i:nil="false">ValueHere</e653:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e653:LinkedAgencies i:nil="false">
          <e653:CustomerInfo>
            <e653:Id i:nil="false">ValueHere</e653:Id>
            <e653:Name i:nil="false">ValueHere</e653:Name>
          </e653:CustomerInfo>
        </e653:LinkedAgencies>
        <e653:SalesHouseCustomerId i:nil="false">ValueHere</e653:SalesHouseCustomerId>
        <TaxInformation xmlns:e655="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e655:KeyValuePairOfstringstring>
            <e655:key i:nil="false">ValueHere</e655:key>
            <e655:value i:nil="false">ValueHere</e655:value>
          </e655:KeyValuePairOfstringstring>
        </TaxInformation>
        <e653:BackUpPaymentInstrumentId i:nil="false">ValueHere</e653:BackUpPaymentInstrumentId>
        <e653:BillingThresholdAmount i:nil="false">ValueHere</e653:BillingThresholdAmount>
        <e653:BusinessAddress i:nil="false">
          <e653:City i:nil="false">ValueHere</e653:City>
          <e653:CountryCode i:nil="false">ValueHere</e653:CountryCode>
          <e653:Id i:nil="false">ValueHere</e653:Id>
          <e653:Line1 i:nil="false">ValueHere</e653:Line1>
          <e653:Line2 i:nil="false">ValueHere</e653:Line2>
          <e653:Line3 i:nil="false">ValueHere</e653:Line3>
          <e653:Line4 i:nil="false">ValueHere</e653:Line4>
          <e653:PostalCode i:nil="false">ValueHere</e653:PostalCode>
          <e653:StateOrProvince i:nil="false">ValueHere</e653:StateOrProvince>
          <e653:TimeStamp i:nil="false">ValueHere</e653:TimeStamp>
        </e653:BusinessAddress>
      </Account>
    </UpdateAccountRequest>
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
    <UpdateAccountResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateAccountResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateAccountResponse> UpdateAccountAsync(
	Account account)
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
	Account account) throws RemoteException, Exception
{
	UpdateAccountRequest request = new UpdateAccountRequest();

	request.setAccount(account);

	return CustomerManagementService.getService().updateAccount(request);
}
```
```php
static function UpdateAccount(
	$account)

	$updateAccountRequest = new UpdateAccountRequest();

	$request->Account = $account;

	return $CustomerManagementProxy->GetService()->UpdateAccount($request);
}
```
```python
response=customermanagement.UpdateAccount(
	Account=AccountHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

