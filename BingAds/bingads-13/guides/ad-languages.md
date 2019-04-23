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
Countdown customizers let you easily add a countdown (by day, hour, and then minute) to an event in your [Expanded Text Ad](expanded-text-ads.md) and [Responsive Search Ad](responsive-search-ads.md). The following language codes are supported for [countdown customizers](countdown-customizers.md).

|Language Code|Language|
|------------|------------|
|DA|Danish|
|NL|Dutch|
|en-AU|English|
|en-GB|English|
|en-US|English|
|FI|Finnish|
|FR|French|
|DE|German|
|IT|Italian|
|NO|Norwegian|
|pt-BR|Portuguese|
|pt-PT|Portuguese|
|ES|Spanish|
|ES-41Spanish|
|SV|Swedish|
|zh-HK|TraditionalChinese|
|zh-TW|TraditionalChinese|

## <a name="structuredsnippetheaders"></a>Structured Snippet Headers
Structured Snippet headers must be specified in the same language that you intend it to be shown. For example, if you want header *Amenities* in English you must specify the header as *Amenities*. If you want header *Ausstattung* in German you must specify the header as *Ausstattung* (*Amenities* in German). The following headers are supported per language.

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

## <a name="actionadextension-actiontext"></a>Action Text for Action Ad Extensions
The action text displayed for action ad extensions will depend on the language that you set when creating or updating the action ad extension. For example, if you want action text displayed as *Act Now* in English you must specify the action type as *ActNow* and set the language to *English*. If you want action text displayed as *Jetzt handeln* in German you must likewise set the action type to *ActNow*, but set the language to *German*. 

Bing Ads does not support all action types for all languages. If you attempt to use an unsupported action type and language combination, an error will be returned. This table lists the rare exceptions i.e. where the translated text exceeds 16 characters.

|Language|Action Types Not Supported| 
|-----|-----|
|Dutch|PostJob|
|French|FindStore,NewCars,TestDrive,UsedCars,ViewCars,VisitStore|
|German|FreePlay,FreeQuote,FreeTrial,StartFree,UsedCars|
|Italian|FreeQuote|
|Norwegian|FreeTrial|

When using the Bing Ads API you will always set the action type using an English pascal case enumeration value i.e., one of the language strings in the first comma separated row below. The language translations are documented for your convenience, although you will never use them directly via the Bing Ads API. 

```csv
Language,ActNow,ApplyNow,BetNow,BidNow,BookACar,BookHotel,BookNow,Browse,BuyNow,ChatNow,Compare,ContactUs,Coupon,Directions,Donate,Download,EmailNow,EnrollNow,Explore,FileNow,FindJob,FindStore,FreePlay,FreeQuote,FreeTrial,GetDeals,GetOffer,GetQuote,JoinNow,LearnMore,ListenNow,LogIn,Message,NewCars,OrderNow,PlayGame,PlayNow,PostJob,Register,RentACar,RentNow,Reserve,Sale,SaveNow,Schedule,SeeMenu,SeeMore,SeeOffer,SellNow,ShopNow,Showtimes,SignIn,SignUp,StartFree,StartNow,Subscribe,SwitchNow,TestDrive,TryNow,UsedCars,ViewCars,ViewNow,ViewPlans,VisitSite,VisitStore,VoteNow,Watch,WatchMore,WatchNow
Danish,Handl nu,Ansøg nu,Spil nu,Byd nu,Reservér en bil,Bestil hotel,Reservér nu,Gennemse,Køb nu,Chat nu,Sammenlign nu,Kontakt os,Kupon,Rutevejledning,Doner,Download,Send e-mail nu,Tilmeld dig nu,Udforsk,Anmeld nu,Find job,Find butik,Gratis spil,Gratis tilbud,Gratis prøve,Få tilbud,Få tilbud,Få et tilbud,Deltag nu,Få mere at vide,Lyt nu,Log på,Besked,Nye biler,Bestil nu,Spil spil,Spil nu,Opslå job,Registrer,Lej en bil,Lej nu,Reservér,Udsalg,Gem nu,Spilleplan,Se menu,Se mere,Se tilbud,Sælg nu,Shop nu,Spilletider,Log på,Tilmeld dig,Start gratis,Start nu,Abonner,Skift nu,Prøvetur,Prøv nu,Brugte biler,Se biler,Start nu,Vis planer,Besøg websted,Besøg butik,Stem nu,Se,Se mere,Se nu
Dutch,Nu beslissen,Nu solliciteren,Nu inzetten,Nu bieden,Auto huren,Hotel boeken,Nu boeken,Bladeren,Nu kopen,Nu chatten,Vergelijken,Contact opnemen,Waardebon,Route,Doneren,Downloaden,Nu e-mailen,Nu inschrijven,Verkennen,Nu inzenden,Vacature zoeken,Winkel zoeken,Gratis spelen,Gratis offerte,Gratis demo,Deals zien,Aanbieding zien,Offerte krijgen,Nu meedoen,Meer informatie,Nu luisteren,Aanmelden,Bericht,Nieuwe auto's,Nu bestellen,Game spelen,Nu spelen,Vacature plaatsen(Not supported),Registreren,Auto huren,Nu huren,Reserveren,Sale,Nu besparen,Schema,Menu zien,Meer zien,Aanbieding zien,Nu verkopen,Nu shoppen,Aanvangstijd,Aanmelden,Registreren,Gratis beginnen,Nu beginnen,Abboneren,Nu wisselen,Proefrit,Nu proberen,Occasions,Auto's tonen,Nu tonen,Plannen tonen,Site bezoeken,Winkel bezoeken,Nu stemmen,Kijken,Meer kijken,Nu kijken
English,Act Now,Apply Now,Bet Now,Bid Now,Book A Car,Book Hotel,Book Now,Browse,Buy Now,Chat Now,Compare,Contact Us,Coupon,Directions,Donate,Download,Email Now,Enroll Now,Explore,File Now,Find Job,Find Store,Free Play,Free Quote,Free Trial,Get Deals,Get Offer,Get Quote,Join Now,Learn More,Listen Now,Log In,Message,New Cars,Order Now,Play Game,Play Now,Post Job,Register,Rent A Car,Rent Now,Reserve,Sale,Save Now,Schedule,See Menu,See More,See Offer,Sell Now,Shop Now,Showtimes,Sign In,Sign Up,Start Free,Start Now,Subscribe,Switch Now,Test Drive,Try Now,Used Cars,View Cars,View Now,View Plans,Visit Site,Visit Store,Vote Now,Watch,Watch More,Watch Now
Finnish,Toimi nyt,Käytä nyt,Veikkaa nyt,Tarjoa nyt,Varaa auto,Varaa hotelli,Varaa nyt,Selaa,Osta nyt,Keskustele nyt,Vertaa,Ota yhteyttä,Kuponki,Reittiohjeet,Lahjoita,Lataa,Sähköpostita,Ilmoittaudu nyt,Etsi,Hae nyt,Etsi työpaikka,Etsi kauppa,Ilmainen peli,Ilmaistarjous,Ilmaiskokeilu,Hae sopimuksia,Hae tarjous,Hae tarjous,Liity nyt,Lue lisää,Kuuntele nyt,Kirjaudu sisään,Viesti,Uudet autot,Tilaa nyt,Pelaa peli,Toista nyt,Lähetä työ,Rekisteröi,Vuokraa auto,Vuokraa nyt,Varaa,Myynti,Tallenna nyt,Aikataulu,Näytä valikko,Näytä lisää,Näytä tarjous,Myy nyt,Osta nyt,Esitysajat,Kirjaudu sisään,Rekisteröidy,Aloita ilmainen,Aloita nyt,Tilaa,Vaihda nyt,Koeajo,Kokeile nyt,Käytetyt autot,Näytä autot,Näytä nyt,Suunnitelmat,Käy paikalla,Siirry kauppaan,Äänestä nyt,Katso,Katso lisää,Katso nyt
French,Allez-y,Appliquer,Parier,Faire une offre,Réserver voiture,Réserver hôtel,Réserver,Parcourir,Acheter,Discuter,Comparer,Nous contacter,Coupon,Itinéraires,Faire un don,Télécharger,Envoyer e-mail,S’inscrire,Explorer,Ranger,Trouver emploi,Trouver un magasin(Not supported),Jeu gratuit,Devis gratuit,Essai gratuit,Obtenir offres,Obtenir offre,Obtenir devis,Rejoindre,En savoir plus,Écouter,Connexion,Message,Nouvelles voitures(Not supported),Commander,Jouer,Lire,Publier emploi,S’inscrire,Louer voiture,Louer,Réserver,Vente,Enregistrer,Planifier,Voir le menu,Afficher plus,Voir l’offre,Vendre,Acheter,Horaires,Connexion,S’inscrire,Démarrer gratuit,Démarrer,S’abonner,Changer,Version d’évaluation(Not supported),Essayer,Voitures d’occasion(Not supported),Afficher voitures(Not supported),Afficher,Afficher plans,Visiter le site,Visiter un magasin(Not supported),Voter,Regarder,Regarder plus,Regarder
German,Jetzt handeln,Jetzt bewerben,Jetzt wetten,Jetzt bieten,Auto buchen,Hotel buchen,Jetzt buchen,Durchsuchen,Jetzt kaufen,Jetzt chatten,Vergleichen,Kontaktieren,Coupon,Wegbeschreibung,Spenden,Download,E-Mail senden,Registrieren,Erkunden,Einreichen,Job suchen,Shop suchen,Kostenlos spielen(Not supported),Kostenloses Angebot(Not supported),Kostenlose Testversion(Not supported),Angebote,Angebot,Angebot,Jetzt beitreten,Mehr Info,Jetzt anhören,Anmelden,Nachricht,Neue Autos,Jetzt bestellen,Spiel spielen,Jetzt spielen,Job posten,Registrieren,Auto mieten,Jetzt mieten,Reservieren,Vertrieb,Jetzt speichern,Zeitplan,Menü anzeigen,Mehr anzeigen,Angebot anzeigen,Jetzt verkaufen,Jetzt einkaufen,Vorstellungen,Anmelden,Registrieren,Kostenlos starten(Not supported),Jetzt starten,Abonnieren,Jetzt wechseln,Testfahrt,Jetzt testen,Gebrauchtfahrzeuge(Not supported),Autos anzeigen,Jetzt ansehen,Pläne anzeigen,Site besuchen,Shop besuchen,Jetzt abstimmen,Ansehen,Weitere ansehen,Jetzt ansehen
Italian,Agisci ora,Applica ora,Scommetti ora,Offri ora,Prenota un'auto,Prenota hotel,Prenota ora,Sfoglia,Acquista ora,Chatta ora,Confronta,Contattaci,Coupon,Indicazioni,Dona,Scarica,Invia e-mail,Iscriviti ora,Esplora,Inoltra ora,Trova lavoro,Trova il negozio,Gioco gratuito,Preventivo gratis(Not supported),Prova gratuita,Ottieni offerte,Ottieni offerta,Preventivo,Partecipa ora,Ulteriori info,Ascolta ora,Accedi,Messaggio,Auto nuove,Ordina ora,Gioca,Riproduci ora,Offerta lavoro,Registrati,Noleggia auto,Noleggia ora,Prenota,Vendita,Salva ora,Pianifica,Visualizza menu,Vedi altro,Vedi offerta,Vendi ora,Acquista ora,Orari,Accedi,Iscriviti,Inizia gratis,Inizia ora,Sottoscrivi,Cambia subito,Prova su strada,Prova ora,Auto usate,Visualizza auto,Visualizza ora,Vedi piani,Vai al sito,Visita negozio,Vota ora,Guarda,Guarda altro,Guarda ora
Norwegian,Handle nå,Søk nå,Sats nå,By nå,Reserver en bil,Reserver hotell,Reserver nå,Bla gjennom,Kjøp nå,Chat nå,Sammenlign,Kontakt oss,Kupong,Veibeskrivelse,Doner,Last ned,Send e-post nå,Registrer deg,Utforsk,Søk nå,Finn jobb,Finn butikk,Gratis spill,Gratis anbud,Gratis prøveversjon(Not supported),Få tilbud,Få tilbud,Få anbud,Bli med nå,Les mer,Hør nå,Logg på,Melding,Nye biler,Bestill nå,Spill,Spill nå,Legg ut jobb,Registrer deg,Lei en bil,Lei nå,Reserver,Salg,Spar nå,Terminliste,Se meny,Se mer,Se tilbud,Selg nå,Handle nå,Visningstider,Logg på,Meld deg på,Start gratis,Start nå,Abonner,Bytt nå,Testkjør,Prøv nå,Brukte biler,Vis biler,Vis nå,Se planer,Gå til side,Gå til butikk,Stem nå,Se,Se mer,Se nå
Portuguese,Aja Agora,Solicitar Agora,Apostar Agora,Fazer Lance,Alugar um Carro,Reservar Hotel,Reservar Agora,Procurar,Comprar Agora,Conversar Agora,Comparar,Fale Conosco,Cupom,Trajeto,Doar,Download,Enviar Email,Registrar Agora,Explorar,Arquivar Agora,Buscar Trabalho,Encontrar Loja,Jogo Grátis,Cotação Grátis,Avalie Grátis,Obter Ofertas,Obter Oferta,Obter Cotação,Ingressar Agora,Saiba Mais,Ouvir Agora,Fazer Logon,Mensagem,Carros Novos,Encomendar,Jogar Jogo,Jogar Agora,Postar Trabalho,Registrar,Alugar um Carro,Alugar Agora,Reservar,Venda,Salvar Agora,Agenda,Ver Menu,Ver Mais,Ver Oferta,Vender Agora,Comprar Agora,Horários,Entrar,Inscrever-se,Começar Grátis,Iniciar Agora,Assinar,Mudar Agora,Test Drive,Experimentar Já,Carros Usados,Exibir Carros,Exibir Agora,Exibir Planos,Acessar Site,Visitar Loja,Votar Agora,Assistir,Assistir Mais,Assistir Agora
Spanish,Actuar ahora,Aplicar ahora,Apostar ahora,Pujar ahora,Reservar coche,Reservar hotel,Reservar ahora,Explorar,Comprar ahora,Chat ahora,Comparar,Contáctanos,Cupón,Indicaciones,Donar,Descargar,Enviar correo,Inscribirse,Explorar,Archivar ahora,Buscar trabajo,Buscar tienda,Jugar gratis,Presupuesto,Jugar ahora,Obtener ofertas,Obtener oferta,Obtener oferta,Unirse ahora,Más información,Escuchar ahora,Iniciar sesión,Mensaje,Coches nuevos,Pedir ahora,Jugar juego,Jugar ahora,Publicar anuncio,Registro,Alquilar coche,Alquilar ahora,Reservar,Rebajas,Guardar ahora,Programación,Ver menú,Ver más,Ver oferta,Vender ahora,Comprar ahora,Horarios,Iniciar sesión,Registrarse,Comenzar gratis,Iniciar ahora,Suscribirse,Cambiar ahora,Probar coche,Probar ahora,Coches usados,Ver coches,Ver ahora,Ver planes,Visitar sitio,Visitar tienda,Votar ahora,Ver,Ver más,Ver ahora
Swedish,Gör det nu,Ansök nu,Spela nu,Bjud nu,Boka en bil,Boka hotel,Boka nu,Bläddra,Köp nu,Chatta nu,Jämför,Kontakta oss,Kupong,Vägbeskrivning,Donera,Ladda ned,Skicka mejl nu,Registrera nu,Utforska,Spara nu,Hitta jobb,Hitta butik,Spela gratis,Gratis offert,Prova gratis,Se erbjudanden,Se erbjudanden,Begär offert,Gå med nu,Mer information,Lyssna nu,Logga in,Meddelande,Nya bilar,Beställ nu,Spela,Spela nu,Lägg upp jobb,Registrera dig,Hyr bil,Hyr nu,Reservera,Rea,Spara nu,Schemalägg,Visa meny,Visa mer,Visa erbjudande,Sälj nu,Shoppa nu,Föreställningar,Logga in,Registrering,Börja gratis,Börja nu,Prenumerera,Växla nu,Provkör,Prova nu,Begagnade bilar,Visa bilar,Visa nu,Visa planer,Besök plats,Besök butik,Rösta nu,Visa,Visa mer,Titta nu
TraditionalChinese,立即行動,立即申請,立即下注,立即出價,買車,訂旅館,立即預訂,瀏覽,立即購買,立即交談,比較,與我們連絡,優待券,路線,捐贈,下載,立即寄電子郵件,立即報名,探索,立即提交,找工作,尋找商店,免費玩,免費報價,免費試用,取得優惠,取得優惠,取得報價,立即加入,深入了解,立即聆聽,登入,訊息,新車,立即訂購,玩遊戲,立即玩,張貼職缺,註冊,租車,立即租下,預約,特賣,立即省錢,排程,查看菜單,查看更多,查看優惠,立即銷售,立即選購,放映時間,登入,註冊,免費開始,立即開始,訂閱,立即切換,試駕,立即試試,二手車,檢視車輛,立即檢視,檢視方案,造訪網站,造訪商店,立即投票,觀看,觀看更多,立即觀看
```
