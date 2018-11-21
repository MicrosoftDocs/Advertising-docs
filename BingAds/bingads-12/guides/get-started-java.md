---
title: "Get Started Using Java with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads Java SDK and discover code examples.
---
# Get Started Using Java with Bing Ads Services
To get started developing Bing Ads applications with Java, you can start with the [provided examples](code-examples.md) or follow one of the application walkthroughs for a [Web](walkthrough-web-application-java.md) or [Desktop](walkthrough-desktop-application-java.md) application. 

You will need user credentials with access to Bing Ads either in [production](https://secure.bingads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](get-started.md) and [Sandbox](sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) (email address user name) in production, you must also must [register](authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Authentication With the SDKs](sdk-authentication.md#oauth).

## <a name="installation"></a>Install the SDK
The Bing Ads Java [SDK](client-libraries.md) depends on the libraries listed at the [Maven Repository](http://mvnrepository.com/artifact/com.microsoft.bingads/microsoft.bingads/).

When you create a Maven project and include the *microsoft.bingads* Maven artifact as shown below, additional dependencies are installed automatically. If you are not using a Maven project, you must include the correct version of each dependency. For more information, please see the [Walkthrough: Bing Ads Web Application in Java](walkthrough-web-application-java.md) or [Walkthrough: Bing Ads Desktop Application in Java](walkthrough-desktop-application-java.md) application examples.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  ...
  <dependencies>
    <dependency>
      <groupId>com.microsoft.bingads</groupId>
      <artifactId>microsoft.bingads</artifactId>
      <version>12.0.1</version>
    </dependency>
  </dependencies>
</project>
```
> [!NOTE]
> Version 12.0.1 is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads Java [SDK](client-libraries.md) installed, you can either browse the [Bing Ads Code Examples](code-examples.md), download the examples from [GitHub](https://github.com/BingAds/BingAds-Java-SDK/tree/master/examples), or follow one of the application walkthroughs for a [Web](walkthrough-web-application-java.md) or [Desktop](walkthrough-desktop-application-java.md) application.

## See Also
[Bing Ads Client Libraries](client-libraries.md)    
[Bing Ads Code Examples](code-examples.md)    
[Bing Ads Web Service Addresses](web-service-addresses.md)  
[Handling Service Errors and Exceptions](handle-service-errors-exceptions.md)  
[Sandbox](sandbox.md)  
