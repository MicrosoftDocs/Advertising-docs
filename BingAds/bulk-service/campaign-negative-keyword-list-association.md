---
title: "Campaign Negative Keyword List Association"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
dev_langs:
  - csharp
---
# Campaign Negative Keyword List Association
Defines an association record between a [Campaign](../bulk-service/campaign.md) and a [Negative Keyword List](../bulk-service/negative-keyword-list.md) that can be uploaded and downloaded in a bulk file. To upload or download the campaign or negative keyword list, use the [Campaign](../bulk-service/campaign.md) or [Negative Keyword List](../bulk-service/negative-keyword-list.md) record.
	
## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Campaign Negative Keyword List Association* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)

You can download all fields of the *Campaign Negative Keyword List Association* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *CampaignNegativeKeywordListAssociations* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](~/guides/bulk-download-upload.md).

The following Bulk CSV example would associate a negative keyword list to a campaign if the valid *Id* and *Parent Id* are provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Keyword,Match Type,Name
Format Version,,,,,,,,,,5
Campaign Negative Keyword List Association,Active,-19,-112,,,ClientIdGoesHere,,,,
```

If you are using the [Bing Ads SDKs](~/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignNegativeKeywordList* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignNegativeKeywordList
var bulkCampaignNegativeKeywordList = new BulkCampaignNegativeKeywordList
{
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // SharedEntityAssociation object of the Campaign Management service.
    SharedEntityAssociation = new SharedEntityAssociation
    {
        // 'Parent Id' column header in the Bulk file
        EntityId = campaignIdKey,
        // 'Id' column header in the Bulk file
        SharedEntityId = negativeKeywordListIdKey,
    },

    // 'Status' column header in the Bulk file
    Status = Status.Active
};

uploadEntities.Add(bulkCampaignNegativeKeywordList);

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
The name of the campaign where the negative keyword list is associated or removed.

**Add:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or *Campaign*.

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Delete:** Read-only  

### <a name="id"></a>Id
The identifier of the negative keyword list that is associated or removed from the campaign.

This bulk field maps to the *Id* field of the [Negative Keyword List](../bulk-service/negative-keyword-list.md) record. 

**Add:** Read-only and Required. You must either specify an existing negative keyword list identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Negative Keyword List](../bulk-service/negative-keyword-list.md) record. This is recommended if you are adding new negative keyword list and associating it with a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk-service/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The identifier of the campaign where this negative keyword list is associated or removed.
	
This bulk field maps to the *Id* field of the [Campaign](../bulk-service/campaign.md) record. 

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](../bulk-service/campaign.md) record. This is recommended if you are adding new negative keyword list and associating it with a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk-service/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or *Campaign*.

### <a name="status"></a>Status
Represents the association status between the campaign and the negative keyword list. If the negative keyword list is not associated with the campaign, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Delete:** Required. The Status must be set to *Deleted*. 
	
