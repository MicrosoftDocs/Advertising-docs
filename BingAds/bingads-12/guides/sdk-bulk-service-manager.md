---
title: "Bulk Service Manager"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Learn about using Bulk Service Manager with the Bing Ads SDKs.
dev_langs:
  - csharp
  - java
  - python
---
# Bulk Service Manager
Take advantage of the [Bulk service](../bulk-service/bulk-service-reference.md) to efficiently manage ads and keywords for all campaigns in an account. The SDK provides classes to accelerate productivity for downloading and uploading entities. For example the *DownloadFileAsync* method of the *BulkServiceManager* class will submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. Use the *BulkFileReader* class instead of writing a file parser to read the download results. The *BulkFileReader* provides access to the bulk file records in *BulkEntity* derived classes, which contain data objects and values sets corresponding to the [Campaign Management service](../campaign-management-service/campaign-management-service-reference.md).

The *BulkServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](sdk-authentication.md#authorization-data).

> [!NOTE]
> The *BulkServiceManager* is available with the .NET, Java, and Python SDKs.

The *BulkServiceManager* automatically polls for the result file in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *BulkServiceManager* will poll in the following sequence of minutes: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *BulkServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration by passing a *CancellationToken* to the *UploadEntitiesAsync*, *DownloadEntitiesAsync*, *UploadFileAsync*, *DownloadFileAsync*, or *TrackAsync* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples below. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are uploading or downloading large files, you should consider setting the *UploadHttpTimeout* or *DownloadHttpTimeout* properties. 

The *BulkServiceManager* supports the following workflows.

- You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with BulkServiceManager](#backgroundcompletion). 

- You can submit a download or upload request and then poll until the result file is ready to download. For more information, see [Submit and Download with BulkServiceManager](#submitdownload).

- If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. For more information, see [Download Results with BulkServiceManager](#downloadresults).

- If you are migrating from a deprecated bulk file format version, you can use an *IBulkService* instance of *ServiceClient* to upload and download campaigns using any format version [Bulk File Schema](../bulk-service/bulk-file-schema.md). The low level approach requires that you submit your download or upload, poll until the results are available, and then download the results file. For more information, see [Using ServiceClient&lt;TService&gt;](sdk-authentication.md##serviceclient) and [Bulk Download and Upload](bulk-download-upload.md).
    
> [!NOTE]
> If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the file or directory limits. You can specify a different working directory for each *BulkServiceManager* instance. For details see [Working Directory and BulkServiceManager](#workingdirectory).

## <a name="backgroundcompletion"></a>Background Completion with BulkServiceManager
You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    BulkService = new BulkServiceManager(authorizationData);

    var progress = new Progress<BulkOperationProgressInfo>(x =>
        Console.WriteLine(String.Format("{0} % Complete", x.PercentComplete.ToString(CultureInfo.InvariantCulture))));

    var downloadParameters = new DownloadParameters
    {
        CampaignIds = null,
        DataScope = DataScope.EntityData,
        Entities = BulkDownloadEntity.Keywords,
        FileType = DownloadFileType.Csv,
        LastSyncTimeInUTC = null,
        ResultFileDirectory = FileDirectory,
        ResultFileName = ResultFileName,
        OverwriteResultFile = false    // Set this value true if you want to overwrite the same file.
    };

    // You may optionally cancel the DownloadFileAsync operation after a specified time interval. 
    // Pass this object to the DownloadFileAsync operation or specify CancellationToken.None. 

    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    // Submit the download request, and the results file will be downloaded to the specified local file. 

    var resultFile = (await BulkService.DownloadFileAsync(downloadParameters, progress, tokenSource.Token));

    Console.WriteLine(string.Format("Download result file: {0}\n", resultFile));
}
```
```java
BulkService = new BulkServiceManager(authorizationData);

// Poll for downloads at reasonable intervals. You know your data better than anyone. 
// If you download an account that is well less than one million keywords, consider polling 
// at 15 to 20 second intervals. If the account contains about one million keywords, consider polling 
// at one minute intervals after waiting five minutes. For accounts with about four million keywords, 
// consider polling at one minute intervals after waiting 10 minutes. 

BulkService.setStatusPollIntervalInMilliseconds(5000);

Progress<BulkOperationProgressInfo> progress = new Progress<BulkOperationProgressInfo>() {
    @Override
    public void report(BulkOperationProgressInfo value) {
        System.out.println(value.getPercentComplete() + "% Complete\n");
    }
};

DownloadParameters downloadParameters = new DownloadParameters();
downloadParameters.setCampaignIds(null);
ArrayList<DataScope> dataScope = new ArrayList<DataScope>();
dataScope.add(DataScope.ENTITY_DATA);
downloadParameters.setDataScope(dataScope);
downloadParameters.setFileType(FileType);
downloadParameters.setLastSyncTimeInUTC(null);
ArrayList<BulkDownloadEntity> bulkDownloadEntities = new ArrayList<BulkDownloadEntity>();
bulkDownloadEntities.add(BulkDownloadEntity.KEYWORDS);
downloadParameters.setEntities(bulkDownloadEntities);
downloadParameters.setResultFileDirectory(new File(FileDirectory));
downloadParameters.setResultFileName(ResultFileName);
downloadParameters.setOverwriteResultFile(true);    // Set this value true if you want to overwrite the same file.

// Submit the download request, and the results file will be downloaded to the specified local file. 
// You may optionally cancel the downloadFileAsync operation after a specified time interval.
File resultFile = BulkService.downloadFileAsync(
		downloadParameters, 
		progress, 
		null).get(3600000, TimeUnit.MILLISECONDS);

System.out.printf("Download result file: %s\n", resultFile.getName());
```

```python
bulk_service_manager = BulkServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds = 5000, 
    environment = ENVIRONMENT,
)
        
download_parameters = DownloadParameters(
    campaign_ids=None,
    data_scope=['EntityData'],
    entities=entities,
    file_type=FILE_TYPE,
    last_sync_time_in_utc=None,
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    overwrite_result_file = True, # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
)

result_file_path = bulk_service_manager.download_file(download_parameters, progress = None)

print("Download result file: {0}\n".format(result_file_path))
```

## <a name="submitdownload"></a>Submit and Download with BulkServiceManager
Submit the download request and then use the BulkDownloadOperation result to track status yourself using GetStatusAsync.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    var BulkService = new BulkServiceManager(authorizationData);

    var submitDownloadParameters = new SubmitDownloadParameters
    {
        CampaignIds = null,
        DataScope = DataScope.EntityData,
        Entities = BulkDownloadEntity.Keywords,
        FileType = DownloadFileType.Csv,
        LastSyncTimeInUTC = null
    };

    var bulkDownloadOperation = await BulkService.SubmitDownloadAsync(submitDownloadParameters);

    // You may optionally cancel the TrackAsync operation after a specified time interval. 
    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    BulkOperationStatus<DownloadStatus> downloadStatus = await bulkDownloadOperation.TrackAsync(null, tokenSource.Token);

    // You can use TrackAsync to poll until complete as shown above, 
    // or use custom polling logic with GetStatusAsync as shown below.

    //BulkOperationStatus<DownloadStatus> downloadStatus;
    //var waitTime = new TimeSpan(0, 0, 5);

    //for (int i = 0; i < 24; i++)
    //{
    //    Thread.Sleep(waitTime);

    //    downloadStatus = await bulkDownloadOperation.GetStatusAsync();

    //    if (downloadStatus.Status == DownloadStatus.Completed)
    //    {
    //        break;
    //    }
    //}

    var resultFilePath = await bulkDownloadOperation.DownloadResultFileAsync(
        FileDirectory,
        ResultFileName,
        decompress: true,
        overwrite: true // Set this value true if you want to overwrite the same file.
    );   

    Console.WriteLine(String.Format("Download result file: {0}\n", resultFilePath));
}
```
```java
BulkService = new BulkServiceManager(authorizationData);

SubmitDownloadParameters submitDownloadParameters = new SubmitDownloadParameters();
submitDownloadParameters.setCampaignIds(null);
ArrayList<DataScope> dataScope = new ArrayList<DataScope>();
dataScope.add(DataScope.ENTITY_DATA);
submitDownloadParameters.setDataScope(dataScope);
submitDownloadParameters.setFileType(FileType);
submitDownloadParameters.setLastSyncTimeInUTC(null);
ArrayList<BulkDownloadEntity> bulkDownloadEntities = new ArrayList<BulkDownloadEntity>();
bulkDownloadEntities.add(BulkDownloadEntity.KEYWORDS);
submitDownloadParameters.setEntities(bulkDownloadEntities);

// Submit the download request. You can use the BulkDownloadOperation result to track status yourself using getStatusAsync,
// or use trackAsync to indicate that the application should wait until the download status is completed.

BulkDownloadOperation bulkDownloadOperation = BulkService.submitDownloadAsync(
		submitDownloadParameters,
		null).get();

// You may optionally cancel the trackAsync operation after a specified time interval.
BulkOperationStatus<DownloadStatus> downloadStatus = 
		bulkDownloadOperation.trackAsync(null).get(3600000, TimeUnit.MILLISECONDS);

// You can use trackAsync to poll until complete as shown above, 
// or use custom polling logic with getStatusAsync as shown below.

//		BulkOperationStatus<DownloadStatus> downloadStatus;
//		
//		for (int i = 0; i < 24; i++)
//		{
//		    Thread.sleep(5000);
//		    downloadStatus = bulkDownloadOperation.getStatusAsync(null).get(3600000, TimeUnit.MILLISECONDS);
//		    if (downloadStatus.getStatus() == DownloadStatus.COMPLETED)
//		    {
//		        break;
//		    }
//		}

File resultFile = bulkDownloadOperation.downloadResultFileAsync(
    new File(FileDirectory),
    ResultFileName,
    true, // Set this value to true if you want to decompress the ZIP file.
    true,  // Set this value true if you want to overwrite the named file.
    null).get();

System.out.println(String.format("Download result file: %s\n", resultFile.getName()));
```
```python
bulk_service_manager = BulkServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds = 5000, 
    environment = ENVIRONMENT,
)

submit_download_parameters = SubmitDownloadParameters(
    data_scope = [ 'EntityData' ],
    entities = [ 'Campaigns', 'AdGroups', 'Keywords', 'Ads' ],
    file_type = 'Csv',
    campaign_ids = None,
    last_sync_time_in_utc = None,
    performance_stats_date_range = None
)

bulk_download_operation = bulk_service_manager.submit_download(submit_download_parameters)

# You may optionally cancel the track() operation after a specified time interval.
download_status = bulk_download_operation.track(timeout_in_milliseconds=3600000)

# You can use BulkDownloadOperation.track() to poll until complete as shown above, 
# or use custom polling logic with getStatus() as shown below.
#for i in range(10):
#    time.sleep(bulk_service_manager.poll_interval_in_milliseconds / 1000.0)

#    download_status = bulk_download_operation.get_status()
        
#    if download_status.status == 'Completed':
#        break
    
result_file_path = bulk_download_operation.download_result_file(
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    decompress = True, 
    overwrite = True, # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
)
    
print("Download result file: {0}\n".format(result_file_path))
```

## <a name="downloadresults"></a>Download Results with BulkServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. Track the result to ensure that the download status is completed.

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    BulkService = new BulkServiceManager(authorizationData);

    var progress = new Progress<BulkOperationProgressInfo>(x =>
        Console.WriteLine(String.Format("{0} % Complete", x.PercentComplete.ToString(CultureInfo.InvariantCulture))));

    // If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier 
    // and use it to download the result file. 

    // You may optionally cancel the TrackAsync operation after a specified time interval. 
    var tokenSource = new CancellationTokenSource();
    tokenSource.CancelAfter(3600000);

    var bulkDownloadOperation = new BulkDownloadOperation(requestId, authorizationData);

    // Use TrackAsync to indicate that the application should wait to ensure that 
    // the download status is completed.
    var bulkOperationStatus = await bulkDownloadOperation.TrackAsync(null, tokenSource.Token);

    var resultFilePath = await bulkDownloadOperation.DownloadResultFileAsync(
        FileDirectory,
        ResultFileName,
        decompress: true,
        overwrite: true);   // Set this value true if you want to overwrite the same file.

    Console.WriteLine(String.Format("Download result file: {0}", resultFilePath));
    Console.WriteLine(String.Format("Status: {0}", bulkOperationStatus.Status));
    Console.WriteLine(String.Format("TrackingId: {0}\n", bulkOperationStatus.TrackingId));
}
```
```java
Progress<BulkOperationProgressInfo> progress = new Progress<BulkOperationProgressInfo>() {
    @Override
    public void report(BulkOperationProgressInfo value) {
        System.out.println(value.getPercentComplete() + "% Complete\n");
    }
};

java.lang.String requestId = <RequestIdGoesHere>;

BulkDownloadOperation bulkDownloadOperation = new BulkDownloadOperation(requestId, authorizationData);

// Poll for downloads at reasonable intervals. You know your data better than anyone. 
// If you download an account that is well less than one million keywords, consider polling 
// at 15 to 20 second intervals. If the account contains about one million keywords, consider polling 
// at one minute intervals after waiting five minutes. For accounts with about four million keywords, 
// consider polling at one minute intervals after waiting 10 minutes. 

bulkDownloadOperation.setStatusPollIntervalInMilliseconds(5000);

// You may optionally cancel the trackAsync operation after a specified time interval.
BulkOperationStatus<DownloadStatus> downloadStatus = bulkDownloadOperation.trackAsync(progress, null).get(3600000, TimeUnit.MILLISECONDS);

System.out.printf("Download Status:\nPercentComplete: %s\nResultFileUrl: %s\nStatus: %s\n",
        downloadStatus.getPercentComplete(), downloadStatus.getResultFileUrl(), downloadStatus.getStatus());

File resultFile = bulkDownloadOperation.downloadResultFileAsync(
    new File(FileDirectory),
    ResultFileName,
    true,    // Set this value to true if you want to decompress the ZIP file
    true,    // Set this value true if you want to overwrite the same file.
    null).get();

System.out.println(String.format("Download result file: %s", resultFile.getName()));
System.out.println(String.format("Status: %s", downloadStatus.getStatus()));
System.out.println(String.format("TrackingId: %s\n", downloadStatus.getTrackingId()));
```
```python
request_id = <RequestIdGoesHere>

bulk_download_operation = BulkDownloadOperation(
    request_id = request_id, 
    authorization_data = authorization_data, 
    poll_interval_in_milliseconds = 5000,
    environment = ENVIRONMENT
)

# Use track() to indicate that the application should wait to ensure that 
# the download status is completed.
# You may optionally cancel the track() operation after a specified time interval.
bulk_operation_status = bulk_download_operation.track(timeout_in_milliseconds=3600000)

result_file_path = bulk_download_operation.download_result_file(
    result_file_directory = FILE_DIRECTORY, 
    result_file_name = DOWNLOAD_FILE_NAME, 
    decompress = True, 
    overwrite = True, # Set this value true if you want to overwrite the same file.
    timeout_in_milliseconds=3600000 # You may optionally cancel the download after a specified time interval.
) 

print("Download result file: {0}\n".format(result_file))
print("Status: {0}\n".format(bulk_operation_status.status))
```

## <a name="workingdirectory"></a>Working Directory and BulkServiceManager
With the .NET and Java SDKs, you can set the working directory where *BulkServiceManager* should store temporary bulk files. For example, when you call *DownloadEntitiesAsync* with the Bing Ads .NET SDK, although you will only directly work with *BulkEntity* objects a bulk file is downloaded to a temporary directory. Likewise via *UploadEntitiesAsync* a temporary file is written to the working directory, and then uploaded to the Bulk service. The system temp directory will be used if another working directory is not specified. If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the temp directory limits. There may be other reasons to use a custom working directory. You can specify a different working directory for each *BulkServiceManager* instance by setting the *WorkingDirectory* property. You are also responsible for creating and removing any directories. After you have iterated over the bulk entities you can clean up the files from the working directory.

> [!IMPORTANT] 
> The *CleanupTempFiles* method removes all files (but not sub-directories) within the working directory, whether or not the files were created by the current BulkServiceManager instance. 

```csharp
public async Task RunAsync(AuthorizationData authorizationData)
{
    BulkService = new BulkServiceManager(authorizationData);

    var progress = new Progress<BulkOperationProgressInfo>(x =>
        Console.WriteLine(String.Format("{0} % Complete", x.PercentComplete.ToString(CultureInfo.InvariantCulture))));

    var downloadParameters = new DownloadParameters
    {
        CampaignIds = null,
        DataScope = DataScope.EntityData,
        Entities = BulkDownloadEntity.Keywords,
        FileType = DownloadFileType.Csv,
        LastSyncTimeInUTC = null,
        ResultFileDirectory = FileDirectory,
        ResultFileName = ResultFileName,
        OverwriteResultFile = false    // Set this value true if you want to overwrite the same file.
    };

    // The system temp directory will be used if another working directory is not specified. If you are 
    // using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the file or directory limits. 
    // You can specify a different working directory for each BulkServiceManager instance.

    BulkService.WorkingDirectory = FileDirectory;

    // The DownloadEntitiesAsync method returns IEnumerable<BulkEntity>, so the download file will not
    // be accessible e.g. for CleanupTempFiles until you iterate over the result e.g. via ToList().

    var resultEntities = (await BulkService.DownloadEntitiesAsync(downloadParameters)).ToList();

    // The CleanupTempFiles method removes all files (but not sub-directories) within the working directory, 
    // whether or not the files were created by this BulkServiceManager instance. 

    BulkService.CleanupTempFiles();
}
```
```java
BulkService = new BulkServiceManager(authorizationData);

BulkService.setStatusPollIntervalInMilliseconds(5000);

Progress<BulkOperationProgressInfo> progress = new Progress<BulkOperationProgressInfo>() {
    @Override
    public void report(BulkOperationProgressInfo value) {
        System.out.println(value.getPercentComplete() + "% Complete\n");
    }
};

DownloadParameters downloadParameters = new DownloadParameters();
downloadParameters.setCampaignIds(null);
ArrayList<DataScope> dataScope = new ArrayList<DataScope>();
dataScope.add(DataScope.ENTITY_DATA);
downloadParameters.setDataScope(dataScope);
downloadParameters.setFileType(FileType);
downloadParameters.setLastSyncTimeInUTC(null);
ArrayList<BulkDownloadEntity> bulkDownloadEntities = new ArrayList<BulkDownloadEntity>();
bulkDownloadEntities.add(BulkDownloadEntity.KEYWORDS);
downloadParameters.setEntities(bulkDownloadEntities);
downloadParameters.setResultFileDirectory(new File(FileDirectory));
downloadParameters.setResultFileName(ResultFileName);
downloadParameters.setOverwriteResultFile(true);    // Set this value true if you want to overwrite the same file.

// The system temp directory will be used if another working directory is not specified. If you are 
// using a cloud service such as Microsoft Azure you'll want to ensure you do not exceed the file or directory limits. 
// You can specify a different working directory for each BulkServiceManager instance.

BulkService.setWorkingDirectory(new File(FileDirectory));

// The downloadEntitiesAsync method returns BulkEntityIterable, so the download file will not
// be accessible e.g. for cleanupTempFiles until you iterate over the result and close the BulkEntityIterable instance.

BulkEntityIterable tempEntities = BulkService.downloadEntitiesAsync(downloadParameters, null, null).get();

ArrayList<BulkEntity> resultEntities = new ArrayList<BulkEntity>();
for (BulkEntity entity : tempEntities) {
    resultEntities.add(entity);
}

tempEntities.close();

// The cleanupTempFiles method removes all files (not sub-directories) within the working directory, 
// whether or not the files were created by this BulkServiceManager instance. 

BulkService.cleanupTempFiles();
```

## See Also
[Sandbox](sandbox.md)  
[Bing Ads Code Examples](code-examples.md)    
[Bing Ads Web Service Addresses](web-service-addresses.md)  

