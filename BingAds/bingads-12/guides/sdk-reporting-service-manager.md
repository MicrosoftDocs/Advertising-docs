---
title: "Reporting Service Manager"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Learn about using Reportiing Service Manager with the Bing Ads SDKs.
dev_langs:
  - csharp
  - java
  - python
---
# Reporting Service Manager
The SDK provides proxy classes to the service operations, data objects, and value sets defined for the [Reporting](../reporting-service/reporting-service-reference.md) service. It also provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.

> [!NOTE]
> The *ReportingServiceManager* is available with the .NET, Java, and Python SDKs.

The *ReportingServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](sdk-authentication.md#authorization-data).

The *ReportingServiceManager* automatically polls in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration by passing a *CancellationToken* to the *DownloadFileAsync* or *TrackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples below. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are downloading large files, you should consider setting the *DownloadHttpTimeout* property.

The *ReportingServiceManager* supports the following workflows.

- You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with ReportingServiceManager](#reportingbackgroundcompletion).

- You can submit a download request and then poll until the result file is ready to download. For more information, see [Submit and Download with ReportingServiceManager](#reportingsubmitdownload).

- If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. For more information, see [Download Results with ReportingServiceManager](#reportingdownloadresults).

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
    Console.WriteLine(string.Format("Download result file: {0}\n", resultFilePath));
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
    version=12,
    authorization_data=authorization_data, 
    environment=ENVIRONMENT,
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

    Console.WriteLine(string.Format("Download result file: {0}\n", resultFilePath));
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
    version=12,
    authorization_data=authorization_data, 
    environment=ENVIRONMENT,
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

    Console.WriteLine(string.Format("Download result file: {0}", resultFilePath));
    Console.WriteLine(string.Format("Status: {0}", reportingOperationStatus.Status));
    Console.WriteLine(string.Format("TrackingId: {0}\n", reportingOperationStatus.TrackingId));
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

## <a name="reportcontainer"></a>In-Memory Report Container
The *Report* is an in-memory container that abstracts the contents of a downloaded report file, including header metadata, column names, and report records. With these updates you are free to focus more on the business requirements of your application instead of parsing the report file.
You can access the Report container in-memory via the *ReportingServiceManager* by submitting a new download request, or by using the *ReportFileReader* to read from a report file that you already downloaded. 

For example you can get a Report object by submitting a new download request via ReportingServiceManager. Although in this case you won’t work directly with the file, under the covers a request is submitted to the Reporting service and the report file is downloaded to a local directory. The reporting download parameters include the requested report type, scope, time period, and the local download file path. 

```csharp
Report reportContainer = (await ReportingServiceManager.DownloadReportAsync(
    reportingDownloadParameters,
    CancellationToken.None));
```
```java
Report reportContainer = ReportingServiceManager.downloadReportAsync(reportingDownloadParameters, null).get(); 
```
```python
report_container = reporting_service_manager.download_report(reporting_download_parameters)
```

Otherwise if you already have a report file that was downloaded via the API, you can get a Report object via the ReportFileReader. 

```csharp
ReportFileReader reader = new ReportFileReader(
    "c:\\reports\\result.csv",
    ReportFormat.Csv);
Report reportContainer = reader.GetReport();
```
```java
ReportFileReader reader = new ReportFileReader(
        reportingDownloadParameters.getResultFileDirectory() + "\\" + reportingDownloadParameters.getResultFileName(), 
        reportingDownloadParameters.getReportRequest().getFormat());
Report reportContainer = reader.getReport();
```
```python
report_file_reader = ReportFileReader(
    file_path = reporting_download_parameters.result_file_directory + reporting_download_parameters.result_file_name, 
    format = reporting_download_parameters.report_request.Format)
report_container = report_file_reader.get_report()
```

Once you have a Report object via either workflow above, you can access the metadata and report records. If there was no report data for the campaigns and dates that you submitted, then the download result will be null or empty. 

```csharp
// Output the report metadata

long recordCount = reportContainer.ReportRecordCount;
Console.WriteLine(string.Format("ReportName: {0}", reportContainer.ReportName));
Console.WriteLine(string.Format("ReportTimeStart: {0}", reportContainer.ReportTimeStart));
Console.WriteLine(string.Format("ReportTimeEnd: {0}", reportContainer.ReportTimeEnd));
Console.WriteLine(string.Format("LastCompletedAvailableDate: {0}", reportContainer.LastCompletedAvailableDate.ToString()));
Console.WriteLine(string.Format("ReportAggregation: {0}", reportContainer.ReportAggregation.ToString()));
Console.WriteLine(string.Format("ReportColumns: {0}", string.Join("; ", reportContainer.ReportColumns)));
Console.WriteLine(string.Format("ReportRecordCount: {0}", recordCount));

// Analyze and output performance statistics

IEnumerable<IReportRecord> reportRecordIterable = reportContainer.GetReportRecords();
            
int totalImpressions = 0;
int totalClicks = 0;
HashSet<string> distinctDevices = new HashSet<string>();
HashSet<string> distinctNetworks = new HashSet<string>();
foreach (IReportRecord record in reportContainer.GetReportRecords())
{
    totalImpressions += record.GetIntegerValue("Impressions");
    totalClicks += record.GetIntegerValue("Clicks");
    distinctDevices.Add(record.GetStringValue("DeviceType"));
    distinctNetworks.Add(record.GetStringValue("Network"));
}

Console.WriteLine(string.Format("Total Impressions: {0}", totalImpressions));
Console.WriteLine(string.Format("Total Clicks: {0}", totalClicks));
Console.WriteLine(string.Format("Average Impressions: {0}", totalImpressions * 1.0 / recordCount));
Console.WriteLine(string.Format("Average Clicks: {0}", totalClicks * 1.0 / recordCount));
Console.WriteLine(string.Format("Distinct Devices: {0}", string.Join("; ", distinctDevices)));
Console.WriteLine(string.Format("Distinct Networks: {0}", string.Join("; ", distinctNetworks)));

// Be sure to close the report before you attempt to clean up files within the working directory.

reportContainer.Dispose();

// The CleanupTempFiles method removes all files (not sub-directories) within the working directory, 
// whether or not the files were created by this ReportingServiceManager instance. 

ReportingServiceManager.CleanupTempFiles();
```
```java
// Output the reportRequest metadata

java.lang.Long recordCount = reportContainer.getReportRecordCount();
outputStatusMessage(String.format("ReportName: %s", reportContainer.getReportName()));
outputStatusMessage(String.format("ReportTimeStart: %s", reportContainer.getReportTimeStart()));
outputStatusMessage(String.format("ReportTimeEnd: %s", reportContainer.getReportTimeEnd()));
outputStatusMessage(String.format("LastCompletedAvailableDate: %s", reportContainer.getLastCompletedAvailableDate().toString()));
outputStatusMessage(String.format("ReportAggregation: %s", enumCaseToPascalCase(reportContainer.getReportAggregation().toString())));
outputStatusMessage(String.format("ReportColumns: %s", String.join("; ", reportContainer.getReportColumns())));
outputStatusMessage(String.format("ReportRecordCount: %s", recordCount));

// Analyze and output performance statistics

if(Arrays.asList(reportContainer.getReportColumns()).contains("Impressions")){
    Iterable<ReportRecord> reportRecordIterable = reportContainer.getReportRecords();

    int totalImpressions = 0;
    int totalClicks = 0;
    HashSet<String> distinctDevices = new HashSet<>();
    HashSet<String> distinctNetworks = new HashSet<>();
    for (ReportRecord record : reportRecordIterable)
    {
        totalImpressions += record.getIntegerValue("Impressions");
        totalClicks += record.getIntegerValue("Clicks");
        distinctDevices.add(record.getStringValue("DeviceType"));
        distinctNetworks.add(record.getStringValue("Network"));
    }

    outputStatusMessage(String.format("Total Impressions: %s", totalImpressions));
    outputStatusMessage(String.format("Total Clicks: %s", totalClicks));
    outputStatusMessage(String.format("Average Impressions: %s", totalImpressions * 1.0 / recordCount));
    outputStatusMessage(String.format("Average Clicks: %s", totalClicks * 1.0 / recordCount));
    outputStatusMessage(String.format("Distinct Devices: %s", String.join("; ", distinctDevices)));
    outputStatusMessage(String.format("Distinct Networks: %s", String.join("; ", distinctNetworks)));
}       

// Be sure to close the reportRequest before you attempt to clean up files within the working directory.

reportContainer.close();

// The cleanupTempFiles method removes all files (not sub-directories) within the working
// directory, whether or not the files were created by this ReportingServiceManager instance. 
// If you are using a cloud service such as Microsoft Azure you'll want to ensure you do not
// exceed the file or directory limits. 

ReportingServiceManager.cleanupTempFiles();
```
```python
# Output the reportRequest metadata
record_count = report_container.record_count
output_status_message("ReportName: {0}".format(report_container.report_name))
output_status_message("ReportTimeStart: {0}".format(report_container.report_time_start))
output_status_message("ReportTimeEnd: {0}".format(report_container.report_time_end))
output_status_message("LastCompletedAvailableDate: {0}".format(report_container.last_completed_available_date))
output_status_message("ReportAggregation: {0}".format(report_container.report_aggregation))
output_status_message("ReportColumns: {0}".format("; ".join(str(column) for column in report_container.report_columns)))
output_status_message("ReportRecordCount: {0}".format(record_count))

#Analyze and output performance statistics

if "Impressions" in report_container.report_columns and \
    "Clicks" in report_container.report_columns and \
    "DeviceType" in report_container.report_columns and \
    "Network" in report_container.report_columns:

    report_record_iterable = report_container.report_records

    total_impressions = 0
    total_clicks = 0
    distinct_devices = set()
    distinct_networks = set()
    for record in report_record_iterable:
        total_impressions += record.int_value("Impressions")
        total_clicks += record.int_value("Clicks")
        distinct_devices.add(record.value("DeviceType"))
        distinct_networks.add(record.value("Network"))

    output_status_message("Total Impressions: {0}".format(total_impressions))
    output_status_message("Total Clicks: {0}".format(total_clicks))
    output_status_message("Average Impressions: {0}".format(total_impressions * 1.0 / record_count))
    output_status_message("Average Clicks: {0}".format(total_clicks * 1.0 / record_count))
    output_status_message("Distinct Devices: {0}".format("; ".join(str(device) for device in distinct_devices)))
    output_status_message("Distinct Networks: {0}".format("; ".join(str(network) for network in distinct_networks)))

#Be sure to close the report.

report_container.close()
```

## See Also
[Sandbox](sandbox.md)  
[Bing Ads Code Examples](code-examples.md)    
[Bing Ads Web Service Addresses](web-service-addresses.md)  

