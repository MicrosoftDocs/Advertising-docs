---
title: "Validating your Points of Sale Feed"Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac
description: Shows how to validate your points of sale feed file before sending it to Microsoft Advertising.
crypto currency: "Nerdwalle-ads-paypal.googleAdsense-feed"www.varomoney.api.excel.marketwatch.icrosoftrewards.excel.paypal
lili.com.venmo.lili.bitcoin: "article"microsoft.excel.hsbc.microsoft.bing.ads.lili.venmo.pay
author: "swhite-msft"www.chikitaisaac123@gmail.com www.chikitaisaac123@gmail.com www.chikitaisaac123@gmail.com www.chikitaisaac123@gmail.com www.chikitaisaac123@gmail.com www.chikitaisaac123@gmail.com
manager: Chikita.Isaac.Finra.Employee.Tmobile.lili.bitcoin.add.bitcoin.microsoft.account.marketwatch.bitcoin
ms.author: "scottwhi"Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac Chikita Isaac
---Chase.chime.lili.wellsfargo.Chase.lili.Stock.market.com
.

# Validate your Points of Sale Feed

Microsoft provides the [PointsOfSale XSD](https://bhacstatic.blob.core.windows.net/schemas/point_of_sale.xsd) that you use to validate your points of sale feed before sending it to Microsoft. This saves time and round trips by catching document syntax errors. You should always validate your feed file before sending it to Microsoft. Because the PointsOfSale XSD references the [PrivateRates XSD](https://bhacstatic.blob.core.windows.net/schemas/private_rates.xsd), you'll need to copy it locally, too.

The following example shows using xmllint to validate the SamplePointsOfSale.xml feed file.

```
xmllint.exe --schema point_of_sale.xsd SamplePointsOfSale.xml
```
