---
title: "Campaign Job Function Criterion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Job Function Criterion fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Job Function Criterion Record - Bulk
Defines an campaign job function criterion that can be uploaded and downloaded in a bulk file. 

You can target people in a specific job function according to LinkedIn by setting the [Profile Id](#profileid). 

Microsoft Advertising applies a union of both campaign and ad group level profile criterions. However, if you apply a criterion with the same profile ID e.g., target or exclude the same company name at both the campaign and ad group level, then the ad group level criterion will override the campaign level criterion. 

> [!TIP]
> For an overview of how to use target criterions, see [Show Ads to Your Target Audience](../guides/show-ads-target-audience.md).

You can download all *Campaign Job Function Criterion* records in the account by including the [DownloadEntity](downloadentity.md) value of *CampaignTargetCriterions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new campaign job function criterion if a valid [Parent Id](#parentid) value is provided. 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Campaign,Client Id,Modified Time,Bid Adjustment,Name,Profile Id,
Format Version,,,,,,,,,,6.0,,
Campaign Job Function Criterion,Active,,-1111,,,,ClientIdGoesHere,,20,,ProfileIdGoesHere,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkCampaignJobFunctionCriterion* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignJobFunctionCriterion
var bulkCampaignJobFunctionCriterion = new BulkCampaignJobFunctionCriterion
{
    // 'Campaign' column header in the Bulk file is read-only
    CampaignName = null,

    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // 'Profile' column header in the Bulk file is read-only
    ProfileName = null,

    // Map properties in the Bulk file to the 
    // BiddableCampaignCriterion object of the Campaign Management service.

    BiddableCampaignCriterion = new BiddableCampaignCriterion
    {
        // 'Parent Id' column header in the Bulk file
        CampaignId = campaignIdKey,

        Criterion = new ProfileCriterion
        {
            // 'Profile Id' column header in the Bulk file
            ProfileId = 0,

            // Maps to the 'Campaign Job Function Criterion' record name in the Bulk file
            ProfileType = ProfileType.JobFunction
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

uploadEntities.Add(bulkCampaignJobFunctionCriterion);

var entityUploadParameters = new EntityUploadParameters
{
    Entities = uploadEntities,
    ResponseMode = ResponseMode.ErrorsAndResults,
    ResultFileDirectory = FileDirectory,
    ResultFileName = DownloadFileName,
    OverwriteResultFile = true,
};

var uploadResultEntities = (await BulkServiceManager.UploadEntitiesAsync(entityUploadParameters)).ToList();
```

For a *Campaign Job Function Criterion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Bid Adjustment](#bidadjustment)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Profile](#profile)
- [Profile Id](#profileid)
- [Status](#status)

## <a name="bidadjustment"></a>Bid Adjustment
The percentage amount that you want to adjust the bid for the corresponding [Profile Id](#profileid). 

Supported values are negative ninety (-90) through positive nine hundred (900). 

> [!NOTE]
> If the campaign uses MaxClicks, MaxConversions, or TargetCpa bid strategy types, then the multiplier will inform rather than directly modify or override the automated bid. For auto bidding the multiplier is used as a weighted percentage to inform Microsoft Advertising about how much you value the criterion relative to other criteria. For example, a -50% bid multiplier for a mobile device criterion with the Max Conversions bid strategy to indicate that you value conversions from mobile traffic half as much as other device types. The same bid multiplier with the Max Clicks bid strategy would indicate that you value clicks on mobile half as much as other device types.
> Additionally, if the campaign uses MaxClicks, MaxConversions, or TargetCpa bid strategy types, the valid range of values that you can use to inform auto bidding is -100.00 through 30.00.

**Add:** Optional. The bid adjustment will be set to the default of *0* if not included.  
**Update:** Required  
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign where this criterion is applied or removed.

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Optional  

## <a name="id"></a>Id
The Microsoft Advertising unique identifier of the criterion.

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

## <a name="parentid"></a>Parent Id
The identifier of the campaign where this criterion is applied or removed.
	
This bulk field maps to the *Id* field of the [Campaign](campaign.md) record. 

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are adding new criterions to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

## <a name="profile"></a>Profile
The display name of the audience profile in English. 

**Add:** Read-only  
**Update:** Read-only  
**Delete:** Read-only  

## <a name="profileid"></a>Profile Id
The identifier of the audience profile that you want to target with the corresponding *Bid Adjustment*. 

**Add:** Required  
**Update:** Required  
**Delete:** Required  

## <a name="status"></a>Status
Represents the association status between the campaign and the criterion. If the criterion is applied to the campaign, this field's value is *Active*. To delete the criterion, set the status to *Deleted*.

**Add:** Read-only. The status will always be set to *Active* when you add criterions. If you upload another value e.g., *Foo* the result file will contain the same value although the criterion is active.  
**Update:** Optional  
**Delete:** Required. The Status must be set to *Deleted*. To delete a specific job function criterion, you must upload the [Status](#status), [Id](#id), and [Parent Id](#parentid).

