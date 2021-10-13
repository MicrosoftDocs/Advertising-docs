---
title: Submit online product inventory update feeds
description: Here is how you create a feed file using a spreadsheet program.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Submit online product inventory update feeds

For product attributes that you update frequently, like price, availability, sale price, and sale price effective date, you can easily make updates using online product inventory update feeds. While you will still need to submit your full product feed at least once every 30 days, you can use the update feed for the specific attributes that are already in your full product feed: price, availability, sale price, and sale price effective date.

## Why should I use the online product inventory update feed?

- Allows for faster processing for frequently changing attributes.
- Keeps your product ads data up-to-date.
- Allows the option to submit only offers that have changed.

## When should I use the online product inventory update feed?

There are two different feed types you can use to upload your product data. The first is the main product feed file for your product data for Microsoft Merchant Center, which should be submitted at least every 30 days. Any time you upload a new product feed file, it overwrites the previous uploads.

On the other hand, you want to use the online product inventory update feed when you want to update only price, availability, sale price, and sale price effective date that’s already been submitted in your main product feed file. This means:

- You can update the price, availability, sale price, and sale price effective date quickly and frequently.
- You can make updates only to these attributes without having to update the entire feed file.
- If there is an error with the update feed file, it won’t impact the main product feed file.

The online product inventory update feed can be uploaded manually through the update feed tab or via FTP/SFTP. Once the feed has been processed, the report will be available in the update feed tab on the top banner. See how to upload the online product inventory update feed below.

## Upload feed file via FTP/SFTP (Files under 1GB)
You can use this option if the feed file is smaller than 1GB. This is the recommended option if the feed file is larger than 4MB.

           When  submitting via FTP/SFTP:
- The file name must be in the following format: ```inventoryfeed_{market}.txt``` (for example, ```inventoryfeed```_enus.txt).
- The supported market values are enus, enuk, dede, frfr, enau, enca, and enin.
- The file name is case sensitive.
- If you send the file with a zip file, both the zip file name and the file name must follow the naming format above.

**FTP/SFTP server requirements**

The recommended FTP/SFTP upload mechanism is via an FTP/SFTP program. It is however possible to do so via the command line or custom scripts (such as Python’s ftplib.FTP module).            The FileZilla FTP/SFTP client is recommended for all platforms.

Use the following settings for file transfer with your FTP/SFTP client:

- Host: ftps://feeds.adcenter.microsoft.com
- Username: Your store’s FTP/SFTP user name. Your user name must be 6 - 64 characters and cannot include any special characters. Use only a - z, A- Z, and 0 - 9.
- Password: Your store’s FTP/SFTP password
- Transfer Mode: Passive

Learn more about [FTP/SFTP upload](./hlp_BA_CONC_BMCFTPRequirements.md).

The feed contains five attributes, as detailed below.

|Attribute|What it is|Required in txt header row?|Can value be blank?|
|---|---|---|---|
|'id'|The ID of the product that will be updated. The ID must match the ID provided in the full product feed file.|Yes|No|
|'price'|The price submitted here overrides the price from the last submission of the product feed file. If price is submitted, the value cannot be blank. No changes will be made if the value is blank and you’ll receive the following error message:                **Offer cannot be updated as price cannot be blank. Please add a valid price value.**|No|No|
|'availability'|The availability submitted here overrides the availability from the last submission of the product feed file. If availability is submitted, the value cannot be blank. No changes will be made if the value is blank and you’ll receive the following error message:                **Offer cannot be updated as availability cannot be blank. Please add a valid availability value.**|No|No|
|'sale price' and 'sale price effective date'|The sale price and sale price effective date submitted here overrides what was last submitted from the product feed file. If blank values are submitted, it will void the previous sale details submitted from the last product feed file.|No|Yes|

## Upload feed file manually (Files under 4MB)
You can use this option if the feed file is smaller than 4MB.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then the **Update feed** tab.
1. Click **Manual upload**.
1. Select target country/region and language.
1. Select **Browse** and select the online product inventory update feed file.
1. Click **Upload**.

## Check feed status
Once the feed has been processed, the report will be available in the update feed tab on the top banner.

1. On the top menu, click **Tools** and then click ** Microsoft Merchant Center**  (or from the global menu at the top of the page, click **Tools** and then **Microsoft Merchant Center**).
1. Click the store name and then the **Update feed** tab.
1. See the top banner for the feed status.

## Example submissions of the online product inventory update feed
## Update price

|id|price|
|---|---|
|Offer1|20|

## Update availability

|id|availability|
|---|---|
|Offer2|Out of stock|

## Update sale price and sale price effective date

|id|sale_price|sale_price_effective_date|
|---|---|---|
|Offer3|30|2017-01-01T00:00/2017-04-30T00:00|

## Void sale price

|id|sale_price|sale_price_effective_date|
|---|---|---|
|Offer4|||

## File format requirements
- File must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip, .tar.gz, .tgz.              -	.xml files are also accepted (if Google-formatted).
- The file name must be in the following format: inventoryfeed_{market}.txt (for example, inventoryfeed_enus.txt). This also applies to the file inside compressed files.
- In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip, .tar.gz, .tgz) must have the matching file name.
- File must start with a single header row
- Each product offer has to be on a separate line of the file
- Do not include HTML in the text files
- Do not include trailing tabs at the end of lines
- Do not include tabs or line breaks in the middle of offer attributes
- Special/Invalid characters will cause processing problems. Learn more about Accepted Symbols in Feed Files next

## Accepted symbols in feed files
Here are the symbols/special characters and what attribute they are accepted in.

|Symbols|Where you can use|
|---|---|
|Period [.]|Prices, URLs|
|Colon [:]                Question [?]                Forward-slash [/]                Equal [=]|URLs|
|Hyphen [-]|Offer Identifiers where this is valid (eg: ISBN, MPN)|
|Pipe [|]                Comma [,]                 Greater [>]|Multi-value fields (MerchantCategory, B_Category, ads_label)|
|Any Unicode symbol|Brand, Title, Description|


