---
title: "Ad Group Negative Job Function Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Ad Group Negative Job Function Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Ad Group Negative Job Function Criterion Record - Bulk
Defines an ad group negative job function criterion that can be uploaded and downloaded in a bulk file. 

You can exclude people in a specific job function according to LinkedIn by setting the [Profile Id](#profileid). 

> [!NOTE]
> Not everyone is enabled for Audience campaigns in the Microsoft Audience Network yet. If you don't, don't worry. It's coming soon. 

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group Negative Job Function Criterion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Profile](#profile)
- [Profile Id](#profileid)
- [Status](#status)

You can download all fields of the *Ad Group Negative Job Function Criterion* record by including the [DownloadEntity](downloadentity.md) value of *AdGroupTargetCriterions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new ad group negative job function criterion if a valid ad group identifier (*Parent Id*) is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Name,Profile Id,
Format Version,,,,,,,,,5,,
Ad Group Negative Job Function Criterion,Active,,-1111,,,,ClientIdGoesHere,,,ProfileIdGoesHere,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupNegativeJobFunctionCriterion* class (coming soon), instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupNegativeJobFunctionCriterion
var bulkAdGroupNegativeJobFunctionCriterion = new BulkAdGroupNegativeJobFunctionCriterion
{
    // 'Ad Group' column header in the Bulk file is read-only
    AdGroupName = null,

    // 'Campaign' column header in the Bulk file is read-only
    CampaignName = null,

    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // 'Profile' column header in the Bulk file is read-only
    ProfileName = null,

    // Map properties in the Bulk file to the 
    // NegativeAdGroupCriterion object of the Campaign Management service.

    NegativeAdGroupCriterion = new NegativeAdGroupCriterion
    {
        // 'Parent Id' column header in the Bulk file
        AdGroupId = adGroupIdKey,

        Criterion = new ProfileCriterion
        {
            // 'Profile Id' column header in the Bulk file
            ProfileId = 0,

            // Maps to the 'Ad Group Negative Job Function Criterion' record name in the Bulk file
            ProfileType = ProfileType.JobFunction
        },

        // 'Id' column header in the Bulk file
        Id = null,

        // 'Status' column header in the Bulk file
        Status = AdGroupCriterionStatus.Active,
    }
};

uploadEntities.Add(bulkAdGroupNegativeJobFunctionCriterion);

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

### <a name="profile"></a>Profile
The display name of the audience profile in English. 

To download profile display names in other languages you can call the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation via the Campaign Management API.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

### <a name="profileid"></a>Profile Id
The identifier of the audience profile that you want to exclude. 

To download profile identifiers call the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation via the Campaign Management API.

**Add:** Required  
**Update:** Required  
**Delete:** Required  

### <a name="status"></a>Status
Represents the association status between the ad group and the criterion. If the criterion is applied to the ad group, this field's value is *Active*, and otherwise the value is *Deleted*.

**Add:** Read-only  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific job function criterion, you must upload the *Status*, *Id*, and *Parent Id*.

