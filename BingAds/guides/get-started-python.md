---
title: "Get Started Using Python with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
dev_langs:
  - python
---
# Get Started Using Python with Bing Ads Services
To get started developing Bing Ads applications with Python, [install the SDK](#installation) and either start with the [provided examples](https://github.com/BingAds/BingAds-Python-SDK) or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-java.md) or [Desktop](../guides/walkthrough-desktop-application-python.md) application. You can also browse the [Bing Ads Code Examples](../guides/code-examples.md) gallery. The examples have been developed with the Bing Ads Python SDK in the environment described below. Your custom configuration may vary.

-   [Setting Up the Development Environment](#requirements)  
-   [Installing the SDK](#installation)  
-   [Walkthroughs](#walkthrough)  
-   [Using AuthorizationData](#authorizationdata)  
-   [Using OAuth](#oauth)  
-   [Using ServiceClient](#serviceclient)  
-   [Using BulkServiceManager](#bulkservicemanager)  
-   [Using ReportingServiceManager](#reportingservicemanager)  
-   [Using Suds](#suds)  
-   [Exception Handling](#exceptionhandling)  
-   [Configuring Sandbox](#sandbox)  

## <a name="requirements"></a>Setting Up the Development Environment

### Credentials
You need user credentials with access to Bing Ads either in production or sandbox. You also need a developer token. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) in production, the Microsoft account user must [sign up](https://secure.azure.bingads.microsoft.com/Auth) or [manage](../guides/customer-accounts.md#managingusers) an existing Bing Ads account. You also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Using OAuth](#oauth) below.

For a web application, you will need to deploy to a server with a publicly available redirection URL. For more information, see [Walkthrough: Bing Ads Web Application in Python](../guides/walkthrough-web-application-java.md).

### Tools
The Python Examples for Bing Ads are developed with the [Python Tools for Visual Studio (PTVS)](http://pytools.codeplex.com/) on [Visual Studio Community](https://www.visualstudio.com/vs/community/).

### Python Interpreter
The Bing Ads Python SDK supports Python 2.6, 2.7, 3.3, and 3.4. You should install and run one of the supported versions.

### Dependencies
The Bing Ads Python SDK uses the [suds-jurko-0.6](https://bitbucket.org/jurko/suds) library as a proxy for all of Bing Ads web services. For more information about using Suds with Bing Ads, see [Using Suds](#suds).

## <a name="installation"></a>Installing the SDK
To install the Bing Ads Python SDK for the first time, run the following either from your IDE or command line prompt.

```powershell
pip.exe install bingads
```
To confirm that the Bing Ads Python SDK is installed, run the following. You should see ?bingads (&lt;version&gt;)? in the output list.

```powershell
pip.exe list
```
If you already have the Bing Ads Python SDK installed, you can run this command to get the latest bits.

```powershell
pip.exe install --upgrade bingads
```

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads Python SDK installed, you can either download the examples from [GitHub](https://github.com/BingAds/BingAds-Python-SDK) or follow one of the application walkthroughs for a [Walkthrough: Bing Ads Web Application in Python](../guides/walkthrough-web-application-java.md) or [Walkthrough: Bing Ads Desktop Application in Python](../guides/walkthrough-desktop-application-python.md) application.

## <a name="authorizationdata"></a>Using AuthorizationData
You must initialize a new instance of *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager* with *AuthorizationData*. The class contains properties that Bing Ads uses to authorize a user. The *ServiceClient*, *BulkServiceManager*, and *ReportingServiceManager* classes handle common request header fields for you, allowing you to specify the *Authentication*, *customer_id*, *account_id*, and *developer_token* properties in the *AuthorizationData* object once for each service. For more information, see [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).

The following code block shows how to create an instance of *AuthorizationData* and set its *Authentication*, *customer_id*, *account_id*, and *developer_token* properties.

```python
authorization_data = AuthorizationData(
    authentication = <AuthenticationGoesHere>,
    customer_id = <CustomerIdGoesHere>,
    account_id = <AccountIdGoesHere>,
    developer_token = '<DeveloperTokenGoesHere>'
)
```
The *Authentication* property must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant*, *OAuthDesktopMobileImplicitGrant*, or *PasswordAuthentication*. When *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager* call Bing Ads services, they set the *AuthenticationToken* header element for each service request message to the value of the *AccessToken* property of your Authentication-derived instance. For more information, see [Service Request Header](../guides/authentication-oauth.md#serviceheaders), [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager)

Some services such as Customer Management do not accept *customer_id* and *account_id* headers, so they will be ignored if you specified them in the *AuthorizationData* object.

## <a name="oauth"></a>Using OAuth
The OAuth classes in the SDK abstract the low level user authorization details, so you can focus at a high level on your security requirements. The SDK objects take care of low level details such as formatting the authorization and redirect URIs and setting the request headers.

To use OAuth with the Bing Ads Python SDK, the *Authentication* property of your AuthorizationData object must be set to an Authentication-derived class such as *OAuthWebAuthCodeGrant*, *OAuthDesktopMobileAuthCodeGrant* or *OAuthDesktopMobileImplicitGrant*. For repeat or long term authentication, you should follow the authorization code grant flow for obtaining an access token. This is a standard OAuth 2.0 flow and is defined in detail in the [Authorization Code Grant section of the OAuth 2.0 spec](http://tools.ietf.org/html/draft-ietf-oauth-v2-15#section-4.1). For more information both about authorization code and implicit grant flows, see [Authentication with OAuth](../guides/authentication-oauth.md).

1.  Create an instance of *OAuthWebAuthCodeGrant*, that will be used to manage Microsoft Account user authorization. Replace *CLIENT_ID*, *CLIENT_SECRET*, and *REDIRECTION_URI* with the values configured in [Registering Your Application](../guides/authentication-oauth.md#registerapplication).

    ```python
    oauth_web_auth_code_grant = OAuthWebAuthCodeGrant(
        client_id=CLIENT_ID,
        client_secret=CLIENT_SECRET,
        redirection_uri=REDIRECTION_URI
    )
    
    # It is recommended that you specify a non guessable 'state' request parameter to help prevent
    # cross site request forgery (CSRF). 
    oauth_web_auth_code_grant.state="ClientStateGoesHere"
    ```

2.  Request user consent by connecting to the Microsoft Account authorization endpoint through a web browser control. Call the *getAuthorizationEndpoint* method of the *OAuthWebAuthCodeGrant* instance that you created in the earlier step, and send the redirect response.

    ```python
    oauth_web_auth_code_grant.get_authorization_endpoint()
    ```
    
    The user will be prompted through the Microsoft Account authorization web browser control to grant permissions for your application to manage their Bing Ads accounts.
    
    The authorization service calls back to your application with the redirection URI, which includes an authorization code if the user authorized your application to manage their Bing Ads accounts. For example the callback Url includes an authorization code as follows if the user granted permissions for your application to manage their Bing Ads accounts: *https://contoso.com/redirect/?code=CODE&state=ClientStateGoesHere*. If the user granted your application permissions to manage their Bing Ads accounts, you should use the code right away in the next step. The short duration of the authorization code, for example 5 minutes, is subject to change.
    
    If the user denied your application permissions to manage their Bing Ads accounts, the callback URI includes an error and error description field as follows: *REDIRECTURI?error=access_denied&error_description=ERROR_DESCRIPTION&state=ClientStateGoesHere*.

3.  Use the authorization code to request the *access_token*, *refresh_token*, and *access_token_expires_in_seconds* values from the *oauth_tokens* property of your *OAuthWebAuthCodeGrant* instance. Pass the full callback Url to the *request_oauth_tokens_by_response_uri* method of your *OAuthWebAuthCodeGrant* instance. This method uses the authorization code fragment to request the access token and refresh token.

    ```python
    if oauth_web_auth_code_grant.state != "ClientStateGoesHere":
       raise Exception("The OAuth response state does not match the client request state.")

    oauth_web_auth_code_grant.request_oauth_tokens_by_response_uri(RESPONSE_URI)
    oauth_tokens = oauth_web_auth_code_grant.oauth_tokens
    access_token = oauth_tokens.access_token
    ```
       
    If this step succeeded, your application has permissions to manage the user's Bing Ads accounts. To call Bing Ads services, you should initialize either *ServiceClient*, *BulkServiceManager*, and *ReportingServiceManager* with *AuthorizationData* that contains your *OAuthWebAuthCodeGrant* instance.
    
    For more information, see [Using AuthorizationData](#authorizationdata), [Using ServiceClient](#serviceclient), [Using BulkServiceManager](#bulkservicemanager), and [Using ReportingServiceManager](#reportingservicemanager).
    
4.  When calling Bing Ads services with *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager*, each instance will refresh your access token automatically if they detect the AuthenticationTokenExpired (109) error code. It is important to save the most recent refresh token whenever new OAuth tokens are received. You will want to register a callback function to automatically save the refresh token anytime it is refreshed. For example if you defined have a save_refresh_token() method that securely stores your refresh token, set the authentication token_refreshed_callback property of each *OAuthWebAuthCodeGrant* instance.

    ```python
    oauth_web_auth_code_grant.token_refreshed_callback=save_refresh_token
    ```
        
    You can also get the *AccessToken*, *RefreshToken*, and *ExpiresIn* values from the *OAuthTokens* property of your *OAuthWebAuthCodeGrant* instance by calling *request_oauth_tokens_by_refresh_token*.
    
    ```python
    if refresh_token is not None:
        oauth_web_auth_code_grant.request_oauth_tokens_by_refresh_token(refresh_token)
    ```
  
    > [!NOTE]
    > Whereas the refresh token parameter does not have a defined expiration period, you should expect it to last several months. 
    
    You may need to start again from Step 1 and request user consent if, for example the Microsoft Account user changed their password, removed a device from their list of trusted devices, or removed permissions for your application to authenticate on their behalf.

## <a name="serviceclient"></a>Using ServiceClient
To call the corresponding methods of a Bing Ads service, you can use an instance of the *ServiceClient* class and set its *service* property to one of the following string values.

-   *AdInsightService*
-   *BulkService*
-   *CampaignManagementService*
-   *CustomerBillingService*
-   *CustomerManagementService*
-   *ReportingService*

The *ServiceClient* class handles common request header fields for you, allowing to specify the *Authentication*, *customer_id*, *account_id*, and *developer_token* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

For example the following code shows how to use the Customer Management service to get the current authenticated user.

```python
customer_service = ServiceClient(
    'CustomerManagementService', 
    authorization_data=authorization_data, 
    environment = ENVIRONMENT,
)

user = customer_service.GetUser(UserId = None).User
```
You can pass Suds factory created objects to each service client, for example Campaign and TextAd. For more information, see [Using Suds](#suds).

## <a name="bulkservicemanager"></a>Using BulkServiceManager
Take advantage of the [Bulk service](~/bulk/bulk-service-reference.md) to efficiently manage ads and keywords for all campaigns in an account. The SDK provides classes to accelerate productivity for downloading and uploading entities. For example the *download_file* method of the *BulkServiceManager* class will submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. Use the *BulkFileReader* class instead of writing a file parser to read the download results. The *BulkFileReader* provides access to the bulk file records in *BulkEntity* derived classes, which contain data objects and values sets corresponding to the [Campaign Management service](~/campaign-management/campaign-management-service-reference.md).

The *BulkServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *customer_id*, *account_id*, and *developer_token* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *BulkServiceManager* automatically polls for the result file in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *poll_interval_in_milliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *BulkServiceManager* will poll in the following sequence of minutes: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *BulkServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration by passing a value for the *timeout_in_milliseconds* parameter to the *upload_entities*, *download_entities*, *upload_file*, *download_file*, or *track* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples below. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. 

The *BulkServiceManager* supports the following workflows.

-   You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with BulkServiceManager](#backgroundcompletion).

-   You can submit a download or upload request and then poll until the result file is ready to download. For more information, see [Submit and Download with BulkServiceManager](#submitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. For more information, see [Download Results with BulkServiceManager](#downloadresults).

-   If you are migrating from a deprecated bulk file format version, you can use an instance of *ServiceClient*, where its *service* property is set to *BulkService*, to upload and download campaigns using any format version [Bulk File Schema](~/bulk/bulk-file-schema.md). The low level approach requires that you submit your download or upload, poll until the results are available, and then download the results file. For more information, see [Using ServiceClient](#serviceclient) and [Bulk Download and Upload](../guides/bulk-download-upload.md).

### <a name="backgroundcompletion"></a>Background Completion with BulkServiceManager
You can submit a download or upload request and the *BulkServiceManager* will automatically return results. The *BulkServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

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

### <a name="submitdownload"></a>Submit and Download with BulkServiceManager
Submit the download request and then use the BulkDownloadOperation result to track status yourself using *get_status*.

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

### <a name="downloadresults"></a>Download Results with BulkServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download or upload request identifier and use it to download the result file. Use the *track* method to indicate that the application should wait to ensure that the download status is completed.

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

## <a name="reportingservicemanager"></a>Using ReportingServiceManager
The SDK provides proxy classes to the service operations, data objects, and value sets defined for the [Reporting](~/reporting/reporting-service-reference.md) service.
It also provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.

The *ReportingServiceManager* class handles common request header fields for you, allowing to specify the *Authentication*, *CustomerId*, *AccountId*, and *DeveloperToken* properties in the *AuthorizationData* object once for each service. For more information, see [Using AuthorizationData](#authorizationdata).

The *ReportingServiceManager* automatically polls in 1000 millisecond intervals for the first five attempts, and that behavior is not configurable. The *poll_interval_in_milliseconds* property determines the time interval between each polling attempt after the initial five attempts. The default value is 5000, so if you do not set this value the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 10, 15, 20, and so on. If you set this value to 10000, the *ReportingServiceManager* will poll in the following sequence: 1, 2, 3, 4, 5, 15, 25, 35, and so on. The minimum poll interval is 1000, and if you specify a value less than 1000 an exception will be thrown.

The *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration by passing a value for the *timeout_in_milliseconds* parameter to the *download_file* or *track* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples below. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error.

The *ReportingServiceManager* supports the following workflows.

-   You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling. For more information, see [Background Completion with ReportingServiceManager](#reportingbackgroundcompletion).

-   You can submit a download request and then poll until the result file is ready to download. For more information, see [Submit and Download with ReportingServiceManager](#reportingsubmitdownload).

-   If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. For more information, see [Download Results with ReportingServiceManager](#reportingdownloadresults).

### <a name="reportingbackgroundcompletion"></a>Background Completion with ReportingServiceManager
You can submit a download request and the *ReportingServiceManager* will automatically return results. The *ReportingServiceManager* abstracts the details of checking for result file completion, and you don't have to write any code for results polling.

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

### <a name="reportingsubmitdownload"></a>Submit and Download with ReportingServiceManager
Submit the download request and then use the ReportingDownloadOperation result to track status yourself using get_status().

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

### <a name="reportingdownloadresults"></a>Download Results with ReportingServiceManager
If for any reason you have to resume from a previous application state, you can use an existing download request identifier and use it to download the result file. Use track() to indicate that the application should wait to ensure that the download status is completed.

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

## <a name="suds"></a>Using Suds
The Bing Ads Python SDK uses the *suds-jurko* SOAP SDK to instantiate programming elements for the Bing Ads API i.e., service operations, data objects, and value sets. You will pass Suds factory objects via either a *ServiceClient*, *BulkServiceManager*, or *ReportingServiceManager* class. Since Suds is included as an SDK dependency, you can use Suds directly to call any of the Bing Ads web services.

Please keep in mind the following rules, suggestions, and tips related to Suds in the Bing Ads Python SDK.

-   One of the most common exceptions we hear about is *ERROR:suds.resolver:(ClassGoesHere) not-found*. Usually this can be resolved by using the namespace prefix for the Suds object.

-   To discover all SOAP objects with namespace prefix that are available for each service, you can print the soap client. For example, the following statements will return Campaign, AdGroup, ExpandedTextAd, and Keyword, among others.

    ```python
    campaign_service = ServiceClient(
        service='CampaignManagementService', 
        authorization_data=authorization_data, 
        environment = ENVIRONMENT,
        version = 11,
    )
    print campaign_service.soap_client
    ```

-   For many objects passed to the campaign management service via Suds you can create dictionary objects. 
               From a performance perspective, the dictionary approach is faster than the alternative *service.factory.create* method.

    ```python
    ad_groups = {
        'AdGroup':
            [
                {
                    'Name': "Women's Shoe Sale",
                    'AdDistribution': 'Search',
                    'EndDate': {
                        'Day': '31',
                        'Month': '12',
                        'Year': strftime("%Y", gmtime())
                    },
                    'SearchBid': {
                        'Amount': 0.09
                    },
                    'Language': 'English'
                },
            ]
        }
    ```

-   For derived types such as [ExpandedTextAd](~/campaign-management/expandedtextad.md), [NegativeKeyword](~/campaign-management/negativekeyword.md), and [NegativeKeywordList](~/campaign-management/negativekeywordlist.md), the Suds library requires that you use factory.create.

    ```python
    ads = campaign_service.factory.create('ArrayOfAd')
    expanded_text_ad=campaign_service.factory.create('TextAd')
    expanded_text_ad.TitlePart1='Contoso'
    expanded_text_ad.TitlePart2='Fast & Easy Setup'
    expanded_text_ad.Text='Huge Savings on red shoes.'
    expanded_text_ad.Path1='seattle'
    expanded_text_ad.Path2='shoe sale'
    expanded_text_ad.Type='ExpandedText'
    expanded_text_ad.Status=None
    expanded_text_ad.EditorialStatus=None

    # With FinalUrls you can separate the tracking template, custom parameters, and 
    # landing page URLs.
    final_urls=campaign_service.factory.create('ns4:ArrayOfstring')
    final_urls.string.append('http://www.contoso.com/womenshoesale')
    expanded_text_ad.FinalUrls=final_urls

    # Final Mobile URLs can also be used if you want to direct the user to a different page 
    # for mobile devices.
    final_mobile_urls=campaign_service.factory.create('ns4:ArrayOfstring')
    final_mobile_urls.string.append('http://mobile.contoso.com/womenshoesale')
    expanded_text_ad.FinalMobileUrls=final_mobile_urls

    # You could use a tracking template which would override the campaign level
    # tracking template. Tracking templates defined for lower level entities 
    # override those set for higher level entities.
    # In this example we are using the campaign level tracking template.
    expanded_text_ad.TrackingUrlTemplate=None,

    # Set custom parameters that are specific to this ad, 
    # and can be used by the ad, ad group, campaign, or account level tracking template. 
    # In this example we are using the campaign level tracking template.
    url_custom_parameters=campaign_service.factory.create('ns0:CustomParameters')
    parameters=campaign_service.factory.create('ns0:ArrayOfCustomParameter')
    custom_parameter1=campaign_service.factory.create('ns0:CustomParameter')
    custom_parameter1.Key='promoCode'
    custom_parameter1.Value='PROMO' + str(index)
    parameters.CustomParameter.append(custom_parameter1)
    custom_parameter2=campaign_service.factory.create('ns0:CustomParameter')
    custom_parameter2.Key='season'
    custom_parameter2.Value='summer'
    parameters.CustomParameter.append(custom_parameter2)
    url_custom_parameters.Parameters=parameters
    expanded_text_ad.UrlCustomParameters=url_custom_parameters

    ads.Ad.append(expanded_text_ad)
    ```

-   Any non-primitive elements must be specified for the Suds client e.g. *EditorialStatus* of type [AdEditorialStatus](~/campaign-management/adeditorialstatus.md), even though the Bing Ads services do not require such elements.

-   Bing Ads Campaign Management service operations require that if you specify a non-primitives, it must be one of the values defined by the service i.e. it cannot be a nil element. Since Suds requires non-primitives and Bing Ads won't accept nil elements in place of an enum value, you must either set the non-primitives or they must be set to None. Also note that if the element is ready only you must set it to *None*. For example set *expanded_text_ad.EditorialStatus=None*. 

To call the corresponding methods of a Bing Ads service, you can use an instance of the *ServiceClient* class and pass the Suds factory object. For more information, see [Using ServiceClient](#serviceclient).

## <a name="exceptionhandling"></a>Exception Handling
One of the most common exceptions we hear about is *ERROR:suds.resolver:(ClassGoesHere) not-found*. Usually this can be resolved by using the namespace prefix for the Suds object. For more information see [Using Suds](#suds).

In addition to handling Python platform exceptions, your application should be prepared to handle Bing Ads API service level exceptions and Bing Ads Python SDK wrapper exceptions. 

Bing Ads API service level exceptions include AdApiFaultDetail, ApiBatchFault, ApiFault, ApiFaultDetail, and EditorialApiFaultDetail. For more information, see [Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md). 

You should also handle the following Bing Ads Python SDK exceptions, which abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

Exception  |Namespaces  |Description  
---------|---------|---------     
BulkException     |BingAds.V11.Bulk         |This exception is thrown if an attempt was made to poll for a completed bulk results file and the bulk service returns a failed status.
BulkDownloadException     |BingAds.V11.Bulk         |This exception is thrown if timeout occurs while attempting to download a bulk file.
BulkUploadException     |BingAds.V11.Bulk         |This exception is thrown if timeout occurs while attempting to download a bulk upload results file.
EntityReadException     |BingAds.V11.Bulk         |This exception is thrown when attempting to read entities from a bulk file using BulkFileReader. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example the bulk file that you are attempting to read from might have an invalid value in one of the fields.
EntityWriteException     |BingAds.V11.Bulk         |This exception is thrown when attempting to write entities to a bulk file using BulkFileWriter. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid value for one of the upload entities.
FileDownloadException     |BingAds         |This exception is thrown if timeout occurs while attempting to download a bulk upload results file.  
FileUploadException     |BingAds         |This exception is thrown if timeout occurs while attempting to upload a bulk file.      
OAuthTokenRequestException     |BingAds         |This exception is thrown if an error was returned from the Microsft Account authorization server. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid client ID. 
ReportingException     |BingAds.V11.Reporting         |This exception is thrown if an attempt was made to poll for a completed reporting results file and the reporting service returns a failed status.  
ReportingDownloadException     |BingAds.V11.Reporting         |This exception is thrown if timeout occurs while attempting to download a reporting results file.  
SdkException      |BingAds         |The base exception class for the Bing Ads Python SDK. This exception is never raised.
TimeoutException      |BingAds         |This exception is thrown if timeout occurs.
     
Some exceptions are only returned when using *BulkServiceManager* (using BingAds.Bulk or BingAds.V11.Bulk) or ReportingServiceManager (using BingAds.V11.Reporting). The *BulkServiceManager* will automatically retry upload, download, and polling operations up to the maximum timeout duration that you specified. You can set the maximum retry timeout duration for the *BulkServiceManager* by passing a value for the *timeout_in_milliseconds* parameter to the *upload_entities*, *download_entities*, *upload_file*, *download_file*, or *track* operations, as shown in the [Background Completion](#backgroundcompletion), [Submit and Download](#submitdownload), and [Download Results](#downloadresults) examples in the sections above. If no timeout is specified, the *BulkServiceManager* will continue to retry until the server returns a timeout or internal error. Likewise, the *ReportingServiceManager* will automatically retry download and polling operations up to the maximum timeout duration that you specify. You can set the maximum retry timeout duration for the *ReportingServiceManager* by passing a value for the *timeout_in_milliseconds* parameter to the *download_file* or *track* operations, as shown in the [Background Completion](#reportingbackgroundcompletion), [Submit and Download](#reportingsubmitdownload), and [Download Results](#reportingdownloadresults) examples in the sections above. If no timeout is specified, the *ReportingServiceManager* will continue to retry until the server returns a timeout or internal error. 


## <a name="sandbox"></a>Configuring Sandbox
To use the [Sandbox](../guides/sandbox.md) environment set the environment property of each *ServiceClient* instance to 'sandbox' (not case sensitive). If the sandbox environment setting is malformed or missing, the default environment is production.

```python
bulk_service_manager = BulkServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds = 5000, 
    environment = 'sandbox',
    version = 11,
)

customer_service = ServiceClient(
    'CustomerManagementService', 
    authorization_data=authorization_data, 
    environment = 'sandbox',
    version = 11,
)

reporting_service_manager = ReportingServiceManager(
    authorization_data=authorization_data, 
    poll_interval_in_milliseconds = 5000, 
    environment = 'sandbox',
    version = 11,
)
```
> [!NOTE]
> To switch between sandbox and production, you must create a new *ServiceClient* or *BulkServiceManager* instance. Once initialized you may not reset the environment property of the *ServiceClient* or *BulkServiceManager*.

