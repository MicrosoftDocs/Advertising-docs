---
title: Using the API and FTP/SFTP in Microsoft Merchant Center
description: Learn about uploading your feed in Microsoft Merchant Center through a manual feed, FTP/SFTP, or API.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Using the API and FTP/SFTP in Microsoft Merchant Center

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course (requires Adobe Flash Player).      ](https://go.microsoft.com/fwlink?LinkId=2129851)    </content_tile>

If a feed is uploaded using the FTP/SFTP, it was accessible by the API. We now provide you with the flexibility to access and update your offers with Bing in any form, whether it’s through a manual feed, FTP/SFTP, or via API. If uploading via FTP/SFTP, the file name of .tsv, .txt, or .xml files have to match the file name specified for a feed’s settings. In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip) must have the matching file name.

With this feature, you can now:  
- Execute read-only requests from the API. If you want to use the API to fetch information and status updates on your products to use to build product groups, this will help to optimize your campaigns.
- Use the API to update pricing and inventory throughout the day, and the FTP/SFTP to upload the entire data feed once a day.
- Switch over to the content API for management of the feeds seamlessly.

When can I use the API and FTP/SFTP together?  
- Use FTP/SFTP and the API to update different feeds. For example, you can use the API to update feed A and FTP/SFTP to update feed B.
- Use the API only to get products or determine the status of a product. For example, if you use FTP/SFTP update feed A, you may use the API only to get products from feed A.

Though we recommend not using the same feed using FTP/SFTP and the API, if you do so, you must wait until the FTP/SFTP process completes before using the API to update the feed. The only exception to using FTP/SFTP and the API to update the same feed at the same time is if you use the API to update only the "price," "salePrice," and "salePriceEffectiveDate" fields of the feed.


