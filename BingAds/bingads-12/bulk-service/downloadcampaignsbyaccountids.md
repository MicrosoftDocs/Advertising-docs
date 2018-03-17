---
title: DownloadCampaignsByAccountIds Service Operation - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Downloads settings and performance data for all of the account's campaigns.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# DownloadCampaignsByAccountIds Service Operation - Bulk
Downloads settings and performance data for all of the account's campaigns. You can request all campaign data or only the data that has changed since the last time you downloaded the account.

You must use the same user credentials for the download request operation (either [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)) and the [GetBulkDownloadStatus](getbulkdownloadstatus.md) polling operation.

> [!TIP]
> The [Bulk File Schema](bulk-file-schema.md) provides details about records that you can download and upload. Please adhere to the best practices to ensure fair usage for yourself and all Bing Ads clients. For details please see [Bulk Download Best Practices](../guides/bulk-download-upload.md#downloadbestpractices) and [Bulk Upload Best Practices](../guides/bulk-download-upload.md#uploadbestpractices).

## <a name="request"></a>Request Elements
The *DownloadCampaignsByAccountIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accountids"></a>AccountIds|The identifier of the account that contains the campaign data to download. The maximum number of accounts that you can specify is one.<br /><br />The size of the account that you can download is limited to four million keywords. If you try to download an account that contains more than 4 million keywords, the call will fail with error 3207 (AccountTooBigToDownload). If the call fails, please call the [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md) operation to download the account by campaigns. The Details element of the fault includes a comma-delimited list of the campaign IDs that the account owns.|**long** array|
|<a name="compressiontype"></a>CompressionType|The compression type of the download file. For possible values, see [CompressionType](compressiontype.md). The default is Zip.|[CompressionType](compressiontype.md)|
|<a name="datascope"></a>DataScope|You may include quality score data such as ad relevance, in addition to entity data such as campaign settings. The default value is EntityData.<br /><br />You may include multiple values as flags. How you specify multiple flags depends on the programming language that you use. For example, C# treats these values as flag values and Java treats them as an array of strings. The SOAP should include a string that contains a space-delimited list of values for example, `<DataScope>EntityData QualityScoreData</DataScope>`.<br /><br /> If *BidSuggestionsData* or *QualityScoreData* are included, you must request a full sync. To perform a full sync, set *LastSyncTimeInUTC* to NULL.|[DataScope](datascope.md)|
|<a name="downloadentities"></a>DownloadEntities|The entities to include in the download. For a list of entities that you can download, see the [DownloadEntity](downloadentity.md) value set.<br /><br /> You must specify at least one download entity, and otherwise the operation will error.|[DownloadEntity](downloadentity.md) array|
|<a name="downloadfiletype"></a>DownloadFileType|The file type of the download file. For possible values, see [DownloadFileType](downloadfiletype.md). The default is CSV.|[DownloadFileType](downloadfiletype.md)|
|<a name="formatversion"></a>FormatVersion|The format for records of the download file.<br /><br />As a best practice you should always specify the latest format version. Currently the only supported format version for Bing Ads API Version 12 is 6.0.<br /><br />You should manage records according to the [Bulk File Schema](bulk-file-schema.md) for the corresponding format version. |**string**|
|<a name="lastsynctimeinutc"></a>LastSyncTimeInUTC|The last time that you requested a download. The date and time is expressed in Coordinated Universal Time (UTC).<br /><br />If you specify the last sync time, only those entities that have changed (added, updated, or deleted) since the specified date and time will be downloaded. You cannot specify a date and time older than 90 days, as otherwise an error will be returned.<br/><br/> Target criterion are treated slightly different from other entities, and deleted records are not returned. If any changes were made to a campaign or ad group's target, then all currently active sub target criterion records are returned.<br /><br />Typically, you request a full download the first time you call the operation by setting this element to null. On all subsequent calls you set the last sync time to the time stamp of the previous download.<br /><br />The download file contains the time stamp of the download in the *SyncTime* column of the *Account* record. Use the time stamp to set *LastSyncTimeInUTC* the next time that you request a download.<br /><br />After requesting a full download, the only time that you should again request a full download would be if your account was included in a data migration (for example, the sitelink version 2 migration in calendar year 2017). If you specify a last sync time that predates the end of the migration process, the download will fail with CampaignServiceFullSyncRequired (error code 3603).|**dateTime**|
|<a name="performancestatsdaterange"></a>PerformanceStatsDateRange|This element is not supported in Bing Ads API Version 12, and will be removed in a future version. If you want data aggregated by day, week, or month, you can use the Bing Ads Reporting API. For more details see [Reports](../guides/reports.md).|[PerformanceStatsDateRange](performancestatsdaterange.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DownloadCampaignsByAccountIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="downloadrequestid"></a>DownloadRequestId|The identifier of the download request. You use the identifier to call the [GetBulkDownloadStatus](getbulkdownloadstatus.md) operation to check the status of the download. The identifier is valid for a maximum of two days. If you have not successfully downloaded the file within this period, it is removed from the download site and you will need to get a new download request identifier.<br /><br />The string has a length up to 40 and can contain any character.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <Action mustUnderstand="1">DownloadCampaignsByAccountIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DownloadCampaignsByAccountIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <AccountIds i:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
        <a1:long>ValueHere</a1:long>
      </AccountIds>
      <CompressionType i:nil="false">ValueHere</CompressionType>
      <DataScope>ValueHere</DataScope>
      <DownloadEntities i:nil="false">
        <DownloadEntity>ValueHere</DownloadEntity>
      </DownloadEntities>
      <DownloadFileType i:nil="false">ValueHere</DownloadFileType>
      <FormatVersion i:nil="false">ValueHere</FormatVersion>
      <LastSyncTimeInUTC i:nil="false">ValueHere</LastSyncTimeInUTC>
      <PerformanceStatsDateRange i:nil="false">
        <CustomDateRangeEnd i:nil="false">
          <Day>ValueHere</Day>
          <Month>ValueHere</Month>
          <Year>ValueHere</Year>
        </CustomDateRangeEnd>
        <CustomDateRangeStart i:nil="false">
          <Day>ValueHere</Day>
          <Month>ValueHere</Month>
          <Year>ValueHere</Year>
        </CustomDateRangeStart>
        <PredefinedTime i:nil="false">ValueHere</PredefinedTime>
      </PerformanceStatsDateRange>
    </DownloadCampaignsByAccountIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DownloadCampaignsByAccountIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v12">
      <DownloadRequestId d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</DownloadRequestId>
    </DownloadCampaignsByAccountIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DownloadCampaignsByAccountIdsResponse> DownloadCampaignsByAccountIdsAsync(
	IList<long> accountIds,
	CompressionType? compressionType,
	DataScope dataScope,
	IList<DownloadEntity> downloadEntities,
	DownloadFileType? downloadFileType,
	string formatVersion,
	DateTime? lastSyncTimeInUTC,
	PerformanceStatsDateRange performanceStatsDateRange)
{
	var request = new DownloadCampaignsByAccountIdsRequest
	{
		AccountIds = accountIds,
		CompressionType = compressionType,
		DataScope = dataScope,
		DownloadEntities = downloadEntities,
		DownloadFileType = downloadFileType,
		FormatVersion = formatVersion,
		LastSyncTimeInUTC = lastSyncTimeInUTC,
		PerformanceStatsDateRange = performanceStatsDateRange
	};

	return (await BulkService.CallAsync((s, r) => s.DownloadCampaignsByAccountIdsAsync(r), request));
}
```
```java
static DownloadCampaignsByAccountIdsResponse downloadCampaignsByAccountIds(
	ArrayOflong accountIds,
	CompressionType compressionType,
	ArrayList<DataScope> dataScope,
	ArrayOfDownloadEntity downloadEntities,
	DownloadFileType downloadFileType,
	java.lang.String formatVersion,
	Calendar lastSyncTimeInUTC,
	PerformanceStatsDateRange performanceStatsDateRange) throws RemoteException, Exception
{
	DownloadCampaignsByAccountIdsRequest request = new DownloadCampaignsByAccountIdsRequest();

	request.setAccountIds(accountIds);
	request.setCompressionType(compressionType);
	request.setDataScope(dataScope);
	request.setDownloadEntities(downloadEntities);
	request.setDownloadFileType(downloadFileType);
	request.setFormatVersion(formatVersion);
	request.setLastSyncTimeInUTC(lastSyncTimeInUTC);
	request.setPerformanceStatsDateRange(performanceStatsDateRange);

	return BulkService.getService().downloadCampaignsByAccountIds(request);
}
```
```php
static function DownloadCampaignsByAccountIds(
	$accountIds,
	$compressionType,
	$dataScope,
	$downloadEntities,
	$downloadFileType,
	$formatVersion,
	$lastSyncTimeInUTC,
	$performanceStatsDateRange)
{

	$GLOBALS['Proxy'] = $GLOBALS['BulkProxy'];

	$request = new DownloadCampaignsByAccountIdsRequest();

	$request->AccountIds = $accountIds;
	$request->CompressionType = $compressionType;
	$request->DataScope = $dataScope;
	$request->DownloadEntities = $downloadEntities;
	$request->DownloadFileType = $downloadFileType;
	$request->FormatVersion = $formatVersion;
	$request->LastSyncTimeInUTC = $lastSyncTimeInUTC;
	$request->PerformanceStatsDateRange = $performanceStatsDateRange;

	return $GLOBALS['BulkProxy']->GetService()->DownloadCampaignsByAccountIds($request);
}
```
```python
response=bulk_service.DownloadCampaignsByAccountIds(
	AccountIds=AccountIds,
	CompressionType=CompressionType,
	DataScope=DataScope,
	DownloadEntities=DownloadEntities,
	DownloadFileType=DownloadFileType,
	FormatVersion=FormatVersion,
	LastSyncTimeInUTC=LastSyncTimeInUTC,
	PerformanceStatsDateRange=PerformanceStatsDateRange)
```

## Requirements
Service: [BulkService.svc v12](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v12/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v12  

