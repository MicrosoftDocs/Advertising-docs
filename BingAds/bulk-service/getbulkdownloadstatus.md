---
title: GetBulkDownloadStatus Service Operation - Bulk
ms.service: bing-ads-bulk-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the status of a bulk download request.
---
# GetBulkDownloadStatus Service Operation - Bulk
Gets the status of a bulk download request.

> [!NOTE]
> You must use the same user credentials for the download request operation (either [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) or [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md)) and  the [GetBulkDownloadStatus](../bulk-service/getbulkdownloadstatus.md) polling operation.

## <a name="request"></a>Request Elements
The *GetBulkDownloadStatusRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="requestid"></a>RequestId|The identifier of the download request.<br /><br />The [DownloadCampaignsByAccountIds](../bulk-service/downloadcampaignsbyaccountids.md) and [DownloadCampaignsByCampaignIds](../bulk-service/downloadcampaignsbycampaignids.md) operations return this element as the *DownloadRequestId*.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetBulkDownloadStatusResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="errors"></a>Errors|An array of *OperationError* objects corresponding to errors encountered during the system processing of the bulk file after your download request was submitted.|[OperationError](operationerror.md) array|
|<a name="forwardcompatibilitymap"></a>ForwardCompatibilityMap|The list of key and value strings for forward compatibility to avoid otherwise breaking changes when new elements are added in the current API version.<br /><br /> Forward compatibility changes will be noted here in future releases. There are currently no forward compatibility changes for the *GetBulkDownloadStatusResponse* message object.|[KeyValuePairOfstringstring](keyvaluepairofstringstring.md) array|
|<a name="percentcomplete"></a>PercentComplete|The progress completion percentage for system processing of the bulk download file.|**int**|
|<a name="requeststatus"></a>RequestStatus|The status of the download. The possible values are as follows.<br /><br />Completed - The download completed successfully.<br /><br />InProgress - The download is in progress.<br /><br />Failed - The download failed. You may submit a new download with fewer entities, without performance data, or try again to submit the same download later.<br /><br />FailedFullSyncRequired - The request's *LastSyncTimeInUTC* element must be set to null, for example if the specified account was included in a data migration. After requesting a full download, you may begin requesting delta downloads again.|**string**|
|<a name="resultfileurl"></a>ResultFileUrl|The URL that contains the download data. This element contains the URL when the *Status* element is *Success*.<br /><br /> You have five minutes from the time that *GetBulkDownloadStatus* returns success to start downloading the file. If you do not start the download within this time period, you will need to call *GetBulkDownloadStatus* again to get a new URL.<br /><br />The download file is compressed (in zip format), so you must unzip the file to access the data.<br /><br />For information about the bulk file format, see [Bulk File Schema](../bulk-service/bulk-file-schema.md).|**string**|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
    <Action mustUnderstand="1">GetBulkDownloadStatus</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <GetBulkDownloadStatusRequest xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <RequestId i:nil="false">ValueHere</RequestId>
    </GetBulkDownloadStatusRequest>
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
    <GetBulkDownloadStatusResponse xmlns="https://bingads.microsoft.com/CampaignManagement/v11">
      <Errors d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <OperationError>
          <Code>ValueHere</Code>
          <Details d4p1:nil="false">ValueHere</Details>
          <ErrorCode d4p1:nil="false">ValueHere</ErrorCode>
          <Message d4p1:nil="false">ValueHere</Message>
        </OperationError>
      </Errors>
      <ForwardCompatibilityMap xmlns:e99="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e99:KeyValuePairOfstringstring>
          <e99:key d4p1:nil="false">ValueHere</e99:key>
          <e99:value d4p1:nil="false">ValueHere</e99:value>
        </e99:KeyValuePairOfstringstring>
      </ForwardCompatibilityMap>
      <PercentComplete>ValueHere</PercentComplete>
      <RequestStatus d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</RequestStatus>
      <ResultFileUrl d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</ResultFileUrl>
    </GetBulkDownloadStatusResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<GetBulkDownloadStatusResponse> GetBulkDownloadStatusAsync(
	string requestId)
{
	var request = new GetBulkDownloadStatusRequest
	{
		RequestId = requestId
	};

	return (await BulkService.CallAsync((s, r) => s.GetBulkDownloadStatusAsync(r), request));
}
```
```java
static GetBulkDownloadStatusResponse getBulkDownloadStatus(
	java.lang.String requestId) throws RemoteException, Exception
{
	GetBulkDownloadStatusRequest request = new GetBulkDownloadStatusRequest();

	request.setRequestId(requestId);

	return BulkService.getService().getBulkDownloadStatus(request);
}
```
```php
static function GetBulkDownloadStatus(
	$requestId)
{

	$GLOBALS['Proxy'] = $GLOBALS['BulkProxy'];

	$request = new GetBulkDownloadStatusRequest();

	$request->RequestId = $requestId;

	return $GLOBALS['BulkProxy']->GetService()->GetBulkDownloadStatus($request);
}
```
```python
response=bulk.GetBulkDownloadStatus(
	RequestId=RequestId)
```

## Requirements
Service: [BulkService.svc v11](https://bulk.api.bingads.microsoft.com/Api/Advertiser/CampaignManagement/v11/BulkService.svc)  
Namespace: https://bingads.microsoft.com/CampaignManagement/v11  

