---
title: "Campaign Location Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Location Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Location Criterion Record - Bulk
Defines a campaign location criterion that can be uploaded and downloaded in a bulk file.

With location criterions, you can choose to show ads to potential customers in, searching for, or viewing pages about:
*  All available countries/regions
*  Selected cities, zip codes, metro areas, counties, states/provinces, and countries/regions

Each location criterion defines a location code for the accompanying criterion bid adjustment. 

The maximum number of combined location and negative location criterions that you can specify per campaign or ad group is 10,000.  

> [!NOTE]
> You can only have one [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md) record per campaign to determine the location intent option that applies for all of the campaign's [Campaign Location Criterion](../bulk-service/campaign-location-criterion.md) and [Campaign Radius Criterion](../bulk-service/campaign-radius-criterion.md) records. When you create the campaign's first criterion, a [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md) record will also be added automatically with the default *Target* set to *PeopleInOrSearchingForOrViewingPages*. You can add or update a campaign's [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md), whether or not the campaign has any other criterions. You cannot delete a campaign's [Campaign Location Intent Criterion](../bulk-service/campaign-location-intent-criterion.md), although it has no purpose without location or radius criterions. 

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *Campaign Location Criterion* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)
- [Sub Type](#subtype)
- [Target](#target)

You can download all fields of the *Campaign Location Criterion* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *CampaignTargetCriterions* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](/bingads/guides/bulk-download-upload.md).

The following Bulk CSV example would add a new campaign location criterion if a valid campaign identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Client Id,Modified Time,Target,Bid Adjustment,Name,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,5,,,,,,,,
Campaign Location Criterion,Active,,-111,Country,,ClientIdGoesHere,,190,20,,,,,,,,,
```

If you are using the [Bing Ads SDKs](/bingads/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignLocationCriterion* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignLocationCriterion
var bulkCampaignLocationCriterion = new BulkCampaignLocationCriterion
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

        Criterion = new LocationCriterion
        {
            // 'Target' column header in the Bulk file
            LocationId = 190,

            // 'Sub Type' column header in the Bulk file
            LocationType = "Country"
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
};

uploadEntities.Add(bulkCampaignLocationCriterion);

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

Supported values are negative ninety (-90) through positive nine hundred (900). 

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
The identifier of the a campaign where this criterion is applied or removed.
	
This bulk field maps to the *Id* field of the [Campaign](../bulk-service/campaign.md) record. 

**Add:** Read-only and Required. You must either specify an existing a campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](../bulk-service/campaign.md) record. This is recommended if you are adding new criterions to a new a campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](/bingads/bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="status"></a>Status
Represents the association status between the a campaign and the criterion bid. If the criterion bid is set for the a campaign, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific location criterion bid, you must upload the *Status*, *Id*, and *Parent Id*. 

### <a name="subtype"></a>Sub Type
The location sub type that you are targeting. For example the value is *City* if the record represents a city location criterion.

Possible values are *City*, *Country*, *County*, *MetroArea*, *PostalCode*, and *State*.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="target"></a>Target
The identifier of the location that you want to target with the corresponding *Bid Adjustment*. The location identifier corresponds to the *ID* field of the geographical locations file. For more information, see [Geographical Location Codes](/bingads/guides/geographical-location-codes.md) and [GetGeoLocationsFileUrl](/bingads/campaign-management-service/getgeolocationsfileurl.md).

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  
