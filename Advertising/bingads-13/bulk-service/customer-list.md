---
title: "Customer List Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Describes the Customer List fields in a Bulk file.
dev_langs:
  - csharp
---
# Customer List Record - Bulk
Defines a customer list that can be downloaded and uploaded in a bulk file. 

> [!NOTE]
> Customer lists are available for customers in the feature pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 579).  

> [!IMPORTANT]
> Before you can upload customer list data via Bulk API, you must first create one customer list audience and accept the terms and conditions in the Microsoft Advertising UI. The initial customer list doesn't need to contain any customer data, but you must click I ACCEPT. By clicking "I accept" you (1) agree that you are able to lawfully disclose audience details, which is personal data, to Microsoft and (2) accept the Customer Match Terms, the Microsoft Advertising Agreement, and the Microsoft Advertising policies. Microsoft will use the data that you upload in accordance with the [Customer Match Terms](https://go.microsoft.com/fwlink/?linkid=2106709).

A customer list is a set of customer contact information that you have compiled to enable customer match. Each list can include multiple Email and CRMID items. 
- Include the [Customer List](customer-list.md) record in the Bulk upload file and set its [Action Type](customer-list.md#actiontype) field to "Add", "Remove", or "Replace". 
- Include one or more [Customer List Item](customer-list-item.md) records in the same Bulk upload file and set the [Parent Id](customer-list-item.md#parentid), [Sub Type](customer-list-item.md#subtype), and [Text](customer-list-item.md#text) fields. 

You can add or update a [Customer List](customer-list.md) record without any [Customer List Item](customer-list-item.md) records in the same Bulk upload file; however, you cannot upload any [Customer List Item](customer-list-item.md) records without the accompanying parent [Customer List](customer-list.md) record. 

After 48 hours, check the Audience Size fields e.g., [Audience Search Size](#audiencesearchsize) to see how many of these customers we matched on the Bing Network. At that point, your ads can start showing for this new audience.

> [!TIP]
> For an overview and more information about audiences, see the [Audience APIs](../guides/universal-event-tracking.md#audience) technical guide. 

You can download all *Customer List* records in the account by including the [DownloadEntity](downloadentity.md) value of *CustomerLists* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new customer list. 

```csv
Type,Status,Id,Parent Id,Client Id,Modified Time,Name,Description,Scope,Audience,Action Type
Format Version,,,,,,6.0,,,,,,
Customer List,Active,-10,,ClientIdGoesHere,,,New customer list description,Customer,New Customer List,Add
```

For a *Customer List* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Action Type](#actiontype)
- [Audience](#audience)
- [Audience Network Size](#audiencenetworksize)
- [Audience Search Size](#audiencesearchsize)
- [Client Id](#clientid)
- [Description](#description)
- [Id](#id)
- [Membership Duration](#membershipduration)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Scope](#scope)
- [Status](#status)
- [Supported Campaign Types](#supportedcampaigntypes)


## <a name="actiontype"></a>Action Type
Determines whether to add, remove, or replace the [Customer List Item](customer-list-item.md) records that you include in the same Bulk upload file. 

If the action type is "Add", the service will attempt to add the [Customer List Item](customer-list-item.md) records that you include in the same Bulk upload file. 

If the action type is set to "Remove", the service will attempt to remove the [Customer List Item](customer-list-item.md) records that you include in the same Bulk upload file. 

If the action type is set to "Replace", all previous customer match data for this list will be removed, and the service will attempt to add the [Customer List Item](customer-list-item.md) records that you include in the same Bulk upload file. 

**Add:** Optional. By default the "Add" action type is used for new customer lists. Whether or not you set a value, this field is ignored for new customer lists.   
**Update:** Required if you are also including [Customer List Item](customer-list-item.md) records for an existing audience in the same Bulk upload file, and otherwise this field is optional.    
**Delete:** Read-only  

## <a name="audience"></a>Audience
The name of the customer list.

The name can contain a maximum of 128 characters.  

**Add:** Required  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="audiencenetworksize"></a>Audience Network Size
The total number of people who are active members of this audience in the Audience network. This gives you an idea of how many Audience network users you can target.

The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.

**Add:** Read-only  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="audiencesearchsize"></a>Audience Search Size
The total number of people who are active members of this audience in the Search network. This gives you an idea of how many search users you can target.

The audience needs to have at least 300 people before Microsoft Advertising will use it for optimizations.

This property will be empty for up to 24 hours while the audience is being built, for example if you add or update the customer list membership duration, rule, or tag identifier. 

This property will be empty if the UET tag associated with the customer list has a status of Unverified or Inactive, because the customer list can't receive the customer information from your website that it needs to build the list.

**Add:** Read-only  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="description"></a>Description
The description of the customer list. Use a description to help you remember what audience you are targeting with this customer list.

The description can contain a maximum of 1,024 characters.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed. If you set this field to the *delete_value* string, the prior setting is removed.   
**Delete:** Read-only  

## <a name="id"></a>Id
The system-generated identifier of the customer list.

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

## <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="membershipduration"></a>Membership Duration
When you create a customer list, you can specify how far back in time Microsoft Advertising should look for actions that match your customer list definition in order to add people to your list.

The mimimum duration is 1 day and the maximum duration allowed is 180 days.

**Add:** Optional  
**Update:** Optional. If no value is set for the update, this setting is not changed.    
**Delete:** Read-only  

## <a name="parentid"></a>Parent Id
The Microsoft Advertising identifier of the customer that contains the customer list. 

**Add:** Optional  
**Update:** Read-only. You cannot change the parent ID.  
**Delete:** Read-only  

## <a name="scope"></a>Scope
Scope defines what accounts can use this customer list. For a customer list the only supported scope is *Customer*, and the customer list can be associated with any campaigns and ad groups across all of the customer's accounts.  

**Add:** Required  
**Update:** Read-only. You cannot change the scope.    
**Delete:** Read-only  

## <a name="status"></a>Status
The customer list status.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Read-only    
**Delete:** Required. The Status must be set to *Deleted*.

## <a name="supportedcampaigntypes"></a>Supported Campaign Types
The semicolon delimited list of campaign types that support this customer list.

Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.

**Add:** Read-only  
**Update:** Read-only    
**Delete:** Read-only
