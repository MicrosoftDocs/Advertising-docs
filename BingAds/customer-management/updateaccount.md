---
title: UpdateAccount Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# UpdateAccount Service Operation
Updates the details of the specified account.

## <a name="request"></a>Request Elements
The *UpdateAccountRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="account"></a>Account|An *AdvertiserAccount* object that contains the updated account information.<br /><br />This operation overwrites the existing account data with the contents of the account object that you pass. This operation performs a full update, and not a partial update. The *Account* object must contain the time stamp value from the last time that the *Account* object was written to. To ensure that the time stamp contains the correct value, call the [GetAccount](../customer-management/getaccount.md) operation. You can then update the account data as appropriate, and call *UpdateAccount*.|[Account](account.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateAccountResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the account was last updated. The value is in Coordinated Universal Time (UTC).<br/><br/>**Note:** The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

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
      <Account xmlns:e447="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false" i:type="-- derived type specified here with the appropriate prefix --">
        <e447:AccountType>ValueHere</e447:AccountType>
        <e447:BillToCustomerId i:nil="false">ValueHere</e447:BillToCustomerId>
        <e447:CountryCode i:nil="false">ValueHere</e447:CountryCode>
        <e447:CurrencyType i:nil="false">ValueHere</e447:CurrencyType>
        <e447:AccountFinancialStatus i:nil="false">ValueHere</e447:AccountFinancialStatus>
        <e447:Id i:nil="false">ValueHere</e447:Id>
        <e447:Language i:nil="false">ValueHere</e447:Language>
        <ForwardCompatibilityMap xmlns:e448="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e448:KeyValuePairOfstringstring>
            <e448:key i:nil="false">ValueHere</e448:key>
            <e448:value i:nil="false">ValueHere</e448:value>
          </e448:KeyValuePairOfstringstring>
        </ForwardCompatibilityMap>
        <e447:LastModifiedByUserId i:nil="false">ValueHere</e447:LastModifiedByUserId>
        <e447:LastModifiedTime i:nil="false">ValueHere</e447:LastModifiedTime>
        <e447:Name i:nil="false">ValueHere</e447:Name>
        <e447:Number i:nil="false">ValueHere</e447:Number>
        <e447:ParentCustomerId>ValueHere</e447:ParentCustomerId>
        <e447:PaymentMethodId i:nil="false">ValueHere</e447:PaymentMethodId>
        <e447:PaymentMethodType i:nil="false">ValueHere</e447:PaymentMethodType>
        <e447:PrimaryUserId i:nil="false">ValueHere</e447:PrimaryUserId>
        <e447:AccountLifeCycleStatus i:nil="false">ValueHere</e447:AccountLifeCycleStatus>
        <e447:TimeStamp i:nil="false">ValueHere</e447:TimeStamp>
        <e447:TimeZone i:nil="false">ValueHere</e447:TimeZone>
        <e447:PauseReason i:nil="false">ValueHere</e447:PauseReason>
        <!--These fields are applicable if the derived type attribute is set to AdvertiserAccount-->
        <e447:LinkedAgencies i:nil="false">
          <e447:CustomerInfo>
            <e447:Id i:nil="false">ValueHere</e447:Id>
            <e447:Name i:nil="false">ValueHere</e447:Name>
          </e447:CustomerInfo>
        </e447:LinkedAgencies>
        <e447:SalesHouseCustomerId i:nil="false">ValueHere</e447:SalesHouseCustomerId>
        <TaxInformation xmlns:e449="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
          <e449:KeyValuePairOfstringstring>
            <e449:key i:nil="false">ValueHere</e449:key>
            <e449:value i:nil="false">ValueHere</e449:value>
          </e449:KeyValuePairOfstringstring>
        </TaxInformation>
        <e447:BackUpPaymentInstrumentId i:nil="false">ValueHere</e447:BackUpPaymentInstrumentId>
        <e447:BillingThresholdAmount i:nil="false">ValueHere</e447:BillingThresholdAmount>
        <e447:BusinessAddress i:nil="false">
          <e447:City i:nil="false">ValueHere</e447:City>
          <e447:CountryCode i:nil="false">ValueHere</e447:CountryCode>
          <e447:Id i:nil="false">ValueHere</e447:Id>
          <e447:Line1 i:nil="false">ValueHere</e447:Line1>
          <e447:Line2 i:nil="false">ValueHere</e447:Line2>
          <e447:Line3 i:nil="false">ValueHere</e447:Line3>
          <e447:Line4 i:nil="false">ValueHere</e447:Line4>
          <e447:PostalCode i:nil="false">ValueHere</e447:PostalCode>
          <e447:StateOrProvince i:nil="false">ValueHere</e447:StateOrProvince>
          <e447:TimeStamp i:nil="false">ValueHere</e447:TimeStamp>
        </e447:BusinessAddress>
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
```csharp
protected async Task<UpdateAccountResponse> UpdateAccountAsync(
	Account account)
{
	var request = new UpdateAccountRequest
	{
		Account = account
	};

	return (await CustomerManagement.CallAsync((s, r) => s.UpdateAccountAsync(r), request));
}
```
```java
static UpdateAccountResponse updateAccount(
	Account account)
{
	UpdateAccountRequest request = new UpdateAccountRequest();

	request.setAccount(account);

	return CustomerManagement.getService().updateAccount(request);
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

