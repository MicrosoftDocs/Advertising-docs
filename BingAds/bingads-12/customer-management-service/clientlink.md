---
title: ClientLink Data Object - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines a client link object.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# ClientLink Data Object - Customer Management
Defines a client link object. Acceptance of a client link invitation enables an agency to  manage the corresponding client accounts. To send an invitation to manage a client account, call the [AddClientLinks](addclientlinks.md) operation and specify one client link per account to manage. For more information about the client link lifecycle, see [Link to Client Accounts](../guides/management-model-agencies.md#clientlink).

> [!NOTE]
> This object does not have a system defined identifier. To uniquely identify a client link, use either the *ClientAccountId* or *ClientAccountNumber* paired with either the *ManagingCustomerId* or *ManagingCustomerNumber*.

## Syntax
```xml
<xs:complexType name="ClientLink" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:sequence>
    <xs:element minOccurs="0" name="ClientAccountId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="ClientAccountNumber" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="ManagingCustomerId" nillable="true" type="xs:long" />
    <xs:element minOccurs="0" name="ManagingCustomerNumber" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Note" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="Name" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="InviterEmail" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="InviterName" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="InviterPhone" nillable="true" type="xs:string" />
    <xs:element minOccurs="0" name="IsBillToClient" type="xs:boolean" />
    <xs:element minOccurs="0" name="StartDate" nillable="true" type="xs:dateTime" />
    <xs:element minOccurs="0" name="Status" nillable="true" type="tns:ClientLinkStatus" />
    <xs:element minOccurs="0" name="SuppressNotification" type="xs:boolean" />
    <xs:element minOccurs="0" name="LastModifiedDateTime" type="xs:dateTime" />
    <xs:element minOccurs="0" name="LastModifiedByUserId" type="xs:long" />
    <xs:element minOccurs="0" name="Timestamp" nillable="true" type="xs:base64Binary" />
    <xs:element minOccurs="0" name="ForwardCompatibilityMap" nillable="true" type="q5:ArrayOfKeyValuePairOfstringstring" xmlns:q5="http://schemas.datacontract.org/2004/07/System.Collections.Generic" />
  </xs:sequence>
</xs:complexType>
```

## <a name="elements"></a>Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="clientaccountid"></a>ClientAccountId|The identifier of the client account to manage.<br /><br />When adding a client link, either the *ClientAccountId* or *ClientAccountNumber* is required, but specifying both will cause the operation to fail.<br/><br/>**Add:** Optional<br/>**Update:** Read-only and Required|**long**|
|<a name="clientaccountnumber"></a>ClientAccountNumber|The number of the client account to manage.<br /><br />When adding a client link, either the *ClientAccountId* or *ClientAccountNumber* is required, but specifying both will cause the operation to fail.<br/><br/>**Add:** Optional<br/>**Update:** Read-only and Required|**string**|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *ClientLink* object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="inviteremail"></a>InviterEmail|The email of the user who created the client link request.<br /><br />This value does not need to be the same as, nor is it used to modify, the email already stored in Bing Ads for the current authenticated user.<br /><br />If not specified, the service will set this value to the email already stored in Bing Ads for the current authenticated user.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**string**|
|<a name="invitername"></a>InviterName|The name of the parent customer of the user who  created the client link request.<br /><br />This value does not need to be the same as, nor is it used to modify, the customer name already stored in Bing Ads.<br /><br />If not specified, the service will set this value to the parent customer name already stored in Bing Ads for the current authenticated user.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**string**|
|<a name="inviterphone"></a>InviterPhone|The phone number of the user who created the client link request.<br /><br />This value does not need to be the same as, nor is it used to modify, the phone number already stored in Bing Ads for the current authenticated user.<br /><br />If not specified, the service will set this value to the phone number already stored in Bing Ads for the current authenticated user.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**string**|
|<a name="isbilltoclient"></a>IsBillToClient|Determines whether the owner of the client account or the managing customer is responsible for billing payments.<br /><br />If set to true the client will be responsible and otherwise, since the default value is false, the managing customer is responsible for billing.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**boolean**|
|<a name="lastmodifiedbyuserid"></a>LastModifiedByUserId|The identifier of the last user to update the client link's information.<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**long**|
|<a name="lastmodifieddatetime"></a>LastModifiedDateTime|The date and time that the client link was last updated. The value is in Coordinated Universal Time (UTC).<br /><br /> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).<br/><br/>**Add:** Read-only<br/>**Update:** Read-only|**dateTime**|
|<a name="managingcustomerid"></a>ManagingCustomerId|The identifier of the customer who manages or is requesting to manage the client account.<br /><br />When adding a client link, either the *ManagingCustomerId* or *ManagingCustomerNumber* is required, but specifying both will cause the operation to fail.<br/><br/>**Add:** Optional<br/>**Update:** Read-only and Required|**long**|
|<a name="managingcustomernumber"></a>ManagingCustomerNumber|The number of the customer who manages or is requesting to manage the client account.<br /><br />When adding a client link, either the *ManagingCustomerId* or *ManagingCustomerNumber* is required, but specifying both will cause the operation to fail.<br/><br/>**Add:** Optional<br/>**Update:** Read-only and Required|**string**|
|<a name="name"></a>Name|The friendly name that can be used to reference this client link.<br /><br />The name can contain a maximum of 40 characters.<br /><br />A default name will be provided if none is specified. The name does not need to be unique compared to other client links for the user.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**string**|
|<a name="note"></a>Note|Optional message from the requestor providing context and details about the client link invitation.<br/><br/>**Add:** Optional<br/>**Update:** Optional. If no value is specified on update, this Bing Ads setting is not changed.|**string**|
|<a name="startdate"></a>StartDate|The date when the status would update. For an accepted link request the status would transition towards Active on this date, and for an unlink request the status would transition towards Inactive on this date.<br /><br />If not specified, this value will be set to the current date and time.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**dateTime**|
|<a name="status"></a>Status|Determines the life cycle status of the client link, for example whether the client link has been accepted or declined.<br /><br />When adding a client link this element cannot be specified, and the service sets the effective status to LinkPending.<br/><br/>**Add:** Read-only<br/>**Update:** Required|[ClientLinkStatus](clientlinkstatus.md)|
|<a name="suppressnotification"></a>SuppressNotification|Determines whether or not to send email notification of the client link invitation to the primary user of the client account.<br /><br />If set to true the client will not receive an email and otherwise, since the default value is false, the client will receive an email notification.<br/><br/>**Add:** Optional<br/>**Update:** Read-only|**boolean**|
|<a name="timestamp"></a>Timestamp|Reserved for future use.|**base64Binary**|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11/Entities  

## Used By
[AddClientLinks](addclientlinks.md)  
[SearchClientLinks](searchclientlinks.md)  
[UpdateClientLinks](updateclientlinks.md)  
