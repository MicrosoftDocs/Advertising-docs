---
title: "Profile Data Files"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Find out about audience profile data supported with the Bing Ads API.
---
# Profile Data Files
Profile data can be used to show ads to people in a specific company name, industry, or job function (according to LinkedIn). You can call the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation to get a temporary file URL that can be used to download the latest profile data. You can also get the profile data from the [Bing Ads Developer Portal](https://developers.azure.bingads.microsoft.com/Account). You must be signed in to the developer portal with a Microsoft account user who has Bing Ads credentials.

> [!NOTE]
> As a best practice you should download the file instead of opening it directly through an application such as Microsoft Excel. If you view the profile data in a text editor, be sure to use UTF-8 encoding instead of ANSI, otherwise some characters will not be displayed accurately.

For code examples that demonstrate how to download the profile data, see [Profile Data Code Example](code-example-profile-data.md).

## <a name="profiletypes"></a>Profile Types
The company name, industry, and job function profile data are available in three seperate files i.e., companies.csv, industries.csv, and jobfunctions.csv.

Each comma separated value (CSV) file contains data organized in the following non-localized column headings. Only the Display Name and Descriptor columns are localized depending on the file URL used above.

> [!IMPORTANT]
> New columns may be added at any time, so your implementation must ignore unknown columns.
> 
> The order of profile data is not guaranteed, so you should not take dependencies on any perceived column sort order or hierarchy.

### <a name="companyname"></a>Company Name Profile
If you set the [ProfileType](../campaign-management-service/getprofiledatafileurl.md#profiletype) to *CompanyName* when calling the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation, the following company name data is available in the downloaded *companies.csv* file. 

|Column Name|Description|
|---------------|---------------|
|Profile Id|The unique Bing Ads system identifier for the profile.<br/><br/>In *companies.csv* this is the unique identifier of the company.|
|Company Display Name|The display name of the company for example, "Microsoft".|
|Company Logo Url|The full https path for the company's logo image.|
|Industry Display Name|The display name for the industry that this company belongs to for example, "Technology".|
|Company Size|The approximate number or range of employees at the company.<br/><br/>Currently the possible values include One, TwotoTen, EleventoFifty, FiftyOnetoTwoHundred, TwoHundredOnetoFiveHundred, FiveHundredOnetoOneThousand, OneThousandOnetoFiveThousand, FiveThousandOnetoTenThousand, and OverTenThousand. New values may be added in the future, so you should not depend on a fixed set.|
|Replaces|Reserved for future use to indicate which profile or profiles are replaced by the profile in this row.|
|Status|Reserved for future use to indicate whether the profile in this row is active or deprecated. Currently there are no deprecated profiles provided in the CSV file.|

### <a name="industry"></a>Industry Profile
If you set the [ProfileType](../campaign-management-service/getprofiledatafileurl.md#profiletype) to *Industry* when calling the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation, the following industry data is available in the downloaded *industries.csv* file. 

|Column Name|Description|
|---------------|---------------|
|Profile Id|The unique Bing Ads system identifier for the profile.<br/><br/>In *industries.csv* this is the unique identifier of the industry.|
|Industry Display Name|The display name for the industry for example, "Food Production".|
|Industry Group Display Name|The display name of the group that this industry belongs to for example, "Manufacturing".|
|Replaces|Reserved for future use to indicate which profile or profiles are replaced by the profile in this row.|
|Status|Reserved for future use to indicate whether the profile in this row is active or deprecated. Currently there are no deprecated profiles provided in the CSV file.|

### <a name="jobfunction"></a>Job Function Profile
If you set the [ProfileType](../campaign-management-service/getprofiledatafileurl.md#profiletype) to *JobFunction* when calling the [GetProfileDataFileUrl](../campaign-management-service/getprofiledatafileurl.md) operation, the following job function data is available in the downloaded *companies.csv* file. 

|Column Name|Description|
|---------------|---------------|
|Profile Id|The unique Bing Ads system identifier for the profile.<br/><br/>In *jobfunctions.csv* this is the unique identifier of the job function.|
|Job Function Display Name|The display name of this job function for example, "Accounting".|
|Replaces|Reserved for future use to indicate which profile or profiles are replaced by the profile in this row.|
|Status|Reserved for future use to indicate whether the profile in this row is active or deprecated. Currently there are no deprecated profiles provided in the CSV file.|

## See Also
[Audience Ads](audience-ads.md)  
