---
title: "Campaign Negative Custom Audience Association Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Negative Custom Audience Association fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Negative Custom Audience Association Record - Bulk
Defines a Campaign Negative Custom Audience Association that can be uploaded and downloaded in a bulk file. 

Audience targets cannot be set both campaign and ad group level. If you set any biddable campaign level audience criteria, then you cannot set any biddable ad group level audience criteria. Audience exclusions can be set at both campaign and ad group level. Microsoft Advertising applies a union of both campaign and ad group level exclusions.

> [!NOTE]
> Not everyone has the campaign level audience targets feature yet. If you don't, don't worry. It's coming soon.

You can download all *Campaign Negative Custom Audience Association* records in the account by including the [DownloadEntity](downloadentity.md) value of *CampaignNegativeCustomAudienceAssociations* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new Campaign Negative Custom Audience Association if a valid [Parent Id](#parentid) value is provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Campaign,Client Id,Modified Time,Bid Adjustment,Name,Audience Id,Audience
Format Version,,,,,,,,,6.0,,
Campaign Negative Custom Audience Association,Paused,,-1111,,,ClientIdGoesHere,,,,CustomAudienceIdHere,My Custom Audience
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkCampaignNegativeCustomAudienceAssociation* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignNegativeCustomAudienceAssociation
var bulkCampaignNegativeCustomAudienceAssociation = new BulkCampaignNegativeCustomAudienceAssociation
{
    // 'Campaign' column header in the Bulk file
    CampaignName = null,

    // Map properties in the Bulk file to the 
    // NegativeCampaignCriterion object of the Campaign Management service.
    NegativeCampaignCriterion = new NegativeCampaignCriterion
    {
        // 'Parent Id' column header in the Bulk file
        CampaignId = campaignIdKey,
        Criterion = new AudienceCriterion
        {
            // 'Audience Id' column header in the Bulk file
            AudienceId = customAudienceIdKey,
        },
        // 'Id' column header in the Bulk file
        Id = null,
        // 'Status' column header in the Bulk file
        Status = CampaignCriterionStatus.Paused
    },
    // 'Campaign' column header in the Bulk file
    CampaignName = null,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
    // 'Audience' column header in the Bulk file
    AudienceName = null,
};

uploadEntities.Add(bulkCampaignNegativeCustomAudienceAssociation);

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

For an *Campaign Negative Custom Audience Association* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Audience](#audience)
- [Audience Id](#audienceid)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Status](#status)


## <a name="audience"></a>Audience
The name of the custom audience.

This bulk field maps to the *Audience* field of the [Custom Audience](custom-audience.md) record.

**Add:** Read-only and Required for some use cases. You must either specify the [Audience](#audience) or [Audience Id](#audienceid) field. If you are adding new Campaign Negative Custom Audience Associations with new custom audiences in the same Bulk file, and if you do not set the [Audience Id](#audienceid) field, then this [Audience](#audience) field must be set as a logical key to the same value as the *Audience* field of the [Custom Audience](custom-audience.md) record. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="audienceid"></a>Audience Id
The Microsoft Advertising identifier of the custom audience associated with the campaign.

This bulk field maps to the *Id* field of the [Custom Audience](custom-audience.md) record.

**Add:** Read-only and Required for some use cases. You must either specify the [Audience](#audience) or [Audience Id](#audienceid) field. If you set the [Audience Id](#audienceid) field, you must either specify an existing custom audience identifier or specify a negative identifier that is equal to the *Id* field of the parent [Custom Audience](custom-audience.md) record. If the [Audience Id](#audienceid) field is not set, then you must set the [Audience](#audience) field as a logical key to the same value as the *Audience* field of the [Custom Audience](custom-audience.md) record. Any of these options are recommended if you are adding new Campaign Negative Custom Audience Associations with new custom audiences in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only    
**Delete:** Read-only  

## <a name="campaign"></a>Campaign
The name of the campaign that is associated with the custom audience.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Campaign](#campaign) field. 

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

## <a name="id"></a>Id
The system generated identifier for the association between a campaign and custom audience.

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
The system generated identifier of the campaign that is associated to the custom audience.

This bulk field maps to the *Id* field of the [Campaign](campaign.md) record.

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](campaign.md) record. This is recommended if you are associating custom audiences to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](../bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the [Parent Id](#parentid) or [Campaign](#campaign) field.

## <a name="status"></a>Status
The association status. 

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The default status value is *Active*.   
**Update:** Optional    
**Delete:** Required. The Status must be set to *Deleted*.

