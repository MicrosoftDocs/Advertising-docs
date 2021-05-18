---
title: How to prevent your ads from showing to certain people
description: Prevent your ad from appearing in specific locations, on specific web sites within the search network, or from displaying to certain IP addresses. You can set exclusions on a each ad or across multiple ads at the same time.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How to prevent your ads from showing to certain people

If you want to prevent your ad from appearing in specific locations, on specific web sites within the search network, or prevent your ads from displaying to certain IP addresses, you can configure exclusions.

## To prevent your ads from showing in specific locations
1. To exclude specific locations at the campaign level:
   - From the main menu on the left, click **All campaigns** and then **Campaigns**.
   - Click the name of the campaign (in the **Campaign** column) that you want to edit.
   - Click **Settings**.

1. To exclude specific locations at the ad group level:
   - From the main menu on the left, click **All campaigns** and then **Ad groups**.
   - Click on the ad group title (in the **Ad group** column) that you want to edit.
   - Click **Settings**.

1. Click **Edit location targets** below **Location** and then select **Let me choose specific locations**.
1. Select locations you want to exclude — cities and metro areas within the United States, Canada, United Kingdom, France, and Australia; states/provinces; countries/regions; or postal codes — by searching for your specific location and clicking **Exclude** from the search results.  (Note: You cannot exclude using radius targeting.)
1. Click **Done**.

## To prevent specific websites from showing your ads
1. To exclude specific websites at the campaign level:
   - From the main menu on the left, click **All campaigns** and then **Campaigns**.
   - Select the checkbox next to the name of the campaign that you want to edit.

1. To exclude specific websites at the ad group level:
   - From the main menu on the left, click **All campaigns** and then **Ad groups**.
   - Select the checkbox next to the name of the ad group that you want to edit.

1. Click **Edit**&nbsp;&gt;&nbsp;**Other changes**.
1. For **Select a setting**, select **Website exclusions**, and then enter the URLs of websites you want to exclude in the box.
1. Click **Apply**.

> [!NOTE]
> You can specify a maximum of 2,500 URLs to exclude.
> Each URL must specify the domain name, and can specify one subdomain name and a maximum of two directories.
> Duplicate URLs are not added.
> Ad-group-level website exclusions override campaign-level website exclusions.

## To block specific IP addresses from seeing your ads
1. From the main menu on the left, click **All campaigns** and then **Campaigns**.
1. Select the checkbox next to the name of the campaign that you want to edit.
1. Click **Edit**&nbsp;&gt;&nbsp;**Other changes**.
1. For **Select a setting**, select **IP address exclusions**.
1. Enter the IP addresses that you want to be blocked from seeing your ads in the box. Enter one IP address per line. You can also add a range of addresses using a wildcard character (\*).
1. Click **Apply**.

> [!NOTE]
> IP exclusions must be added at the campaign level, not the ad group level.
> You can exclude a maximum of 100 IP addresses (or IP address ranges) per campaign.
> You can only exclude IPv4 addresses. These addresses must include all four octets, each with an integer that ranges from 0 - 255. Only the last octet can be a wildcard character (\*).  For example,*127.0.0.\**. This would include all IP addresses from 127.0.0.0 to 127.0.0.255.

 

