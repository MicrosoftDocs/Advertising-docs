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
> This Bing Ads API Version 12 preview documentation is subject to change.
# AddClientLinks Service Operation - Customer Management
Initiates the client link process to manage the account of another customer. Sends an invitation from an agency to a potential client.  For more information about the client link lifecycle, see [Link to Client Accounts](../guides/management-model-agencies.md#clientlink).

> [!NOTE]
> The client account must have a valid payment instrument set up for post-pay billing. Prepaid accounts are not supported for management by agencies.

Only an agency may call this service operation. For more information about becoming an agency, see the [Resources for agency partners](https://advertise.bingads.microsoft.com/en-us/resources/bing-partner-program/agency-resources).

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).

There is no set limit to the amount of client accounts that can be linked to an agency.

> [!NOTE]
>This feature is not supported in sandbox.

## <a name="request"></a>Request Elements
The *AddClientLinksRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="clientlinks"></a>ClientLinks|The list of client links to add.<br /><br />You should limit your request to 10 client links per call.|[ClientLink](clientlink.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *AddClientLinksResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="operationerrors"></a>OperationErrors|A list of one or more reasons why the service operation failed, and no client links were added.|[OperationError](operationerror.md) array|
|<a name="partialerrors"></a>PartialErrors|An array of *OperationError* lists that contain details for any client links that were not successfully added.<br /><br />Results are returned in the same order corresponding to the requested client links. The number of first dimension list elements is equal to the requested client links count. For successfully added client links, the *OperationError* element at the corresponding index is null.|[OperationError](operationerror.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">AddClientLinks</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <ClientLinks xmlns:e314="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e314:ClientLink>
          <e314:ClientAccountId i:nil="false">ValueHere</e314:ClientAccountId>
          <e314:ClientAccountNumber i:nil="false">ValueHere</e314:ClientAccountNumber>
          <e314:ManagingCustomerId i:nil="false">ValueHere</e314:ManagingCustomerId>
          <e314:ManagingCustomerNumber i:nil="false">ValueHere</e314:ManagingCustomerNumber>
          <e314:Note i:nil="false">ValueHere</e314:Note>
          <e314:Name i:nil="false">ValueHere</e314:Name>
          <e314:InviterEmail i:nil="false">ValueHere</e314:InviterEmail>
          <e314:InviterName i:nil="false">ValueHere</e314:InviterName>
          <e314:InviterPhone i:nil="false">ValueHere</e314:InviterPhone>
          <e314:IsBillToClient>ValueHere</e314:IsBillToClient>
          <e314:StartDate i:nil="false">ValueHere</e314:StartDate>
          <e314:Status i:nil="false">ValueHere</e314:Status>
          <e314:SuppressNotification>ValueHere</e314:SuppressNotification>
          <e314:LastModifiedDateTime>ValueHere</e314:LastModifiedDateTime>
          <e314:LastModifiedByUserId>ValueHere</e314:LastModifiedByUserId>
          <e314:Timestamp i:nil="false">ValueHere</e314:Timestamp>
          <ForwardCompatibilityMap xmlns:e315="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e315:KeyValuePairOfstringstring>
              <e315:key i:nil="false">ValueHere</e315:key>
              <e315:value i:nil="false">ValueHere</e315:value>
            </e315:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e314:ClientLink>
      </ClientLinks>
    </AddClientLinksRequest>
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
    <AddClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <OperationErrors xmlns:e316="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e316:OperationError>
          <e316:Code>ValueHere</e316:Code>
          <e316:Details d4p1:nil="false">ValueHere</e316:Details>
          <e316:Message d4p1:nil="false">ValueHere</e316:Message>
        </e316:OperationError>
      </OperationErrors>
      <PartialErrors xmlns:e317="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e317:ArrayOfOperationError>
          <e317:OperationError>
            <e317:Code>ValueHere</e317:Code>
            <e317:Details d4p1:nil="false">ValueHere</e317:Details>
            <e317:Message d4p1:nil="false">ValueHere</e317:Message>
          </e317:OperationError>
        </e317:ArrayOfOperationError>
      </PartialErrors>
    </AddClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
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
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

