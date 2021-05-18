---
title: How do I create a feed file?
description: Here is how you create a feed file using a spreadsheet program.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# How do I create a feed file?

Here is how you create a feed file using a spreadsheet program. If you want to use a text editor, make sure to use [the required attributes](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md). You can also take a look at a [short example of a feed file](https://go.microsoft.com/fwlink?LinkId=506749).

> [!NOTE]
> Your feed file must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip, .tar.gz, .tgz. We only support .xml files if it is an existing Google-formatted .xml file.

1. Open Microsoft Excel or other spreadsheet program.
1. Create a header row in the first row entering the attribute names that would be used to describe products.   Be sure each attribute is in its own column and you include all [required attributes](./hlp_BA_CONC_AboutBingMerchantCenterCatalogFile.md).
1. Enter your product offer information in the rows below the header row, using one row for each product.               Each item’s attribute values should be listed in the same column as the corresponding header attribute name. This means a product’s id must be in the column with header attribute “id”.
1. Save your spreadsheet as a tab delimited excel file. If using Microsoft Excel, save as Text (Tab delimited) (\*.txt).

## File format requirements

**Note** : If the following file format requirements are not met, your feed file will not be processed.

- File must be tab delimited plain text with extensions: .txt, .zip, .gz, .gzip, .tar.gz, .tgz.        -	.xml files are also accepted (if Google-formatted).
- File name cannot contain any spaces.
- The file name can have a maximum of 90 characters.
- If uploading via FTP, the file name of .txt or .xml files have to match the file name specified for a feed’s settings.        In the case of compressed text format, the compressed .txt file inside the archive (.zip, .gz, .gzip, .tar.gz, .tgz) must have the matching file name. Any feed file that is archived needs to have a single compressed file inside.
- File must start with a single header row.
- Each product offer has to be on a separate line of the file.
- Do not include HTML in the text files.
- Do not include trailing tabs at the end of lines.
- Do not include tabs or line breaks in the middle of offer attributes.
- Special/Invalid characters will cause processing problems. Learn more about Accepted Symbols in feed files next.

## Accepted symbols in feed files

Here are the symbols/special characters and what attribute they are accepted in.

|Symbols|Where you can use|
|---|---|
|Period [.]|Prices, URLs|
|Colon [:]          Question [?]          Forward-slash [/]          Equal [=]|URLs|
|Hyphen [-]|Offer Identifiers where this is valid (eg: ISBN, MPN)|
|Pipe [|]          Comma [,]           Greater [>]|Multi-value fields (MerchantCategory, B_Category)|
|Percent [%]          Special ASCII characters|Redirect URL (ads_redirect)|
|Any Unicode symbol|Brand, Title, Description|


