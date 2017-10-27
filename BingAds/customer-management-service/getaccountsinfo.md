---
title: GetAccountsInfo Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: "article"
ms.date: 11/01/2017
author: eric-urban
ms.author: eur
description: Gets a list of objects that contains account identification information, for example the name and identifier of the account, for the specified customer.
---
# GetAccountsInfo Service Operation - Customer Management
Gets a list of objects that contains account identification information, for example the name and identifier of the account, for the specified customer.

## <a name="request"></a>Request Elements
The *GetAccountsInfoRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|The identifier of the customer who owns the accounts to get. If not set, the user's credentials are used to determine the customer.|**long**|
|<a name="onlyparentaccounts"></a>OnlyParentAccounts|Determines whether to return only the accounts that belong to the customer or to also return the accounts that the customer manages for other customers. To return all accounts (those that belong to the customer and those that the customer manages), set this element to **false**; otherwise, set to **true** to return account information for only the specified customer. The default is **false**.|**boolean**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetAccountsInfoResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountsinfo"></a>AccountsInfo|An array of *AccountInfo* objects that identifies the list of accounts that the customer owns.<br /><br />To get the account data for an account in the list, access the *Id* element of the *AccountInfo* object and use it to call [GetAccount](../customer-management-service/getaccount.md).<br /><br />Note that there can be a delay of up to five minutes from the time that you add an account until the [GetAccountsInfo](../customer-management-service/getaccountsinfo.md) returns the account in the response.|[AccountInfo](accountinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">GetAccountsInfo</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetAccountsInfoRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <CustomerId i:nil="false">ValueHere</CustomerId>
      <OnlyParentAccounts>ValueHere</OnlyParentAccounts>
    </GetAccountsInfoRequest>
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
    <GetAccountsInfoResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <AccountsInfo xmlns:e10="https://bingads.microsoft.com/Customer/v11/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e10:AccountInfo>
          <e10:Id>ValueHere</e10:Id>
          <e10:Name d4p1:nil="false">ValueHere</e10:Name>
          <e10:Number d4p1:nil="false">ValueHere</e10:Number>
          <e10:AccountLifeCycleStatus>ValueHere</e10:AccountLifeCycleStatus>
          <e10:PauseReason d4p1:nil="false">ValueHere</e10:PauseReason>
        </e10:AccountInfo>
      </AccountsInfo>
    </GetAccountsInfoResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetAccountsInfoResponse> GetAccountsInfoAsync(
	long customerId,
	bool onlyParentAccounts)
{
	var request = new GetAccountsInfoRequest
	{
		CustomerId = customerId,
		OnlyParentAccounts = onlyParentAccounts
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetAccountsInfoAsync(r), request));
}
```
```java
static GetAccountsInfoResponse getAccountsInfo(
	java.lang.Long customerId,
	boolean onlyParentAccounts) throws RemoteException, Exception
{
	GetAccountsInfoRequest request = new GetAccountsInfoRequest();

	request.setCustomerId(customerId);
	request.setOnlyParentAccounts(onlyParentAccounts);

	return CustomerManagementService.getService().getAccountsInfo(request);
}
```
```php
static function GetAccountsInfo(
	$customerId,
	$onlyParentAccounts)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetAccountsInfoRequest();

	$request->CustomerId = $customerId;
	$request->OnlyParentAccounts = $onlyParentAccounts;

	return $GLOBALS['CustomerManagementProxy']->GetService()->GetAccountsInfo($request);
}
```
```python
response=customermanagement_service.GetAccountsInfo(
	CustomerId=CustomerId,
	OnlyParentAccounts=OnlyParentAccounts)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

