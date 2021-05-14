---
title: Can I use the Google feed file?
description: Microsoft Merchant Center supports the use of Google data feeds for catalog feed files.
ms.service: "Bing-Ads"
ms.topic: "article"
author: eric-urban
ms.author: eur
---

# Can I use the Google feed file?

Microsoft Merchant Center supports the use of Google data feeds for catalog feed files. This way merchants won’t have to redo the work already done for Google's Product Listing Ads. Make it even easier to import your Google feed files to Microsoft Merchant Center by using the Google Merchant Center import tool. [Learn more](./hlp_BA_CONC_BMC_GMCImportIntro.md)

## Supported File Encoding Types

Microsoft Merchant Center will auto-detect the encoding format of Google-formatted feed files. The supported encoding types are:

- UTF-8
- UTF-16 (little endian and big endian)
- UTF-32 (little endian and big endian)

## Supported File Types

Microsoft Merchant Center will process Google-formatted with the following file extensions:

- .txt
- .xml
- .gz
- .zip
- .gzip
- .tar.gz
- .tgz

Unfortunately Bing does not support .bz2 which Google accepts.

## XML Format Support Limitations

The multi-value attributes in the Google feed that are used by Bing are:

- g:product_type
- g:adwords_labels

The multi-part attributes in the Google feed are not used by Bing.

## Supported Product Offer Attributes:

All Google-specified attributes are accepted by Bing. Bing's requirements for these fields accommodate Google's requirements (such as min/max lengths) for parity across both merchant centers. However not all [Google's fields](./hlp_BA_CONC_BMCGoogleAttributes.md) are used by Microsoft Merchant Center ignores those that are of no use at this time.


