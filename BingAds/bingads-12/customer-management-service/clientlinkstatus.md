---
title: ClientLinkStatus Value Set - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the possible status values of a ClientLink.
---
# ClientLinkStatus Value Set - Customer Management
Defines the possible status values of a [ClientLink](../customer-management-service/clientlink.md).

For more information about the client link lifecycle, see [Link to Client Accounts](~/guides/management-model-agencies.md#clientlink).

## Syntax
```xml
<xs:simpleType name="ClientLinkStatus" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:annotation>
    <xs:appinfo>
      <ActualType Name="unsignedByte" Namespace="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/2003/10/Serialization/" />
    </xs:appinfo>
  </xs:annotation>
  <xs:restriction base="xs:string">
    <xs:enumeration value="LinkPending" />
    <xs:enumeration value="LinkCanceled" />
    <xs:enumeration value="LinkExpired" />
    <xs:enumeration value="LinkAccepted" />
    <xs:enumeration value="LinkDeclined" />
    <xs:enumeration value="LinkInProgress" />
    <xs:enumeration value="Active" />
    <xs:enumeration value="LinkFailed" />
    <xs:enumeration value="UnlinkRequested" />
    <xs:enumeration value="UnlinkPending" />
    <xs:enumeration value="UnlinkCanceled" />
    <xs:enumeration value="UnlinkInProgress" />
    <xs:enumeration value="Inactive" />
    <xs:enumeration value="UnlinkFailed" />
  </xs:restriction>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="active"></a>Active|The link is established and the managing customer can access the client account.<br /><br />The previous status was LinkInProgress.|
|<a name="inactive"></a>Inactive|The unlink process has completed and the managing customer can no longer access the client account.<br /><br />The previous status was UnlinkInProgress.|
|<a name="linkaccepted"></a>LinkAccepted|The invited client should use this value to accept the link invitation.<br /><br />The previous status was LinkPending.|
|<a name="linkcanceled"></a>LinkCanceled|The link request has been canceled by the agency.<br /><br />The previous status was LinkPending.|
|<a name="linkdeclined"></a>LinkDeclined|The link request has been declined by the invited client.<br /><br />The previous status was LinkPending.|
|<a name="linkexpired"></a>LinkExpired|The link is inactive due to expiry. The client did not accept or decline the request within 30 days.<br /><br />The previous status was LinkPending.|
|<a name="linkfailed"></a>LinkFailed|The link process failed to complete successfully.<br /><br />The previous status was LinkInProgress.|
|<a name="linkinprogress"></a>LinkInProgress|The link process is in progress and either waiting for the billing transition to complete or the specified client link start date has not yet arrived.<br /><br />The previous readable status was LinkPending, and the previous write-only status set by the client was LinkAccepted.|
|<a name="linkpending"></a>LinkPending|The [ClientLink](../customer-management-service/clientlink.md) has been added via the [AddClientLinks](../customer-management-service/addclientlinks.md) operation. The link request has been sent and is pending approval from the client.|
|<a name="unlinkcanceled"></a>UnlinkCanceled|Reserved for future use.|
|<a name="unlinkfailed"></a>UnlinkFailed|The unlink process failed to complete successfully, for example because the billing transition could not be completed.<br /><br />The previous status was UnlinkInProgress.|
|<a name="unlinkinprogress"></a>UnlinkInProgress|The unlink process is in progress and waiting for the billing transition to complete.<br /><br />The previous status was UnlinkPending.|
|<a name="unlinkpending"></a>UnlinkPending|A request to terminate the link has been sent. The request is waiting for the system to begin the unlink progress.<br /><br />The previous status was Active, and the next status will be UnlinkInProgress.|
|<a name="unlinkrequested"></a>UnlinkRequested|The agency should use this value to request an unlink.<br /><br />The previous status was Active.|

## Requirements
Service: [CustomerManagementService.svc v11](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v11/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v11  

## Used By
[ClientLink](clientlink.md)  
