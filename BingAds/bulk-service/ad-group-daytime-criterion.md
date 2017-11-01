---
title: "Ad Group DayTime Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group DayTime Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group DayTime Criterion Record - Bulk
Defines an ad group day and time criterion that can be uploaded and downloaded in a bulk file.

As your campaign progresses, you may find that your click-through rate and conversion rate are highest during certain times, for example, weeknights. This might be a perfect opportunity to use bid adjustments to improve your chances of displaying your ad Monday through Friday from 6:00 P.M. to 11:00 P.M.. When targeting by time, you are targeting the searcher's local time zone. For example, if you increase your bid by 10% for 6:00 P.M. to 11:00 P.M., that bid adjustment will be effective from 6:00 P.M. to 11:00 P.M. Eastern Time for searchers in New York, then be effective 6:00 P.M. to 11:00 P.M. Pacific Time for searchers in Seattle. Now you are showing your ads when your potential customers are online!

Each day and time criterion defines the day, from hour, from minute, to hour, and to minute requirements for the accompanying criterion bid adjustment. 

The maximum number of day and time criterions that you can specify per campaign or ad group is 49. You may not specify any overlapping day and time ranges, for example Monday from 3:00AM to 5:00AM and Monday 4:00AM to 6:00AM are not allowed for the same campaign or ad group. Also for a given campaign or ad group, the maximum number of day and time criterions per day that you can specify is seven. For example you can specify up to 7 day and time criterions where the *Day* is set to Monday.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group DayTime Criterion* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [From Hour](#fromhour)
- [From Minute](#fromminute)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)
- [Target](#target)
- [To Hour](#tohour)
- [To Minute](#tominute)

You can download all fields of the *Ad Group DayTime Criterion* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *AdGroupTargetCriterions* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](~/guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group day and time criterion if a valid ad group identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Target,Bid Adjustment,Name,OS Names,Radius,Unit,From Hour,From Minute,To Hour,To Minute,Latitude,Longitude
Format Version,,,,,,,,,,,5,,,,,,,,,
Ad Group DayTime Criterion,Active,,-1111,,,,ClientIdGoesHere,,Monday,20,,,,,0,0,4,0,,
```

If you are using the [Bing Ads SDKs](~/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupDayTimeCriterion* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupDayTimeCriterion
var bulkAdGroupDayTimeCriterion = new BulkAdGroupDayTimeCriterion
{
    // 'Ad Group' column header in the Bulk file is read-only
    AdGroupName = null,
                    
    // 'Campaign' column header in the Bulk file is read-only
    CampaignName = null,

    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // BiddableAdGroupCriterion object of the Campaign Management service.

    AdGroupCriterion = new BiddableAdGroupCriterion
    {
        // 'Parent Id' column header in the Bulk file
        AdGroupId = adGroupIdKey,
                        
        Criterion = new DayTimeCriterion
        {
            // 'Target' column header in the Bulk file
            Day = Day.Monday,

            // 'From Hour' column header in the Bulk file
            FromHour = 0,

            // 'To Hour' column header in the Bulk file
            ToHour = 4,

            // 'From Minute' column header in the Bulk file
            FromMinute = Minute.Zero,

            // 'To Minute' column header in the Bulk file
            ToMinute = Minute.Zero
        },

        CriterionBid = new BidMultiplier
        {
            // 'Bid Adjustment' column header in the Bulk file
            Multiplier = 20,
        },

        // 'Id' column header in the Bulk file
        Id = null,

        // 'Status' column header in the Bulk file
        Status = AdGroupCriterionStatus.Active,
    }
};

uploadEntities.Add(bulkAdGroupDayTimeCriterion);

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

### <a name="bidadjustment"></a>Bid Adjustment
The percentage amount that you want to adjust the bid for the corresponding *Target*, *From Hour*, *From Minute*, *To Hour*, and *To Minute*.

Supported values are negative ninety (-90) through positive nine hundred (900). 

**Add:** Optional. The bid adjustment will be set to the default of *0* if not included.  
**Update:** Required  
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

### <a name="fromhour"></a>From Hour
The starting hour to target.

Supported values range from 0 to 23.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="fromminute"></a>From Minute
The starting minute to target.

Supported values are *Zero*, *Fifteen*, *Thirty*, and *FortyFive*.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

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
	
This bulk field maps to the *Id* field of the [Ad Group](../bulk-service/ad-group.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](../bulk-service/ad-group.md) record. This is recommended if you are adding new criterions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

### <a name="status"></a>Status
Represents the association status between the ad group and the criterion bid. If the criterion bid is set for the ad group, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific day and time criterion bid, you must upload the *Status*, *Id*, and *Parent Id*.

### <a name="target"></a>Target
The day that you want to target with the corresponding *Bid Adjustment*. 

Supported values are *Sunday*, *Monday*, *Tuesday*, *Wednesday*, *Thursday*, *Friday*, and *Saturday*. 

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="tohour"></a>To Hour
The ending hour to target.

Supported values range from 0 to 23.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  

### <a name="tominute"></a>To Minute
The ending minute to target.

Supported values are *Zero*, *Fifteen*, *Thirty*, and *FortyFive*.

**Add:** Required  
**Update:** Required  
**Delete:** Read-only  
