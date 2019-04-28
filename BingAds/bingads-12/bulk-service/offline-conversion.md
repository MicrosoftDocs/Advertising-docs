---
title: "Offline Conversion Record - Bulk"
ms.service: bing-ads-bulk-service
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Describes the Offline Conversion fields in a Bulk file.
dev_langs:
  - csharp
---
# Offline Conversion Record - Bulk
Defines an offline conversion that can be uploaded in a bulk file.

> [!NOTE]
> Bulk download is not supported. You cannot get, update, or delete an offline conversion.

To set up offine conversion tracking, create an [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md). If you set the *CountType* of the [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) to *All*, then all offline conversions for the same *MicrosoftClickId* with different conversion times will be added cumulatively. If you set the *CountType* of the [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) to *Unique*, then only the first conversion that happens after an ad click will be counted. Duplicate offline conversions with the same *MicrosoftClickId* and *ConversionTime* will be ignored. In other words only the first offline conversion for a given *MicrosoftClickId* and *ConversionTime* will be counted.

After the [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) is set up, wait two hours and then send Microsoft Advertising the offline conversion data. It can take up to five hours to view conversion data in the Microsoft Advertising reporting. For more information, see [Tracking offline conversions](https://help.ads.microsoft.com/#apex/3/en/56852/2).

> [!NOTE]
> Although you can upload offline conversions in sandbox for functional testing, the offline conversion data will not be attributed in sandbox performance reporting data.

The following Bulk CSV example would add a new offline conversion. 

```csv
Type,Status,Id,Parent Id,Client Id,Name,Conversion Currency Code,Conversion Name,Conversion Time,Conversion Value,Microsoft Click Id
Format Version,,,,,6.0,,,,,
Offline Conversion,,,,ClientIdGoesHere,,USD,My Goal Name,7/27/2017 6:50:54 PM,10,f894f652ea334e739002f7167ab8f8e3
```

If you are using the [Bing Ads SDKs](../guides/client-libraries.md) for .NET, Java, or Python, you can save time using the [BulkServiceManager](../guides/sdk-bulk-service-manager.md) to upload the *BulkOfflineConversion* object, instead of calling the service operations directly and writing custom code to parse each field in the bulk file. 

```csharp
var uploadEntities = new List<BulkEntity>();

// Map properties in the Bulk file to the BulkOfflineConversion
var bulkOfflineConversion = new BulkOfflineConversion
{
    // 'Client Id' column header in the Bulk file
    ClientId = "ClientIdGoesHere",

    // Map properties in the Bulk file to the 
    // Label object of the Campaign Management service.
    OfflineConversion = new OfflineConversion
    {
        // 'Conversion Currency Code' column header in the Bulk file
        ConversionCurrencyCode = "USD",
        // 'Conversion Name' column header in the Bulk file
        ConversionName = "My Goal Name",
        // 'Conversion Time' column header in the Bulk file
        ConversionTime = DateTime.UtcNow,
        // 'Conversion Value' column header in the Bulk file
        ConversionValue = 10,
        // 'Microsoft Click Id' column header in the Bulk file
        MicrosoftClickId = "f894f652ea334e739002f7167ab8f8e3"
    }
};

uploadEntities.Add(bulkOfflineConversion);

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

For an *Offline Conversion* record, the following attribute fields are available in the [Bulk File Schema](bulk-file-schema.md). 

- [Client Id](#clientid)
- [Conversion Currency Code](#conversioncurrencycode)
- [Conversion Name](#conversionname)
- [Conversion Time](#conversiontime)
- [Conversion Value](#conversionvalue)
- [Microsoft Click Id](#microsoftclickid)

## <a name="clientid"></a>Client Id
Used to associate records in the bulk upload file with records in the results file. The value of this field is not used or stored by the server; it is simply copied from the uploaded record to the corresponding result record. It may be any valid string to up 100 in length.

**Add:** Optional  

## <a name="conversioncurrencycode"></a>Conversion Currency Code
The currency code for the offline conversion.

For more information, see [Currencies](../guides/currencies.md).

**Add:** Optional. If you do not specify an offline conversion currency code, then the *CurrencyCode* element of the goal's [ConversionGoalRevenue](../campaign-management-service/conversiongoalrevenue.md) is used.  

## <a name="conversionname"></a>Conversion Name
The conversion goal name.

This name must match an existing conversion goal name, otherwise the offline conversion goal data will not be applied.

**Add:** Required  

## <a name="conversiontime"></a>Conversion Time
The date and time when the offline conversion occurred. 

The date and time must be within the last 90 days, otherwise the operation will fail when you attempt to send Microsoft Advertising the offline conversion data.

> [!IMPORTANT]
> The value must be in Coordinated Universal Time (UTC). This differs from the time zone options when you upload offline conversions in the Microsoft Advertising web application. For information about the format of the date and time, see the dateTime entry in [Primitive XML Data Types](https://go.microsoft.com/fwlink/?linkid=859198).

To be counted by Microsoft Advertising as an offline conversion after successful upload, the following additional requirements must be met:
-  The date and time of the conversion must be set later than the date and time of the recorded click.  
-  The date and time must be within the conversion window. The *ConversionWindowInMinutes* property of the [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) determines the maximum length of time in minutes after a click that conversions will be tracked.

For example if three clicks were recorded on April 30th, if the *ConversionWindowInMinutes* of the [OfflineConversionGoal](../campaign-management-service/offlineconversiongoal.md) is equal to 30 days (43200 minutes), and if you send Microsoft Advertising the following offline conversions on July 31st, then Microsoft Advertising will only count the one with MicrosoftClickId=*2* as an offline conversion.
-  MicrosoftClickId=*1*; ConversionTime=*2017-04-30T17:02:35.6853793Z*  
-  MicrosoftClickId=*2*; ConversionTime=*2017-05-15T17:02:35.6853793Z*  
-  MicrosoftClickId=*3*; ConversionTime=*2017-06-15T17:02:35.6853793Z*

The offline conversion data with MicrosoftClickId=*1* will not be uploaded since the conversion date and time is more than 90 days ago, and the offline conversion data with MicrosoftClickId=*3* will not be counted because it does not fall within the conversion window (April 30 through May 29).

**Add:** Required   

## <a name="conversionvalue"></a>Conversion Value
The offline conversion value.

**Add:** Optional. If you do not specify an offline conversion value, then the *Value* element of the goal's [ConversionGoalRevenue](../campaign-management-service/conversiongoalrevenue.md) is used.  

## <a name="microsoftclickid"></a>Microsoft Click Id
The MSCLKID for the offline conversion.

To ensure that auto-tagging is enabled for Microsoft click ID tracking, use the *MSCLKID Auto Tagging Enabled* field of the [Account](account.md) record. 

**Add:** Required  


