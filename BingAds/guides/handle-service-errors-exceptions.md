---
title: "Handling Service Errors and Exceptions"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
---
# Handling Service Errors and Exceptions
For details on error handling and troubleshooting your application, please see the sections below.

-   [Partial Success using the Campaign Management Service](#partialsuccess)  
-   [Fault Model Overview](#faultoverview)  
-   [Common Errors](#commonerrors)  
-   [Troubleshooting Your Application](#troubleshooting)  
-   [Engaging Support](#engagesupport)  

## <a name="partialsuccess"></a>Partial Success using the Campaign Management Service
For most entities, partial success is supported when calling [Campaign Management](~/campaign-management/campaign-management-service-reference.md) service operations. This means that when adding, updating, or deleting entities in batches of one or more, the operation may succeed for some and fail for part of the batch. For each list index where an entity was not added, the corresponding element will be null. The *PartialErrors* element represents an array of [BatchError](~/campaign-management/batcherror.md) objects that contain details for any entities that were not successfully added, updated, or deleted. The list only includes a [BatchError](~/campaign-management/batcherror.md) for unsuccessful attempts, and does not include null elements at the index of each successfully added entity. Similarly some operations return *NestedPartialErrors* as a list of [BatchErrorCollection](~/campaign-management/batcherrorcollection.md), or a two dimensional [BatchError](~/campaign-management/batcherror.md).

> [!NOTE]
> The [ApplyProductPartitionActions](~/campaign-management/applyproductpartitionactions.md) operation includes *PartialErrors* in the response; however, partial success is not supported. Either the entire set of requested actions succeed and the *AdGroupCriterionIds* response list is fully populated, or all of them fail and the *PartialErrors* response list is fully populated. 

## <a name="faultoverview"></a>Fault Model Overview
When an operation fails, it can return one of the following faults. To determine the fault exceptions that an operation can return, see the reference page for the operation.

-   *AdApiFaultDetail*  
-   *ApiBatchFault*  
-   *ApiFault*  
-   *ApiFaultDetail*  
-   *EditorialApiFaultDetail*

All fault objects are derived from the *ApplicationFault* object. The *ApplicationFault* object defines the *TrackingId* element, which uniquely identifies the log entry that contains the details of the API call.

The fault exceptions include one or more error objects. The error objects contain the details of why the service operation failed and a code that uniquely identifies the error. For a list of error codes, see [Bing Ads Operation Error Codes](../guides/operation-error-codes.md).

Available fault and data objects vary per service. The following table describes the fault model and links to error data objects for each service.

|Service|Description|
|-----------|---------------|
|Ad Insight|All ad insight operations may throw *AdApiFaultDetail* and *ApiFaultDetail*.<br /><br />For more information, see [Ad Insight Error Data Objects](~/ad-insight/ad-insight-data-objects.md).|
|Bulk|All bulk operations may throw *AdApiFaultDetail* and *ApiFaultDetail*.<br /><br />For more information, see [Bulk Error Data Objects](~/bulk/bulk-data-objects.md).|
|Campaign Management|All campaign management operations may throw *AdApiFaultDetail*.<br /><br />Some campaign management operations such as [AddAdGroupCriterions](~/campaign-management/addadgroupcriterions.md), [UpdateAdGroupCriterions](~/campaign-management/updateadgroupcriterions.md), [SetAdExtensionsAssociations](~/campaign-management/setadextensionsassociations.md), and [UpdateAdExtensions](~/campaign-management/updateadextensions.md) throw either *ApiFaultDetail* or *EditorialApiFaultDetail*.<br /><br />For more information, see [Campaign Management Error Data Objects](~/campaign-management/campaign-management-data-objects.md).|
|Customer Billing|All customer billing operations may throw *AdApiFaultDetail* and *ApiFault*.<br /><br />Some customer billing operations may also throw *ApiBatchFault*.<br /><br />For more information, see [Customer Billing Error Data Objects](~/customer-billing/customer-billing-data-objects.md).|
|Customer Management|All customer management operations may throw *AdApiFaultDetail* and *ApiFault*.<br /><br />For more information, see [Customer Management Error Data Objects](~/customer-management/customer-management-data-objects.md).|
|Reporting|All reporting operations may throw *AdApiFaultDetail* and *ApiFaultDetail*.<br /><br />For more information, see [Reporting Error Data Objects](~/reporting/reporting-data-objects.md).|

## <a name="commonerrors"></a>Common Errors
Runtime errors may be caught and handled. Documentation is available for potential error codes which may be observed. The following are some common errors that you may encounter.

### Code 105
Typically indicates usage of an incorrect username, password, or developer token for the target environment. For example your credentials may be valid in production, and when targeting sandbox you would observe code *105*.

### Code 106
Typically indicates that while the credentials are correct for the target environment, the user does not have access to one of the entities specified in the request. For example, calling *SubmitGenerateReport* where the specified user does not have permissions to the specified account identifier.

### HTTP 500
All Bing Ads services adhere to the Simple Object Access Protocol (SOAP) 1.1 specification whereby errors are returned with a HTTP 500 code. For example, see the following.

```
HTTP/1.1 500 Internal Server Error
```
This is not in and of itself representative of an actionable code, and you should inspect the fault details for more information on the specific error.

## <a name="troubleshooting"></a>Troubleshooting Your Application
Typically when a call fails it is because the SOAP elements are invalid, out of order, or you specified the wrong credentials. To verify both cases, you should capture the request SOAP envelope. You can [contact support](http://go.microsoft.com/fwlink/?LinkId=517018) or compare your capture to the corresponding SOAP example documented for each service operation. The following sections describe examples of how you can capture the SOAP request using a variety of platforms.

### Troubleshooting .NET Applications
#### Fiddler Options
You can follow these steps to capture the SOAP envelopes from a .NET application using a third-party tool such as [Fiddler](http://fiddler2.com/get-fiddler). After installing Fiddler, export the Fiddler certificate from the root certificate store. Click **Tools** &gt; **Fiddler Options**. Select the **HTTPS** tab, and click the **Decrypt HTTPS traffic** check box. Click **OK**, and then follow the prompts to export the Fiddler certificate. 

### Troubleshooting Java Applications

#### HttpTransportPipe

To output the HTTP trace you can set the HttpTransportPipe *dump* property to "true" (string) as follows:
```java
System.setProperty("com.sun.xml.ws.transport.http.client.HttpTransportPipe.dump", "true");
```

#### Fiddler Options
You can follow these steps to capture the SOAP envelopes from a Java application using a third-party tool such as [Fiddler](http://fiddler2.com/get-fiddler). 

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
    
#### Spring Framework and Apache CXF Options
You can use the [Spring Framework](https://docs.spring.io/spring/docs/current/spring-framework-reference/html/overview.html) and [Apache CXF](http://cxf.apache.org/docs/index.html) to capture the SOAP envelopes, for example if you are running a Maven application in Eclipse.

1.  Set up the development environment as described in [Get Started Using Java with Bing Ads Services](../guides/get-started-java.md). 
   
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
          <version>10.4.12</version>
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
    > Version 10.4.12 of the Bing Ads Java SDK is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).
   
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
    
### Troubleshooting Python Applications

If you are using the Bing Ads Python SDK you can include logging to output traffic, for example the SOAP request and response. Each of the Python code examples include these statements to print the output all SOAP traffic to the console. Be sure to uncomment them if you want to view the traffic.

```python
import logging
logging.basicConfig(level=logging.INFO)
logging.getLogger('suds.client').setLevel(logging.DEBUG)
```

### Troubleshooting PHP Applications
In PHP you can use the following methods to capture the SOAP envelopes. Each of the PHP code examples include these statements to print the errors to the console.   

```php
print $proxy->GetService()->__getLastRequest()."\n";
print $proxy->GetService()->__getLastResponse()."\n";
```

### Perl Options
In Perl you can use the *SOAP::Lite* statement to capture the SOAP envelopes.

```
use SOAP::Lite ( +trace => all, maptype => {} );
```

## <a name="engagesupport"></a>Engaging Support
To get help with issues that you cannot resolve, consider posting in the [API Developer](https://social.msdn.microsoft.com/forums/en-us/home?forum=BingAds) forum where an active Bing Ads product team or member of the developer community will try and help. If you do not find timely information via the developer forum, or if the investigation involves sensitive account or personal details, please contact [Bing Ads Support](https://advertise.bingads.microsoft.com/en-us/bing-ads-support).

To resolve the issue efficiently, please provide support with the following information up front.

-   **Reproduction Steps**: Include all header and body elements of the SOAP request, except for the *AuthenticationToken* or *Password* header element.

    > [!NOTE]
    > If you are managing user authentication with OAuth, and escalating an issue related to error code *105* or *106*, please also include the user identifier corresponding to the Microsoft Account.
    > 
    > To get the user identifier for the current user, call the [GetUser](~/customer-management/getuser.md) service operation and leave the *UserId* element null. If [GetUser](~/customer-management/getuser.md) returns error code *1001*, then the Microsoft Account is not linked to any Bing Ads account. For more information about linking a Microsoft Account, see [Authentication with OAuth](../guides/authentication-oauth.md).

-   **Issue or Error**: Include all elements of the SOAP response, and please also note the date and time when the error occurred.

-   **Historical Performance**: Indicate whether the same request had worked for you in the past.

-   **Frequency**: Indicate whether you can now reproduce the issue every time or intermittently.

-   **Environment**: Indicate whether the issue occurs in the production or sandbox environment.

## <a name="wcf"></a>WCF Exceptions using C#
Generic SOAP faults that are not specific to Bing Ads API may also be thrown, and should be caught by your application. For example, C# applications may throw Windows Communication Foundation (WCF) exceptions such as Exception, TimeoutException, and CommunicationException.

For information about exceptions that you should expect from WCF, see [Expected Exceptions](https://docs.microsoft.com/en-us/dotnet/framework/wcf/samples/expected-exceptions).

You should not call the *Close* method in the finally block to release the service object. The objection is that the *Close* method can throw exceptions. If *Close* throws an exception, you must call the *Abort* method to ensure that all resources are released; otherwise, you could be leaking resources on the server. The recommended practice is to call *Close* within the try block, and call *Abort* from the caught exceptions.

For the same reason, the use of the **using** statement is not recommended. For more information, see [Avoiding Problems with the Using Statement](https://docs.microsoft.com/en-us/dotnet/framework/wcf/samples/avoiding-problems-with-the-using-statement).

## See Also
[Bing Ads Operation Error Codes](../guides/operation-error-codes.md)  
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

