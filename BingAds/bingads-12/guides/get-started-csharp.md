---
title: "Get Started Using C# with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads .NET SDK and discover code examples.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change.

# Get Started Using C# with Bing Ads Services
To get started developing Bing Ads applications with a .NET language, you can start with the [provided examples](../guides/code-examples.md) or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-csharp.md) or [Desktop](../guides/walkthrough-desktop-application-csharp.md) application. The examples have been developed with the Bing Ads .NET [SDK](../guides/client-libraries.md) and [Visual Studio Community](https://www.visualstudio.com/vs/community/). Your custom configuration may vary.

You will need user credentials with access to Bing Ads either in [production](https://secure.bingads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](../guides/get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) (email address username) in production, you must also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Authentication With the SDKs](../guides/sdk-authentication.md#oauth).

## <a name="installation"></a>Install the SDK
To use the Bing Ads .NET SDK, you must first install and use .NET Framework 4.5 or later. In [Visual Studio Community](https://www.visualstudio.com/vs/community/) go to the project **Properties** -&gt; **Application** -&gt; **Target framework** and make sure that **.NET Framework 4.5** is selected.

Install the Bing Ads .NET SDK through [NuGet](https://www.nuget.org/packages/Microsoft.BingAds.SDK/), either through the [Manage NuGet Packages](#manage-nuget) user interface, or through the [Package Manager Console](#package-manager). For information about installing NuGet, see [http://docs.nuget.org](http://docs.nuget.org/docs/start-here/installing-nuget).

> [!NOTE]
> The NuGet installation includes the following required libraries.
> 
> -   *Microsoft.BingAds.dll* - The Bing Ads .NET [SDK](../guides/client-libraries.md)
> -   *System.Runtime.Serialization.dll*
> -   *System.ServiceModel.dll*

### <a name="manage-nuget"></a>Manage NuGet Packages

1. Right-click on your Visual Studio project and select **Manage NuGet Packages**.

2. Browse online for *Microsoft.BingAds.SDK* e.g., try searching for *bingads*..
   ![Install .NET SDK](../guides/media/net-sdk-install.png "Install .NET SDK")  

3. Select the project or projects where you want the SDK installed, and click the **Install** button*.

### <a name="package-manager"></a>NuGet Package Manager Console

1. Click on **Tools** -&gt; **NuGet Package Manager** -&gt; **Package Manager Console**.

2. Choose the default project where you want the SDK installed, and then within the console command line, type `Install-Package Microsoft.BingAds.SDK`. 

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads .NET SDK installed, you can either browse the [Bing Ads Code Examples](../guides/code-examples.md) in C# or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-csharp.md) or [Desktop](../guides/walkthrough-desktop-application-csharp.md) application.

## See Also
[Bing Ads Client Libraries](../guides/client-libraries.md)    
[Bing Ads Code Examples](../guides/code-examples.md)    
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  
[Handling Service Errors and Exceptions](../guides/handle-service-errors-exceptions.md)  
[Sandbox](../guides/sandbox.md)  
