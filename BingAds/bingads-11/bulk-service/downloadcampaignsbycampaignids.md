---
title: DownloadCampaignsByCampaignIds Service Operation - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Downloads settings and performance data for the specified campaigns.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# DownloadCampaignsByCampaignIds Service Operation - Bulk
Downloads settings and performance data for the specified campaigns. You can request all campaign data or only the data that has changed since the last time you downloaded the campaign.

You must use the same user credentials for the download request operation (either [DownloadCampaignsByAccountIds](downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](downloadcampaignsbycampaignids.md)) and the [GetBulkDownloadStatus](getbulkdownloadstatus.md) polling operation.

> [!TIP]
> The [Bulk File Schema](bulk-file-schema.md) provides details about records that you can download and upload. Please adhere to the best practices to ensure fair usage for yourself and all Bing Ads clients. For details please see [Bulk Download Best Practices](../guides/bulk-download-upload.md#downloadbestpractices) and [Bulk Upload Best Practices](../guides/bulk-download-upload.md#uploadbestpractices).

## <a name="request"></a>Request Elements
The *DownloadCampaignsByCampaignIdsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="campaigns"></a>Campaigns|The campaigns to download. You can specify a maximum of 1,000 campaigns. The campaigns that you specify must belong to the same account.|[CampaignScope](campaignscope.md) array|
|<a name="compressiontype"></a>CompressionType|The compression type of the download file. For possible values, see [CompressionType](compressiontype.md). The default is Zip.|[CompressionType](compressiontype.md)|
|<a name="datascope"></a>DataScope|You may include performance data such as spend, in addition to entity data such as campaign settings. The default is *EntityData* which will exclude performance data from the download.<br/><br/>You may include multiple values as flags. How you specify multiple flags depends on the programming language that you use. For example, C# treats these values as flag values and Java treats them as an array of strings. The SOAP should include a string that contains a space-delimited list of values for example, `<DataScope>EntityData EntityPerformanceData</DataScope>`.<br/><br/>If *BidSuggestionsData*, *EntityPerformanceData*, or *QualityScoreData* are included, you must request a full sync to get performance data. To perform  a full sync, set *LastSyncTimeInUTC* to NULL.<br/><br/>If *EntityPerformanceData* is included, you must specify the *CustomerId* in the service request header.<br/><br/>The *EntityPerformanceData* data scope is deprecated and will not be supported in Bing Ads API Version 12. If you want data aggregated by day, week, or month, you can use the Bing Ads Reporting API. For more details see [Reports](../guides/reports.md).|[DataScope](datascope.md)|
|<a name="downloadentities"></a>DownloadEntities|The entities to include in the download. For a list of entities that you can download, see the [DownloadEntity](downloadentity.md) value set.<br/><br/>You must specify at least one download entity, and otherwise the operation will error.|[DownloadEntity](downloadentity.md) array|
|<a name="downloadfiletype"></a>DownloadFileType|The format of the download file. For possible values, see [DownloadFileType](downloadfiletype.md). The default is CSV.|[DownloadFileType](downloadfiletype.md)|
|<a name="formatversion"></a>FormatVersion|The format for records of the download file.<br/><br/>As a best practice you should always specify the latest format version. Currently the only supported format version for Bing Ads API Version 11 is 5.0.<br/><br/>You should manage records according to the [Bulk File Schema](bulk-file-schema.md) for the corresponding format version. |**string**|
|<a name="lastsynctimeinutc"></a>LastSyncTimeInUTC|The last time that you requested a download. The date and time is expressed in Coordinated Universal Time (UTC).<br/><br/>If you specify the last sync time, only those entities that have changed (added, updated, or deleted) since the specified date and time will be downloaded. You cannot specify a date and time older than 90 days, as otherwise an error will be returned.<br/><br/>Target criterion are treated slightly different from other entities, and deleted records are not returned. If any changes were made to a campaign or ad group's target, then all currently active sub target criterion records are returned.<br/><br/>Typically, you request a full download the first time you call the operation by setting this element to null. On all subsequent calls you set the last sync time to the time stamp of the previous download.<br/><br/>The download file contains the time stamp of the download in the *SyncTime* column of the *Account* record. Use the time stamp to set *LastSyncTimeInUTC* the next time that you request a download.<br/><br/>After requesting a full download, the only time that you should again request a full download would be if your account was included in a data migration (for example, the sitelink version 2 migration). If you specify a last sync time that predates the end of the migration process, the download will fail with CampaignServiceFullSyncRequired (error code 3603).|**dateTime**|
|<a name="performancestatsdaterange"></a>PerformanceStatsDateRange|Defines the start and end date when downloading performance data.<br/><br/>If the *DataScope* element includes *EntityPerformanceData*, then the start and end date must be set with this element.<br/><br/>The date range cannot exceed one year. For example April 1, 2015 through March 31, 2016 or April 1, 2016 through March 31, 2017 are both valid date ranges; however January 1, 2016 through April 30, 2017 is invalid.|[PerformanceStatsDateRange](performancestatsdaterange.md)|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *DownloadCampaignsByCampaignIdsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="downloadrequestid"></a>DownloadRequestId|The identifier of the download request. You use the identifier to call the [GetBulkDownloadStatus](getbulkdownloadstatus.md) operation to check the status of the download. The identifier is valid for a maximum of two days. If you have not successfully downloaded the file within this period, it is removed from the download site and you will need to get a new download request identifier.<br/><br/>The string has a length up to 40 and can contain any character.|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">DownloadCampaignsByCampaignIds</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <DownloadCampaignsByCampaignIdsRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Campaigns i:nil="false">
        <CampaignScope>
          <CampaignId>ValueHere</CampaignId>
          <ParentAccountId>ValueHere</ParentAccountId>
        </CampaignScope>
      </Campaigns>
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
    </DownloadCampaignsByCampaignIdsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <DownloadCampaignsByCampaignIdsResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <DownloadRequestId d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</DownloadRequestId>
    </DownloadCampaignsByCampaignIdsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<DownloadCampaignsByCampaignIdsResponse> DownloadCampaignsByCampaignIdsAsync(
	IList<CampaignScope> campaigns,
	CompressionType? compressionType,
	DataScope dataScope,
	IList<DownloadEntity> downloadEntities,
	DownloadFileType? downloadFileType,
	string formatVersion,
	DateTime? lastSyncTimeInUTC,
	PerformanceStatsDateRange performanceStatsDateRange)
{
	var request = new DownloadCampaignsByCampaignIdsRequest
	{
		Campaigns = campaigns,
		CompressionType = compressionType,
		DataScope = dataScope,
		DownloadEntities = downloadEntities,
		DownloadFileType = downloadFileType,
		FormatVersion = formatVersion,
		LastSyncTimeInUTC = lastSyncTimeInUTC,
		PerformanceStatsDateRange = performanceStatsDateRange
	};

	return (await BulkService.CallAsync((s, r) => s.DownloadCampaignsByCampaignIdsAsync(r), request));
}
```
```java
static DownloadCampaignsByCampaignIdsResponse downloadCampaignsByCampaignIds(
	ArrayOfCampaignScope campaigns,
	CompressionType compressionType,
	ArrayList<DataScope> dataScope,
	ArrayOfDownloadEntity downloadEntities,
	DownloadFileType downloadFileType,
	java.lang.String formatVersion,
	Calendar lastSyncTimeInUTC,
	PerformanceStatsDateRange performanceStatsDateRange) throws RemoteException, Exception
{
	DownloadCampaignsByCampaignIdsRequest request = new DownloadCampaignsByCampaignIdsRequest();

	request.setCampaigns(campaigns);
	request.setCompressionType(compressionType);
	request.setDataScope(dataScope);
	request.setDownloadEntities(downloadEntities);
	request.setDownloadFileType(downloadFileType);
	request.setFormatVersion(formatVersion);
	request.setLastSyncTimeInUTC(lastSyncTimeInUTC);
	request.setPerformanceStatsDateRange(performanceStatsDateRange);

	return BulkService.getService().downloadCampaignsByCampaignIds(request);
}
```
```php
static function DownloadCampaignsByCampaignIds(
	$campaigns,
	$compressionType,
	$dataScope,
	$downloadEntities,
	$downloadFileType,
	$formatVersion,
	$lastSyncTimeInUTC,
	$performanceStatsDateRange)
{

	$GLOBALS['Proxy'] = $GLOBALS['BulkProxy'];

	$request = new DownloadCampaignsByCampaignIdsRequest();

	$request->Campaigns = $campaigns;
	$request->CompressionType = $compressionType;
	$request->DataScope = $dataScope;
	$request->DownloadEntities = $downloadEntities;
	$request->DownloadFileType = $downloadFileType;
	$request->FormatVersion = $formatVersion;
	$request->LastSyncTimeInUTC = $lastSyncTimeInUTC;
	$request->PerformanceStatsDateRange = $performanceStatsDateRange;

	return $GLOBALS['BulkProxy']->GetService()->DownloadCampaignsByCampaignIds($request);
}
```
```python
response=bulk_service.DownloadCampaignsByCampaignIds(
	Campaigns=Campaigns,
	CompressionType=CompressionType,
	DataScope=DataScope,
	DownloadEntities=DownloadEntities,
	DownloadFileType=DownloadFileType,
	FormatVersion=FormatVersion,
	LastSyncTimeInUTC=LastSyncTimeInUTC,
	PerformanceStatsDateRange=PerformanceStatsDateRange)
```

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https\://bingads.microsoft.com/CampaignManagement/v11  

