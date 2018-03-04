---
title: "Ad Group Negative Location Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group Negative Location Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group Negative Location Criterion Record - Bulk
Defines an ad group negative location criterion that can be uploaded and downloaded in a bulk file.

Although location criterions are most often used to designate the specific locations where you want to show your ads, Bing Ads also lets you specify locations you want to exclude from seeing your ads.

Each negative location criterion defines a location code where you do not want your ads to show. 

The maximum number of combined location and negative location criterions that you can specify per campaign or ad group is 10,000. 

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group Negative Location Criterion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)
- [Sub Type](#subtype)
- [Target](#target)

You can download all fields of the *Ad Group Negative Location Criterion* record by including the [DownloadEntity](downloadentity.md) value of *AdGroupTargetCriterions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group negative location criterion if a valid ad group identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Target,Bid Adjustment,Name,OS Names,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,5,,,,,,,,,
Ad Group Negative Location Criterion,Active,,-1111,PostalCode,,,ClientIdGoesHere,,79381,,,,,,,,,,,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupNegativeLocationCriterion* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupNegativeLocationCriterion
var bulkAdGroupNegativeLocationCriterion = new BulkAdGroupNegativeLocationCriterion
{
    // 'Ad Group' column header in the Bulk file is read-only
    AdGroupName = null,

    // 'Campaign' column header in the Bulk file is read-only
    CampaignName = null,

    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // BiddableAdGroupCriterion object of the Campaign Management service.

    AdGroupCriterion = new NegativeAdGroupCriterion
    {
        // 'Parent Id' column header in the Bulk file
        AdGroupId = adGroupIdKey,

        Criterion = new LocationCriterion
        {
            // 'Target' column header in the Bulk file
            LocationId = 79381,

            // 'Sub Type' column header in the Bulk file
            LocationType = "PostalCode"
        },

        // 'Id' column header in the Bulk file
        Id = null,

        // 'Status' column header in the Bulk file
        Status = AdGroupCriterionStatus.Active,
    }
};

uploadEntities.Add(bulkAdGroupNegativeLocationCriterion);

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
The name of the ad group where this criterion is applied or removed.  

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group where this criterion is applied or removed.

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
The identifier of the ad group where this criterion is applied or removed.
	
This bulk field maps to the *Id* field of the [Ad Group](ad-group.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](ad-group.md) record. This is recommended if you are adding new criterions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="status"></a>Status
Represents the association status between the ad group and the criterion bid. If the criterion bid is set for the ad group, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific negative location criterion, you must upload the *Status*, *Id*, and *Parent Id*. 

### <a name="subtype"></a>Sub Type
The location sub type that you are not targeting. For example the value is *City* if the record represents a city location criterion.

Possible values are *City*, *Country*, *County*, *MetroArea*, *PostalCode*, and *State*.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="target"></a>Target
The identifier of the location that you do not want to target. The location identifier corresponds to the *ID* field of the geographical locations file. For more information, see [Geographical Location Codes](../guides/geographical-location-codes.md) and [GetGeoLocationsFileUrl](../campaign-management-service/getgeolocationsfileurl.md).

**Add:** Required  
**Update:** Required  
**Delete:** Read-only    
