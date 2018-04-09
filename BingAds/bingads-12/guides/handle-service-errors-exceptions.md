---
title: "Handling Service Errors and Exceptions"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Learn about error handling and troubleshooting your application.
---
# Handling Service Errors and Exceptions
This article describes details on error handling and troubleshooting your application.

## <a name="faultoverview"></a>Fault Model Overview
When a Bing Ads service operation fails, it will return a service fault e.g., the Customer Management service can return [ApiFault](../customer-management-service/apifault.md). The fault exceptions include one or more error objects. The error objects contain the details of why the service operation failed and a code that uniquely identifies the error. For a list of error codes, see [Bing Ads Operation Error Codes](operation-error-codes.md).

Available fault and data objects vary per service. This table describes the fault model and links to error data objects for each service.

|Service|Description|
|-----------|---------------|
|Ad Insight|All ad insight operations may throw [AdApiFaultDetail](../ad-insight-service/adapifaultdetail.md) and [ApiFaultDetail](../ad-insight-service/apifaultdetail.md).|
|Bulk|All bulk operations may throw [AdApiFaultDetail](../bulk-service/adapifaultdetail.md) and [ApiFaultDetail](../bulk-service/apifaultdetail.md).|
|Campaign Management|All campaign management operations may throw [AdApiFaultDetail](../campaign-management-service/adapifaultdetail.md).<br /><br />Some campaign management operations may also throw [ApiFaultDetail](../campaign-management-service/apifaultdetail.md) or [EditorialApiFaultDetail](../campaign-management-service/editorialapifaultdetail.md).<br /><br />For more information, see [Campaign Management Data Objects](../campaign-management-service/campaign-management-data-objects.md).|
|Customer Billing|All customer billing operations may throw [AdApiFaultDetail](../customer-billing-service/adapifaultdetail.md) and [ApiFault](../customer-billing-service/apifault.md).<br /><br />Some customer billing operations may also throw [ApiBatchFault](../customer-billing-service/apibatchfault.md).|
|Customer Management|All customer management operations may throw [AdApiFaultDetail](../customer-management-service/adapifaultdetail.md) and [ApiFault](../customer-management-service/apifault.md).|
|Reporting|All reporting operations may throw *AdApiFaultDetail* and *ApiFaultDetail*.|

> [!NOTE]
> All fault objects are derived from the *ApplicationFault* object. The *ApplicationFault* object defines the *TrackingId* element, which uniquely identifies the log entry that contains the details of the API call. If you need to [contact support](http://go.microsoft.com/fwlink/?LinkId=517018), please provide the tracking ID with the date and time when you called the service operation. 

## <a name="partial-success"></a>Partial Success
Partial success means that when adding, updating, or deleting entities in batches of one or more, the operation may succeed for some and fail for part of the batch. 

### <a name="partial-success-bulk"></a>Partial Success With the Bulk Service
When you [upload](bulk-download-upload.md) records in a [Bulk file](../bulk-service/bulk-file-schema.md), the upload may succeed for some records and fail for others in the batch. When you call [GetBulkUploadUrl](../bulk-service/getbulkuploadurl.md) you can choose whether or not to receive errors in the upload results file. 

### <a name="partial-success-campaign-management"></a>Partial Success With the Campaign Management Service
For most entities, partial success is supported when calling [Campaign Management](../campaign-management-service/campaign-management-service-reference.md) service operations. For each list index where an entity was not added, the corresponding element will be null. The *PartialErrors* element represents an array of [BatchError](../campaign-management-service/batcherror.md) objects that contain details for any entities that were not successfully added, updated, or deleted. The list only includes a [BatchError](../campaign-management-service/batcherror.md) for unsuccessful attempts, and does not include null elements at the index of each successfully added entity. Similarly some operations return *NestedPartialErrors* as a list of [BatchErrorCollection](../campaign-management-service/batcherrorcollection.md), or a two dimensional [BatchError](../campaign-management-service/batcherror.md).

> [!NOTE]
> The [ApplyProductPartitionActions](../campaign-management-service/applyproductpartitionactions.md) operation includes *PartialErrors* in the response; however, partial success is not supported. Either the entire set of requested actions succeed and the *AdGroupCriterionIds* response list is fully populated, or all of them fail and the *PartialErrors* response list is fully populated. 

## <a name="commonerrors"></a>Common Errors
Runtime errors may be caught and handled. Documentation is available for potential error codes which may be observed. The following are some common errors that you may encounter.

### Code 105
Typically indicates usage of an incorrect username, password, or developer token for the target environment. For example your credentials may be valid in production, and when targeting sandbox you would observe code *105*.

### Code 106
Typically indicates that while the credentials are correct for the target environment, the user does not have access to one of the entities specified in the request. For example, calling *SubmitGenerateReport* where the specified user does not have permissions to the specified account identifier.

### HTTP 500
All Bing Ads services adhere to the Simple Object Access Protocol (SOAP) 1.1 specification whereby errors are returned with a HTTP 500 code. For example, see the following.

```http
HTTP/1.1 500 Internal Server Error
```
This is not in and of itself representative of an actionable code, and you should inspect the fault details for more information on the specific error.

## <a name="net-exceptions"><a/>.NET Exceptions
If you use the Bing Ads .NET [SDK](client-libraries.md), your application should be prepared to handle Bing Ads API [service level exceptions](#faultoverview), [WCF exceptions](#net-wcf-exceptions), and [Bing Ads .NET SDK](#net-sdk-exceptions) exceptions described below. 

For troubleshooting .NET applications, see [.NET SDK Troubleshooting](#net-troubleshooting).

### <a name="net-wcf-exceptions"></a>WCF Exceptions
Generic SOAP faults that are not specific to Bing Ads API may also be thrown, and should be caught by your application. For example, .NET applications may throw Windows Communication Foundation (WCF) exceptions such as Exception, TimeoutException, and CommunicationException. For information about exceptions that you should expect from WCF, see [Expected Exceptions](https://docs.microsoft.com/en-us/dotnet/framework/wcf/samples/expected-exceptions).

You should not call the *Close* method in the finally block to release the service object. The objection is that the *Close* method can throw exceptions. If *Close* throws an exception, you must call the *Abort* method to ensure that all resources are released; otherwise, you could be leaking resources on the server. The recommended practice is to call *Close* within the try block, and call *Abort* from the caught exceptions.

For the same reason, the use of the **using** statement is not recommended. For more information, see [Avoiding Problems with the Using Statement](https://docs.microsoft.com/en-us/dotnet/framework/wcf/samples/avoiding-problems-with-the-using-statement).

### <a name="net-sdk-exceptions"></a>.NET SDK Exceptions
The Bing Ads .NET SDK exceptions abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

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

### <a name="net-troubleshooting"></a>.NET SDK Troubleshooting
Unless there is a [known service issue](https://developers.bingads.microsoft.com/Support), typically when a call fails it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. 

#### <a name="net-troubleshooting-fiddler"></a>Fiddler Options
You can follow these steps to capture the SOAP envelopes from a .NET application using a third-party tool such as [Fiddler](http://fiddler2.com/get-fiddler). 
 - After installing Fiddler, export the Fiddler certificate from the root certificate store. 
 - Click **Tools** &gt; **Fiddler Options**. 
 - Select the **HTTPS** tab, and click the **Decrypt HTTPS traffic** check box. 
 - Click **OK**, and then follow the prompts to export the Fiddler certificate. 

## <a name="java-exceptions"><a/>Java Exceptions
If you use the Bing Ads Java [SDK](client-libraries.md), your application should be prepared to handle Bing Ads API [service level exceptions](#faultoverview) and [Bing Ads Java SDK](#java-sdk-exceptions) exceptions described below. 

For troubleshooting Java applications, see [Java SDK Troubleshooting](#java-troubleshooting).

### <a name="java-sdk-exceptions"></a>Java SDK Exceptions
The Bing Ads Java SDK exceptions abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

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

### <a name="java-troubleshooting"></a>Java SDK Troubleshooting
Unless there is a [known service issue](https://developers.bingads.microsoft.com/Support), typically when a call fails it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. 

#### <a name="java-troubleshooting-httptransportpipe"></a>HttpTransportPipe
To output the HTTP trace you can set the HttpTransportPipe *dump* property to "true" (string) as follows:
```java
System.setProperty("com.sun.xml.ws.transport.http.client.HttpTransportPipe.dump", "true");
```

#### <a name="java-troubleshooting-fiddler"></a>Fiddler Options
When it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. You can follow these steps to capture the SOAP envelopes from a Java application using a third-party tool such as [Fiddler](http://fiddler2.com/get-fiddler). 

1.  After installing Fiddler, export the Fiddler certificate from the root certificate store. Click **Tools** &gt; **Fiddler Options**. Select the **HTTPS** tab, and click the **Decrypt HTTPS traffic** check box. Click **OK**, and then follow the prompts to export the Fiddler certificate.

2.  Use the following command to import the certificate into the cacert store used by Java, for example execute from PowerShell as Administrator.

    ```powershell
    c:\Program Files\Java\jre6\bin>keytool -importcert -v -alias "Fiddler cert" -trustcacerts -keystore "C:\Program Files\Java\jdk1.8.0_20\jre\lib\security\cacerts" -storepass changeit -file <DesktopPathGoesHere>\FiddlerRoot.cer
    ```

3.  Add the following lines to your Java application.

    ```java
    System.setProperty("https.proxyHost", "127.0.0.1");
    System.setProperty("https.proxyPort", "8888");
    ```
    
#### <a name="java-troubleshooting-spring-cxf"></a>Spring Framework and Apache CXF Options
You can use the [Spring Framework](https://docs.spring.io/spring/docs/current/spring-framework-reference/html/overview.html) and [Apache CXF](http://cxf.apache.org/docs/index.html) to capture the SOAP envelopes, for example if you are running a Maven application in Eclipse.

1.  Set up the development environment as described in [Get Started Using Java with Bing Ads Services](get-started-java.md). 
   
2.  Edit pom.xml to include the *org.springframework* dependency. The following is a complete pom.xml example.
    ```xml
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <groupId>com.microsoft.bingads.examples</groupId>
      <artifactId>BingAdsDesktopApp</artifactId>
      <version>0.0.1-SNAPSHOT</version>
      <dependencies>
        <dependency>
          <groupId>com.microsoft.bingads</groupId>
          <artifactId>microsoft.bingads</artifactId>
          <version>11.12.1</version>
        </dependency>
        <dependency>
          <groupId>org.springframework</groupId>
          <artifactId>spring-context</artifactId>
          <version>4.2.6.RELEASE</version>
        </dependency>
      </dependencies>
    </project>
    ```
    > [!NOTE]
    > Version 11.12.1 of the Bing Ads Java SDK is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).
   
2.  Add cxf.xml to your project, and add the following xml.
    ```xml
    <beans xmlns="http://www.springframework.org/schema/beans"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xmlns:cxf="http://cxf.apache.org/core"
        xsi:schemaLocation="
        http://cxf.apache.org/core http://cxf.apache.org/schemas/core.xsd
        http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.0.xsd">
      <cxf:bus>
        <cxf:features>
          <cxf:logging/>
        </cxf:features>
      </cxf:bus> 
    </beans>
    ```
    
3.  Add the following lines to your Java application.

    ```java
    System.setProperty("https.proxyHost", "127.0.0.1");
    System.setProperty("https.proxyPort", "8888");
    ```

## <a name="php-exceptions"><a/>PHP Exceptions
If you use the Bing Ads PHP [SDK](client-libraries.md), your application should be prepared to handle Bing Ads API [service level exceptions](#faultoverview) and [Bing Ads PHP SDK](#php-sdk-exceptions) exceptions described below. 

For troubleshooting PHP applications, see [PHP SDK Troubleshooting](#php-troubleshooting).

### <a name="php-troubleshooting"></a>PHP SDK Troubleshooting
Unless there is a [known service issue](https://developers.bingads.microsoft.com/Support), typically when a call fails it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. 

#### <a name="php-troubleshooting-print"></a>Print SOAP
In PHP you can use the following methods to print the SOAP envelopes. Each of the PHP code examples include these statements to print the errors to the console.   

```php
print $proxy->GetService()->__getLastRequest()."\n";
print $proxy->GetService()->__getLastResponse()."\n";
```

### <a name="php-sdk-exceptions"></a>PHP SDK Exceptions
The Bing Ads PHP SDK exceptions abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

You should also handle the *OAuthTokenRequestException*, which is thrown if an error was returned from the Microsft Account authorization server. To resolve this exception you can first check the stack trace to see the error details, in case there is some action you can take to resolve the issue. For example you might have specified an invalid client ID. 
    
## <a name="python-exceptions"><a/>Python Exceptions
If you use the Bing Ads Python [SDK](client-libraries.md), your application should be prepared to handle Bing Ads API [service level exceptions](#faultoverview) and [Bing Ads Python SDK](#python-sdk-exceptions) exceptions described below. 

For troubleshooting Python applications, see [Python SDK Troubleshooting](#python-troubleshooting).

### <a name="python-sdk-exceptions"></a>Python SDK Exceptions
The Bing Ads Python SDK exceptions abstract some of the service level exceptions. To work around most of the exceptions you can try again, and feel free to contact support if the issue persists after multiple retry attempts.

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
     
### <a name="python-troubleshooting"></a>Python SDK Troubleshooting
Unless there is a [known service issue](https://developers.bingads.microsoft.com/Support), typically when a call fails it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. 

#### <a name="python-troubleshooting-logging"></a>Logging
If you are using the Bing Ads Python SDK you can include logging to output traffic, for example the SOAP request and response. Each of the Python code examples include these statements to print the output all SOAP traffic to the console. Be sure to uncomment them if you want to view the traffic.

```python
import logging
logging.basicConfig(level=logging.INFO)
logging.getLogger('suds.client').setLevel(logging.DEBUG)
```
    
## <a name="contact-support"></a>Contact Support
To get help with issues that you cannot resolve, consider posting in the [API Developer](https://social.msdn.microsoft.com/forums/en-us/home?forum=BingAds) forum where an active Bing Ads product team or member of the developer community will try and help. If you do not find timely information via the developer forum, or if the investigation involves sensitive account or personal details, please contact [Bing Ads Support](https://advertise.bingads.microsoft.com/en-us/bing-ads-support).

> [!TIP]
> To resolve the issue efficiently, please provide support with the following information up front.
> - **Reproduction Steps**: Include all header and body elements of the SOAP request, except for the *AuthenticationToken* or *Password* header elements.
> - **Issue or Error**: Include the complete SOAP response with tracking ID, and please also note the date and time when the error occurred.
> - **Historical Performance**: Indicate whether the same request had worked for you in the past.
> - **Frequency**: Indicate whether you can now reproduce the issue every time or intermittently.
> - **Environment**: Indicate whether the issue occurs in the production or sandbox environment.

## See Also
[Bing Ads Operation Error Codes](operation-error-codes.md)  
[Bing Ads Web Service Addresses](web-service-addresses.md)  

