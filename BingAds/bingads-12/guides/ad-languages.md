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
Your ad language setting determines the language you will use when you write your ads and should be the language of your customers. The campaign level languages setting applies to all ad groups in the campaign; However, if languages are set at both the ad group and campaign level, the ad group-level language will override the campaign-level language. The ad group level language setting applies to all ads in an ad group. 

> [!NOTE]
> Not everyone has the Campaign languages feature yet. If you don't, don't worry. It's coming soon.

Your ad language in combination with your [location targeting](show-ads-target-audience.md) determines who will see your ads. When determining if your ads are eligible to be shown to a particular search user, Bing Ads first determines if your ad language allows for your ad to be shown in a particular country or region then considers the location criteria (and other criteria) settings you have configured. If the target criteria is met and the ad language is available in the country/region, the ad is eligible to display. To learn more, see the Bing Ads help article [How does ad language and location targeting affect who can see my ads?](https://help.bingads.microsoft.com/#apex/3/en/51100/0)

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
|Portuguese|PT<br/><br/>This code differs from the ISO standard for Brazilian Portuguese, PTB.|
|Spanish|ES|
|Swedish|SV|
|TraditionalChinese|ZH|
		
## <a name="productlanguage"></a>Product Language
Your [customer](../customer-management-service/customer.md) language determines the language of the Bing Ads interface. 

The following country codes are supported per customer language e.g. [resellers](management-model-resellers.md) can use these languages and countries in the [Customer](../customer-management-service/customer.md) object when calling the [SignupCustomer](../customer-management-service/signupcustomer.md) operation.

> [!NOTE]
> In New Zealand, Bing Ads is available only on the Bing network. 

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
Countdown customizers let you easily add a countdown (by day, hour, and then minute) to an event in your [Expanded Text Ad](expanded-text-ads.md). The following language codes are supported for [countdown functions](expanded-text-ads.md#countdown).

|Language Code|Language|Countdown Length|
|------------|------------|------------------|
|DA|Danish|8|
|NL|Dutch|8|
|en-AU|English|8|
|en-GB|English|8|
|en-US|English|8|
|FI|Finnish|9|
|FR|French|9|
|DE|German|10|
|IT|Italian|7|
|NO|Norwegian|7|
|pt-BR|Portuguese|8|
|pt-PT|Portuguese|8|
|ES|Spanish|8|
|ES-419|Spanish|8|
|SV|Swedish|8|
|zh-HK|TraditionalChinese|7|
|zh-TW|TraditionalChinese|7|


## <a name="structuredsnippetheaders"></a>Structured Snippet Headers
Structured Snippet headers must be specified in the same language that you intend it to be shown. For example, if you want header *Amenities* in English you must specify the header as *Amenities*.  If you want header *Ausstattung* in German you must specify the header as *Ausstattung* (*Amenities* in German). The following headers are supported per language.

```csv
Language,Amenities,Brands,Courses,Degree programs,Destinations,Featured hotels,Goods,Insurance coverage,Items,Models,Neighborhoods,Services,Service catalog,Shows,Styles,Types
Chinese (Traditional zh-TW),設施,品牌,課程,學位課程,目的地,精選飯店,商品,承保範圍,項目,型號,社區,服務,服務目錄,節目,款式,類型
Danish,Faciliteter,Mærker,Kurser,Kandidatprogrammer,Destinationer,Udvalgte hoteller,Varer,Forsikringsdækning,Elementer,Modeller,Kvarterer,Serviceydelser,Servicekatalog,Shows,Design,Typer
Dutch,Voorzieningen,Merken,Cursussen,Studieprogramma's,Bestemmingen,Aanbevolen hotels,Producten,Dekking,Items,Modellen,Buurten,Services,Servicecatalogus,Shows,Stijlen,Typen
English,Amenities,Brands,Courses,Degree programs,Destinations,Featured hotels,Goods,Insurance coverage,Items,Models,Neighborhoods,Services,Service catalog,Shows,Styles,Types
Finnish,Mukavuudet,Tuotemerkit,Kurssit,Tutkinto-ohjelmat,Määränpäät,Esitellyt hotellit,Tavarat,Vakuutuksen kattavuus,Nimikkeet,Mallit,Kaupunginosat,Palvelut,Huoltoluettelo,Esitykset,Tyylit,Tyypit
French (France),Équipements,Marques,Cours,Programmes d'études,Destinations,Sélection d'hôtels,Biens,Couverture d'assurance,Éléments,Modèles,Quartiers,Services,Catalogue de services,Émissions,Styles,Types
German,Ausstattung,Marken,Kurse,Studiengänge,Ziele,Vorgestellte Hotels,Waren,Versicherungsleistung,Artikel,Modelle,Viertel,Dienstleistungen,Dienstkatalog,Serien,Stile,Typen
Italian,Attrattive,Marche,Corsi,Corsi di studio,Destinazioni,Hotel consigliati,Beni,Copertura assicurativa,Articoli,Modelli,Quartieri,Servizi,Catalogo de servizi,Programmi,Stili,Tipi
Norwegian,Fasiliteter,Merkevarer,Kurs,Universitetsprogrammer,Destinasjoner,Fremhevede hoteller,Varer,Forsikring,Gjenstander,Modeller,Nabolag,Tjenester,Servicekatalog,TV-serier,Stiler,Typer
Portuguese (Brazil pt-BR),Comodidades,Marcas,Cursos,Programas de graduação,Destinos,Hotéis em destaque,Bens,Cobertura do seguro,Itens,Modelos,Vizinhança,Serviços,Catálogo de serviços,Programas,Estilos,Tipos
Spanish (Latin America es-419),Servicios adicionales,Marcas,Cursos,Carreras universitarias,Destinos,Hoteles destacados,Artículos,Cobertura de seguro,Elementos,Modelos,Barrios,Servicios,Catálogo de servicios,Programas,Estilos,Tipos
Swedish,Bekvämligheter,Varumärken,Kurser,Utbildningar,Resmål,Hotellval,Varor,Försäkringstyper,Objekt,Bilmodeller,Grannskap,Tjänster,Servicekatalog,Program,Stilar,Typer
```
