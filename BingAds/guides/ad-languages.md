---
title: "Ad Languages"
ms.service: "bing-ads"
ms.topic: "article"
author: "eric-urban"
ms.author: "eur"
description: Language options in Bing Ads give you control over your advertising campaign and experience. 
---
# Ad Languages
Language options in Bing Ads give you control over your advertising campaign and experience. 
 
## <a name="adlanguage"></a>Ad Language
Your ad language setting determines the language you will use when you write your ads and should be the language of your customers. The campaign level languages setting applies to all ad groups in the campaign; However, If languages are set at both the ad group and campaign level, the ad group-level language will override the campaign-level language. The ad group level language setting applies to all ads in an ad group. 

> [!NOTE] 
> Not everyone has the Campaign languages feature yet. If you don't, don't worry. It's coming soon.

Your ad language in combination with your [location targeting](/bingads/guides/show-ads-target-audience.md) determines who will see your ads. When determining if your ads are eligible to be shown to a particular search user, Bing Ads first determines if your ad language allows for your ad to be shown in a particular country or region then considers the location criteria (and other criteria) settings you have configured. If the target criteria is met and the ad language is available in the country/region, the ad is eligible to display. To learn more, see the Bing Ads help article [How does ad language and location targeting affect who can see my ads?](https://help.bingads.microsoft.com/#apex/3/en/51100/0)

The following are the possible languages that you may use to write your ads and keywords.

|Language|Language Code|
|------------|-----------------|
|Danish|DA|
|Dutch|NL|
|English|EN|
|Finnish|FI|
|French|FR|
|German|DE|
|Italian|IT|
|Norwegian|NO|
|Portuguese|PT<br /><br />This code differs from the ISO standard for Brazilian Portuguese, PTB.|
|Spanish|ES|
|Swedish|SV|
|TraditionalChinese<br /><br />You must use *TraditionalChinese* (without space) when setting the language of a campaign or ad group.<br /><br />You must use *Traditional Chinese* (with space) when setting request elements using the Ad Insight Service.|ZH|
		
## <a name="productlanguage"></a>Product Language
Your [customer](/bingads/customer-management-service/customer.md) language determines the language of the Bing Ads interface. 

The following country codes are supported per customer language e.g. [resellers](/bingads/guides/management-model-resellers.md) can use these languages and countries in the [Customer](/bingads/customer-management-service/customer.md) object when calling the [SignupCustomer](/bingads/customer-management-service/signupcustomer.md) operation.

> [!NOTE]
> In New Zealand, Bing Ads is available only on the Bing network. For other countries listed below, Bing Ads is available on the Yahoo Bing Network.

|Language|Country Code|
|------------|------------------|
|English|AD, AG, AI, AL, AM, AQ, AS, AU, AW, AZ, BA, BB, BD, BE, BG, BI, BM, BN, BS, BT, BW, BY, BZ, CC, CK, CV, CX, CY, CZ, DJ, DM, EE, ER, ET, FJ, FM, FO, GA, GB, GD, GE, GF, GH, GI, GL, GM, GN, GP, GQ, GR, GU, GW, GY, HR, HU, ID, IE, IL, IN, IS, JM, JP, KE, KG, KH, KI, KM, KN, KR, KY, KZ, LA, LC, LI, LK, LR, LS, LT, LV, MC, MD, ME, MG, MH, MK, MM, MN, MO, MP, MQ, MR, MS, MT, MU, MV, MW, MY, NA, NC, NF, NG, NP, NR, NU, NZ, PF, PG, PH, PK, PL, PM, PN, PR, PS, PW, RE, RO, RS, RU, RW, SB, SC, SG, SH, SI, SK, SL, SM, SO, SR, ST, SZ, TC, TH, TJ, TK, TM, TO, TR, TT, TV, TZ, UA, UG, US, UZ, VA, VG, VI, VN, VU, WF, WS, YT, ZA, ZM, ZW|
|French|BF, BJ, CD, CF, CG, CI, CM, FR, HT, LU, ML, NE, SN, TD, TG|
|German|AT, CH, DE|
|Italian|IT|
|Portuguese|AO, BR, MZ, PT, TL|
|Spanish|AR, BO, CL, CO, CR, DO, EC, ES, GT, HN, MX, NI, PA, PE, PY, SV, UY, VE|
|TraditionalChinese|HK, TW|

		
## <a name="countdownlanguage"></a>Countdown Language
Countdown customizers let you easily add a countdown (by day, hour, and then minute) to an event in your [Expanded Text Ad](/bingads/guides/expanded-text-ads.md). The following language codes are supported for [countdown functions](/bingads/guides/expanded-text-ads.md#countdown).

|Language Code|Language|Countdown Length|
|------------|------------|------------------|
|DA|Danish|11|
|NL|Dutch|10|
|en-AU|English|10|
|en-GB|English|10|
|en-US|English|10|
|FI|Finnish|12|
|FR|French|10|
|DE|German|10|
|IT|Italian|10|
|NO|Norwegian|11|
|pt-BR|Portuguese|10|
|pt-PT|Portuguese|10|
|ES|Spanish|10|
|ES-419|Spanish|10|
|SV|Swedish|10|
|zh-HK|Traditional Chinese|7|
|zh-TW|Traditional Chinese|7|


## <a name="structuredsnippetheaders"></a>Structured Snippet Headers
Structured Snippet headers must be specified in the same language that you intend it to be shown. For example, if you want header *Amenities* in English you must specify the header as *Amenities*.  If you want header *Ausstattung* in German you must specify the header as *Ausstattung* (*Amenities* in German). The following headers are supported per language.

```csv
Language,Amenities,Brands,Courses,Degree programs,Destinations,Featured hotels,Goods,Insurance coverage,Items,Models,Neighborhoods,Services,Service catalog,Shows,Styles,Types
Chinese (Traditional zh-TW),設施,品牌,課程,學位課程,目的地,精選飯店,商品,承保範圍,項目,型號,社區,服務,服務目錄,節目,款式,類型
Dutch,Voorzieningen,Merken,Cursussen,Studieprogramma's,Bestemmingen,Aanbevolen hotels,Producten,Dekking,Items,Modellen,Buurten,Services,Servicecatalogus,Shows,Stijlen,Typen
English,Amenities,Brands,Courses,Degree programs,Destinations,Featured hotels,Goods,Insurance coverage,Items,Models,Neighborhoods,Services,Service catalog,Shows,Styles,Types
French (France),Équipements,Marques,Cours,Programmes d'études,Destinations,Sélection d'hôtels,Biens,Garanties,Éléments,Modèles,Quartiers,Services,Catalogue de services,Émissions,Styles,Types
German,Ausstattung,Marken,Kurse,Studiengänge,Ziele,Vorgestellte Hotels,Waren,Versicherungsleistung,Artikel,Modelle,Viertel,Dienstleistungen,Dienstkatalog,Serien,Stile,Typen
Italian,Servizi,Brand,Corsi,Corsi di laurea,Destinazioni,Hotel consigliati,Beni,Coperture assicurative,Articoli,Modelli,Quartieri,Servizi,Catalogo de servizi,Programmi,Stili,Tipi
Portuguese (Brazil pt-BR),Comodidades,Marcas,Cursos,Programas de graduação,Destinos,Hotéis em destaque,Bens,Cobertura do seguro,Itens,Modelos,Bairros,Serviços,Catálogo de serviços,Programas,Estilos,Tipos
Spanish (Latin America es-419),Servicios adicionales,Marcas,Cursos,Carreras universitarias,Destinos,Hoteles destacados,Artículos,Cobertura de seguro,Elementos,Modelos,Barrios,Servicios,Catálogo de servicios,Programas,Estilos,Tipos
Swedish,Faciliteter,Varumärken,Kurser,Utbildningsprogram,Resmål,Utvalda hotell,Varor,Försäkringstyper,Objekt,Modeller,Områden,Tjänster,Servicekatalog,Program,Stilar,Typer
```
