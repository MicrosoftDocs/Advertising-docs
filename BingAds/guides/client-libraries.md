---
title: "Client Libraries"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: The Bing Ads Software Development Kits enhance the experience of developing Bing Ads applications with .NET, Java, PHP, and Python languages.
---
# Client Libraries
You can develop Bing Ads applications with any programming language that supports web services. The Bing Ads Software Development Kits (SDK) enhance the experience of developing Bing Ads applications with .NET, Java, PHP, and Python languages. Each SDK includes a proxy to all Bing Ads API web services and abstracts low level details of authentication with OAuth. You can use the high level *BulkServiceManager* and *ReportingServiceManager* interfaces to abstract and execute operations in the low level Bulk and Reporting services. For example instead of calling *SubmitGenerateReport* and *PollGenerateReport* to download a report, you download a report using one method with the *ReportingServiceManager* class.

> [!NOTE]
> The PHP SDK does not include *BulkServiceManager* and *ReportingServiceManager* interfaces as described for the other three SDKs.

## <a name="repositories"></a>SDK Repositories

|SDK|Documentation|Source|Distribution|Code Examples|License|
|-------|-----------------|----------|----------------|-----------------|-----------|
|Bing Ads .NET SDK|[Get Started](../guides/get-started-csharp.md)|[GitHub](https://github.com/BingAds/BingAds-dotNet-SDK)|[NuGet](https://www.nuget.org/packages/Microsoft.BingAds.SDK/)|[GitHub](https://github.com/BingAds/BingAds-dotNet-SDK/tree/master/examples/BingAdsExamples) &#124; [Docs](../guides/code-examples.md)|[Bing Ads .NET SDK License](https://github.com/BingAds/BingAds-dotNet-SDK/blob/master/LICENSE.md)|
|Bing Ads Java SDK|[Get Started](../guides/get-started-java.md) |[GitHub](https://github.com/BingAds/BingAds-Java-SDK)|[Maven](https://github.com/BingAds/BingAds-Java-SDK#Maven-Artifact)|[GitHub](https://github.com/BingAds/BingAds-Java-SDK/tree/master/examples) &#124; [Docs](../guides/code-examples.md)|[Bing Ads Java SDK License](https://github.com/BingAds/BingAds-Java-SDK/blob/master/LICENSE)|
|Bing Ads PHP SDK|[Get Started](../guides/get-started-php.md)|[GitHub](https://github.com/BingAds/BingAds-PHP-SDK)|[Packagist](https://packagist.org/packages/microsoft/bingads)|[GitHub](https://github.com/BingAds/BingAds-PHP-SDK/tree/master/samples) &#124; [Docs](../guides/code-examples.md)|[Bing Ads PHP SDK License](https://github.com/BingAds/BingAds-PHP-SDK/blob/master/LICENSE.md)|
|Bing Ads Python SDK|[Get Started](../guides/get-started-python.md) |[GitHub](https://github.com/BingAds/BingAds-Python-SDK)|[PyPi](https://pypi.python.org/pypi/bingads)|[GitHub](https://github.com/BingAds/BingAds-Python-SDK/tree/master/examples) &#124; [Docs](../guides/code-examples.md)|[Bing Ads Python SDK License](https://github.com/BingAds/BingAds-Python-SDK/blob/master/LICENSE)|

## <a name="namespaces"></a>Namespaces

### <a name="latestnamespaces"></a>Latest Namespaces
The SDKs support all active [Bing Ads Web Service Addresses](../guides/web-service-addresses.md) in sandbox and production. 

You should use the following namespaces corresponding to the latest version of each service. These are the supported high level public namespaces. Internal and lower level namespaces are not documented here. You can find out more information about internal namespaces within the GitHub [SDK Repositories](#repositories) for each SDK.

|Namespace|Description|
|-------------|---------------|
|*Microsoft.BingAds*|Provides classes related to authentication that can be used to access any Bing Ads Web Service.<br/>[Bing Ads Content API](~/shopping-content/index.md) clients can use the authentication classes provided with the SDK; however, the SDK does not include classes for calling the Content API.|
|*Microsoft.BingAds.V11.AdInsight*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Ad Insight](~/ad-insight-service/ad-insight-service-reference.md) service.|
|*Microsoft.BingAds.V11.Bulk*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Bulk](~/bulk-service/bulk-service-reference.md) service.<br />Provides classes to accelerate productivity for downloading and uploading entities. For example an instance of the *BulkServiceManager* class can submit your download request to the bulk service, poll the service until completed, and download the file to the local directory that you specified in the request. Use the *BulkFileReader* class instead of writing a file parser to read the download results. The *BulkFileReader* provides access to the bulk file records in *BulkEntity* derived classes, which contain the familiar data objects and value sets in version 11 of the [Campaign Management](~/campaign-management-service/campaign-management-service-reference.md) service.|
|*Microsoft.BingAds.V11.CampaignManagement*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Campaign Management](~/campaign-management-service/campaign-management-service-reference.md) service.|
|*Microsoft.BingAds.V11.CustomerBilling*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Customer Billing](~/customer-billing-service/customer-billing-service-reference.md) service.|
|*Microsoft.BingAds.V11.CustomerManagement*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Customer Management](~/customer-management-service/customer-management-service-reference.md) service.|
|*Microsoft.BingAds.V11.Reporting*|Provides proxy classes to the service operations, data objects, and value sets defined for version 11 of the [Reporting](~/reporting-service/reporting-service-reference.md) service.<br />Provides classes to accelerate productivity for downloading reports. For example an instance of the *ReportingServiceManager* class can submit your download request to the reporting service, poll the service until completed, and download the file to the local directory that you specified in the request.|

## See Also
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  

