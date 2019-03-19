---
title: AddClientLinks Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Initiates the client link process to manage the account of another customer.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# AddClientLinks Service Operation - Customer Management
Initiates the client link process to manage the account of another customer. Sends an invitation from an agency to a potential client.  For more information about the client link lifecycle, see [Link to Client Accounts](../guides/management-model-agencies.md#clientlink).

Only an agency may call this service operation. For more information about becoming an agency, see the [Resources for agency partners](https://advertise.bingads.microsoft.com/en-us/resources/bing-partner-program/agency-resources).

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).

There is no set limit to the amount of client accounts that can be linked to an agency.

> [!NOTE]
> This feature is not supported in sandbox.
> 
> The client account must have a valid payment instrument set up for post-pay billing. Prepaid accounts are not supported for management by agencies.

## <a name="request"></a>Request Elements
The *AddClientLinksRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="clientlinks"></a>ClientLinks|The list of client links to add.<br/><br/>You should limit your request to 10 client links per call.|[ClientLink](clientlink.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddClientLinksResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="operationerrors"></a>OperationErrors|A list of one or more reasons why the service operation failed, and no client links were added.|[OperationError](operationerror.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of *OperationError* lists that contain details for any client links that were not successfully added.<br/><br/>Results are returned in the same order corresponding to the requested client links. The number of first dimension list elements is equal to the requested client links count. For successfully added client links, the *OperationError* element at the corresponding index is null.|[OperationError](operationerror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">AddClientLinks</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <AddClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <ClientLinks xmlns:e1449="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e1449:ClientLink>
          <e1449:ClientAccountId i:nil="false">ValueHere</e1449:ClientAccountId>
          <e1449:ClientAccountNumber i:nil="false">ValueHere</e1449:ClientAccountNumber>
          <e1449:ManagingCustomerId i:nil="false">ValueHere</e1449:ManagingCustomerId>
          <e1449:ManagingCustomerNumber i:nil="false">ValueHere</e1449:ManagingCustomerNumber>
          <e1449:Note i:nil="false">ValueHere</e1449:Note>
          <e1449:Name i:nil="false">ValueHere</e1449:Name>
          <e1449:InviterEmail i:nil="false">ValueHere</e1449:InviterEmail>
          <e1449:InviterName i:nil="false">ValueHere</e1449:InviterName>
          <e1449:InviterPhone i:nil="false">ValueHere</e1449:InviterPhone>
          <e1449:IsBillToClient>ValueHere</e1449:IsBillToClient>
          <e1449:StartDate i:nil="false">ValueHere</e1449:StartDate>
          <e1449:Status i:nil="false">ValueHere</e1449:Status>
          <e1449:SuppressNotification>ValueHere</e1449:SuppressNotification>
          <e1449:LastModifiedDateTime>ValueHere</e1449:LastModifiedDateTime>
          <e1449:LastModifiedByUserId>ValueHere</e1449:LastModifiedByUserId>
          <e1449:Timestamp i:nil="false">ValueHere</e1449:Timestamp>
          <e1449:ForwardCompatibilityMap xmlns:e1450="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e1450:KeyValuePairOfstringstring>
              <e1450:key i:nil="false">ValueHere</e1450:key>
              <e1450:value i:nil="false">ValueHere</e1450:value>
            </e1450:KeyValuePairOfstringstring>
          </e1449:ForwardCompatibilityMap>
        </e1449:ClientLink>
      </ClientLinks>
    </AddClientLinksRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <AddClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v13">
      <OperationErrors xmlns:e1451="https://bingads.microsoft.com/Customer/v13/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1451:OperationError>
          <e1451:Code>ValueHere</e1451:Code>
          <e1451:Details d4p1:nil="false">ValueHere</e1451:Details>
          <e1451:Message d4p1:nil="false">ValueHere</e1451:Message>
        </e1451:OperationError>
      </OperationErrors>
      <PartialErrors xmlns:e1452="https://bingads.microsoft.com/Customer/v13/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e1452:ArrayOfOperationError>
          <e1452:OperationError>
            <e1452:Code>ValueHere</e1452:Code>
            <e1452:Details d4p1:nil="false">ValueHere</e1452:Details>
            <e1452:Message d4p1:nil="false">ValueHere</e1452:Message>
          </e1452:OperationError>
        </e1452:ArrayOfOperationError>
      </PartialErrors>
    </AddClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<AddClientLinksResponse> AddClientLinksAsync(
	IList<ClientLink> clientLinks)
{
	var request = new AddClientLinksRequest
	{
		ClientLinks = clientLinks
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.AddClientLinksAsync(r), request));
}
```
```java
static AddClientLinksResponse addClientLinks(
	ArrayOfClientLink clientLinks) throws RemoteException, Exception
{
	AddClientLinksRequest request = new AddClientLinksRequest();

	request.setClientLinks(clientLinks);

	return CustomerManagementService.getService().addClientLinks(request);
}
```
```php
static function AddClientLinks(
	$clientLinks)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new AddClientLinksRequest();

	$request->ClientLinks = $clientLinks;

	return $GLOBALS['CustomerManagementProxy']->GetService()->AddClientLinks($request);
}
```
```python
response=customermanagement_service.AddClientLinks(
	ClientLinks=ClientLinks)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  
