---
title: "Video Ad Extension Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: eric-urban
ms.author: eur
description: Describes the Video Ad Extension fields in a Bulk file.
dev_langs:
  - csharp
---
# Video Ad Extension Record - Bulk
Defines a video ad extension that can be downloaded and uploaded in a bulk file.

> [!NOTE]
> Not everyone has this feature yet. If you don't, don't worry - it's coming soon!

You can associate a video ad extension with the account or with campaigns and ad groups in the account. Each entity (account, campaign, or ad group) can be associated with up to 20 video ad extensions. An expanded text ad will only include one video (one headline with 3 - 10 values) per impression. Use the [Account Video Ad Extension](account-video-ad-extension.md), [Ad Group Video Ad Extension](ad-group-video-ad-extension.md), and [Campaign Video Ad Extension](campaign-video-ad-extension.md) records to manage video ad extension associations. 

You can download all *Video Ad Extension* records in the account by including the [DownloadEntity](downloadentity.md) value of *VideoAdExtensions* in the [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) service request. Additionally the download request must include the [EntityData](datascope.md#entitydata) scope. For more details about the Bulk service including best practices, see [Bulk Download and Upload](../guides/bulk-download-upload.md).

The following Bulk CSV example would add a new Video Ad Extension to the account's shared library. 

```csv
Type,Status,Id,Parent Id,Campaign,Ad Group,Client Id,Modified Time,Start Date,End Date,Device Preference,Name,Ad Schedule,Use Searcher Time Zone,Video Header,Video Values
Format Version,,,,,,,,,,,6.0,,,,
Video Ad Extension,Active,-18,0,,,ClientIdGoesHere,,,12/31/2020,,,(Monday[09:00-21:00]),FALSE,Brands,Windows;Xbox;Skype
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload and download the *BulkVideoAdExtension* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkVideoAdExtension
var bulkVideoAdExtension = new BulkVideoAdExtension
{
    // 'Parent Id' column header in the Bulk file
    AccountId = 0,
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",
                
    // Map properties in the Bulk file to the 
    // VideoAdExtension object of the Campaign Management service.
    VideoAdExtension = new VideoAdExtension
    {
        // 'Header' column header in the Bulk file
        Header = "Brands",
        // 'Id' column header in the Bulk file
        Id = videoAdExtensionIdKey,
                    
        // 'Ad Schedule' column header in the Bulk file
        Scheduling = new Schedule
        {
            // Each day and time range is delimited by a semicolon (;) in the Bulk file
            DayTimeRanges = new[]
            {
                // Within each day and time range the format is Day[StartHour:StartMinue-EndHour:EndMinute].
                new DayTime
                {
                    Day = Day.Monday,
                    StartHour = 9,
                    StartMinute = Minute.Zero,
                    EndHour = 21,
                    EndMinute = Minute.Zero,
                },
            },
            // 'End Date' column header in the Bulk file
            EndDate = new Microsoft.BingAds.V13.CampaignManagement.Date
            {
                Month = 12,
                Day = 31,
                Year = DateTime.UtcNow.Year + 1
            },
            // 'Start Date' column header in the Bulk file
            StartDate = null,
            // 'Use Searcher Time Zone' column header in the Bulk file
            UseSearcherTimeZone = false,
        },

        // 'Status' column header in the Bulk file
        Status = AdExtensionStatus.Active,
        // 'Video Values' column header in the Bulk file
        // Each value is delimited by a semicolon (;) in the Bulk file
        Values = new[] { "Windows", "Xbox", "Skype" },

    },
};

uploadEntities.Add(bulkVideoAdExtension);

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

