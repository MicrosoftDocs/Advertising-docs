---
title: "Campaign DeviceOS Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign DeviceOS Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# Campaign DeviceOS Criterion Record - Bulk
Defines a campaign device OS criterion that can be uploaded and downloaded in a bulk file.

When you target by device, you choose to show ads to potential customers when they're using desktops and tablets or smartphones. 

Each device criterion defines a device name for the accompanying criterion bid adjustment. 

The maximum number of device criterions that you can specify per campaign or ad group is three. You must either have three separate criterions for *Computers*, *Smartphones*, and *Tablets*, otherwise no device criterions can exist for the campaign or ad group.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Campaign DeviceOS Criterion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)
- [Target](#target)

You can download all fields of the *Campaign DeviceOS Criterion* record by including the [DownloadEntity](downloadentity.md) value of *CampaignTargetCriterions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add three new campaign device criterions (one for each device type) if a valid campaign identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Bid Adjustment,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,6,,,,,,,,
Campaign DeviceOS Criterion,Active,,-111,,,ClientIdGoesHere,,Computers,20,,,,,,,,,
Campaign DeviceOS Criterion,,,-111,,,ClientIdGoesHere,,Smartphones,0,,,,,,,,,
Campaign DeviceOS Criterion,,,-111,,,ClientIdGoesHere,,Tablets,0,,,,,,,,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignDeviceOSCriterion* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

var bulkCampaignDeviceCriterions = new[] {
    // Map properties in the Bulk file to the BulkCampaignDeviceCriterion
    new BulkCampaignDeviceCriterion
    {
        // 'Campaign' column header in the Bulk file is read-only
        CampaignName = null,

        // 'Client Id' column header in the Bulk file
        ClientId = "ClientIdGoesHere",

        // Map properties in the Bulk file to the 
        // BiddableCampaignCriterion object of the Campaign Management service.

        CampaignCriterion = new BiddableCampaignCriterion
        {
            // 'Parent Id' column header in the Bulk file
            CampaignId = campaignIdKey,

            Criterion = new DeviceCriterion
            {
                // 'Target' column header in the Bulk file
                DeviceName = "Computers",
            },

            CriterionBid = new BidMultiplier
            {
                // 'Bid Adjustment' column header in the Bulk file
                Multiplier = 20,
            },

            // 'Id' column header in the Bulk file
            Id = null,

            // 'Status' column header in the Bulk file
            Status = CampaignCriterionStatus.Active,
        }
    },
    new BulkCampaignDeviceCriterion
    {
        ClientId = "ClientIdGoesHere",
        CampaignCriterion = new BiddableCampaignCriterion
        {
            CampaignId = campaignIdKey,
            Criterion = new DeviceCriterion
            {
                DeviceName = "Smartphones",
            },
            CriterionBid = new BidMultiplier
            {
                Multiplier = 0,
            },
        }
    },
    new BulkCampaignDeviceCriterion
    {
        ClientId = "ClientIdGoesHere",
        CampaignCriterion = new BiddableCampaignCriterion
        {
            CampaignId = campaignIdKey,
            Criterion = new DeviceCriterion
            {
                DeviceName = "Tablets",
            },
            CriterionBid = new BidMultiplier
            {
                Multiplier = 0,
            },
        }
    },
};

foreach (var bulkCampaignDeviceCriterion in bulkCampaignDeviceCriterions)
{
    uploadEntities.Add(bulkCampaignDeviceCriterion);
}

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

### <a name="bidadjustment"></a>Bid Adjustment
The percentage amount that you want to adjust the bid for the corresponding *Target*. 

Supported values are -100 (negative one hundred) through positive 900 (nine hundred) percent. Setting the bid adjustment to -100 percent will result in the exclusion of the corresponding *Target*.

**Add:** Optional. The bid adjustment will be set to the default of *0* if not included.  
**Update:** Required  
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign where this criterion is applied or removed.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Optional  

### <a name="id"></a>Id
The Bing Ads unique identifier of the criterion.

> [!NOTE] 
> Previously with Campaign Management API version 10 it was possible to associate one target identifier with multiple campaigns and ad groups using the AddTargetsToLibrary, SetTargetToCampaign, and SetTargetToAdGroup operations. After a campaign or ad group had been disassociated from the shared target, the criterion identifier would be set to *0* (zero) in the Bulk download or Bulk upload result file. 

**Add:** Read-only  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The identifier of the campaign where this criterion is applied or removed.
	
This bulk field maps to the *Id* field of the [Campaign](campaign.md) record. 

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are adding new criterions to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="status"></a>Status
Represents the association status between the campaign and the criterion bid. If the criterion bid is set for the campaign, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific device criterion bid, you must upload the *Status*, *Id*, and *Parent Id*.

### <a name="target"></a>Target
The name of the device that you want to target with the corresponding *Bid Adjustment*. 

Supported values are *Computers*, *Smartphones*, and *Tablets*.
  
**Add:** Required. Three separate bids for *Computers*, *Smartphones*, and *Tablets* should be specified together in the bulk file (each bid in a seperate record / row). If you do not add individual device criterions representing each of the three device types, no device criterions will be added for the campaign.  
**Update:** Required  
**Delete:** Read-only  
