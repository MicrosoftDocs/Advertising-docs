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
      <ClientLinks xmlns:e908="https://bingads.microsoft.com/Customer/v12/Entities" i:nil="false">
        <e908:ClientLink>
          <e908:ClientAccountId i:nil="false">ValueHere</e908:ClientAccountId>
          <e908:ClientAccountNumber i:nil="false">ValueHere</e908:ClientAccountNumber>
          <e908:ManagingCustomerId i:nil="false">ValueHere</e908:ManagingCustomerId>
          <e908:ManagingCustomerNumber i:nil="false">ValueHere</e908:ManagingCustomerNumber>
          <e908:Note i:nil="false">ValueHere</e908:Note>
          <e908:Name i:nil="false">ValueHere</e908:Name>
          <e908:InviterEmail i:nil="false">ValueHere</e908:InviterEmail>
          <e908:InviterName i:nil="false">ValueHere</e908:InviterName>
          <e908:InviterPhone i:nil="false">ValueHere</e908:InviterPhone>
          <e908:IsBillToClient>ValueHere</e908:IsBillToClient>
          <e908:StartDate i:nil="false">ValueHere</e908:StartDate>
          <e908:Status i:nil="false">ValueHere</e908:Status>
          <e908:SuppressNotification>ValueHere</e908:SuppressNotification>
          <e908:LastModifiedDateTime>ValueHere</e908:LastModifiedDateTime>
          <e908:LastModifiedByUserId>ValueHere</e908:LastModifiedByUserId>
          <e908:Timestamp i:nil="false">ValueHere</e908:Timestamp>
          <ForwardCompatibilityMap xmlns:e909="http://schemas.datacontract.org/2004/07/System.Collections.Generic" i:nil="false">
            <e909:KeyValuePairOfstringstring>
              <e909:key i:nil="false">ValueHere</e909:key>
              <e909:value i:nil="false">ValueHere</e909:value>
            </e909:KeyValuePairOfstringstring>
          </ForwardCompatibilityMap>
        </e908:ClientLink>
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
      <OperationErrors xmlns:e910="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e910:OperationError>
          <e910:Code>ValueHere</e910:Code>
          <e910:Details d4p1:nil="false">ValueHere</e910:Details>
          <e910:Message d4p1:nil="false">ValueHere</e910:Message>
        </e910:OperationError>
      </OperationErrors>
      <PartialErrors xmlns:e911="https://bingads.microsoft.com/Customer/v12/Exception" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e911:ArrayOfOperationError>
          <e911:OperationError>
            <e911:Code>ValueHere</e911:Code>
            <e911:Details d4p1:nil="false">ValueHere</e911:Details>
            <e911:Message d4p1:nil="false">ValueHere</e911:Message>
          </e911:OperationError>
        </e911:ArrayOfOperationError>
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

