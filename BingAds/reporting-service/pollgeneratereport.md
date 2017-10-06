---
title: PollGenerateReport Service Operation
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the status of a report request.
---
# PollGenerateReport Service Operation
Gets the status of a report request.

> [!NOTE]
> You must use the same user credentials for the [SubmitGenerateReport](../reporting-service/submitgeneratereport.md) and [PollGenerateReport](../reporting-service/pollgeneratereport.md). For more information, see [Request and Download a Report](~/guides/request-download-report.md).

## <a name="request"></a>Request Elements
The *PollGenerateReportRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="reportrequestid"></a>ReportRequestId|The identifier of the report request. The [SubmitGenerateReport](../reporting-service/submitgeneratereport.md) operation returns the identifier.|**string**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *PollGenerateReportResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="reportrequeststatus"></a>ReportRequestStatus|Contains the status of the report request and the download URL.|[ReportRequestStatus](reportrequeststatus.md)|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
The following template shows the order of the [body](#request-body) and [header](#request-header) elements for the SOAP request.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Reporting/v11">
    <Action mustUnderstand="1">PollGenerateReport</Action>
    <ApplicationToken i:nil="false">ValueHere</ApplicationToken>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <CustomerAccountId i:nil="false">ValueHere</CustomerAccountId>
    <CustomerId i:nil="false">ValueHere</CustomerId>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
    <Password i:nil="false">ValueHere</Password>
    <UserName i:nil="false">ValueHere</UserName>
  </s:Header>
  <s:Body>
    <PollGenerateReportRequest xmlns="https://bingads.microsoft.com/Reporting/v11">
      <ReportRequestId i:nil="false">ValueHere</ReportRequestId>
    </PollGenerateReportRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
The following template shows the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Reporting/v11">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <PollGenerateReportResponse xmlns="https://bingads.microsoft.com/Reporting/v11">
      <ReportRequestStatus d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <ReportDownloadUrl d4p1:nil="false">ValueHere</ReportDownloadUrl>
        <Status>ValueHere</Status>
      </ReportRequestStatus>
    </PollGenerateReportResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](~/guides/client-libraries.md). See [Bing Ads Code Examples](~/guides/code-examples.md) for more examples.
```csharp
public async Task<PollGenerateReportResponse> PollGenerateReportAsync(
	string reportRequestId)
{
	var request = new PollGenerateReportRequest
	{
		ReportRequestId = reportRequestId
	};

	return (await Reporting.CallAsync((s, r) => s.PollGenerateReportAsync(r), request));
}
```
```java
static PollGenerateReportResponse pollGenerateReport(
	java.lang.String reportRequestId) throws RemoteException, Exception
{
	PollGenerateReportRequest request = new PollGenerateReportRequest();

	request.setReportRequestId(reportRequestId);

	return Reporting.getService().pollGenerateReport(request);
}
```
```php
static function PollGenerateReport(
	$reportRequestId)

	$pollGenerateReportRequest = new PollGenerateReportRequest();

	$request->ReportRequestId = $reportRequestId;

	return $ReportingProxy->GetService()->PollGenerateReport($request);
}
```
```python
response=reporting.PollGenerateReport(
	ReportRequestId=ReportRequestIdHere
)
```

## Requirements
Service: [ReportingService.svc v11](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https://bingads.microsoft.com/Reporting/v11  

