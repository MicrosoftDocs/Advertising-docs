---
title: "Ad Group Image Ad Extension Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group Image Ad Extension fields in a Bulk file.
dev_langs:
  - csharp
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Ad Group Image Ad Extension Record - Bulk
Defines an association record between an [Ad Group](ad-group.md) and a [Image Ad Extension](image-ad-extension.md) that can be uploaded and downloaded in a bulk file. To upload or download the ad group or image ad extension, use the [Ad Group](ad-group.md) or [Image Ad Extension](image-ad-extension.md) record.
	
## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group Image Ad Extension* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Status](#status)

You can download all fields of the *Ad Group Image Ad Extension* record by including the [DownloadEntity](downloadentity.md) value of *AdGroupImageAdExtensions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would associate an image ad extension to an ad group if the valid *Id* and *Parent Id* are provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Name
Format Version,,,,,,,,6
Ad Group Image Ad Extension,Active,-11,-1111,,,ClientIdGoesHere,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupImageAdExtension* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupImageAdExtension
var bulkAdGroupImageAdExtension = new BulkAdGroupImageAdExtension
{
    // Map properties in the Bulk file to the 
    // AdExtensionIdToEntityIdAssociation object of the Campaign Management service.
    AdExtensionIdToEntityIdAssociation = new AdExtensionIdToEntityIdAssociation
    {
        // 'Id' column header in the Bulk file
        AdExtensionId = imageAdExtensionIdKey,
        // 'Parent Id' column header in the Bulk file
        EntityId = adGroupIdKey,
    },
                
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
    // 'Status' column header in the Bulk file
    Status = Status.Active,
};

uploadEntities.Add(bulkAdGroupImageAdExtension);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkService.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

### <a name="adgroup"></a>Ad Group
The name of the ad group where this ad extension is associated or removed.  

**Add:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group where this ad extension is associated or removed.

**Add:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad extension that failed editorial review. 

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Reason Codes](../guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad extension.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdExtensionEditorialStatus Value Set](../campaign-management-service/adextensioneditorialstatus.md).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Delete:** Read-only  

### <a name="id"></a>Id
The identifier of the ad extension that is associated or removed from the ad group.

This bulk field maps to the *Id* field of the [Image Ad Extension](image-ad-extension.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad extension identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Image Ad Extension](image-ad-extension.md) record. This is recommended if you are adding new ad extensions and associations in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The identifier of the ad group where this ad extension is associated or removed.
	
This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are associating ad extensions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="status"></a>Status
Represents the association status between the ad group and the ad extension. 

Possible values are *Active* and *Deleted*. If the ad extension is associated with the ad group, this field's value is *Active*.

**Add:** Read-only  
**Delete:** Required. The Status must be set to *Deleted*. 
