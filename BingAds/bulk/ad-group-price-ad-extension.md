---
title: "Ad Group Price Ad Extension"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
dev_langs:
  - csharp
---
# Ad Group Price Ad Extension
Defines an association record between an [Ad Group](../bulk/ad-group.md) and a [Price Ad Extension](../bulk/price-ad-extension.md) that can be uploaded and downloaded in a bulk file. To upload or download the ad group or Price Ad Extension, use the [Ad Group](../bulk/ad-group.md) or [Price Ad Extension](../bulk/price-ad-extension.md) record.

> [!NOTE]
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.
	
## <a name="entitydata"></a>Attribute Fields in the Bulk File
For an *Ad Group Price Ad Extension* record, the following attribute fields are available in the [Bulk File Schema](../bulk/bulk-file-schema.md). 

- [Ad Group](#adgroup)
- [Campaign](#campaign)
- [Client Id](#clientid)
- [Editorial Location](#editoriallocation)
- [Editorial Reason Code](#editorialreasoncode)
- [Editorial Status](#editorialstatus)
- [Editorial Term](#editorialterm)
- [Id](#id)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Publisher Countries](#publishercountries)
- [Status](#status)

You can download all fields of the *Ad Group Price Ad Extension* record by including the [DownloadEntity](../bulk/downloadentity.md) value of *AdGroupPriceAdExtensions* in the [DownloadCampaignsByAccountIds](../bulk/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk/downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](../bulk/datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](~/guides/bulk-download-upload.md).

The following Bulk CSV example would associate a price ad extension to an ad group if the valid *Id* and *Parent Id* are provided. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Name
Format Version,,,,,,,,5
Ad Group Price Ad Extension,Active,-11,-1111,,,ClientIdGoesHere,,
```

If you are using the [Bing Ads SDKs](~/guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to upload and download the *BulkAdGroupPriceAdExtension* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkAdGroupPriceAdExtension
var bulkAdGroupPriceAdExtension = new BulkAdGroupPriceAdExtension
{
    // Map properties in the Bulk file to the 
    // AdExtensionIdToEntityIdAssociation object of the Campaign Management service.
    AdExtensionIdToEntityIdAssociation = new AdExtensionIdToEntityIdAssociation
    {
        // 'Id' column header in the Bulk file
        AdExtensionId = priceAdExtensionIdKey,
        // 'Parent Id' column header in the Bulk file
        EntityId = adGroupIdKey,
    },
                
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
    // 'Status' column header in the Bulk file
    Status = Status.Active,
};

uploadEntities.Add(bulkAdGroupPriceAdExtension);

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
The name of the ad group where this ad extension is associated or removed.  

**Add:** Read-only and Required  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="campaign"></a>Campaign
The name of the campaign that contains the ad group where this ad extension is associated or removed.

**Add:** Read-only  
**Delete:** Read-only  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  
**Delete:** Read-only  

### <a name="editoriallocation"></a>Editorial Location
The component or property of the ad extension that failed editorial review. 

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialreasoncode"></a>Editorial Reason Code
A code that identifies the reason for the failure. For a list of possible reason codes, see [Editorial Failure Reason Codes](~/guides/editorial-failure-reason-codes.md). 

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialstatus"></a>Editorial Status
The editorial status of the ad extension.

Possible values include *Active*, *ActiveLimited*, *Disapproved*, and *Inactive*. For more details, see [AdExtensionEditorialStatus Value Set](~/campaign-management/adextensioneditorialstatus.md).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="editorialterm"></a>Editorial Term
The term that failed editorial review.

This field will not be set if a combination of terms caused the failure or if the failure was based on a policy violation.

**Add:** Read-only  
**Delete:** Read-only  

### <a name="id"></a>Id
The identifier of the ad extension that is associated or removed from the ad group.

This bulk field maps to the *Id* field of the [Price Ad Extension](../bulk/price-ad-extension.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad extension identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Price Ad Extension](../bulk/price-ad-extension.md) record. This is recommended if you are adding new ad extensions and associations in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="parentid"></a>Parent Id
The identifier of the ad group where this ad extension is associated or removed.
	
This bulk field maps to the *Id* field of the [Ad Group](../bulk/ad-group.md) record. 

**Add:** Read-only and Required. You must either specify an existing ad group identifier, or specify a negative identifier that is equal to the *Id* field of the parent [Ad Group](../bulk/ad-group.md) record. This is recommended if you are associating ad extensions to a new ad group in the same Bulk file. For more information, see [Bulk File Schema Reference Keys](~/bulk/bulk-file-schema.md#referencekeys).  
**Delete:** Read-only and Required  

> [!NOTE]
> For add and delete, you must specify either the *Parent Id* or both of the *Ad Group* and *Campaign* fields. 

### <a name="publishercountries"></a>Publisher Countries
The list of publisher countries whose editorial guidelines do not allow the specified [term](#editorialterm).

In a bulk file, the list of publisher countries are delimited with a semicolon (;).

**Add:** Read-only  
**Delete:** Read-only  

### <a name="status"></a>Status
Represents the association status between the ad group and the ad extension. 

Possible values are *Active* and *Deleted*. If the ad extension is associated with the ad group, this field's value is *Active*.

**Add:** Read-only  
**Delete:** Required. The Status must be set to *Deleted*. 
	
## <a name="entityperformancedata"></a>Performance Data Fields in the Bulk File
If the [DataScope Value Set](../bulk/datascope.md) element of the download request includes *EntityPerformanceData*, the download file will also include the following fields in this record.

|Column Header|Description|
|-----------------|---------------|
|*Spend*|The cost per click (CPC) summed for each click.|
|*Impressions*|The number of times an ad has been displayed on search results pages. Without impressions there are no clicks or conversions.|
|*Clicks*|The number of times that the ads in the account were clicked.|
|*CTR*|The click-through rate (CTR) is the number of times an ad was clicked, divided by the number of times the ad was shown (impressions). For example, if your ads got 50 clicks given 2,348 impressions, your CTR is 2.13 (%).

The formula for calculating CTR is *(Clicks / Impressions) * 100*.|
|*Avg CPC*|The average cost per click (CPC). The total cost of all clicks on an ad divided by the number of clicks. This is the average amount you're actually charged each time your ad is clicked. For example, if you paid a total of 48.35 for 300 clicks, your average CPC is 0.16.

The formula for calculating the average CPC is *(Spend /Clicks)*.|
|*Avg CPM*|The average of the cost-per-thousand impressions of the ads.

The value will be 0 (zero) if the corresponding ad groups do not specify the Content ad distribution medium.|
|*Avg position*|The average position of the ad on a webpage.|
|*Conversions*|The number of conversions. A conversion is the completion of an action by a customer after viewing your ad. The action could be purchasing your product, registering for your webinar, joining an organization, or whatever you consider your goal and best measure of the ad's success.|
|*CPA*|The cost per conversion. The formula for calculating the cost per conversion is *(Spend / Conversions)*.

Only ads in campaigns that enable conversion tracking contribute to the conversion number, so unless all campaigns in the account enable conversion tracking, the number will not be accurate.|
