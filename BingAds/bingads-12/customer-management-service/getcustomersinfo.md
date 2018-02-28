---
title: GetCustomersInfo Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets a list of objects that contain customer identification information, for example the name and identifier of the customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.
# GetCustomersInfo Service Operation - Customer Management
Gets a list of objects that contain customer identification information, for example the name and identifier of the customer.

The list that this operation returns is based on the customers that the user that you specify in the *UserName* header element of the request, has access to. If the user is a member of the reseller's user group, the list will contain all customers that the reseller has signed up or a subset of customers if the user is limited to a subset of customers by a user role.

## <a name="request"></a>Request Elements
The *GetCustomersInfoRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customernamefilter"></a>CustomerNameFilter|A partial or full name of the customers that you want to get. The operation includes the customer in the result if the customer's name begins with the specified filter name. If you do not want to filter by customer name, set this element to an empty string.<br /><br />The operation performs a case-insensitive comparison when it compares your name filter value to the customer names. For example, if you specify "t" as the filter value, the list will include customers whose names begin with "t" or "T".|**string**|
|<a name="topn"></a>TopN|A nonzero positive integer that specifies the number of customers to return in the result.|**int**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetCustomersInfoResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customersinfo"></a>CustomersInfo|An array of *CustomerInfo* objects that identifies the list of customers that meet the filter criteria.<br /><br />To get the customer data for a customer in the list, access the *Id* element of the *CustomerInfo* object and use it to call [GetCustomer](../customer-management-service/getcustomer.md).|[CustomerInfo](customerinfo.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">GetCustomersInfo</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetCustomersInfoRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <CustomerNameFilter i:nil="false">ValueHere</CustomerNameFilter>
      <TopN>ValueHere</TopN>
    </GetCustomersInfoRequest>
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
    <GetCustomersInfoResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <CustomersInfo xmlns:e326="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e326:CustomerInfo>
          <e326:Id d4p1:nil="false">ValueHere</e326:Id>
          <e326:Name d4p1:nil="false">ValueHere</e326:Name>
        </e326:CustomerInfo>
      </CustomersInfo>
    </GetCustomersInfoResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetCustomersInfoResponse> GetCustomersInfoAsync(
	string customerNameFilter,
	int topN)
{
	var request = new GetCustomersInfoRequest
	{
		CustomerNameFilter = customerNameFilter,
		TopN = topN
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.GetCustomersInfoAsync(r), request));
}
```
```java
static GetCustomersInfoResponse getCustomersInfo(
	java.lang.String customerNameFilter,
	int topN) throws RemoteException, Exception
{
	GetCustomersInfoRequest request = new GetCustomersInfoRequest();

	request.setCustomerNameFilter(customerNameFilter);
	request.setTopN(topN);

	return CustomerManagementService.getService().getCustomersInfo(request);
}
```
```php
static function GetCustomersInfo(
	$customerNameFilter,
	$topN)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new GetCustomersInfoRequest();

	$request->CustomerNameFilter = $customerNameFilter;
	$request->TopN = $topN;

	return $GLOBALS['CustomerManagementProxy']->GetService()->GetCustomersInfo($request);
}
```
```python
response=customermanagement_service.GetCustomersInfo(
	CustomerNameFilter=CustomerNameFilter,
	TopN=TopN)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

