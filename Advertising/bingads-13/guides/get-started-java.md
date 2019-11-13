---
title: "Get Started Using Java with Bing Ads API"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads Java SDK and discover code examples.
---
# Get Started Using Java with Bing Ads API
To get started developing Bing Ads API applications with Java, you can start with the [provided examples](code-examples.md) or follow one of the application walkthroughs for a [Web](walkthrough-web-application-java.md) or [Desktop](walkthrough-desktop-application-java.md) application. 

You will need user credentials with access to Microsoft Advertising either in [production](https://ads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](get-started.md) and [Sandbox](sandbox.md#access).  

To authenticate via OAuth, you must also register an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For more details about registering an application in production and the authorization code grant flow, see [Authentication with OAuth](authentication-oauth.md) and [Authentication With the SDKs](sdk-authentication.md#oauth). Although in production you must use your own application ID (a.k.a. client ID), all Microsoft Advertising customers can use the public "Sandbox Tutorial App" client ID in sandbox i.e., **db41b09d-6e50-4f4a-90ac-5a99caefb52f**. For more information, please see [Sandbox](sandbox.md#access). 

## <a name="installation"></a>Install the SDK
The Bing Ads Java [SDK](client-libraries.md) depends on the libraries listed at the [Maven Repository](https://mvnrepository.com/artifact/com.microsoft.bingads/microsoft.bingads/).

When you create a Maven project and include the *microsoft.bingads* Maven artifact as shown below, additional dependencies are installed automatically. If you are not using a Maven project, you must include the correct version of each dependency. For more information, please see the [Walkthrough: Bing Ads API Web Application in Java](walkthrough-web-application-java.md) or [Walkthrough: Bing Ads API Desktop Application in Java](walkthrough-desktop-application-java.md) application examples.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  ...
  <dependencies>
    <dependency>
      <groupId>com.microsoft.bingads</groupId>
      <artifactId>microsoft.bingads</artifactId>
      <version>13.0.1</version>
    </dependency>
  </dependencies>
</project>
```
> [!NOTE]
> Version 13.0.1 is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads Java [SDK](client-libraries.md) installed, you can either browse the [Bing Ads API Code Examples](code-examples.md), download the examples from [GitHub](https://github.com/BingAds/BingAds-Java-SDK/tree/master/examples), or follow one of the application walkthroughs for a [Web](walkthrough-web-application-java.md) or [Desktop](walkthrough-desktop-application-java.md) application.

## See Also
[Bing Ads API Client Libraries](client-libraries.md)    
[Bing Ads API Code Examples](code-examples.md)    
[Bing Ads API Web Service Addresses](web-service-addresses.md)  
[Handling Service Errors and Exceptions](handle-service-errors-exceptions.md)  
[Sandbox](sandbox.md)  
