---
title: "Get Started Using C# with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Get Started Using C# with Bing Ads Services
To get started developing Bing Ads applications with a .NET language, [install the SDK](#installation) and either start with the [provided examples](~/guides/code-examples.md) or follow one of the application walkthroughs for a [Web](~/guides/walkthrough-web-application-csharp.md) or [Desktop](~/guides/walkthrough-desktop-application-csharp.md) application. You can also browse the [Bing Ads Code Examples](../guides/code-examples.md) gallery. The examples have been developed with the Bing Ads .NET SDK in the environment described below. Your custom configuration may vary.

-   [Setting Up the Development Environment](#requirements)  
-   [Installing the SDK](#installation)  
-   [Walkthroughs](#walkthrough)  
-   [Using AuthorizationData](#authorizationdata)  
-   [Using OAuth](#oauth)  
-   [Using ServiceClient&lt;TService&gt;](#serviceclient)  
-   [Using BulkServiceManager](#bulkservicemanager)  
-   [Using ReportingServiceManager](#reportingservicemanager)  
-   [Exception Handling](#exceptionhandling)  
-   [Configuring Sandbox](#sandbox)

## <a name="requirements"></a>Setting Up the Development Environment
You need user credentials with access to Bing Ads either in production or sandbox. You also need a developer token. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) in production, the Microsoft account user must [sign up](https://secure.azure.bingads.microsoft.com/Auth) or [manage](../guides/customer-accounts.md#managingusers) an existing Bing Ads account. You also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Using OAuth](#oauth) below.

The examples are developed and run with [Visual Studio Community](https://www.visualstudio.com/vs/community/). To use the Bing Ads .NET SDK, you must install and use .NET Framework 4.5 or later. In Visual Studio go to the project **Properties** -&gt; **Application** -&gt; **Target framework** and make sure that **.NET Framework 4.5** is selected.

## <a name="installation"></a>Installing the SDK
Install the Bing Ads .NET SDK through [NuGet](https://www.nuget.org/packages/Microsoft.BingAds.SDK/), either through the [Manage NuGet Packages](#managenuget) user interface, or through the [Package Manager Console](#packagemanager). For information about installing NuGet, see [http://docs.nuget.org](http://docs.nuget.org/docs/start-here/installing-nuget).

> [!NOTE]
> The NuGet installation includes the following required libraries.
> 
> -   *Microsoft.BingAds.dll* - The Bing Ads .NET SDK. For more information, see [Bing Ads .NET SDK Reference](../guides/net-sdk-reference.md).
> -   *System.Runtime.Serialization.dll*
> -   *System.ServiceModel.dll*

### <a name="managenuget"></a>Manage NuGet Packages

1.  Right-click on your Visual Studio project and select **Manage NuGet Packages**.

2.  Click the **Online** package category and search for *Bing Ads SDK*.

3.  Click the **Install** button for *Bing Ads SDK*.

### <a name="packagemanager"></a>Package Manager Console

1.  Click on **Tools** -&gt; **NuGet Package Manager** -&gt; **Package Manager Console**.

2.  Within the console command line, type Install-Package Microsoft.BingAds.SDK.

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads .NET SDK installed, you can either browse the [Bing Ads Code Examples](../guides/code-examples.md) in C# or follow one of the application walkthroughs for a [Web](~/guides/walkthrough-web-application-csharp.md) or [Desktop](~/guides/walkthrough-desktop-application-csharp.md) application.

## <a name="authorizationdata"></a>Using AuthorizationData
You must initialize a new instance of *ServiceClient&lt;TService&gt;*, *BulkServiceManager* or *ReportingServiceManager* with *AuthorizationData*. The class contains properties that Bing Ads uses to authorize a user. The *ServiceClient&lt;TService&gt;*, *BulkServiceManager* and *ReportingServiceManager* classes handle common request header fields for you, allowing you to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using ServiceClient&lt;TService&gt;](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

The following code block shows how to create an instance of *AuthorizationData* and set its *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties.

```csharp
var authorizationData = new AuthorizationData
{
    Authentication = <AuthenticationGoesHere>, 
    CustomerId = <CustomerIdGoesHere>,
    AccountId = <AccountIdGoesHere>,
    DeveloperToken = "<DeveloperTokenGoesHere>"
};
```
The *Authentication* property must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant*, *OAuthDesktopMobileImplicitGrant*, or *PasswordAuthentication*.

When *ServiceClient&lt;TService&gt;*, *BulkServiceManager* or *ReportingServiceManager* call Bing Ads services, they set the *AuthenticationToken* header element for each service request message to the value of the *AccessToken* property of your Authentication-derived instance. For more information, see [Service Request Header](../guides/authentication-oauth.md#serviceheaders), [Using ServiceClient&lt;TService&gt;](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

Some services such as Customer Management do not accept *CustomerId* and *CustomerAccountId* headers, so they will be ignored if you specified them in the *AuthorizationData* object.

## <a name="oauth"></a>Using OAuth
The OAuth classes in the SDK abstract the low level user authorization details, so you can focus at a high level on your security requirements. The SDK objects take care of low level details such as formatting the authorization and redirect URIs, setting the request headers, and parsing the redirect traffic and response stream.

To use OAuth with the Bing Ads .NET SDK, the *Authentication* property of your *AuthorizationData* object must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant* or *OAuthDesktopMobileImplicitGrant*. For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token. This is a standard OAuth 2.0 flow and is defined in detail in the [Authorization Code Grant section of the OAuth 2.0 spec](http://tools.ietf.org/html/draft-ietf-oauth-v2-15#section-4.1). The steps below describe the procedural workflow, and references code blocks from the [Walkthrough: Bing Ads Web Application in C&#35;](walkthrough-web-application-csharp.md). For more information both about authorization code and implicit grant flows, see [Authentication with OAuth](../guides/authentication-oauth.md).

1.  Create an instance of *OAuthWebAuthCodeGrant*, that will be used to manage Microsoft Account user authorization. Replace *ClientId*, *ClientSecret*, and *RedirectionUri* with the values configured in [Registering Your Application](../guides/authentication-oauth.md#registerapplication).

    ```csharp
    var oAuthWebAuthCodeGrant = new OAuthWebAuthCodeGrant(ClientId, ClientSecret, new Uri(RedirectionUri));
    
    // It is recommended that you specify a non guessable 'state' request parameter to help prevent
    // cross site request forgery (CSRF). 
    oAuthWebAuthCodeGrant.State = "ClientStateGoesHere";
    ```

2.  Request user consent by connecting to the Microsoft Account authorization endpoint through a web browser control. Call the *GetAuthorizationEndpoint* method of the *OAuthWebAuthCodeGrant* instance that you created in the earlier step.

    ```csharp
    return Redirect(oAuthWebAuthCodeGrant.GetAuthorizationEndpoint().ToString());
    ```
    
    The user will be prompted through the Microsoft Account authorization web browser control to grant permissions for your application to manage their Bing Ads accounts.
    
    The authorization service calls back to your application with the redirection URI, which includes an authorization code if the user authorized your application to manage their Bing Ads accounts. For example the callback Url includes an authorization code as follows if the user granted permissions for your application to manage their Bing Ads accounts: *https://contoso.com/redirect/?code=CODE&state=ClientStateGoesHere*. If the user granted your application permissions to manage their Bing Ads accounts, you should use the code right away in the next step. The short duration of the authorization code, for example 5 minutes, is subject to change.
    
    If the user denied your application permissions to manage their Bing Ads accounts, the callback URI includes an error and error description field as follows: *REDIRECTURI?error=access_denied&error_description=ERROR_DESCRIPTION&state=ClientStateGoesHere*.

3.  Use the authorization code to request the access token and refresh token. Pass the full callback Url to the *RequestAccessAndRefreshTokensAsync* method of your *OAuthWebAuthCodeGrant* instance. This method uses the authorization code fragment to request the access token and refresh token.

    ```csharp
    if (Request["code"] != null)
    {
        // If you set the client state in step #1 above, verify that the authorization
        // server returns the same value before proceeding.
        if (oAuthWebAuthCodeGrant.State != "ClientStateGoesHere")
            throw new HttpRequestException("The OAuth response state does not match the client request state.");
       
        await oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(Request.Url);
    }
    ```
    
    If this step succeeded, your application has permissions to manage the user's Bing Ads accounts. To call Bing Ads services, you should initialize either *ServiceClient&lt;TService&gt;*, *BulkServiceManager*, or *ReportingServiceManager* with *AuthorizationData* that contains your *OAuthWebAuthCodeGrant* instance.
    
    For more information, see [Using AuthorizationData](#authorizationdata), [Using ServiceClient&lt;TService&gt;](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

4.  When calling Bing Ads services with *ServiceClient&lt;TService&gt;*, *BulkServiceManager*, or *ReportingServiceManager*, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to subscribe to the *NewOAuthTokensReceived* event handler. 

    ```csharp
    oAuthWebAuthCodeGrant.NewOAuthTokensReceived += 
        (sender, args) => SaveRefreshToken(args.NewRefreshToken);
    ```
    
    You can also get the *AccessToken*, *RefreshToken*, and *ExpiresIn* values from the *OAuthTokens* property of your *OAuthWebAuthCodeGrant* instance by calling *RequestAccessAndRefreshTokensAsync*.
    
    ```csharp
    if (GetRefreshToken(out refreshToken))
    {
        oAuthWebAuthCodeGrant.RequestAccessAndRefreshTokensAsync(refreshToken);
    }
    ```
  
    > [!NOTE] 
    > Whereas the refresh token parameter does not have a defined expiration period, you should expect it to last several months. 
    
    You may need to start again from Step 1 and request user consent if, for example the Microsoft Account user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf.

## <a name="serviceclient"></a>Using ServiceClient&lt;TService&gt;
You can use an instance of the *ServiceClient&lt;TService&gt;* class to call any methods in the service, where TService is one of the following client service interfaces:

-   *IAdInsightService*  
-   *IBulkService*  
-   *ICampaignManagementService*  
-   *ICustomerBillingService*  
-   *ICustomerManagementService*  
-   *IReportingService*  

The *ServiceClient&lt;TService&gt;* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The primary method of the *ServiceClient&lt;TService&gt;* class is *CallAsync*. The *method* parameter is the delegate for the service operation that you want to call. The *request* parameter of this method must be a request message corresponding to the name of the service operation specified by the first request parameter. The request message must match the service operation that is specified as the delegate in the first request.

```csharp
public TResponse CallAsync<TRequest, TResponse>(
    Func<TService, TRequest, TResponse> method,
    TRequest request
)
```
The header elements that the *CallAsync* method sets will differ depending on the type of authentication specified in *AuthorizationData* object and the requirements of the service. For example if you use one of the OAuth classes such as *OAuthWebAuthCodeGrant*, the *AuthenticationToken* will be set by *CallAsync*, whereas the *UserName* and *Password* headers will remain empty. If you use *PasswordAuthentication*, the *UserName* and *Password* headers will be set by *CallAsync* instead of *AuthenticationToken*.

In the following sample, the method delegate is *(s, r) => s.GetUserAsync(r)* which takes a *GetUserRequest* message as the request parameter (*TRequest*) and returns a *GetUserResponse* message (*TResponse*).

```csharp
private async Task<User> GetUserAsync(long? userId)
{
    var request = new GetUserRequest
    {
        UserId = userId
    };

    return (await _customerService.CallAsync((s, r) => s.GetUserAsync(r), request)).User;
}
```
> [!NOTE]
> If you set the *AuthenticationToken*, *CustomerId*, *AccountId*, *DeveloperToken*, *UserName*, or *Password* header elements in this request parameter, they will be ignored. *ServiceClient&lt;TService&gt;* always uses the *AuthorizationData* provided with its initialization.

## <a name="bulkservicemanager"></a>Using BulkServiceManager
Take advantage of the [Bulk service](~/bulk/bulk-service-reference.md) to efficiently manage ads and keywords for all campaigns in an account. The SDK provides classes to accelerate productivity for downloading and uploading entities. For example the *DownloadFileAsync* method of the *BulkServiceManager* class will submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. Use the *BulkFileReader* class instead of writing a file parser to read the download results. The *BulkFileReader* provides access to the bulk file records in *BulkEntity* derived classes, which contain data objects and values sets corresponding to the [Campaign Management service](~/campaign-management/campaign-management-service-reference.md).

The *BulkServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *BulkServiceManager* automatically polls for the result file in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *BulkServiceManager* will poll in the following sequence of minutes: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *BulkServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration by passing a *CancellationToken* to the *UploadEntitiesAsync*, *DownloadEntitiesAsync*, *UploadFileAsync*, *DownloadFileAsync*, or *TrackAsync* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples below. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are uploading or downloading large files, you should consider setting the *UploadHttpTimeout* or *DownloadHttpTimeout* properties.  

The *BulkServiceManager* supports the following workflows.

-   You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with BulkServiceManager](#backgroundcompletion).  

-   You can submit a download or upload request and then poll until the result file is ready to download. For more information, see [Submit and Download with BulkServiceManager](#submitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. For more information, see [Download Results with BulkServiceManager](#downloadresults).

-   If you are migrating from a deprecated bulk file format version, you can use an *IBulkService* instance of *ServiceClient* to upload and download campaigns using any format version [Bulk File Schema](~/bulk/bulk-file-schema.md). The low level approach requires that you submit your download or upload, poll until the results are available, and then download the results file. For more information, see [Using ServiceClient&lt;TService&gt;](#serviceclient) and [Bulk Download and Upload](../guides/bulk-download-upload.md).
    
> [!NOTE]
> If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the file or directory limits. You can specify a different working directory for each *BulkServiceManager* instance. For details see [Working Directory and BulkServiceManager](#workingdirectory).

### <a name="backgroundcompletion"></a>Background Completion with BulkServiceManager
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

### <a name="submitdownload"></a>Submit and Download with BulkServiceManager
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

### <a name="downloadresults"></a>Download Results with BulkServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. Use TrackAsync to indicate that the application should wait to ensure that the download status is completed.

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

### <a name="workingdirectory"></a>Working Directory and BulkServiceManager
When using the *UploadEntitiesAsync* and *DownloadEntitiesAsync* SDK operations, you can work with the result entities in memory i.e. without reading from a result file. That said, the *BulkServiceManager* downloads the result file by default to the system temp directory. If you are using a hosted service such as Microsoft Azure you'll want to ensure you do not exceed the temp directory limits. There may be other reasons to use a custom working directory. You can specify a different working directory for each *BulkServiceManager* instance by setting the *WorkingDirectory* property and then calling the *CleanupTempFiles* operation after enumerating over the resulting entities in memory. You are also responsible for creating and removing any directories. 

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

    // The CleanupTempFiles method removes all files (not sub-directories) within the working directory, 
    // whether or not the files were created by this BulkServiceManager instance. 

    BulkService.CleanupTempFiles();
}
```

## <a name="reportingservicemanager"></a>Using ReportingServiceManager
The SDK provides proxy classes to the service operations, data objects, and value sets defined for the [Reporting](~/reporting/reporting-service-reference.md) service.

It also provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.

The *ReportingServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *ReportingServiceManager* automatically polls in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *StatusPollIntervalInMilliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration by passing a *CancellationToken* to the *DownloadFileAsync* or *TrackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples below. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. Separately if you are downloading large files, you should consider setting the *DownloadHttpTimeout* property.

The *ReportingServiceManager* supports the following workflows.

-   You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with ReportingServiceManager](#reportingbackgroundcompletion).

-   You can submit a download request and then poll until the result file is ready to download. For more information, see [Submit and Download with ReportingServiceManager](#reportingsubmitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. For more information, see [Download Results with ReportingServiceManager](#reportingdownloadresults).

### <a name="reportingbackgroundcompletion"></a>Background Completion with ReportingServiceManager
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

### <a name="reportingsubmitdownload"></a>Submit and Download with ReportingServiceManager
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

### <a name="reportingdownloadresults"></a>Download Results with ReportingServiceManager
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

## <a name="exceptionhandling"></a>Exception Handling
In addition to handling .NET framework exceptions, your application should be prepared to handle Bing Ads API service level exceptions and Bing Ads .NET SDK wrapper exceptions. 

Bing Ads API service level exceptions include AdApiFaultDetail, ApiBatchFault, ApiFault, ApiFaultDetail, and EditorialApiFaultDetail. For more information, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md). 

You should also handle the following Bing Ads .NET SDK exceptions, which abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

Exception  |Namespaces  |Description  
---------|---------|---------     
CouldNotDownloadResultFileException     |Microsoft.BingAds         |This exception is thrown by the internal SDK HttpService after a failed attempt to download a bulk or reporting result file. 
CouldNotUploadFileException     |Microsoft.BingAds        |This exception is thrown by the internal SDK HttpService after a failed attempt to upload a bulk file.     
OAuthTokenRequestException     |Microsoft.BingAds         |This exception is thrown if an error was returned from the Microsft Account authorization server. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid client ID. 
BulkOperationCouldNotBeCompletedException     |Microsoft.BingAds.V11.Bulk        |This exception is thrown if an attempt was made to poll for a completed bulk results file and the bulk service returns a failed status. 
BulkOperationInProgressException     |Microsoft.BingAds.V11.Bulk        |This exception is thrown if an attempt was made to download a bulk results file that is not yet available.
CouldNotGetBulkOperationStatusException     |Microsoft.BingAds.V11.Bulk         |This exception is thrown if the BulkServiceManager failed to get the upload or download operation status after multiple retries.   
CouldNotSubmitBulkDownloadException     |Microsoft.BingAds.V11.Bulk         |This exception is thrown by the BulkServiceManager when the DownloadCampaignsByAccountIds service operation that it called does not return a valid response.   
CouldNotSubmitBulkUploadException     |Microsoft.BingAds.V11.Bulk         |This exception is thrown by the BulkServiceManager when the GetBulkUploadUrl service operation that it called does not return a valid response.   
EntityReadException     |Microsoft.BingAds.V11.Bulk        |This exception is thrown when attempting to read entities from a bulk file using BulkFileReader. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example the bulk file that you are attempting to read from might have an invalid value in one of the fields.
EntityWriteException     |Microsoft.BingAds.V11.Bulk        |This exception is thrown when attempting to write entities to a bulk file using BulkFileWriter. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid value for one of the upload entities. 
CouldNotGetReportingDownloadStatusException     |Microsoft.BingAds.V11.Reporting         |This exception is thrown if the ReportingServiceManager failed to get the download operation status after multiple retries.         
CouldNotSubmitReportingDownloadException     |Microsoft.BingAds.V11.Reporting         |This exception is thrown by the ReportingServiceManager when the SubmitGenerateReport service operation that it called does not return a valid response. 
ReportingOperationCouldNotBeCompletedException     |Microsoft.BingAds.V11.Reporting         |This exception is thrown if an attempt was made to poll for a completed reporting results file and the reporting service returns a failed status.   
ReportingOperationInProgressException     |Microsoft.BingAds.V11.Reporting         |This exception is thrown if an attempt was made to download a reporting results file that is not yet available. 
     
Some exceptions are only returned when using *BulkServiceManager* (using Microsoft.BingAds.Bulk or Microsoft.BingAds.V11.Bulk) or ReportingServiceManager (using Microsoft.BingAds.V11.Reporting). The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration for the *BulkServiceManager* by passing a *CancellationToken* to the *UploadEntitiesAsync*, *DownloadEntitiesAsync*, *UploadFileAsync*, *DownloadFileAsync*, or *TrackAsync* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples in the sections above. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Likewise, the *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration for the *ReportingServiceManager* by passing a *CancellationToken* to the *DownloadFileAsync* or *TrackAsync* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples in the sections above. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. 


## <a name="sandbox"></a>Configuring Sandbox
Set the *BingAdsEnvironment* key to Sandbox within the *&lt;appSettings&gt;* node of your project root's *Web.config* ([Web](~/guides/walkthrough-web-application-csharp.md) application) or *App.config* ([Desktop](~/guides/walkthrough-desktop-application-csharp.md) application) file.

```csharp
<add key="BingAdsEnvironment" value ="Sandbox"/>
```

You can also set the *apiEnvironment* parameter of individual *BulkServiceManager*, *ServiceClient*, and *ReportingServiceManager* instances. Setting the *apiEnvironment* overrides the global setting only for the specified service client instance or instances. Unless otherwise intended, you should be careful not to inadvertently configure a mixed set of environments.    

```csharp
BulkServiceManager BulkService = new BulkServiceManager(authorizationData, ApiEnvironment.Sandbox);

ServiceClient<ICustomerManagementService> Service = new ServiceClient<ICustomerManagementService>(authorizationData, ApiEnvironment.Sandbox);
    
ReportingServiceManager ReportingService = new ReportingServiceManager(authorizationData, ApiEnvironment.Sandbox);
```

## See Also
[Sandbox](../guides/sandbox.md)  
[Bing Ads Code Examples](../guides/code-examples.md)    
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

