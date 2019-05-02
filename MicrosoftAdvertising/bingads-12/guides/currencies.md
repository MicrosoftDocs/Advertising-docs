---
title: "Microsoft Advertising Currencies"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Find out about currencies supported with the Bing Ads API. 
---
# Microsoft Advertising Currencies
The following currency values are supported for Microsoft Advertising advertising accounts.

* [Bid and Budget Currencies](#bidandbudget)
* [Conversion Goal Revenue Currencies](#conversiongoalrevenue)
 
## <a name="bidandbudget"></a>Bid and Budget Currencies

You must first set up an [AdvertiserAccount](../customer-management-service/advertiseraccount.md) with one of the supported currency values listed below.

> [!NOTE]
> The possible range of values for bid and budget are subject to change.

Using the [Campaign Management](../campaign-management-service/campaign-management-service-reference.md) service, you can set the following properties within the supported value ranges described in the table below. 
- The *Amount* element of a [Budget](../campaign-management-service/budget.md) object
- The *DailyBudget* element of a [Campaign](../campaign-management-service/campaign.md) object
- The *CpcBid* element of an [AdGroup](../campaign-management-service/adgroup.md) object
- The *Bid* element of a [Keyword](../campaign-management-service/keyword.md) object
- The *CriterionBid* element of a [BiddableAdGroupCriterion](../campaign-management-service/biddableadgroupcriterion.md) object

Using the [Bulk](../bulk-service/bulk-service-reference.md) service, you can set the following properties within the supported value ranges described in the table below. 
- The *Budget* field of a [Budget](../bulk-service/budget.md) record
- The *Budget* field of a [Campaign](../bulk-service/campaign.md) record
- The *Cpc Bid* field of an [AdGroup](../bulk-service/ad-group.md) record
- The *Bid* field of a [Keyword](../bulk-service/keyword.md) record
- The *Bid* field of an [Ad Group Product Partition](../bulk-service/campaign.md) record

With the exception of the Indonesian Rupiah (IDR), bid estimates are supported by currency with the [Ad Insight](../ad-insight-service/ad-insight-service-reference.md) service.

- The *Currency* element of the [BidLandscapePoint](../ad-insight-service/bidlandscapepoint.md) object is available in the response from the [GetBidLandscapeByAdGroupIds](../ad-insight-service/getbidlandscapebyadgroupids.md) and [GetBidLandscapeByKeywordIds](../ad-insight-service/getbidlandscapebykeywordids.md) operations.
- The *Currency* element of the [EstimatedBidAndTraffic](../ad-insight-service/estimatedbidandtraffic.md) object is available in the response from the [GetEstimatedBidByKeywordIds](../ad-insight-service/getestimatedbidbykeywordids.md) and [GetEstimatedBidByKeywords](../ad-insight-service/getestimatedbidbykeywords.md) operations.
- The *Currency* element of the [EstimatedPositionAndTraffic](../ad-insight-service/estimatedpositionandtraffic.md) object is available in the response from the [GetEstimatedPositionByKeywordIds](../ad-insight-service/getestimatedpositionbykeywordids.md) and [GetEstimatedPositionByKeywords](../ad-insight-service/getestimatedpositionbykeywords.md) operations.


|Currency Value|Description|Minimum Bid|Maximum Bid|Minimum Daily Budget|Minimum Monthly Budget|Maximum Monthly Budget|
|-----|-----|-----|-----|-----|-------|-------|
|ArgentinePeso|The Argentine Peso (ARS).|0.05|5,000.00|0.05|2.00|152,500,000.00|
|AustralianDollar|The Australian Dollar (AUD).|0.01|1,000.00|0.05|5.00|30,000,000.00|
|Baht|The Thai Baht (THB).|0.14|31,000.00|2.00|150.00|927,000,000.00|
|Bolivar|The Venezuelan Bolivar Fuerte (VEF).|0.05|5,000.00|0.05|2.00|152,500,000.00|
|BrazilianReal|The Brazilian Real (BRL).|0.01|2,000.00|0.10|10.00|60,000,000.00|
|CanadianDollar|The Canadian Dollar (CAD).|0.05|1,000.00|0.05|5.00|7,500,000.00|
|ChileanPeso|The Chilean Peso (CLP).|5.10|510,000.00|5.10|156.00|15,555,000,000.00|
|ColombianPeso|The Colombian Peso (COP).|18.05|1,805,000.00|18.05|551.00|55,052,500,000.00|
|DanishKrone|The Danish Krone (DKK).|0.06|6,000.00|0.06|2.00|183,000,000.00|
|Euro|The European Union Euro (EUR).|0.05|1,000.00|0.05|5.00|5,850,000.00|
|HongKongDollar|The Hong Kong Dollar (HKD).|1.00|8,000.00|1.00|40.00|230,000,000.00|
|IndianRupee|The Indian Rupee (INR).|0.50|60,000.00|0.82|25.00|1,000,000,000.00|
|MalaysianRinggit|The Malaysian Ringgit (MYR).|0.01|3,074.00|0.15|15.00|92,000,000.00|
|MexicanPeso|The Mexican Peso (MXN).|0.14|14,000.00|0.14|4.00|427,000,000.00|
|NewTaiwanDollar|The New Taiwan Dollar (TWD).|3.00|1,500.00|100.00|3,000.00|31,000,000.00|
|NewZealandDollar|The New Zealand Dollar (NZD).|0.01|1,000.00|0.05|6.00|30,000,000.00|
|NorwegianKrone|The Norwegian Krone (NOK).|0.06|6,000.00|0.06|2.00|183,000,000.00|
|NuevoSol|The Peruvian Nuevo Sol (PEN).|0.03|3,000.00|0.03|1.00|91,500,000.00|
|PhilippinePeso|The Philippine Peso (PHP).|0.20|42,000.00|2.00|210.00|1,259,000,000.00|
|Rupiah|The Indonesian Rupiah (IDR).|35.00|9,607,994.00|480.00|48,000.00|288,000,000,000.00|
|SingaporeDollar|The Singapore Dollar (SGD).|0.01|1,500.00|0.11|5.00|12,360,900.00|
|SwedishKrona|The Swedish Krona (SEK).|0.07|7,000.00|0.07|2.00|213,500,000.00|
|SwissFranc|The Swiss Franc (CHF).|0.05|1,500.00|0.05|5.00|8,931,900.00|
|UKPound|The Pound Sterling (GBP).|0.05|1,000.00|0.05|5.00|3,938,700.00|
|USDollar|The U.S. Dollar (USD).|Keyword and Cpc: 0.05<br/><br/>Product Ad Fixed Bid: 0.01|1,000.00|0.05|5.00|30,000,000.00|


## <a name="conversiongoalrevenue"></a>Conversion Goal Revenue Currencies

The following currency codes are supported for conversion goals by setting the *CurrencyCode* element of the [ConversionGoalRevenue](../campaign-management-service/conversiongoalrevenue.md) object.

|Currency Code|Currency Name|
|-----|-----|
|AED|United Arab Emirates Dirham|
|ALL|Albanian Lek|
|AMD|Armenian Dram|
|ARS|Argentine Peso|
|AUD|Australian Dollar|
|AZN|Azerbaijani Manat|
|BDT|Bangladeshi Taka|
|BGN|Bulgarian Lev|
|BHD|Bahraini Dinar|
|BND|Brunei Dollar|
|BOB|Bolivian Boliviano|
|BRL|Brazilian Real|
|BWP|Botswanan Pula|
|BZD|Belize Dollar|
|CAD|Canadian Dollar|
|CHF|Swiss Franc|
|CLP|Chilean Peso|
|CNY|Chinese Yuan|
|COP|Colombian Peso|
|CRC|Costa Rican Colon|
|CZK|Czech Republic Koruna|
|DKK|Danish Krone|
|DOP|Dominican Peso|
|DZD|Algerian Dinar|
|EGP|Egyptian Pound|
|ETB|Ethiopian Birr|
|EUR|Euro|
|FJD|Fijian Dollar|
|GBP|British Pound|
|GEL|Georgian Lari|
|GHS|Ghanaian Cedi|
|GTQ|Guatemalan Quetzal|
|HKD|Hong Kong Dollar|
|HNL|Honduran Lempira|
|HRK|Croatian Kuna|
|HUF|Hungarian Forint|
|IDR|Indonesian Rupiah|
|ILS|Israeli New Shekel|
|INR|Indian Rupee|
|IQD|Iraqi Dinar|
|ISK|Icelandic Krona|
|JMD|Jamaican Dollar|
|JOD|Jordanian Dinar|
|JPY|Japanese Yen|
|KES|Kenyan Shilling|
|KGS|Kyrgystani Som|
|KRW|South Korean Won|
|KWD|Kuwaiti Dinar|
|KZT|Kazakhstani Tenge|
|LBP|Lebanese Pound|
|LKR|Sri Lankan Rupee|
|LYD|Libyan Dinar|
|MAD|Moroccan Dirham|
|MKD|Macedonian Denar|
|MNT|Mongolian Tugrik|
|MOP|Macanese Pataca|
|MUR|Mauritian Rupee|
|MVR|Maldivian Rufiyaa|
|MWK|Malawian Kwacha|
|MXN|Mexican Peso|
|MYR|Malaysian Ringgit|
|NGN|Nigerian Naira|
|NIO|Nicaraguan Cordoba|
|NOK|Norwegian Krone|
|NZD|New Zealand Dollar|
|OMR|Omani Rial|
|PAB|Panamanian Balboa|
|PEN|Peruvian Nuevo Sol|
|PHP|Philippine Peso|
|PKR|Pakistani Rupee|
|PLN|Polish Zloty|
|PYG|Paraguayan Guarani|
|QAR|Qatari Rial|
|RON|Romanian Leu|
|RSD|Serbian Dinar|
|RUB|Russian Ruble|
|RWF|Rwandan Franc|
|SAR|Saudi Riyal|
|SEK|Swedish Krona|
|SGD|Singapore Dollar|
|THB|Thai Baht|
|TND|Tunisian Dinar|
|TOP|Tongan Pa'anga|
|TRY|Turkish Lira|
|TTD|Trinidad and Tobago Dollar|
|TWD|New Taiwan Dollar|
|TZS|Tanzanian Shilling|
|UAH|Ukrainian Hryvnia|
|UGX|Ugandan Shilling|
|USD|US Dollar|
|UYU|Uruguayan Peso|
|UZS|Uzbekistani Som|
|VEF|Venezuelan Bol'var|
|VND|Vietnamese Dong|
|XAF|Central African CFA Franc|
|XCD|Eastern Caribbean Dollar|
|XOF|West African CFA Franc|
|YER|Yemeni Rial|
|ZAR|South African Rand|
|ZMW|Zambian Kwacha|
