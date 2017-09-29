---
title: AddClientLinks Service Operation
ms.service: bing-ads-customer-management
ms.topic: article
author: eric-urban
ms.author: eur
---
# AddClientLinks Service Operation
Initiates the client link process to manage the account of another customer. Sends an invitation from an agency to a potential client.  For more information about the client link lifecycle, see [Link to Client Accounts](~/guides/management-model-agencies.md#clientlink).

> [!NOTE]
> The client account must have a valid payment instrument set up for post-pay billing. Prepaid accounts are not supported for management by agencies.

Only an agency may call this service operation. For more information about becoming an agency, see the [Resources for agency partners](https://advertise.bingads.microsoft.com/en-us/resources/bing-partner-program/agency-resources).

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](~/guides/customer-accounts.md#userroles).

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
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">AddClientLinks</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <AddClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <ClientLinks xmlns:e407="https://bingads.microsoft.com/Customer/v11/Entities" i:nil="false">
        <e407:ClientLink>
          <e407:ClientAccountId i:nil="false">ValueHere</e407:ClientAccountId>
          <e407:ClientAccountNumber i:nil="false">ValueHere</e407:ClientAccountNumber>
          <e407:ManagingCustomerId i:nil="false">ValueHere</e407:ManagingCustomerId>
          <e407:ManagingCustomerNumber i:nil="false">ValueHere</e407:ManagingCustomerNumber>
          <e407:Note i:nil="false">ValueHere</e407:Note>
          <e407:Name i:nil="false">ValueHere</e407:Name>
          <e407:InviterEmail i:nil="false">ValueHere</e407:InviterEmail>
          <e407:InviterName i:nil="false">ValueHere</e407:InviterName>
          <e407:InviterPhone i:nil="false">ValueHere</e407:InviterPhone>
          <e407:IsBillToClient>ValueHere</e407:IsBillToClient>
          <e407:StartDate i:nil="false">ValueHere</e407:StartDate>
          <e407:Status i:nil="false">ValueHere</e407:Status>
          <e407:SuppressNotification>ValueHere</e407:SuppressNotification>
          <e407:LastModifiedDateTime>ValueHere</e407:LastModifiedDateTime>
          <e407:LastModifiedByUserId>ValueHere</e407:LastModifiedByUserId>
          <e407:Timestamp i:nil="false">ValueHere</e407:Timestamp>
          <ForwardCompatibilityMap xmlns:e408="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e408:KeyValuePairOfstringstring>
              <e408:key i:nil="false">ValueHere</e408:key>
              <e408:value i:nil="false">ValueHere</e408:value>
            </e408:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e407:ClientLink>
      </ClientLinks>
    </AddClientLinksRequest>
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
    <AddClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <OperationErrors xmlns:e409="https://bingads.microsoft.com/Customer/v11/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e409:OperationError>
          <e409:Code>ValueHere</e409:Code>
          <e409:Details d4p1:nil="false">ValueHere</e409:Details>
          <e409:Message d4p1:nil="false">ValueHere</e409:Message>
        </e409:OperationError>
      </OperationErrors>
      <PartialErrors xmlns:e410="https://bingads.microsoft.com/Customer/v11/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e410:ArrayOfOperationError>
          <e410:OperationError>
            <e410:Code>ValueHere</e410:Code>
            <e410:Details d4p1:nil="false">ValueHere</e410:Details>
            <e410:Message d4p1:nil="false">ValueHere</e410:Message>
          </e410:OperationError>
        </e410:ArrayOfOperationError>
      </PartialErrors>
    </AddClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
```csharp
protected async Task<AddClientLinksResponse> AddClientLinksAsync(
	IList<ClientLink> clientLinks)
{
	var request = new AddClientLinksRequest
	{
		ClientLinks = clientLinks
	};

	return (await CustomerManagement.CallAsync((s, r) => s.AddClientLinksAsync(r), request));
}
```
```java
static AddClientLinksResponse addClientLinks(
	ArrayOfClientLink clientLinks)
{
	AddClientLinksRequest request = new AddClientLinksRequest();

	request.setClientLinks(clientLinks);

	return CustomerManagement.getService().addClientLinks(request);
}
```
```php
static function AddClientLinks(
	$clientLinks)

	$addClientLinksRequest = new AddClientLinksRequest();

	$request->ClientLinks = $clientLinks;

	return $CustomerManagementProxy->GetService()->AddClientLinks($request);
}
```
```python
response=customermanagement.AddClientLinks(
	ClientLinks=ClientLinksHere
)
```

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https://bingads.microsoft.com/Customer/v11  

