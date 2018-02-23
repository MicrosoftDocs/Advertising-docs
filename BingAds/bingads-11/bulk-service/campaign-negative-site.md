---
title: "Campaign Negative Site Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Negative Site fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Negative Site Record - Bulk
Defines a negative site assigned to an campaign that can be uploaded and downloaded in a bulk file.

In the bulk schema each of the negative sites associated with an campaign are represented individually by their own row. For example if you have two negative sites, they are represented by two *Campaign Negative Site* records in the bulk file with *Status* set to Active. When uploading or downloading records for an updated list of associated negative sites, one record will have *Status* set to Deleted with an empty *Website* field. This indicates that some changes have been made to the list, and the *Campaign Negative Site* records that follow are active.

> [!NOTE]
> The *Campaign Negative Site* can be added and deleted, but cannot be updated.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Campaign Negative Site* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)
- [Website](#website)

You can download all fields of the *Campaign Negative Site* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *CampaignNegativeSites* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new campaign negative site given a valid campaign ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Website,Client Id,Modified Time,Name
Format Version,,,,,,,,,5
Campaign Negative Site,Active,,-112,,,contoso.com,ClientIdGoesHere,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignNegativeSite* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();
	
// Map properties in the Bulk file to the BulkCampaignNegativeSites
var bulkCampaignNegativeSites = new BulkCampaignNegativeSites
{
    // 'Campaign' column header in the Bulk file
    CampaignName = null,
                
    // Map properties in the Bulk file to the 
    // CampaignNegativeSites object of the Campaign Management service.
    CampaignNegativeSites = new CampaignNegativeSites
    {
        // 'Parent Id' column header in the Bulk file
        CampaignId = campaignIdKey,
        NegativeSites = new[]
        {
            // 'Website' column header in the Bulk file
            "contoso.com",
        }
    },

    // 'Status' column header in the Bulk file
    Status = Status.Active,
};

// BulkCampaignNegativeSites does not support 'Client Id' and
// replaces all negative sites for the campaign, whereas BulkCampaignNegativeSite
// enables you to add or delete one negative site at a time.

// Map properties in the Bulk file to the BulkCampaignNegativeSite
var bulkCampaignNegativeSite = new BulkCampaignNegativeSite
{
    // 'Parent Id' column header in the Bulk file
    CampaignId = campaignIdKey,
    // 'Campaign' column header in the Bulk file
    CampaignName = null,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
    // 'Status' column header in the Bulk file
    Status = Status.Active,
    // 'Website' column header in the Bulk file
    Website = "contoso.com",
};

uploadEntities.Add(bulkCampaignNegativeSite);

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

### <a name="campaign"></a>Campaign
The name of the campaign that contains the negative site.

**Add:** Read-only and Required  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or *Campaign* field.

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the negative site.

**Add:** Read-only  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The system generated identifier of the campaign that contains the negative site.

This bulk field maps to the *Id* field of the [Campaign](../bulk-service/campaign.md) record.

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](../bulk-service/campaign.md) record. This is recommended if you are adding new negative sites to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.  
**Delete:** Read-only  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or *Campaign* field.

### <a name="status"></a>Status
Represents the association status between the campaign and the negative site.

If the negative site is associated with the campaign, this  field's value is *Active*.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The default value is *Active*.  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.    
**Delete:**Required. The Status must be set to *Deleted*. To delete a specific negative site, you must upload the *Status*, *Parent Id*, and *Website*. To delete all negative sites for the campaign, you only need to upload the *Status* and *Parent Id* in a single record. Then optionally you can add new negative site records to replace the deleted set. 

### <a name="website"></a>Website


**Add:** Required  
**Update:** Not applicable. A negative site can be added and deleted, but cannot be updated.    
**Delete:** Read-only

