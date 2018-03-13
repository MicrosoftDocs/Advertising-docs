---
title: UpdateClientLinks Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the status of the specified client links.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# UpdateClientLinks Service Operation - Customer Management
Updates the status of the specified client links. To update a client link, the *TimeStamp* element is required for validation, so you must first call the [SearchClientLinks](searchclientlinks.md) to get the existing *ClientLink* object. Then modify the *Status* element of the returned *ClientLink*, and include the updated *ClientLink* object  in a subsequent call to the *UpdateClientLinks* operation. For more information about the client link lifecycle, see [Link to Client Accounts](../guides/management-model-agencies.md#clientlink).

If your user is within an agency, then the operation may be used to update the client link status of any account that you manage or have invited to manage. For more information about becoming an agency, see the [Resources for agency partners](https://advertise.bingads.microsoft.com/en-us/resources/bing-partner-program/agency-resources).

If your user is within a client customer that has one or more accounts managed or invited to be managed by an agency, then you may only use this operation to update the status as *LinkAccepted* or *LinkDeclined*. A  client may also accept or decline the link request via the Bing Ads web application. For more information, see [How to have an agency manage your Bing Ads account](http://help.bingads.microsoft.com/#apex/3/en/52004/3).

The role of the user calling this operation must be Super Admin. For more information, see [User Roles and Available Service Operations](../guides/customer-accounts.md#userroles).

There is no set limit to the amount of client accounts that can be linked to an agency.


> [!NOTE]
>This feature is not supported in sandbox.

## <a name="request"></a>Request Elements
The *UpdateClientLinksRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="clientlinks"></a>ClientLinks|The list of client links to update.<br /><br />You should limit your request to 10 client links per call.|[ClientLink](clientlink.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateClientLinksResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

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
    <Action mustUnderstand="1">UpdateClientLinks</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateClientLinksRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <ClientLinks xmlns:e359="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e359:ClientLink>
          <e359:ClientAccountId i:nil="false">ValueHere</e359:ClientAccountId>
          <e359:ClientAccountNumber i:nil="false">ValueHere</e359:ClientAccountNumber>
          <e359:ManagingCustomerId i:nil="false">ValueHere</e359:ManagingCustomerId>
          <e359:ManagingCustomerNumber i:nil="false">ValueHere</e359:ManagingCustomerNumber>
          <e359:Note i:nil="false">ValueHere</e359:Note>
          <e359:Name i:nil="false">ValueHere</e359:Name>
          <e359:InviterEmail i:nil="false">ValueHere</e359:InviterEmail>
          <e359:InviterName i:nil="false">ValueHere</e359:InviterName>
          <e359:InviterPhone i:nil="false">ValueHere</e359:InviterPhone>
          <e359:IsBillToClient>ValueHere</e359:IsBillToClient>
          <e359:StartDate i:nil="false">ValueHere</e359:StartDate>
          <e359:Status i:nil="false">ValueHere</e359:Status>
          <e359:SuppressNotification>ValueHere</e359:SuppressNotification>
          <e359:LastModifiedDateTime>ValueHere</e359:LastModifiedDateTime>
          <e359:LastModifiedByUserId>ValueHere</e359:LastModifiedByUserId>
          <e359:Timestamp i:nil="false">ValueHere</e359:Timestamp>
          <ForwardCompatibilityMap xmlns:e360="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e360:KeyValuePairOfstringstring>
              <e360:key i:nil="false">ValueHere</e360:key>
              <e360:value i:nil="false">ValueHere</e360:value>
            </e360:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e359:ClientLink>
      </ClientLinks>
    </UpdateClientLinksRequest>
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
    <UpdateClientLinksResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <OperationErrors xmlns:e361="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e361:OperationError>
          <e361:Code>ValueHere</e361:Code>
          <e361:Details d4p1:nil="false">ValueHere</e361:Details>
          <e361:Message d4p1:nil="false">ValueHere</e361:Message>
        </e361:OperationError>
      </OperationErrors>
      <PartialErrors xmlns:e362="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e362:ArrayOfOperationError>
          <e362:OperationError>
            <e362:Code>ValueHere</e362:Code>
            <e362:Details d4p1:nil="false">ValueHere</e362:Details>
            <e362:Message d4p1:nil="false">ValueHere</e362:Message>
          </e362:OperationError>
        </e362:ArrayOfOperationError>
      </PartialErrors>
    </UpdateClientLinksResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateClientLinksResponse> UpdateClientLinksAsync(
	IList<ClientLink> clientLinks)
{
	var request = new UpdateClientLinksRequest
	{
		ClientLinks = clientLinks
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.UpdateClientLinksAsync(r), request));
}
```
```java
static UpdateClientLinksResponse updateClientLinks(
	ArrayOfClientLink clientLinks) throws RemoteException, Exception
{
	UpdateClientLinksRequest request = new UpdateClientLinksRequest();

	request.setClientLinks(clientLinks);

	return CustomerManagementService.getService().updateClientLinks(request);
}
```
```php
static function UpdateClientLinks(
	$clientLinks)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new UpdateClientLinksRequest();

	$request->ClientLinks = $clientLinks;

	return $GLOBALS['CustomerManagementProxy']->GetService()->UpdateClientLinks($request);
}
```
```python
response=customermanagement_service.UpdateClientLinks(
	ClientLinks=ClientLinks)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

