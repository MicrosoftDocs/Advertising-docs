---
title: "In Market Audience Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the In Market Audience fields in a Bulk file.
dev_langs:
  - csharp
---
# In Market Audience Record - Bulk
Defines an in-market audience that can be downloaded in a bulk file. 

> [!NOTE]
> Bulk upload is not supported. You cannot add, update, or delete an in-market audience using the Bing Ads API. Having said that, you can add and delete ad group in-market audience associations and exclusions.

> [!NOTE]
> Not everyone has this feature yet. If you don’t, don’t worry. It’s coming soon.

> [!TIP]
> For an overview of in-market audiences see the [About in-market audiences](https://help.bingads.microsoft.com/#apex/3/en/56851/-1) help topic.

## <a name="entitydata"></a>Attribute Fields in the Bulk File
For a *In Market Audience* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Audience](#audience)
- [Audience Network Size](#audiencenetworksize)
- [Audience Search Size](#audiencesearchsize)
- [Client Id](#clientid)
- [Description](#description)
- [Id](#id)
- [Membership Duration](#membershipduration)
- [Modified Time](#modifiedtime)
- [Parent Id](#parentid)
- [Scope](#scope)
- [Status](#status)
- [Supported Campaign Types](#supportedcampaigntypes)

You can download all fields of the *In Market Audience* record by including the [DownloadEntity](downloadentity.md) value of *InMarketAudiences* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [DataScope](datascope.md) value of *EntityData*. For more information, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following is a Bulk CSV example download for in-market audience. 

```csv
Type,Status,Id,Parent Id,Client Id,Modified Time,Name,Description,Membership Duration,Scope,Audience,
Format Version,,,,,,5,,,,
In Market Audience,Active,IdHere,ParentIdHere,ClientIdGoesHere,,,In Market Audience Description,30,Account,In Market Audience,
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the *BulkServiceManager* to download the *BulkInMarketAudience* class, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 


```csharp
// Map properties in the Bulk file to the BulkInMarketAudience
var bulkInMarketAudience = new BulkInMarketAudience
{
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // InMarketAudience object of the Campaign Management service.
    InMarketAudience = new InMarketAudience
    {
        // 'Audience Network Size' column header in the Bulk file
        AudienceNetworkSize = null,
        // 'Description' column header in the Bulk file
        Description = "In Market Audience Description",
        // 'Id' column header in the Bulk file
        Id = InMarketAudienceIdKey,
        // 'Membership Duration' column header in the Bulk file
        MembershipDuration = 30,
        // 'Audience' column header in the Bulk file
        Name = "In Market Audience",
        // 'Parent Id' column header in the Bulk file
        ParentId = accountIdKey,
        // 'Scope' column header in the Bulk file
        Scope = EntityScope.Account,
        // 'Audience Search Size' column header in the Bulk file
        SearchSize = null,
        // 'Supported Campaign Types' column header in the Bulk file
        SupportedCampaignTypes = null,
    },
                
    // 'Status' column header in the Bulk file
    Status = Status.Active
};
```

### <a name="audience"></a>Audience
The name of the in-market audience.

The name can contain a maximum of 128 characters

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="audiencenetworksize"></a>Audience Network Size
The total number of people who belong to this audience in the Audience network i.e., via Audience campaigns. This gives you an idea of how many Audience network users you can target.

The audience needs to have at least 300 people before Bing Ads will use it for optimizations.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="audiencesearchsize"></a>Audience Search Size
The total number of people who belong to this audience in the Search network. This gives you an idea of how many search users you can target.

The audience needs to have at least 1,000 people before Bing Ads will use it for optimizations.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="description"></a>Description
The description of the in-market audience. Use a description to help you remember what audience you are targeting with this in-market audience.

The description can contain a maximum of 1,024 characters.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="id"></a>Id
The system generated identifier of the in-market audience.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="membershipduration"></a>Membership Duration
When you create an in-market audience in the Bing Ads web application, you can specify how far back in time Bing Ads should look for actions that match your in-market audience definition in order to add people to your list.

The mimimum duration is 1 day and the maximum duration allowed is 180 days.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="modifiedtime"></a>Modified Time
The date and time that the entity was last updated. The value is in Coordinated Universal Time (UTC).

> [!NOTE]
> The date and time value reflects the date and time at the server, not the client. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="parentid"></a>Parent Id
The Bing Ads identifier of the customer that contains the in-market audience.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="scope"></a>Scope
Scope defines what accounts can use this in-market audience. For an in-market audience the only supported scope is *Customer*, and the in-market audience can be associated with any ad groups across all of the customer's accounts.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported  

### <a name="status"></a>Status
The in-market audience status.

Possible values are *Active* or *Deleted*. 

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported

### <a name="supportedcampaigntypes"></a>Supported Campaign Types
The semicolon delimited list of campaign types that support this in-market audience.

Supported values are Audience, DynamicSearchAds, Search, and Shopping. New campaign types might be added in the future, so you should not take any dependency on a fixed set of values.

**Add:** Not supported  
**Update:** Not supported    
**Delete:** Not supported
