---
title: "Management Model for Agencies"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: An agency builds a Bing Ads application for their company to manage the campaigns of their advertising clients.
---
# Management Model for Agencies
An agency builds a Bing Ads application for their company to manage the campaigns of their advertising clients. Agencies may manage some or all aspects of an advertiser account. When sending the invitation to manage a client account, the agency may specify whether the client or agency is responsible for billing. For more information about becoming an agency, see the help article [Managing your clients as an agency with Bing Ads](http://help.bingads.microsoft.com/#apex/3/en/52083/3) or [Resources for agency partners](https://advertise.bingads.microsoft.com/en-us/resources/bing-partner-program/agency-resources).

> [!NOTE]
> The client account must be set up for post-pay billing. Prepaid accounts are not supported for management by agencies.

## Agency Entity Model
The following figure shows two clients managed by an agency.

![Management Model Agency](media/management-model-agency.png "Management Model Agency")

Only an agency Super Admin can [Link to Client Accounts](#clientlink). Linking enables any agency Super Admin to access the specified client account. If the client has multiple accounts, then a client link invitation must be sent for each client account. The super admin may also determine which individual accounts the advertiser campaign manager and viewer users can access. In the figure above **User A** has access to account A1, and **User B** has access to accounts A2, B1, and B2. For more information about user roles, see [User Roles and Available Service Operations](customer-accounts.md#userroles).

## <a name="clientlink"></a>Link to Client Accounts
> [!NOTE] 
> Linking to client accounts as an agency is not supported in the [sandbox](sandbox.md) environment. 

To manage client accounts, a Super Admin user of the agency must send an invitation to the client, which must then be accepted by a Super Admin user of the client. To determine whether a link already exists, call the [SearchClientLinks](../customer-management-service/searchclientlinks.md) operation and check the Status element of any returned [ClientLink](../customer-management-service/clientlink.md). For a list of possible status values, see [ClientLinkStatus value set](../customer-management-service/clientlinkstatus.md). To search by individual account, set the predicate field to ClientAccountId and set the predicate value to the account identifier that you want to find. There is no set limit to the amount of client accounts that can be linked to an agency.

If a link exists with status either Active, LinkAccepted, LinkInProgress, LinkPending, UnlinkInProgress, or UnlinkPending, the agency may not initiate a duplicate client link.

If a client link to the specified account does not yet exist, or if the lifecycle of an existing link had ended with status of Expired, LinkCanceled, LinkDeclined, LinkFailed, or Inactive, then the agency may initiate a new client link invitation by calling the [AddClientLinks](../customer-management-service/addclientlinks.md) operation. The service transitions client link status to LinkPending immediately.

> [!IMPORTANT]
> The agency may specify whether the client or agency is responsible for billing by setting the *IsBillToClient* element in the service request. If not otherwise specified, the agency will be billed.

To update a client link, the *TimeStamp* element is required for validation, so you must first call the [SearchClientLinks](../customer-management-service/searchclientlinks.md) operation to get the existing *ClientLink* object. Then modify the *Status* element of the returned *ClientLink*, and include the updated *ClientLink* object in a subsequent call to the [UpdateClientLinks](../customer-management-service/updateclientlinks.md) operation.

The client may only use the *UpdateClientLinks* operation to update the status as LinkAccepted or LinkDeclined.

> [!NOTE]
> The client may accept or decline through an application built on the Bing Ads API, or through the **Accounts & Billing** tab in the Bing Ads web application. In either case the client credentials must be used to accept or decline. For more information, see the Bing Ads help article [Getting started as an agency with Bing Ads](https://help.bingads.microsoft.com/#apex/3/en/52083/3-500).

If the client sets the status to LinkDeclined, the client link lifecycle ends. You may not update a declined client link, and you must send a new invitation to manage the client account. If the client sets the status to LinkAccepted, the status transitions to LinkInProgress. If the link process succeeds, the service updates the client link status to Active.

If the link process fails, possibly due to a billing transition error, the service updates the client link status to LinkFailed. You may not update a failed client link, and you must send a new invitation to manage the client account.

If the client or agency does not take action within 30 days, the service sets the status to LinkExpired and the client link lifecycle ends. You may not update an expired client link, and you must send a new invitation to manage the client account.

![Link to Client](media/client-link-status-flow.png "Link to Client")

If the client link status is LinkPending, the agency may choose to cancel a prior link request. If the client link status is Active, the agency may choose to initiate the unlink process, which would terminate the existing relationship with the client.

To initiate the unlink process, the agency sets the client link status to UnlinkRequested and calls the [UpdateClientLinks](../customer-management-service/updateclientlinks.md) operation. Updating the status with UnlinkRequested effectively sets the status to UnlinkInProgress. The service transitions client link status to UnlinkPending immediately, and then waits for system resources to proceed. The state should transition quickly to UnlinkInProgress.

If the unlink process fails, possibly due to a billing transition error, the client link resumes to Active status. If the unlink process succeeds the status will update to Inactive, and the client link lifecycle ends. You may not update an inactive client link, and you must send a new invitation to manage the client account.

![Unlink from Client](media/client-unlink-status-flow.png "Unlink from Client")

For code examples that show how to add and update a client link invitation, see [Manage Client Code Example](code-example-manage-client.md).

## See Also
[Customer Accounts](customer-accounts.md)  
[Get Started With the Bing Ads API](get-started.md)  

