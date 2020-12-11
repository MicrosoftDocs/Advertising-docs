---
title: "Customer List Item Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Describes the Customer List Item fields in a Bulk file.
dev_langs:
  - csharp
---
# Customer List Item Record - Bulk
Defines a customer list item that can be uploaded in a bulk file. 

> [!NOTE]
> Bulk download of customer list items is not supported. 

> [!NOTE]
> Customer lists are available for customers in the feature pilot ([GetCustomerPilotFeatures](../customer-management-service/getcustomerpilotfeatures.md) returns 579).  

> [!IMPORTANT]
> Before you can upload customer list data via Bulk API, you must first create one customer list audience and accept the terms and conditions in the Microsoft Advertising UI. The initial customer list doesn't need to contain any customer data, but you must click I ACCEPT. By clicking "I accept" you (1) agree that you are able to lawfully disclose audience details, which is personal data, to Microsoft and (2) accept the Customer Match Terms, the Microsoft Advertising Agreement, and the Microsoft Advertising policies. Microsoft will use the data that you upload in accordance with the [Customer Match Terms](https://go.microsoft.com/fwlink/?linkid=2106709).

A customer list is a set of customer contact information that you have compiled to enable customer match. Each list can include multiple Email and CRMID items. 
- Include the [Customer List](customer-list.md) record in the Bulk upload file and set its [Action Type](customer-list.md#actiontype) field to "Add", "Remove", or "Replace". 
- Include one or more [Customer List Item](customer-list-item.md) records in the same Bulk upload file and set the [Parent Id](customer-list-item.md#parentid), [Sub Type](customer-list-item.md#subtype), and [Text](customer-list-item.md#text) fields. 

You can add or update a [Customer List](customer-list.md) record without any [Customer List Item](customer-list-item.md) records in the same Bulk upload file; however, you cannot upload any [Customer List Item](customer-list-item.md) records without the accompanying parent [Customer List](customer-list.md) record. 

After 48 hours, check the Audience Size fields e.g., [Audience Search Size](customer-list.md#audiencesearchsize) to see how many of these customers we matched on the Bing Network. At that point, your ads can start showing for this new audience.

> [!TIP]
> For an overview and more information about audiences, see the [Audience APIs](../guides/universal-event-tracking.md#audience) technical guide. 

You can download all *Customer List Item* records in the account by including the [DownloadEntity](downloadentity.md) value of *CustomerLists* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new customer list item. 

```csv
Type,Status,Id,Parent Id,Client Id,Modified Time,Name,Description,Scope,Audience,Action Type,Sub Type,Text
Format Version,,,,,,6.0,,,,,,
Customer List,Active,-10,,ClientIdGoesHere,,,New customer list description,Customer,New Customer List,Add,,
Customer List Item,,,-10,ClientIdGoesHere,,,,,,,CRMID,ABCD123457
```

For a *Customer List Item* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Audience](#audience)
- [Client Id](#clientid)
- [Parent Id](#parentid)
- [Sub Type](#subtype)
- [Text](#text)

## <a name="audience"></a>Audience
The name of the parent customer list audience.

The name can contain a maximum of 128 characters. 

**Add:** Required. You must specify either the [Parent Id](#parentid) or [Audience](#audience) field.  
**Delete:** Required. You must specify either the [Parent Id](#parentid) or [Audience](#audience) field.   

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Delete:** Optional  

## <a name="parentid"></a>Parent Id
The identifier of the parent customer list audience.

**Add:** Required. You must specify either the [Parent Id](#parentid) or [Audience](#audience) field.  
**Delete:** Required. You must specify either the [Parent Id](#parentid) or [Audience](#audience) field.  

## <a name="subtype"></a>Sub Type
Determines whether the [Text](#text) field represents a CRMID or hashed Email value. 

Supported values are "CRMID" and "Email". 

**Add:** Required  
**Delete:** Required 

## <a name="text"></a>Text
The CRMID or hashed Email as text. 

If the [Sub Type](#subtype) is "CRMID", this field must contain the CRMID value as plain text up to 100 characters in length. 

If the [Sub Type](#subtype) is "Email", this field cannot contain plain text. The string must be hashed using the SHA-256 algorithm. The hashed Email must be a hexadecimal string of length 64. For example, you must upload a hashed string such as "9180e8ed3ef35bca79a39be7ad1f392e45cc4fc12a1f747df7a35af28f7eb93f" instead of "test@contoso.com". 

**Add:** Required  
**Delete:** Required  
