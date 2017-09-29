---
title: "Get Started Using Java with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Get Started Using Java with Bing Ads Services
To get started developing Bing Ads applications with Java, [install the SDK](#installation) and either start with the [provided examples](~/guides/code-examples.md) or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-java.md) or [Desktop](../guides/walkthrough-desktop-application-java.md) application. You can also browse the [Bing Ads Code Examples](../guides/code-examples.md) gallery. The examples have been developed with the Bing Ads Java SDK in the environment described below. Your custom configuration may vary.

-   [Setting Up the Development Environment](#requirements)  
-   [Installing the SDK](#installation)  
-   [Walkthroughs](#walkthrough)  
-   [Using AuthorizationData](#authorizationdata)  
-   [Using OAuth](#oauth)  
-   [Using ServiceClient](#serviceclient)  
-   [Using BulkServiceManager](#bulkservicemanager)  
-   [Using ReportingServiceManager](#reportingservicemanager)  
-   [Exception Handling](#exceptionhandling)  
-   [Configuring Sandbox](#sandbox)  

## <a name="requirements"></a>Setting Up the Development Environment
You need user credentials with access to Bing Ads either in production or sandbox. You also need a developer token. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) in production, the Microsoft account user must [sign up](https://secure.azure.bingads.microsoft.com/Auth) or [manage](../guides/customer-accounts.md#managingusers) an existing Bing Ads account. You also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Using OAuth](#oauth) below.

You must install a Java Runtime Environment (JRE), version 1.6 or later.

The [Bing Ads Code Examples](../guides/code-examples.md) in Java are developed and run with the Eclipse Java EE IDE for Web Developers, Luna Service Release 1 (4.4.1). For Eclipse downloads, see [http://www.eclipse.org/downloads/](http://www.eclipse.org/downloads/).

For [Authentication with OAuth](../guides/authentication-oauth.md) in a web application, you will need to deploy to a server with a publicly available redirection URL. For more information, see [Deploying a Web Application](../guides/walkthrough-web-application-java.md#deploy).

## <a name="installation"></a>Installing the SDK
The Bing Ads Java SDK depends on the libraries listed at the [Maven Repository](http://mvnrepository.com/artifact/com.microsoft.bingads/microsoft.bingads/).

When you create a Maven project and include the *microsoft.bingads* Maven artifact as shown below, additional dependencies are installed automatically. If you are not using a Maven project, you must include the correct version of each dependency. For more information, please see the [Walkthrough: Bing Ads Web Application in Java](../guides/walkthrough-web-application-java.md) or [Walkthrough: Bing Ads Desktop Application in Java](../guides/walkthrough-desktop-application-java.md) application examples.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  ...
  <dependencies>
    <dependency>
      <groupId>com.microsoft.bingads</groupId>
      <artifactId>microsoft.bingads</artifactId>
      <version>10.4.12</version>
    </dependency>
  </dependencies>
</project>
```
> [!NOTE]
> Version 10.4.12 is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads Java SDK installed, you can either browse the [Bing Ads Code Examples](../guides/code-examples.md), download the examples from [GitHub](https://github.com/BingAds/BingAds-Java-SDK/tree/master/examples), or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-java.md) or [Desktop](../guides/walkthrough-desktop-application-java.md) application.

## <a name="authorizationdata"></a>Using AuthorizationData
You must initialize a new instance of *ServiceClient* or *BulkServiceManager* with *AuthorizationData*. The class contains properties that Bing Ads uses to authorize a user. The *ServiceClient*, *BulkServiceManager*, and *ReportingServiceManager* classes handle common request header fields for you, allowing you to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

The following code block shows how to create an instance of *AuthorizationData* and set its *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties.

```java
static AuthorizationData authorizationData = new AuthorizationData();
authorizationData.setAuthentication(<AuthenticationGoesHere>);
authorizationData.setCustomerId("<CustomerIdGoesHere>");
authorizationData.setAccountId("<AccountIdGoesHere>");
authorizationData.setDeveloperToken("<DeveloperTokenGoesHere>");
```
The *Authentication* property must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant*, *OAuthDesktopMobileImplicitGrant*, or *PasswordAuthentication*. When *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager* call Bing Ads services, they set the *AuthenticationToken* header element for each service request message to the value of the *AccessToken* property of your Authentication-derived instance. For more information, see [Service Request Header](../guides/authentication-oauth.md#serviceheaders), [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

Some services such as Customer Management do not accept *CustomerId* and *CustomerAccountId* headers, so they will be ignored if you specified them in the *AuthorizationData* object.

## <a name="oauth"></a>Using OAuth
The OAuth classes in the client library abstract the low level user authorization details, so you can focus at a high level on your security requirements. The client library objects take care of low level details such as formatting the authorization and redirect URIs and setting the request headers.

To use OAuth with the Bing Ads Java SDK, the *Authentication* property of your AuthorizationData object must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant* or *OAuthDesktopMobileImplicitGrant*. For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token. This is a standard OAuth 2.0 flow and is defined in detail in the [Authorization Code Grant section of the OAuth 2.0 spec](http://tools.ietf.org/html/draft-ietf-oauth-v2-15#section-4.1). For more information both about authorization code and implicit grant flows, see [Authentication with OAuth](../guides/authentication-oauth.md).

1.  Create an instance of *OAuthWebAuthCodeGrant*, that will be used to manage Microsoft Account user authorization. Replace *ClientId*, *ClientSecret*, and *RedirectionUri* with the values configured in [Registering Your Application](../guides/authentication-oauth.md#registerapplication).

    ```java
    OAuthWebAuthCodeGrant oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(ClientId, ClientSecret, new URL(RedirectionUri));
    
    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
    // cross site request forgery (CSRF). 
    oAuthWebAuthCodeGrant.setState("ClientStateGoesHere");
    ```

2.  Request user consent by connecting to the Microsoft Account authorization endpoint through a web browser control. Call the *getAuthorizationEndpoint* method of the *OAuthWebAuthCodeGrant* instance that you created in the earlier step, and send the redirect response.

    ```java
    URL authorizationEndpoint = oAuthWebAuthCodeGrant.getAuthorizationEndpoint();
    response.sendRedirect(authorizationEndpoint.toString());
    ```
    
    The user will be prompted through the Microsoft Account authorization web browser control to grant permissions for your application to manage their Bing Ads accounts.
    
    The authorization service calls back to your application with the redirection URI, which includes an authorization code if the user authorized your application to manage their Bing Ads accounts. For example the callback Url includes an authorization code as follows if the user granted permissions for your application to manage their Bing Ads accounts:  *https://contoso.com/redirect/?code=CODE&state=ClientStateGoesHere*. If the user granted your application permissions to manage their Bing Ads accounts, you should use the code right away in the next step. The short duration of the authorization code, for example 5 minutes, is subject to change.
    
    If the user denied your application permissions to manage their Bing Ads accounts, the callback URI includes an error and error description field as follows: *REDIRECTURI?error=access_denied&error_description=ERROR_DESCRIPTION&state=ClientStateGoesHere*.

3.  Use the authorization code to request the *AccessToken*, *RefreshToken*, and *ExpiresIn* values from the *OAuthTokens* property of your *OAuthWebAuthCodeGrant* instance.  Pass the full callback Url to the *requestAccessAndRefreshTokens* method of your *OAuthWebAuthCodeGrant* instance. This method uses the authorization code fragment to request the access token and refresh token.

    ```java
    if (request.getParameter("code") != null)
    {
        // If you set the client state in step #1 above, verify that the authorization
        // server returns the same value before proceeding.
        if (oAuthWebAuthCodeGrant.getState() != ClientState)
            throw new Exception("The OAuth response state does not match the client request state.");
                           
        oAuthWebAuthCodeGrant.requestAccessAndRefreshTokens(new URL(request.getRequestURL() + "?" + request.getQueryString()));
    }
    ```
    
    If this step succeeded, your application has permissions to manage the user's Bing Ads accounts. To call Bing Ads services, you should initialize either *ServiceClient*, *BulkServiceManager*, and *ReportingServiceManager* with *AuthorizationData* that contains your *OAuthWebAuthCodeGrant* instance.
    
    For more information, see [Using AuthorizationData](#authorizationdata), [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).
    
4.  When calling Bing Ads services with *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager*, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to implement event handling using the *NewOAuthTokensReceivedListener*. 

    ```java
    oAuthWebAuthCodeGrant.setNewTokensListener(new NewOAuthTokensReceivedListener() {
        @Override
        public void onNewOAuthTokensReceived(OAuthTokens newTokens) {
               saveRefreshToken(newTokens.getRefreshToken());
        }
    });

    ```
    
    You can also get the *AccessToken*, *RefreshToken*, and *ExpiresIn* values from the *OAuthTokens* property of your *OAuthWebAuthCodeGrant* instance by calling *requestAccessAndRefreshTokens*.
    
    ```java
    if (refreshToken != null)
    {
        oAuthWebAuthCodeGrant.requestAccessAndRefreshTokens(refreshToken);
    }
    ```
  
    > [!NOTE]
    > Whereas the refresh token parameter does not have a defined expiration period, you should expect it to last several months. 
    
    You may need to start again from Step 1 and request user consent if, for example the Microsoft Account user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf.

## <a name="serviceclient"></a>Using ServiceClient
You can use an instance of the *ServiceClient* class to call any methods in one of the following client service interfaces:

-   *IAdInsightService*  
-   *IBulkService*  
-   *ICampaignManagementService*  
-   *ICustomerBillingService*  
-   *ICustomerManagementService*  
-   *IReportingService*  

The *ServiceClient* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

For example the following sample shows how to use the Customer Management service to get the current authenticated user.

```java
ServiceClient<ICustomerManagementService> CustomerService = new ServiceClient<ICustomerManagementService>(
		authorizationData, 
		ICustomerManagementService.class);

java.lang.Long userId = null;
final GetUserRequest getUserRequest = new GetUserRequest();
getUserRequest.setUserId(userId);

User user = CustomerService.getService().getUser(getUserRequest).getUser();
```

## <a name="bulkservicemanager"></a>Using BulkServiceManager
Take advantage of the [Bulk service](~/bulk/bulk-service-reference.md) to efficiently manage ads and keywords for all campaigns in an account. The client library provides classes to accelerate productivity for downloading and uploading entities. For example the *downloadFileAsync* method of the *BulkServiceManager* class will submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. Use the *BulkFileReader* class instead of writing a file parser to read the download results. The *BulkFileReader* provides access to the bulk file records in *BulkEntity* derived classes, which contain data objects and values sets corresponding to the [Campaign Management service](~/campaign-management/campaign-management-service-reference.md).

The *BulkServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *BulkServiceManager* automatically polls for the result file in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *BulkServiceManager* will poll in the following sequence of minutes: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *BulkServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration when calling the *uploadEntitiesAsync*, *downloadEntitiesAsync*, *uploadFileAsync*, *downloadFileAsync*, or *trackAsync* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples below. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are uploading or downloading large files, you should consider setting the *uploadHttpTimeoutInMilliseconds* or *downloadHttpTimeoutInMilliseconds* properties.  

The *BulkServiceManager* supports the following workflows.

-   You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with BulkServiceManager](#backgroundcompletion).

-   You can submit a download or upload request and then poll until the result file is ready to download. For more information, see [Submit and Download with BulkServiceManager](#submitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. For more information, see [Download Results with BulkServiceManager](#downloadresults).

-   If you are migrating from a deprecated bulk file format version, you can use an *IBulkService* instance of *ServiceClient* to upload and download campaigns using any format version [Bulk File Schema](~/bulk/bulk-file-schema.md). The low level approach requires that you submit your download or upload, poll until the results are available, and then download the results file. For more information, see [Using ServiceClient](#serviceclient) and [Bulk Download and Upload](../guides/bulk-download-upload.md).

> [!NOTE]
> If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the file or directory limits. You can specify a different working directory for each *BulkServiceManager* instance. For details see [Working Directory and BulkServiceManager](#workingdirectory).

### <a name="backgroundcompletion"></a>Background Completion with BulkServiceManager
You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

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

### <a name="submitdownload"></a>Submit and Download with BulkServiceManager
Submit the download request and then use the BulkDownloadOperation result to track status yourself using getStatusAsync.

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

### <a name="downloadresults"></a>Download Results with BulkServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. Use trackAsync to indicate that the application should wait to ensure that the download status is completed.

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

### <a name="workingdirectory"></a>Working Directory and BulkServiceManager
When using the *uploadEntitiesAsync* and *downloadEntitiesAsync* SDK operations, you can work with the result entities in memory i.e. without reading from a result file. That said, the *BulkServiceManager* downloads the result file by default to the system temp directory. If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the temp directory limits. There may be other reasons to use a custom working directory. You can specify a different working directory for each *BulkServiceManager* instance by setting the *WorkingDirectory* property and then calling the *cleanupTempFiles* operation after enumerating over the resulting entities in memory. You are also responsible for creating and removing any directories. 

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

## <a name="reportingservicemanager"></a>Using ReportingServiceManager
The client library provides proxy classes to the service operations, data objects, and value sets defined for the [Reporting](~/reporting/reporting-service-reference.md) service.
It also provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.

The *ReportingServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *ReportingServiceManager* automatically polls in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration when calling the *downloadFileAsync* or *trackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples below. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are downloading large files, you should consider setting the *downloadHttpTimeoutInMilliseconds* property.

The *ReportingServiceManager* supports the following workflows.

-   You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with ReportingServiceManager](#reportingbackgroundcompletion).

-   You can submit a download request and then poll until the result file is ready to download. For more information, see [Submit and Download with ReportingServiceManager](#reportingsubmitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. For more information, see [Download Results with ReportingServiceManager](#reportingdownloadresults).

### <a name="reportingbackgroundcompletion"></a>Background Completion with ReportingServiceManager
You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

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

### <a name="reportingsubmitdownload"></a>Submit and Download with ReportingServiceManager
Submit the download request and then use the ReportingDownloadOperation result to track status yourself using getStatusAsync.

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

### <a name="reportingdownloadresults"></a>Download Results with ReportingServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. Use trackAsync to indicate that the application should wait to ensure that the download status is completed.

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

## <a name="exceptionhandling"></a>Exception Handling
In addition to handling Java runtime exceptions, your application should be prepared to handle Bing Ads API service level exceptions and Bing Ads Java SDK wrapper exceptions. 

Bing Ads API service level exceptions include AdApiFaultDetail, ApiBatchFault, ApiFault, ApiFaultDetail, and EditorialApiFaultDetail. For more information, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md). 

You should also handle the following Bing Ads Java SDK exceptions, which abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

Exception  |Namespaces  |Description  
---------|---------|---------     
CouldNotDownloadResultFileException     |com.microsoft.bingads         |This exception is thrown by the internal SDK HttpService after a failed attempt to download a bulk or reporting result file. 
CouldNotUploadFileException     |com.microsoft.bingads        |This exception is thrown by the internal SDK HttpService after a failed attempt to upload a bulk file.     
OAuthTokenRequestException     |com.microsoft.bingads         |This exception is thrown if an error was returned from the Microsft Account authorization server. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid client ID. 
BulkDownloadCouldNotBeCompletedException     |com.microsoft.bingads.V11.bulk        |This exception is thrown if an attempt was made to poll for a completed bulk download results file and the bulk service returns a failed status.
BulkOperationInProgressException     |com.microsoft.bingads.V11.bulk        |This exception is thrown if an attempt was made to download a bulk results file that is not yet available.
BulkUploadCouldNotBeCompletedException     |com.microsoft.bingads.V11.bulk        |This exception is thrown if an attempt was made to poll for a completed bulk upload results file and the bulk service returns a failed status. 
CouldNotGetBulkOperationStatusException     |com.microsoft.bingads.V11.bulk         |This exception is thrown if the BulkServiceManager failed to get the upload or download operation status after multiple retries.   
CouldNotSubmitBulkDownloadException     |com.microsoft.bingads.V11.bulk         |This exception is thrown by the BulkServiceManager when the DownloadCampaignsByAccountIds service operation that it called does not return a valid response.   
CouldNotSubmitBulkUploadException     |com.microsoft.bingads.V11.bulk         |This exception is thrown by the BulkServiceManager when the GetBulkUploadUrl service operation that it called does not return a valid response.   
EntityReadException     |com.microsoft.bingads.V11.bulk        |This exception is thrown when attempting to read entities from a bulk file using BulkFileReader. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example the bulk file that you are attempting to read from might have an invalid value in one of the fields.
EntityWriteException     |com.microsoft.bingads.V11.bulk        |This exception is thrown when attempting to write entities to a bulk file using BulkFileWriter. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid value for one of the upload entities. 
CouldNotGetReportingDownloadStatusException     |com.microsoft.bingads.V11.reporting         |This exception is thrown if the ReportingServiceManager failed to get the download operation status after multiple retries.         
CouldNotSubmitReportingDownloadException     |com.microsoft.bingads.V11.reporting         |This exception is thrown by the ReportingServiceManager when the SubmitGenerateReport service operation that it called does not return a valid response. 
ReportingOperationCouldNotBeCompletedException     |com.microsoft.bingads.V11.reporting         |This exception is thrown if an attempt was made to poll for a completed reporting results file and the reporting service returns a failed status.   
ReportingOperationInProgressException     |com.microsoft.bingads.V11.reporting         |This exception is thrown if an attempt was made to download a reporting results file that is not yet available. 
     
Some exceptions are only returned when using *BulkServiceManager* (using com.microsoft.bingads.bulk or com.microsoft.bingads.V11.bulk) or ReportingServiceManager (using com.microsoft.bingads.V11.reporting). The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration for the *BulkServiceManager* when calling the *uploadFileAsync*, *downloadFileAsync*, or *trackAsync* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples in the sections above. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Likewise, the *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration for the *ReportingServiceManager* when calling the *uploadEntitiesAsync*, *downloadEntitiesAsync*, *uploadFileAsync*, *downloadFileAsync* or *trackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples in the sections above. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error.  

## <a name="sandbox"></a>Configuring Sandbox
To use the [Sandbox](../guides/sandbox.md) environment, create a new text file named *bingads.properties* within your project source root directory e.g. **ProjectName\src\bingads.properties** and add the following text. The following are the complete contents of the *bingads.properties* file. If the sandbox environment setting is malformed or missing, the default environment is production.

```java
environment=Sandbox
```

You can also set the *apiEnvironment* parameter of individual *BulkServiceManager*, *ServiceClient*, and *ReportingServiceManager* instances. Setting the *apiEnvironment* overrides the global setting only for the specified service client instance or instances. Unless otherwise intended, you should be careful not to inadvertently configure a mixed set of environments.    

```java
BulkServiceManager BulkService = new BulkServiceManager(authorizationData, ApiEnvironment.SANDBOX);

ServiceClient<ICustomerManagementService> CustomerService = 
    new ServiceClient<ICustomerManagementService>(
        authorizationData,
        ApiEnvironment.SANDBOX,
        ICustomerManagementService.class
    );
    
ReportingServiceManager ReportingService = new ReportingServiceManager(authorizationData, ApiEnvironment.SANDBOX);
```

Sandbox does not support OAuth, so you must use *PasswordAuthentication*.

```java
AuthorizationData authorizationData = new AuthorizationData();
authorizationData.setDeveloperToken("DeveloperTokenGoesHere");
PasswordAuthentication passwordAuthentication = 
    new PasswordAuthentication("UserNameGoesHere", "PasswordGoesHere");
authorizationData.setAuthentication(passwordAuthentication);

```

## See Also
[Sandbox](../guides/sandbox.md)  
[Bing Ads Code Examples](../guides/code-examples.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

