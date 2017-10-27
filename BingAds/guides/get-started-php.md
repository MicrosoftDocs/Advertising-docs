---
title: "Get Started Using PHP with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
ms.date: 11/01/2017
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads PHP SDK and discover code examples.
---
# Get Started Using PHP with Bing Ads Services
To get started developing Bing Ads applications with PHP, you can start with the [provided examples](~/guides/code-examples.md) or follow one of the application walkthroughs for a [Web](~/guides/walkthrough-web-application-php.md) or [Desktop](~/guides/walkthrough-desktop-application-php.md) application. The examples have been developed with the Bing Ads PHP [SDK](~/guides/client-libraries.md) and run with [PHP](http://php.net/) 5.6.30. You should be able to use other versions of PHP, packages, and operating systems. However, certain parts of the code and configuration might have to be changed. For information about how to set up a PHP development environment to use web services, see the documentation for your tools. The SOAP and OpenSSL extensions should also be enabled in the PHP.ini file. Enable the curl extension to run the bulk upload samples.

```no-highlight
extension=php_soap.dll
extension=php_openssl.dll
extension=php_curl.dll
```

You will need user credentials with access to Bing Ads either in [production](https://secure.bingads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](~/guides/get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) (email address username) in production, you must also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Authentication With the SDKs](~/guides/sdk-authentication.md#oauth).

## <a name="installation"></a>Install the SDK
You can install the Bing Ads PHP [SDK](~/guides/client-libraries.md) using the [Composer](https://getcomposer.org/doc/00-intro.md#introduction) package manager to fetch from [Packagist](https://packagist.org/packages/microsoft/bingads), or you can clone the source from [GitHub](https://github.com/BingAds/BingAds-PHP-SDK/). This guide describes how you can use Composer to get the latest version of the Bing Ads PHP SDK. 

1.  Download and install [Composer](https://getcomposer.org/doc/00-intro.md#introduction). Microsoft Windows users should also add composer.phar to your *PATH* variable.

2.  Open a command prompt and type `composer require microsoft/bingads`. 

    > [!NOTE]
    > Windows users who did not add *composer.phar* to the *PATH* will need to type `php composer.phar require microsoft/bingads` instead.

3.  To get updates going forward, type `composer update`. If any updates are available at packagist, composer will install the latest version.

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads PHP [SDK](~/guides/client-libraries.md) installed you can either browse the [Bing Ads Code Examples](../guides/code-examples.md), download the examples at [GitHub](https://github.com/BingAds/BingAds-PHP-SDK/), or follow one of the application walkthroughs for a [Web](walkthrough-web-application-php.md) or [Desktop](walkthrough-desktop-application-php.md) application.

## See Also
[Bing Ads Client Libraries](../guides/client-libraries.md)    
[Bing Ads Code Examples](../guides/code-examples.md)    
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  
[Handling Service Errors and Exceptions](~/guides/handle-service-errors-exceptions.md)  
[Sandbox](../guides/sandbox.md)  
