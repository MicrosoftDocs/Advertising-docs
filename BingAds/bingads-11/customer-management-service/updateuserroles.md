---
title: UpdateUserRoles Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Updates the roles of the specified user.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# UpdateUserRoles Service Operation - Customer Management
Updates the roles of the specified user.

## <a name="request"></a>Request Elements
The *UpdateUserRolesRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="customerid"></a>CustomerId|The identifier of the customer to which the user belongs.|**long**|
|<a name="deleteaccountids"></a>DeleteAccountIds|An array of identifiers of the accounts to remove from the list of accounts that the user can manage.<br/><br/>For usage, see the [Remarks](#remarks) section below.|**long** array|
|<a name="deletecustomerids"></a>DeleteCustomerIds|An array of identifiers of the customers to remove from the list of customers that the user can manage.<br/><br/>For usage, see the [Remarks](#remarks) section below.|**long** array|
|<a name="deleteroleid"></a>DeleteRoleId|The identifier of the role to which the values specified in the *DeleteAccountIds* or *DeleteCustomerIds* element applies, if set.<br /><br />For more information about possible role values, see the corresponding **Integer Value** column within the [UserRole](../customer-management-service/userrole.md).|**int**|
|<a name="newaccountids"></a>NewAccountIds|An array of identifiers of the accounts to restrict the user to. The user will be able to manage only these accounts.<br/><br/>If the user is currently restricted to a set of accounts, set this element to the new accounts that you want the user to also manage. For example, if the user currently manages accounts 123 and 456, and you want the user to also manage account 789, set this element to 789.<br/><br/>For usage, see the [Remarks](#remarks) section below.|**long** array|
|<a name="newcustomerids"></a>NewCustomerIds|An array of identifiers of the customers to restrict the user to. The user will be able to manage only these customers.<br/><br/>For usage, see the [Remarks](#remarks) section below.|**long** array|
|<a name="newroleid"></a>NewRoleId|The identifier of the role to which the values specified in the *NewAccountIds* or *NewCustomerIds* element applies to, if set.<br /><br />For more information about possible role values, see the corresponding **Integer Value** column within the [UserRole](../customer-management-service/userrole.md).|**int**|
|<a name="userid"></a>UserId|The identifier of the user whose role you want to update.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *UpdateUserRolesResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="lastmodifiedtime"></a>LastModifiedTime|The date and time that the user roles were last updated. The value is in Coordinated Universal Time (UTC).<br/><br/> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).|**dateTime**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v11">
    <Action mustUnderstand="1">UpdateUserRoles</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <UpdateUserRolesRequest xmlns="https://bingads.microsoft.com/Customer/v11">
      <CustomerId>ValueHere</CustomerId>
      <UserId>ValueHere</UserId>
      <NewRoleId i:nil="false">ValueHere</NewRoleId>
      <NewAccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </NewAccountIds>
      <NewCustomerIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </NewCustomerIds>
      <DeleteRoleId i:nil="false">ValueHere</DeleteRoleId>
      <DeleteAccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </DeleteAccountIds>
      <DeleteCustomerIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </DeleteCustomerIds>
    </UpdateUserRolesRequest>
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
    <UpdateUserRolesResponse xmlns="https://bingads.microsoft.com/Customer/v11">
      <LastModifiedTime>ValueHere</LastModifiedTime>
    </UpdateUserRolesResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<UpdateUserRolesResponse> UpdateUserRolesAsync(
	long customerId,
	long userId,
	int? newRoleId,
	IList<long> newAccountIds,
	IList<long> newCustomerIds,
	int? deleteRoleId,
	IList<long> deleteAccountIds,
	IList<long> deleteCustomerIds)
{
	var request = new UpdateUserRolesRequest
	{
		CustomerId = customerId,
		UserId = userId,
		NewRoleId = newRoleId,
		NewAccountIds = newAccountIds,
		NewCustomerIds = newCustomerIds,
		DeleteRoleId = deleteRoleId,
		DeleteAccountIds = deleteAccountIds,
		DeleteCustomerIds = deleteCustomerIds
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.UpdateUserRolesAsync(r), request));
}
```
```java
static UpdateUserRolesResponse updateUserRoles(
	java.lang.Long customerId,
	java.lang.Long userId,
	int newRoleId,
	ArrayOflong newAccountIds,
	ArrayOflong newCustomerIds,
	int deleteRoleId,
	ArrayOflong deleteAccountIds,
	ArrayOflong deleteCustomerIds) throws RemoteException, Exception
{
	UpdateUserRolesRequest request = new UpdateUserRolesRequest();

	request.setCustomerId(customerId);
	request.setUserId(userId);
	request.setNewRoleId(newRoleId);
	request.setNewAccountIds(newAccountIds);
	request.setNewCustomerIds(newCustomerIds);
	request.setDeleteRoleId(deleteRoleId);
	request.setDeleteAccountIds(deleteAccountIds);
	request.setDeleteCustomerIds(deleteCustomerIds);

	return CustomerManagementService.getService().updateUserRoles(request);
}
```
```php
static function UpdateUserRoles(
	$customerId,
	$userId,
	$newRoleId,
	$newAccountIds,
	$newCustomerIds,
	$deleteRoleId,
	$deleteAccountIds,
	$deleteCustomerIds)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new UpdateUserRolesRequest();

	$request->CustomerId = $customerId;
	$request->UserId = $userId;
	$request->NewRoleId = $newRoleId;
	$request->NewAccountIds = $newAccountIds;
	$request->NewCustomerIds = $newCustomerIds;
	$request->DeleteRoleId = $deleteRoleId;
	$request->DeleteAccountIds = $deleteAccountIds;
	$request->DeleteCustomerIds = $deleteCustomerIds;

	return $GLOBALS['CustomerManagementProxy']->GetService()->UpdateUserRoles($request);
}
```
```python
response=customermanagement_service.UpdateUserRoles(
	CustomerId=CustomerId,
	UserId=UserId,
	NewRoleId=NewRoleId,
	NewAccountIds=NewAccountIds,
	NewCustomerIds=NewCustomerIds,
	DeleteRoleId=DeleteRoleId,
	DeleteAccountIds=DeleteAccountIds,
	DeleteCustomerIds=DeleteCustomerIds)
```

## <a name="remarks"></a>Remarks
As an example use case if an advertiser campaign manager is limited to managing accounts 123, 456, and 789, and you no longer want the user to manage 456, set the following elements accordingly:

-   Set the *NewRoleId* element to 16 (advertiser campaign manager role).

-   Set the *NewAccountIds* element to an array that contains 123 and 789.

-   Set the *DeleteRoleId* element to 16 (advertiser campaign manager role).

-   Set the *DeleteAccountIds* element to an array that contains 456.

If an advertiser campaign manager is limited to managing accounts 123 and 789, and you now want the user to manage all accounts, set the following elements accordingly:

-   Set the *NewRoleId* element to 16 (advertiser campaign manager role).

-   Set the *NewAccountIds* element to NULL.

-   Set the *DeleteRoleId* element to 16 (advertiser campaign manager role).

-   Set the *DeleteAccountIds* element to an array that contains 123, 456, and 789.

Users with account level roles can be restricted to specific accounts. Users with customer level roles can access all accounts within the user's customer, and their access cannot be restricted to specific accounts.

> [!NOTE]
> When attempting to restrict customer level user roles to specific accounts the *UpdateUserRoles* operation will not fail, and the user will retain access for all accounts within the user's customer.

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

