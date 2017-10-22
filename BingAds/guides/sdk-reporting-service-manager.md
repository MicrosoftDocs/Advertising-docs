---
title: "Reporting Service Manager"
ms.service: "bing-ads"
ms.topic: "article"
ms.date: 11/1/2017
author: "eric-urban"
ms.author: "eur"
description: Learn about using Reportiing Service Manager with the Bing Ads SDKs.
dev_langs:
  - csharp
  - java
  - python
---
# Reporting Service Manager
The SDK provides proxy classes to the service operations, data objects, and value sets defined for the [Reporting](~/reporting-service/reporting-service-reference.md) service.

It also provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.

The *ReportingServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](sdk-authentication.md#authorization-data).

The *ReportingServiceManager* automatically polls in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration by passing a *CancellationToken* to the *DownloadFileAsync* or *TrackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples below. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are downloading large files, you should consider setting the *DownloadHttpTimeout* property.

The *ReportingServiceManager* supports the following workflows.

-   You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with ReportingServiceManager](#reportingbackgroundcompletion).

-   You can submit a download request and then poll until the result file is ready to download. For more information, see [Submit and Download with ReportingServiceManager](#reportingsubmitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. For more information, see [Download Results with ReportingServiceManager](#reportingdownloadresults).

## <a name="reportingbackgroundcompletion"></a>Background Completion with ReportingServiceManager
You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    ReportingService = new ReportingServiceManager(authorizationData);
    ReportingService.StatusPollIntervalInMilliseconds = 5000;

    var reportRequest = GetCampaignPerformanceReportRequest(authorizationData.AccountId);

    var reportingDownloadParameters = new ReportingDownloadParameters
    {
        ReportRequest = reportRequest,
        ResultFileDirectory = FileDirectory,
        ResultFileName = ResultFileName,
        OverwriteResultFile = true,
    };

    // You may optionally cancel the DownloadFileAsync operation after a specified time interval. 
    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    var resultFilePath = await ReportingService.DownloadFileAsync(reportingDownloadParameters, tokenSource.Token);
    Console.WriteLine(String.Format("Download result file: {0}\n", resultFilePath));
}
```
```java
ReportingServiceManager = new ReportingServiceManager(authorizationData);
ReportingServiceManager.setStatusPollIntervalInMilliseconds(5000);

ReportRequest reportRequest = getKeywordPerformanceReportRequest();

ReportingDownloadParameters reportingDownloadParameters = new ReportingDownloadParameters();
reportingDownloadParameters.setReportRequest(reportRequest);
reportingDownloadParameters.setResultFileDirectory(new File(FileDirectory));
reportingDownloadParameters.setResultFileName(ResultFileName);
reportingDownloadParameters.setOverwriteResultFile(true);

// You may optionally cancel the downloadFileAsync operation after a specified time interval.
File resultFile = ReportingServiceManager.downloadFileAsync(
		reportingDownloadParameters, 
		null).get(3600000, TimeUnit.MILLISECONDS);

System.out.println(String.format("Download result file: %s\n", resultFile.getName()));
```
```python
reporting_service_manager=ReportingServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds=5000, 
    environment=ENVIRONMENT,
)

# In addition to ReportingServiceManager, you will need a reporting ServiceClient 
# to build the ReportRequest.

reporting_service=ServiceClient(
    'ReportingService', 
    authorization_data=authorization_data, 
    environment=ENVIRONMENT,
    version=11,
)

report_request=get_keyword_report_request()

reporting_download_parameters = ReportingDownloadParameters(
    report_request=report_request,
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    overwrite_result_file = True, # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
)

result_file_path = reporting_service_manager.download_file(reporting_download_parameters)
print("Download result file: {0}\n".format(result_file_path))
```

## <a name="reportingsubmitdownload"></a>Submit and Download with ReportingServiceManager
Submit the download request and then use the ReportingDownloadOperation result to track status yourself using GetStatusAsync.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    ReportingService = new ReportingServiceManager(authorizationData);

    var reportRequest = GetCampaignPerformanceReportRequest(authorizationData.AccountId);

    var reportingDownloadOperation = await ReportingService.SubmitDownloadAsync(reportRequest);

    // You may optionally cancel the TrackAsync operation after a specified time interval.  
    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    var reportingDownloadOperation = await ReportingService.SubmitDownloadAsync(reportRequest);

    ReportingOperationStatus reportingOperationStatus = await reportingDownloadOperation.TrackAsync(tokenSource.Token);
            
    // You can use TrackAsync to poll until complete as shown above, 
    // or use custom polling logic with GetStatusAsync as shown below.

    //ReportingOperationStatus reportingOperationStatus;

    //var waitTime = new TimeSpan(0, 0, 5);
    //for (int i = 0; i < 24; i++)
    //{
    //    Thread.Sleep(waitTime);

    //    reportingOperationStatus = await reportingDownloadOperation.GetStatusAsync();

    //    if (reportingOperationStatus.Status == ReportRequestStatusType.Success)
    //    {
    //        break;
    //    }
    //}

    var resultFilePath = await reportingDownloadOperation.DownloadResultFileAsync(
        FileDirectory,
        ResultFileName,
        decompress: true,
        overwrite: true);   // Set this value true if you want to overwrite the same file.

    Console.WriteLine(String.Format("Download result file: {0}\n", resultFilePath));
}
```
```java
ReportingServiceManager = new ReportingServiceManager(authorizationData);

ReportRequest reportRequest = getKeywordPerformanceReportRequest();

ReportingDownloadOperation reportingDownloadOperation = ReportingServiceManager.submitDownloadAsync(
		reportRequest,
		null).get();

// You may optionally cancel the trackAsync operation after a specified time interval.
ReportingOperationStatus reportingOperationStatus = 
		reportingDownloadOperation.trackAsync(null).get(3600000, TimeUnit.MILLISECONDS);

// You can use trackAsync to poll until complete as shown above, 
// or use custom polling logic with getStatusAsync as shown below.

//		ReportingOperationStatus reportingOperationStatus;
//		
//		for (int i = 0; i < 24; i++)
//		{
//		    Thread.sleep(5000);
//		    reportingOperationStatus = reportingDownloadOperation.getStatusAsync(null).get(3600000, TimeUnit.MILLISECONDS);
//		    if (reportingOperationStatus.getStatus() == ReportRequestStatusType.SUCCESS)
//		    {
//		        break;
//		    }
//		}

File resultFile = reportingDownloadOperation.downloadResultFileAsync(
    new File(FileDirectory),
    ResultFileName,
    true, // Set this value to true if you want to decompress the ZIP file.
    true,  // Set this value true if you want to overwrite the named file.
    null).get();

System.out.println(String.format("Download result file: %s\n", resultFile.getName()));
```
```python
reporting_service_manager=ReportingServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds=5000, 
    environment=ENVIRONMENT,
)

# In addition to ReportingServiceManager, you will need a reporting ServiceClient 
# to build the ReportRequest.

reporting_service=ServiceClient(
    'ReportingService', 
    authorization_data=authorization_data, 
    environment=ENVIRONMENT,
    version=11,
)

report_request=get_keyword_report_request()

reporting_download_operation = reporting_service_manager.submit_download(report_request)

# You may optionally cancel the track() operation after a specified time interval.
reporting_operation_status = reporting_download_operation.track(timeout_in_milliseconds=3600000)

# You can use ReportingDownloadOperation.track() to poll until complete as shown above, 
# or use custom polling logic with get_status() as shown below.
#for i in range(10):
#    time.sleep(reporting_service_manager.poll_interval_in_milliseconds / 1000.0)

#    download_status = reporting_download_operation.get_status()
        
#    if download_status.status == 'Success':
#        break
    
result_file_path = reporting_download_operation.download_result_file(
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    decompress = True, 
    overwrite = True,  # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
)
    
print("Download result file: {0}\n".format(result_file_path))
```

## <a name="reportingdownloadresults"></a>Download Results with ReportingServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. Use TrackAsync to indicate that the application should wait to ensure that the download status is completed.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    ReportingService = new ReportingServiceManager(authorizationData);

    // You may optionally cancel the TrackAsync operation after a specified time interval. 
    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    var reportingDownloadOperation = new ReportingDownloadOperation(<RequestIdGoesHere>, authorizationData);

    // Use TrackAsync to indicate that the application should wait to ensure that 
    // the download status is completed.
    var reportingOperationStatus = await reportingDownloadOperation.TrackAsync(tokenSource.Token);

    var resultFilePath = await reportingDownloadOperation.DownloadResultFileAsync(
        FileDirectory,
        ResultFileName,
        decompress: true,
        overwrite: true);   // Set this value true if you want to overwrite the same file.

    Console.WriteLine(String.Format("Download result file: {0}", resultFilePath));
    Console.WriteLine(String.Format("Status: {0}", reportingOperationStatus.Status));
    Console.WriteLine(String.Format("TrackingId: {0}\n", reportingOperationStatus.TrackingId));
}
```
```java
java.lang.String requestId = <RequestIdGoesHere>;

ReportingDownloadOperation reportingDownloadOperation = new ReportingDownloadOperation(requestId, authorizationData);

reportingDownloadOperation.setStatusPollIntervalInMilliseconds(5000);

// You can use trackAsync to poll until complete as shown here, 
// or use custom polling logic with getStatusAsync.

// You may optionally cancel the trackAsync operation after a specified time interval.
ReportingOperationStatus reportingOperationStatus = 
		reportingDownloadOperation.trackAsync(null).get(3600000, TimeUnit.MILLISECONDS);

File resultFile = reportingDownloadOperation.downloadResultFileAsync(
    new File(FileDirectory),
    ResultFileName,
    true, // Set this value to true if you want to decompress the ZIP file
    true,  // Set this value true if you want to overwrite the named file.
    null).get();

System.out.println(String.format("Download result file: %s", resultFile.getName()));
System.out.println(String.format("Status: %s", reportingOperationStatus.getStatus()));
System.out.println(String.format("TrackingId: %s\n", reportingOperationStatus.getTrackingId()));
```
```python
reporting_download_operation = ReportingDownloadOperation(
    request_id = <RequestIdGoesHere>, 
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds=5000, 
    environment=ENVIRONMENT,
)

# Use track() to indicate that the application should wait to ensure that 
# the download status is completed.
# You may optionally cancel the track() operation after a specified time interval.
reporting_operation_status = reporting_download_operation.track(timeout_in_milliseconds=3600000)
    
result_file_path = reporting_download_operation.download_result_file(
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    decompress = True, 
    overwrite = True,  # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
) 

print("Download result file: {0}".format(result_file_path))
print("Status: {0}\n".format(reporting_operation_status.status))
```

## See Also
[Sandbox](../guides/sandbox.md)  
[Bing Ads Code Examples](../guides/code-examples.md)    
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

