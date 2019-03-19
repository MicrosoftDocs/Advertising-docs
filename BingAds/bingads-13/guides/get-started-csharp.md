---
title: "Get Started Using C# with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads .NET SDK and discover code examples.
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# Get Started Using C# with Bing Ads Services
To get started developing Bing Ads applications with a .NET language, you can start with the [provided examples](code-examples.md) or follow one of the application walkthroughs for a [Web](walkthrough-web-application-csharp.md) or [Desktop](walkthrough-desktop-application-csharp.md) application. The examples have been developed with the Bing Ads .NET [SDK](client-libraries.md) and [Visual Studio Community](https://www.visualstudio.com/vs/community/). Your custom configuration may vary.

You will need user credentials with access to Bing Ads either in [production](https://secure.bingads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](get-started.md) and [Sandbox](sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) (email address user name) in production, you must also must [register](authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Authentication With the SDKs](sdk-authentication.md#oauth).

## <a name="installation"></a>Install the SDK
Install the Bing Ads .NET SDK through [NuGet](https://www.nuget.org/packages/Microsoft.BingAds.SDK/), either through the Manage NuGet Packages user interface, or through the [Package Manager Console](#package-manager). For information about installing NuGet, see [http://docs.nuget.org](http://docs.nuget.org/docs/start-here/installing-nuget).

> [!NOTE]
> The Bing Ads .NET SDK supports .NET Standard 2.0. You can choose from a variety of platforms e.g., .NET Core or .NET Framework 4.6.1. The Bing Ads API examples are developed via [Visual Studio Community 2017](https://www.visualstudio.com/vs/community/) and target .NET Framework 4.7.1. The .NET Standard 2.0 and Bing Ads .NET SDK do not support .NET Framework versions lower than 4.6.1. For more information on .NET Standard and how it relates to other .NET frameworks, refer to this article on [.NET Standard](https://docs.microsoft.com/en-us/dotnet/standard/net-standard). 

### <a name="package-manager"></a>NuGet Package Manager Console

1. Click on **Tools** -&gt; **NuGet Package Manager** -&gt; **Package Manager Console**.
2. Choose the default project where you want the SDK installed, and then within the console command line, type `Install-Package Microsoft.BingAds.SDK`. 
3. If you do not already have references to *System.ServiceModel.Primitives 4.4.1*, *System.ServiceModel.Http 4.4.1*, and *System.ServiceModel.ConfigurationManager 4.4.1*, type `Install-Package System.ServiceModel.Primitives -Version 4.4.1`, `Install-Package System.ServiceModel.Http -Version 4.4.1`, and `Install-Package System.Configuration.ConfigurationManager -Version 4.4.1`.

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads .NET SDK installed, you can either browse the [Bing Ads Code Examples](code-examples.md) in C# or follow one of the application walkthroughs for a [Web](walkthrough-web-application-csharp.md) or [Desktop](walkthrough-desktop-application-csharp.md) application.

## See Also
[Bing Ads Client Libraries](client-libraries.md)    
[Bing Ads Code Examples](code-examples.md)    
[Bing Ads Web Service Addresses](web-service-addresses.md)  
[Handling Service Errors and Exceptions](handle-service-errors-exceptions.md)  
[Sandbox](sandbox.md)  
