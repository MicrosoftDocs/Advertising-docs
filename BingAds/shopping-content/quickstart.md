---
title: "Content API Quickstart"
description: "Describes the Content API and to quickly start making endpoint requests."
author: "brapel"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.date: 11/1/2017
ms.author: "v-brapel"
---

# Bing Ads Content API Quickstart
Bing Ads Content API is a RESTful API that allows advertisers to programmatically manage their [Bing Merchant Center](http://help.bingads.microsoft.com/#apex/3/en/51083/1) catalogs. The Bing Ads Content API is an alternative to using FTP or the Bing Merchant Center web page for catalog management.

This article describes a simple console application that excercises the Bing Ads Content API.

# Prerequisites
- Download and install git from [https://git-scm.com/downloads](https://git-scm.com/downloads)
- If you don’t already have Visual Studio 2017 installed, you can download and use the **free** [Visual Studio 2017 Community Edition](https://www.visualstudio.com/downloads/). 
- Get a Bing Ads account from [http://bingads.microsoft.com](http://bingads.microsoft.com).
- Register your application at [https://apps.dev.microsoft.com](https://apps.dev.microsoft.com).
- [Verify and claim your Website's URL](https://help.bingads.microsoft.com/#apex/3/en/50888/1) using [Bing Webmaster Tools](https://www.bing.com/toolbox/webmaster).
- [Create a Bing Merchant store](http://help.bingads.microsoft.com/#apex/3/en/51085/1).

# Running the application
- Open a command prompt: `cmd.exe`.
- Create a directory to hold the example code; for example: `mkdir C:\code`.
- Change the working directory to the directory you just created: `cd C:\code`.
- Clone the example repository: `git clone https://github.com/brapel/BingAdsContentApiClientExample.git`
- Using Visual Studio open the solution file `C:\code\BingAdsContentApi\BingAdsContentApiClientExample\BingAdsContentApi.sln`.
- Copy your application Client Id from [https://apps.dev.microsoft.com](https://apps.dev.microsoft.com) and paste it into the file `C:\code\BingAds\BingAdsContentApi\BingAdsContentApi\App.config` replacing the text **[YOUR-CLIENT-ID]**.
- Copy your developer token from [https://developers.bingads.microsoft.com/Account](https://developers.bingads.microsoft.com/Account) and paste it into the file `C:\code\BingAds\BingAdsContentApi\BingAdsContentApi\App.config` replacing the text **[YOUR-DEV-TOKEN]**.
- Get your merchant id from [https://secure.bingads.microsoft.com](https://secure.bingads.microsoft.com) by doing the following:
    - Click **Tools** / **Bing Merchant Center**.
    - Click a store or create one if you haven't already.
    - Click **Store Settings**.
    - Copy the Store Id and paste it into the file `C:\code\BingAds\BingAdsContentApi\BingAdsContentApi\App.config` replacing the text **[YOUR-MERCHANT-ID]**.
- Run the app:
    - In the Solution Explorer, right click on the **BingAdsContentApi** project and select **Debug** / **Start new instance**.

