---
title: "Geographical Location Codes"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Geographical Location Codes
Geographical locations data can be used to for [Location Targeting](~/guides/show-ads-target-audience.md#locationcriterion). You can call the [GetGeoLocationsFileUrl](~/campaign-management/getgeolocationsfileurl.md) operation to get a temporary file URL that can be used to download the latest geographical locations data. You can also get the data from the [Bing Ads Developer Portal](https://developers.azure.bingads.microsoft.com/Account). You must be signed in to the developer portal with a Microsoft account user who has Bing Ads credentials. 

> [!NOTE]
> As a best practice you should download the file instead of opening it directly through an application such as Microsoft Excel. If you view the locations data in a text editor, be sure to use UTF-8 encoding instead of ANSI, otherwise some characters will not be displayed accurately.

For code examples that demonstrate how to download the geographical locations codes, see [Geographical Locations Code Example](~/guides/code-example-geographical-locations.md).

## <a name="fileformat"></a>Location Codes File Format
The comma separated value (CSV) file contains data organized in the following non-localized column headings. Only the Display Name and Descriptor columns are localized depending on the file URL used above.

> [!IMPORTANT]
> New columns may be added at any time, so your implementation must ignore unknown columns.
> 
> The order of locations is not guaranteed, so you should not take dependencies on any perceived column sort order or hierarchy.


### <a name="version2"></a>File Format Version 2.0
If you specified *Version* as 2.0 when calling the [GetGeoLocationsFileUrl](~/campaign-management/getgeolocationsfileurl.md) operation, the following data is available in the downloaded file. File format version 2.0 is only supported with Bing Ads API Version 11.

|Column Name|Description|
|---------------|---------------|
|Location Id|The unique Bing Ads system identifier for the location. You must use this value to set the location criterion.|
|Bing Display Name|The optional name that you can use to display the locations data, for example to users of your application. Vertical bars are used to separate the location components from most to least specific. For example given Seattle&#124;Washington&#124;United States the most specific component is the city of Seattle within the state of Washington of the United States.<br/><br/>**Note**: Multiple location IDs can have the same display name. You must not use the display name for anything other than presentation, for example do not assume any hierarchy or take any dependencies on the display name.|
|Location Type|Determines the location sub type (e.g., City) that corresponds to the Location Id column.|
|Replaces|Reserved for future use to indicate which location or locations are replaced by the location in this row.|
|Status|Reserved for future use to indicate whether the location in this row is active or deprecated. Currently there are no deprecated locations provided in the CSV file.|
|AdWords Location Id|The *Google AdWords* Location Criterion Id that matches closest to the Bing Ads geographical location ID. You can use this for mapping Bing Ads locations to the estimated AdWords locations.<br /><br />**Note:** This value is a heuristic estimate that can be used for mapping AdWords and Bing Ads geographical locations.|

### <a name="version2migration"></a>Migrating to File Format Version 2.0
Version 2.0 is only supported with Campaign Management API version 11. If you are migrating from version 1.0 to 2.0 please note the following changes.

|Version 1.0 Column|Version 2.0 Column|
|---------------|---------------|
|Id|Location Id|
|Display Name|Bing Display Name|
|Target Type|Location Type|
|AdWords Location ID|AdWords Location Id|
|Code|N/A (removed)|
|Descriptor|N/A (removed)|


### <a name="version1"></a>File Format Version 1.0
If you specified *Version* as 1.0 when calling the [GetGeoLocationsFileUrl](~/campaign-management/getgeolocationsfileurl.md) operation, the following data is available in the downloaded file. 

> [!IMPORTANT]
> The locations file Version 1.0 is deprecated in favor of version 2.0. After October 31, 2017 version 1.0 will be sunset and only 2.0 will be supported. In the meantime file format version 1.0 is supported with Bing Ads API Version 10 and Version 11.

|Column Name|Description|
|---------------|---------------|
|ID|The unique Bing Ads system identifier for the location.|
|Code|This value can be used to set the location target.<br /><br />**Note:** If this field itself contains commas the enclosed data will be surrounded by quotes, but you should not use the quotes when setting a location target bid. For example *Seattle, Seattle-Tacoma, WA WA US* is a valid city code.|
|Display Name|The optional name that you can use to display the locations data, for example to users of your application. Vertical bars are used to separate the location components from most to least specific. For example given Seattle&#124;Washington&#124;United States the most specific component is the city of Seattle within the state of Washington of the United States.<br/><br/>**Note**: Multiple location codes can have the same display name. You must not use the display name for anything other than presentation, for example do not assume any hierarchy or take any dependencies on the display name.|
|Descriptor|The optional friendly name corresponding to the Target Type column. There is not necessarily a one to one relationship between this value and the Target Type column. You should not assume any hierarchy or take any dependencies on the descriptor.|
|Target Type|Determines the type of location target can accept the value in the Code column.|
|Replaces|Reserved for future use to indicate which location or locations are replaced by the location in this row.|
|Status|Reserved for future use to indicate whether the location in this row is active or deprecated. Currently there are no deprecated locations provided in the CSV file.|
|AdWords Location ID|he *Google AdWords* Location Criterion Id that matches closest to the Bing Ads geographical location ID. You can use this for mapping Bing Ads locations to the estimated AdWords locations.<br /><br />**Note:** This value is a heuristic estimate that can be used for mapping AdWords and Bing Ads geographical locations.|



## See Also
[Show Ads to Your Target Audience](~/guides/show-ads-target-audience.md)  
