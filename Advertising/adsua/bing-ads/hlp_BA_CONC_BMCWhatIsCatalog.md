---
title: About Microsoft Shopping Campaigns feed files
description: A feed file is a logical grouping of your products, containing a list of your products and attributes that define how they'll display on Bing.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# About Microsoft Shopping Campaigns feed files

<content_tile class="training">      [        New to Microsoft Shopping Campaigns? Learn how to get started in this training course.      ](https://go.microsoft.com/fwlink?LinkId=2129851)    </content_tile>

To run a Microsoft Shopping Campaigns, you must upload a feed file. A feed file contains a list of your products and attributes that define how they will display on Bing.    Whenever you want to update your feed, you upload the updated feed file. Each store can have more than one feed but the products in each file must be unique per market.

## How do I create a feed?
After you [verify that you own your URL](./hlp_BA_PROC_ClaimYourDomain.md) and your newly [created store](./hlp_BA_PROC_CreateBingMerchantCenterStore.md) is approved, you create your feed.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store that you want to update.
1. Click the **Feed Management** tab and then **Create feed**.

## What you need to know

- Your feed file must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip. We only support XML files if it is an existing Google-formatted XML file.
- If uploading via FTP/SFTP, the file name of .txt or .xml files have to match the file name specified for a feed’s settings. For compressed text format, the compressed .txt file inside the archive and the archive file (.zip, .gz, .gzip) must have the matching file name. Any feed file that is archived needs to have a single compressed file inside. The max file size should be no more than 3GB (after uncompressed, if the file is compressed).
- The Feed name is used for identifying your feed on Feed Management and in Feed reports. It can be modified at a later time.
- The Feed Location specifies what Market (Country and Language) the feed would be used for.
- Feed File submission methods specifies how you will transfer the product offer information files to Microsoft Merchant Center.

## How to I create or update a feed file?
Here is how you create a feed file using a spreadsheet program. If you want to use a text editor, make sure to use [the required attributes](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md). You can also take a look at a [short example of a feed file](https://go.microsoft.com/fwlink?LinkId=506749).

> [!NOTE]
> Your feed file must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip. We only support .xml files if it is an existing Google-formatted .xml file.

1. Open Microsoft Excel or other spreadsheet program.
1. Create a header row in the first row entering the attribute names that would be used to describe products.   Be sure each attribute is in its own column and you include all [required attributes](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md).
1. Enter your product offer information in the rows below the header row, using one row for each product.              Each item’s attribute values should be listed in the same column as the corresponding header attribute name. This means a product’s id must be in the column with header attribute “id”.
1. Save your spreadsheet as a tab delimited excel file. If using Microsoft Excel, save as Text (Tab delimited) (\*.txt).

## How do I update the feed file?
Your feed expires after 30 days, which causes the products to stop publishing, so you need to update your feed file. To keep your product information fresh, it is a good practice to upload your feed daily.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store that you want to update.
1. Click **Feed Management** tab.
1. Click the feed that you want to update.
1. Click on the **Feed setting** tab.
1. Use one of the [three methods to submit your feed file.](#SubmitFeedFile)
1. Click **Finish**.

## How do I submit my feed file?
After you have created and (optionally) tested a corresponding feed file, it can be submitted to the associated feed. There are four different ways to submit:

<anchor id="SubmitFeedFile" />

## Upload feed file manually (Files under 4MB)
You can use this option if the feed file is smaller than 4MB.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then **Feed management** tab. Select the checkbox beside the file’s associated feed.
1. Click  **Manual upload**.
1. Browse for feed file and click **Upload**.

## Upload feed file via FTP/SFTP (Files under 1GB)
You can use this option if the feed file is smaller than 1GB. This is the recommended option if the feed file is larger than 4MB.

1. On the global menu at the top of the page, click ** Microsoft Merchant Center**.
1. Click the store name and then the **Feeds** tab.
1. Click the feed name you wish to edit.
1. Click **Update feed**.
1. In the panel, select **Upload via FTP/SFTP**.
1. Enter **File name**. Do not include the file extension. For example, “merchant”.
1. Click **Update feed**.
1. If necessary, click **change FTP account** and update your FTP user name and password.  Your user name must be 6 - 64 characters and cannot include any special characters. Use only a - z, A- Z, and 0 - 9.                   You can now upload the file via the FTP/SFTP tool of your choice, using the file name you specified.

**FTP/SFTP server requirements**

The recommended FTP/SFTP upload mechanism is via an FTP/SFTP program. It is however possible to do so via the command line or custom scripts (such as Python’s ftplib.FTP module).                The FileZilla FTP client is recommended for all platforms.

Use the following settings for file transfer with your FTP/SFTP client:

- Host: ftps://feeds.adcenter.microsoft.com
- Username: Your store’s FTP/SFTP user name. Your user name must be 6 - 64 characters and cannot include any special characters. Use only a - z, A- Z, and 0 - 9.
- Password: Your store’s FTP/SFTP password
- Transfer Mode: Passive

Learn more about [FTP/SFTP upload](./hlp_BA_CONC_BMCFTPRequirements.md).

## Automatically download from URL (Files under 1GB)
You can use this option if the feed file is smaller than 1GB and on a publicly accessible server. The feed file will be downloaded once every 24 hours.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then **Feed management** tab.
1. Click the feed name you wish to edit.
1. Click the **Feed settings** tab.
1. Under **Feed file**, click **Automatically download file from URL**.
1. Enter **Source URL**. For example, https://www.contoso.com/feeds/merchant.txt.
1. If required, enter **User name** and **Password**.
1. Click **Save**.

## Downloading your feed file from Google

You can also download your feed file from Google Docs. Keep in mind that we only accept .csv or .tsv formats for feed files from Google.
1. Open your feed file in Google Docs.
1. Click File and select Publish to the web.
1. Click on Web page and select either Comma-separated values (.csv) or Tab-separated values (.tsv).
1. Click Publish.
1. Copy the generated link and use the link as your automatic download URL in your Microsoft Merchant Center feed.

## Use the Google Merchant Center import tool
You can use the Google Merchant Center import tool, if you already have product ads in your Google Merchant Center. Learn how to [use the Google Merchant Center import tool](./hlp_BA_CONC_BMC_GMCImportIntro.md).

## What are the file format requirements and accepted symbols?
## File format requirements

**Note** : If the following file format requirements are not met, your feed file will not be processed.

- File must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip.              -	.xml files are also accepted (if Google-formatted).
- If uploading via FTP/SFTP, the file name of .txt or .xml files have to match the file name specified for a feed’s settings.              In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip) must have the matching file name. Any feed file that is archived needs to have a single compressed file inside.
- File must start with a single header row.
- Each product offer has to be on a separate line of the file.
- Do not include HTML in the text files.
- Do not include trailing tabs at the end of lines.
- Do not include tabs or line breaks in the middle of offer attributes.
- Special/Invalid characters will cause processing problems. Learn more about Accepted Symbols in Feed Files next.

## Accepted symbols in feed files

Here are the symbols/special characters and what attribute they are accepted in.

|Symbols|Where you can use|
|---|---|
|Period [.]|Prices, URLs|
|Colon [:]                Question [?]                Forward-slash [/]                Equal [=]|URLs|
|Hyphen [-]|Offer Identifiers where this is valid (eg: ISBN, MPN)|
|Pipe [|]                Comma [,]                 Greater [>]|Multi-value fields (MerchantCategory, B_Category)|
|Percent [%]                Special ASCII characters|Redirect URL (ads_redirect)|
|Any Unicode symbol|Brand, Title, Description|


