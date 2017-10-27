---
title: "Campaign Product Scope Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
ms.date: 11/01/2017
author: "eric-urban"
ms.author: "eur"
description: Describes the Campaign Product Scope fields in a Bulk file.
dev_langs:
  - csharp
---
# Campaign Product Scope Record - Bulk
Defines a campaign's set of product conditions that can be uploaded and downloaded in a bulk file.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Campaign Product Scope* record, the following attribute fields are available in the [Bulk File Schema](../bulk-service/bulk-file-schema.md). 

- [Campaign](#campaign)
- [Client Id](#clientid)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Product Condition 1](#productcondition1)
- [Product Condition 2](#productcondition2)
- [Product Condition 3](#productcondition3)
- [Product Condition 4](#productcondition4)
- [Product Condition 5](#productcondition5)
- [Product Condition 6](#productcondition6)
- [Product Condition 7](#productcondition7)
- [Product Value 1](#productvalue1)
- [Product Value 2](#productvalue2)
- [Product Value 3](#productvalue3)
- [Product Value 4](#productvalue4)
- [Product Value 5](#productvalue5)
- [Product Value 6](#productvalue6)
- [Product Value 7](#productvalue7)
- [Status](#status)

You can download all fields of the *Campaign Product Scope* record by including the [DownloadEntity](../bulk-service/downloadentity.md) value of *CampaignProductScopes* in the [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk-service/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](~/guides/bulk-download-upload.md).

The following Bulk CSV example would add a new campaign product scope given a valid campaign ID (*Parent Id*). 

```csv
Type,Status,Id,Parent Id,Sub Type,Campaign,Ad Group,Client Id,Modified Time,Bid,Name,Product Condition 1,Product Value 1,Product Condition 2,Product Value 2,Product Condition 3,Product Value 3,Product Condition 4,Product Value 4,Product Condition 5,Product Value 5,Product Condition 6,Product Value 6,Product Condition 7,Product Value 7,Is Excluded,Parent Criterion Id,Tracking Template,Custom Parameter
Format Version,,,,,,,,,,5,,,,,,,,,,,,,,,,,,
Campaign Product Scope,Active,,-113,,,,ClientIdGoesHere,,,,Condition,New,CustomLabel0,MerchantDefinedCustomLabel,,,,,,,,,,,,,,
```

If you are using the [Bing Ads SDKs](~/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkCampaignProductScope* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkCampaignProductScope
var bulkCampaignProductScope = new BulkCampaignProductScope
{
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
                
    // Map properties in the Bulk file to the 
    // SharedEntityAssociation object of the Campaign Management service.
    CampaignCriterion = new CampaignCriterion
    {
        // 'Parent Id' column header in the Bulk file
        CampaignId = campaignIdKey,
        Criterion = new ProductScope
        {
            // Conditions are mapped to Product Value 1..7 and Product Condition 1..7 columns
            Conditions = new []
            {
                new ProductCondition
                {
                    // 'Product Value 1' column header in the Bulk file
                    Attribute = "New",
                    // 'Product Condition 1' column header in the Bulk file
                    Operand = "Condition",
                },
                new ProductCondition
                {
                    // 'Product Value 2' column header in the Bulk file
                    Attribute = "MerchantDefinedCustomLabel",
                    // 'Product Condition 2' column header in the Bulk file
                    Operand = "CustomLabel0",
                },
            },
        },
        // 'Id' column header in the Bulk file
        Id = null,
    },

    // 'Campaign' column header in the Bulk file
    CampaignName = null,
    // 'Status' column header in the Bulk file
    Status = Status.Active
};

uploadEntities.Add(bulkCampaignProductScope);

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
The name of the campaign that contains product scope.

**Add:** Read-only and Required  
**Update:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Campaign* field.

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Update:** Optional    
**Delete:** Read-only  

### <a name="id"></a>Id
The system generated identifier of the product scope.

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
The system generated identifier of the campaign that contains the product scope.

This bulk field maps to the *Id* field of the [Campaign](../bulk-service/campaign.md) record.

**Add:** Read-only and Required. You must either specify an existing campaign identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Campaign](../bulk-service/campaign.md) record. This is recommended if you are adding new product scopes to a new campaign in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk-service/bulk-file-schema.md#referencekeys).  
**Update:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add, update, and delete, you must specify either the *Parent Id* or *Campaign* field.

### <a name="productcondition1"></a>Product Condition 1
The condition’s operand. The operands implicitly include the equal operator. For example, you can read *Brand* as *Brand=*.

> [!NOTE]
> For add and update, at least one product condition and value pair are required, and the index number has no relevance. For example you can specify valid values for *Product Condition 2* and *Product Value 2* and leave the remaining condition and value fields empty.

**Add:** Optional  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product scope and add a new one.    
**Delete:** Read-only  

### <a name="productcondition2"></a>Product Condition 2
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productcondition3"></a>Product Condition 3
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productcondition4"></a>Product Condition 4
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productcondition5"></a>Product Condition 5
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productcondition6"></a>Product Condition 6
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productcondition7"></a>Product Condition 7
Supports the same values and rules as [Product Condition 1](#productcondition1).

### <a name="productvalue1"></a>Product Value 1
The condition’s attribute value.

An attribute’s value must exactly match the value specified in the customer’s Bing Merchant Center catalog file.

For available condition and value settings, see [Bing Shopping Product Conditions](~/guides/product-ads.md#conditions).

**Add:** Required  
**Update:** Read-only. You cannot update the condition or value fields. To update the conditions you must delete the product scope and add a new one.    
**Delete:** Read-only  

### <a name="productvalue2"></a>Product Value 2
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="productvalue3"></a>Product Value 3
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="productvalue4"></a>Product Value 4
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="productvalue5"></a>Product Value 5
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="productvalue6"></a>Product Value 6
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="productvalue7"></a>Product Value 7
Supports the same values and rules as [Product Value 1](#productvalue1).

### <a name="status"></a>Status
The status of the product scope.

Possible values are *Active* or *Deleted*. 

**Add:** Optional. The only possible status is *Active*. If you set the status to *Deleted* it will be ignored and the returned record will have status set to *Active*.  
**Update:** Optional    
**Delete:** Required. The Status must be set to *Deleted*.

