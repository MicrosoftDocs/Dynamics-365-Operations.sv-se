---
title: Nyheter och ändringar i Dynamics AX 7.0 (februari 2016)
description: Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics AX 7.0. Den här versionen innehåller både plattform och programfunktioner och gavs ut i februari 2016.
author: sericks007
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6539bf6acf0216f1491cbf852f2c9a7063fbe26e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752876"
---
# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Nyheter och ändringar i Dynamics AX 7.0 (februari 2016)

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics AX 7.0. Den här versionen innehåller både plattform och programfunktioner och gavs ut i februari 2016.

## <a name="cost-management"></a>Kostnadshantering

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Få en snabb överblick över lagersaldot för produkter i arbete (PIA) samt PIA-inflödet och -utflödet för det valda räkenskapsåret.</td>
<td>Inte tillämpligt</td>
<td>Arbetsytan <strong>Kostnadsredovisning</strong> innehåller ett avsnitt där lagerutdraget eller PIA-lagerutdraget visas för den valda räkenskapsperioden. Lagerutdraget baseras på en cachedatamängd som uppdateras var 24:e timme som standard. Cachedatamängden kan konfigureras så att användare kan uppdatera den manuellt för rapportering i realtid. <strong>Statuskortet för datauppdatering</strong> i arbetsytan <strong>Kostnadsredovisning</strong> visar när cachen senast uppdaterades.</td>
<td>Kostnadscontrollers är intresserade av att veta om lagret eller PIA-lagerutdragssaldot ökar eller minskar över tid. Genom att klassificera drifthändelser i utdragen kan kostnadscontrollern få en översikt över hur lagret flödar. Om lagret eller PIA-lagret utvärderas med standardkostnader kan den registrerade totala avvikelsen också visas.</td>
</tr>
<tr>
<td>Använd modulen <strong>Kostnadshantering</strong>.</td>
<td>Inte tillämpligt</td>
<td>Kostnadshantering presenteras som ett domänområde. Kostnadsrelaterade konfigurationer och insikter var utspridda i Lagerhantering, Produktionskontroll och Leverantörsreskontra.</td>
<td>Eftersom alla uppgifter som är relaterade till kostnadsredovisningen är centraliserade i en modul är det enklare för kostnadscontrollers att underhålla systemet.</td>
</tr>
<tr>
<td>Bokföringstyperna som gäller lagerredovisning och produktionsredovisning har uppdaterats.</td>
<td>Etiketterna i formulären <strong>Lagerbokföring (InventPosting)</strong>, <strong>Resurs (Resource)</strong>, <strong>Resursgrupp (ResourceGroup)</strong> och <strong>Produktionsgrupp (ProductionGroup)</strong> justeras inte alltid mot etiketterna av typen <strong>Redovisningsbokföringstyp (LedgerPostingType)</strong> som faktiskt används. Det är inte enkelt att förstå terminologin som används i etiketterna.</td>
<td>Etiketterna har uppdaterats så att etiketter på sidorna <strong>InventPosting</strong>, <strong>Resurs</strong>, <strong>ResourceGroup</strong> och <strong>ProductionGroup</strong> matchar <strong>LedgerPostingType</strong>-etiketterna. Alla etiketter har också bytt namn så att etiketterna matchar drifthändelserna. Observera att själva bokföringslogiken inte har ändrats.</td>
<td>Det är enklare att konfigurera systemet eftersom de nya etiketterna är relaterade till drifthändelserna som använder den här bokföringstypen.</td>
</tr>
<tr>
<td>Importera/exportera inköpspriset, kostnads- eller försäljningspriset från Microsoft Excel till eller från en kostnadsversion.</td>
<td>Du kan inte importera priser eller kostnader korrekt till en kostnadsversion eftersom datamodellen kräver ett InventDim-ID.</td>
<td>Introduktionen av datatabeller gör det möjligt att tillämpa en import- och exportfunktion. Med den här funktionen kan användare importera/exportera priser eller kostnader till en kostnadsversion.
<ul>
<li>Importera en fullständig lista över nästa års inköpspriser som hämtas från inköpsavdelningen.</li>
<li>Skicka kostnader och standardförsäljningspriser från huvudkontor till ett eller flera försäljningsföretag i samma åtgärd.</li>
</ul></td>
<td>Kostnadscontrollers kan spara mycket tid när de underhåller systemet, särskilt när de måste underhålla förutbestämda kostnader för nästa räkenskapsår.</td>
</tr>
<tr>
<td>Få en snabb överblick av lagersaldot och den genomsnittliga enhetskostnaden för ett kostnadsobjekt.</td>
<td>Användaren måste öppna formuläret Behållning och välja lagerdimensionerna som återspeglar kostnadsobjektet. Därför måste användaren veta vilka lagerdimensioner som valdes för ekonomiskt lager för den specifika produkten.</td>
<td>En ny <strong>kostnadsobjektsida</strong> har lagts till. Som standard visar den här sidan alla kostnadsobjekt som hör till produkten. Sidan visar aktuell lagerkvantitet, värde och den genomsnittliga enhetskostnaden per objekt.</td>
<td>Det tar bort en del av komplexiteten och gör det enklare att vara en kostnadscontroller.</td>
</tr>
<tr>
<td>Använd den nya sidan <strong>Kostnadsposter</strong> vid lagerkontroll.</td>
<td>Det kan vara komplicerat att utföra lagerstyrning av registrerade lagertransaktioner och relaterade kvittningar eftersom samma transaktioner kan vara fysiska eller ekonomiska.</td>
<td>Sidan <strong>Kostnadsposter</strong> ger ett nytt sätt att visa lagertransaktioner.
<ul>
<li>Transaktioner visas i kronologisk ordning.</li>
<li>Endast transaktioner som bidrar till kostnader inkluderas.</li>
<li>Kostnader kan vara fysiska eller ekonomiska.</li>
<li>Kvantiteten kan vara fysisk eller ekonomisk.</li>
<li>Kostnaderna läggs till successivt.</li>
</ul></td>
<td>Kostnadscontrollers kan spara mycket tid när de måste utföra lagerstyrning på transaktionsnivå.</td>
</tr>
<tr>
<td>Använd den nya dialogrutan <strong>PIA-utdrag för produktion</strong> för att visa en översikt över ackumulerade kostnader för en specifik produkt.</td>
<td>Inte tillämpligt</td>
<td>PIA-utdraget visar ett summerat PIA-saldo av den specifika produktionsordern, grupperad i lämpliga kostnadsklassificeringar. Ett diagram visar, i kronologisk ordning, hur driftsbokföringar har påverkat PIA-saldot.</td>
<td>Kostnadscontrollers kan spara mycket tid när de vill veta det aktuella PIA-saldot för en viss produktionsorder eller hur mycket material som har förbrukats för ordern.</td>
</tr>
<tr>
<td>Använd funktionen Visa kostnadsjämförelse som har introducerats för tillverkningsorder. Funktionen gör det enklare att jämföra kostnader som hör till en tillverkningsorder.</td>
<td>Användaren kan bara jämföra uppskattade kostnader och realiserade kostnader. Jämförelsen kan göras på den lägsta nivån.</td>
<td>Med kostnadsjämförelsefunktionen kan kostnadscontrollers jämföra följande data:
<ul>
<li>Aktiv kostnad jämfört med uppskattad kostnad = planeringsavvikelse</li>
<li>Uppskattad kostnad jämfört med realiserad kostnad = produktionsavvikelse</li>
<li>Planeringsavvikelse + produktionsavvikelse = total avvikelse</li>
</ul>
Den här funktionen fungerar oberoende av kostnadsredovisningsmetoder som tilldelats den tillverkade artikeln. Som standard visar ett diagram kostnadsjämförelsen efter typ av kostnadsgrupp. I diagrammet kan användarna borra ner till mer detaljerade nivåer.</td>
<td>Den låter kostnadscontrollers eller produktionschefer analysera var produktionsavvikelserna kommer från, och vad som orsakar dem.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Utvecklare

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Skapa webbaserade lösningar i molnet som är tillgängliga på många enheter. | Inte tillgänglig | Den aktuella versionen av Dynamics AX baseras på en ny webbaserad klient och ett nytt webbaserat klientramverk. | Du kan skapa nästa generations lösningar till dina slutanvändare. |
| Använd Microsoft Visual Studio för att utveckla dina lösningar. | Microsoft MorphX är huvudutvecklingsmiljön, men en del utveckling sker i Visual Studio. | Visual Studio är den enda utvecklingsmiljön. | Välbekanta Dynamics AX 2012-begrepp finns kvar och har anpassats sömlöst till Visual Studio-ramverket och -paradigmerna. Standardinteroperabilitet med andra .NET-språk och .NET-projekt stöds. |
| Kompilera CIL (Common Intermediate Language) för alla funktioner. | X++ kompileras till p-kod. | Den splitternya X++kompileraren skapar CIL för alla funktioner. CIL är samma mellanliggande språk som används av andra .NET-baserade språk. | CIL är snabbare, kan effektivt referera till klasser i hanterade DLL-bibliotek (Dynamic Link Library) och kan köras med många .NET-verktyg. |
| Bädda in BI-rapporter (Business Intelligence) och visualiseringar i Microsoft Dynamics AX-klienten. | Inte tillgänglig | Skapa mycket intuitiva och smidiga visualiseringar. | Du får beslutsgrundande insikter som baseras på BI. |
| Integration med Microsoft Office. | Inte tillgänglig | Nya möjligheter inkluderar appen Excel Data Connector, sidan **Arbetsboksdesigner**, Exportera API och Dokumenthantering. | Du kan skapa produktivitetslösningar för dina slutanvändare. |
| Automatisera version, test och distribution. | Delvis tillgänglig | Distribuera utvecklartopologin med hjälp av VM för utvecklare och version. Konfigurera automatiskt versions-VM för att upptäcka, bygga moduler från Visual Studio Online (VSO) och för att köra tester. C\# och X++-modulkompilering och -referenser stöds. | Utvecklarens produktivitet ökar genom att kostnaden för och arbetet med testning och validering minskas. |
| Anpassa med överlägg och tillägg. | Tillägg är inte tillgängliga. | Den aktuella versionen av Dynamics AX har en ny anpassningsmodell. | Du kan anpassa källkoden och metadata för modellelement som skickats av Microsoft eller externa Microsoft-partners. |
| Bygg nya kontroller och UI-element genom att använda X++ och ett modernt webbramverk. | Anpassade kontroller förlitar sig på externa ramverk som Microsoft ActiveX och Windows Presentation Foundation (WPF). | Det är enklare att bygga kontroller i den aktuella versionen. X++-ramverket kan användas för programbeteende och affärslogik, och en HTML-/JavaScript-baserad klient stöder moderna visualiseringar. | Dina kontroller kan utformas för att se ut och uppföra sig precis som våra OOB-kontroller för Dynamics AX. |
| Utvärdera och finjustera prestanda genom att använda nya verktyg. | PerfSDK, Data Expansion Toolkit, appen Trace Parser WEb och PerfTimer är inte tillgängliga. | PerfSDK, Data Expansion Toolkit, appen Trace Parser Web och PerfTimer är nya. | Med SDK (Software Development Kit) kan du testa och validera prestanda i alla kritiska affärsprocesser genom att köra tester med en enskild användare eller, vid behov, med flera användare. Med Data Expansion Toolkit kan du korrekt expandera alla prestandatester vars huvuddata och transaktionella data måste utökas korrekt. Med Trace Parser kan du validera ett prestandatest med en enskild användare eller en körning med flera användare. Med PerfTimer kan du se om en fråga eller specifikt metodanrop medför prestandaproblem. Därför måste du inte använda spårning och analysera allt i detalj. |
| Exponera uppdaterad vy genom att använda OData. | Inte tillgänglig | Den aktuella versionen av Dynamics AX introducerar en offentlig OData-tjänstslutpunkt som aktiverar åtkomst till Dynamics AX-data på ett konsekvent sätt mellan många klienter. | Dina lösningar kan interagera med RESTful-tjänster, dela data på ett identifierbart sätt och stödja bred integrering med hjälp av HTTP-stackprotokollet. |
| Dra nytta av affärsanslutningen för att skapa affärslogik och stödja integrationsscenarier. | Business Connector kan ringa till koden X ++ från hanterad kod. Vi rekommenderar att du endast använder Business Connector för att författa affärslogik i C\#, inte för integrationsscenarier. | Affärsanslutningen stöds inte längre. Redigeringskravet beror på att X++ kompileras till förvaltad kod. Därför är interop enklare. Integrationsscenarierna uppfylls när OData används. | Du kan inte använda affärsanslutningen framledes. |
| Välj skalan (det vill säga antalet decimaler) i verkliga databasfält och utökade datatyper (EDT:er). | Skalan 16 är standardskalan och kan inte ändras av utvecklaren. | EDT:er och fält har nu en skalegenskap som kan användas för det enskilda fältet och EDT:n. Standard är 6, inte 16. | Prestanda med NCCI-register (stöd för minnesinterna åtgärder i SQL) är snabbare vad gäller storlek när en lägre skala används. Ändra skalan beroende på din användning av enskilda fält. |

## <a name="financial-management"></a>Ekonomisk styrning

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Exportera kontostrukturer till Microsoft Excel.</td>
<td>Inte tillgänglig</td>
<td>Nu kan du välja en kontostruktur och exportera den till Excel.</td>
<td>Många kunder har begärt möjligheten att exportera kontostrukturer till Excel för enklare filtrering.</td>
</tr>
<tr>
<td>Visa redovisning och avancerade regelstrukturer som associeras med en kontostruktur på en sida.</td>
<td> Användaren måste navigera till flera formulär för att visa redovisnings - och kontostrukturen som används.</td>
<td>Faktarutor har lagts till på kontostruktursidan.</td>
<td>Det är enklare att komma åt viktig information när kontostrukturer definieras och redigeras.</td>
</tr>
<tr>
<td>Visa redovisning som associeras med en kontoplan på en enskild sida.</td>
<td>Användaren måste navigera till varje företag och öppna redovisningsformuläret för att se kontoplanen som är tilldelad till redovisningen.</td>
<td>Faktarutor har lagts till på sidan <strong>Kontoplan</strong>.</td>
<td> Det är enklare att komma åt viktig information när en kontoplan definieras och tilldelas.</td>
</tr>
<tr>
<td>Visa justeringar i bokslutsarket och UB-transaktioner i olika kolumner på listsidan <strong>Råbalans</strong>.</td>
<td>Användaren ser båda typer av transaktioner i samma kolumn.</td>
<td>Ytterligare en parameter har lagts till på listsidan <strong>Råbalans</strong>.</td>
<td>Det blir lättare att skapa en mer koncis analys av data och funktionen krävs även för myndighetsrapportering i vissa länder/regioner.</td>
</tr>
<tr>
<td>Använd den nya sidan <strong>Global allmän journal</strong>.</td>
<td>Inte tillgänglig</td>
<td>Använd den nya sidan <strong>Global allmän journal</strong> för att lägga in allmänna journaler. Behörigheter för den här sidan läggs till i rollen <strong>Revisor</strong>.</td>
<td>Gör det möjligt för en revisor för delade tjänster att ange allmänna journaler mellan företag utan att behöva lämna formuläret eller byta företagssammanhang.</td>
</tr> 
<tr>
<td>Använd den nya sidan<strong>Utforskare för redovisningskälla</strong>.</td>
<td>Tillgängliga från Dynamics AX 2012 R3 CU10.</td>
<td>Nya sidan <strong>Utforskare för redovisningskälla</strong> och åtgärder för att navigera dit från listsidan <strong>Råbalans</strong> och från sidan <strong>Verifikationstransaktioner</strong>.</td>
<td>Gör det möjligt att visa den mest detaljerade informationen om källan för en råbalans eller en bokföringspost i redovisningen eller för en ad-hoc-analys.</td>
</tr>
<tr>
<td>Lägga till fler bokföringsskikt.</td>
<td>Det var utvecklare som ansvarade för att lägga till fler bokföringsskikt.</td>
<td>Det finns nu tio bokföringsskikt.</td>
<td>De flesta kunderna lägger till fler bokföringsskikt.</td>
</tr>
<tr>
<td>Använd alternativet Relaterad verifikation.</td>
<td>Inte tillgänglig</td>
<td>Användarna kan använda alternativet Relaterad verifikation för att se verifikationen i motbokningsföretaget vid bokföring av koncerninterna transaktioner. Från de relaterade verifikationerna kan användaren klicka på detaljer och snabbt hoppa till motföretagsverifikationen.</td>
<td>Vid bokföring av koncerninterna transaktioner hade användaren ingen synlighet eller spårning till verifikationen som bokfördes i motbokningsföretaget.</td>
</tr>
<tr>
<td>Stängning av massräkenskapsperiod</td>
<td>Inte tillgänglig</td>
<td>Användaren kan uppdatera åtkomsten till modulen och ändra periodstatus för flera företag samtidigt.</td>
<td>Innan den här funktionen fanns var användarna tvungna att ändra vilket företag de loggade in på, navigera till formuläret Redovisningskalender och manuellt uppdatera åtkomsten till modulen och periodstatusen.</td>
</tr>
<tr>
<td>Låt valutakurserna styras av Oanda.</td>
<td>Det var en utmaning för utvecklarna att konfigurera valutakursleverantören till att importera kurser från Oanda.</td>
<td>Om användarna har en nyckel för Oanda kan de ange den när de konfigurerar valutakursleverantören.</td>
<td>Användarna kan utnyttja OOB-funktionen genom att låta valutakurserna som hämtas från Oanda importeras enligt ett schema.</td>
</tr>
<tr>
<td>Filtrera ekonomiska rapporter (Management Reporter) baserat på dimensioner, attribut, datum och scenarier.</td>
<td> All filtrering av Management Reporter-rapporter hanteras i rapportens design. Om en användare som exempelvis har läsrättigheter vill visa en rapport för något annat datum måste rapportdesignern göra ändringen.</td>
<td>Rapportalternativ har lagts till så att olika filter kan användas när en användare visar en rapport. En ny rapport skapas sedan baserat på dessa filter.</td>
<td>Konsumenter av ekonomiska rapporter kan använda filter för olika dimensioner, datum, attribut och scenarier, utan att be att rapportens design uppdateras.</td>
</tr>
<tr>
<td>Visa ekonomiska rapporter (Management Reporter) i Microsoft Dynamics AX-klienten.</td>
<td>En separat webbklient användes för att visa Management Reporter-rapporter.</td>
<td>Alla ekonomiska rapporter kan nås i Dynamics AX-klienten. Användaren väljer en rapport att visa, så visas rapporten i klienten.</td>
<td>Du kan nu visa ekonomiska rapporter utan att behöva öppna en annan klient eller ett annat program.</td>
</tr>
<tr>
<td>Skriv ut ekonomiska rapporter (Management Reporter) från Microsoft Dynamics AX-klienten.</td>
<td>Vid utskrift av en rapport skulle webbläsarens alternativ för utskrift användas och endast skriva ut vad användaren ser på skärmen.</td>
<td>Användaren kan välja detaljnivå och sidinställningar för en rapport med hjälp av alternativet Skriv ut i den ekonomiska rapporten i Dynamics AX-klienten.</td>
<td>Utskrivna rapporter skrivs ut på det sätt användarna förväntar sig, i stället för att skrivas ut som en webbsida.</td>
</tr><tr>
<td>Analysera ekonomiska data genom att använda innehållet "Övervaka ekonomiska resultat" för Power BI.</td>
<td>Inte tillgänglig</td>
<td>På PowerBI.com, välj <strong>Hämta data</strong> och välj sedan innehållspaketet <strong>Dynamics AX – Ekonomiska resultat</strong>. Ange URL:en för din Dynamics AX-slutpunkt för att visa dina data på instrumentpanelen.</td>
<td>Me bara tre eller fyra klick kan organisationer distribuera en Power BI-instrumentpanel som innehåller viktiga ekonomiska data. Innehållet kan anpassas av organisationen.</td>
</tr>
<tr>
<td>Spåra processer för räkenskapsperiodens stängning.</td>
<td>Inte tillgänglig</td>
<td>Stängningsmallar och stängningsscheman kan skapas med konfigurationen Räkenskapsperiodens stängning. Använd arbetsytan <strong>Räkenskapsperiodens stängning</strong> för att följa förloppet för stängningstidsplaner över flera företag.</td>
<td>Denna arbetsyta eliminerar manuella system för att definiera, tidsplanera och kommunicera stängningsaktiviteter. Därför reduceras antalet dagar för stängningen.</td>
</tr>
<tr>
<td>Övervaka budget jämfört med faktiska siffror och skapa redovisningsprognoser med hjälp av arbetsytan <strong>Redovisningsbudgetar och prognoser</strong> och ytterligare förfrågningsformulär.</td>
<td>Inte tillgänglig</td>
<td> Arbetsytan kan öppnas via Dynamics AX-instrumentpanelen. Det finns länkar till flera nya förfrågningssidor: <strong>Sammanfattning av verkliga värden och budget</strong>, <strong>Budgetkontrollstatistik</strong>, <strong>Budgetregisterposter</strong> och <strong>Budgetplaner</strong>.</td>
<td>Nya förfrågningssidor ger enkel åtkomst till budgetinformation. Arbetsytan kombinerar alla budgetunderhålls- och övervakningsuppgifter på en plats som är enkel för budget- eller redovisningsansvariga att använda.</td>
</tr>
<tr>
<td>Skapa layouter för budgetplaner och prognoser.</td>
<td>Dokumentet <strong>Budgetplan</strong> visas som en lista med rader som har giltighetsdatum och belopp för kombinationer av ekonomiska dimensioner. Användaren måste skapa och använda Excel-mallar för att visa budgetplandata i en pivottabell.</td>
<td>Det finns ett obegränsat antal tillgängliga layouter för budgetplaner och prognoser. Du kan kombinera valda ekonomiska dimensioner, användardefinierade kolumner och andra radattribut (till exempel kommentarer, projekt och tillgångar) i layouten. Användarna kan ändra layouten för budgetplandokumentet när som helst och redigera data genom att använda vald layout. Konfigurationen av budgetplaneringen förenklas genom elimineringen av scenariebegränsningar och användningen av layouter för att definiera vilka data som kan visas och redigeras i varje fas av budgetplandokumentet.</td>
<td>Det ger flexibilitet att skapa och redigera budgetplaner genom att använda både Excel- och Dynamics AX-klienten. Mallar för Excel-arbetsböcker kan skapas med hjälp av layoutinställningarna för budgetplanen.</td>
</tr>
<tr>
<td>Skriv ut rapporten <strong>Leverantörsfakturatransaktioner</strong> med hjälp av informationen från rapporten <strong>Detaljerad förfallodagslista</strong>, som inkluderar antalet dagar efter förfallodatumet.</td>
<td>Du måste skriva ut två olika rapporter: <strong>Detaljerad förfallodagslista</strong> och <strong>Leverantörsfakturatransaktioner</strong>.</td>
<td>Informationen i de två rapporterna har konsoliderats i rapporten <strong>Leverantörsfakturatransaktioner</strong>. Rapporten <strong>Detaljerad förfallodagslista</strong> var föråldrad.</td>
<td>Den eliminerar behovet att skriva ut två separata men relaterade rapporter.</td>
</tr>
<tr>
<td>Skapa lagstadgade rapporter direkt i PDF-format.</td>
<td>Du måste först skapa en lagstadgad rapport i ett format och sedan exportera den till PDF-format.</td>
<td>PDF-formatet är standardformatet för lagstadgade rapporter.</td>
<td>Du får en enhetlig visningsupplevelse på både datorskärmen och en utskriven papperskopia.</td>
</tr>
<tr>
<td>Kör momskvittningsprocessen som en batchprocess.</td>
<td>Inte tillgänglig</td>
<td>På sidan <strong>Momskvittningsperiod</strong> kan du ange att kvittningen ska köras i batchläge.</td>
<td>För perioder som har många momstransaktioner kan kvittningsprocessen vara tidskrävande, och det kanske är bättre att köra processen i bakgrunden som en batchprocess.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Stiftelse

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Få åtkomst till klienten när som helst, var som helst.</td>
<td>AX 2012-skrivbordsklienten tillhandahåller en fullständig uppsättning formulär, men kan bara köras på datorer som kör Microsoft Windows och kräver installation. Terminal Server används ofta med skrivbords klienten för att ge åtkomst över en WAN-nätverk (Wide Area Network). Enterprise Portal-webbklienten tillhandahåller en reducerad uppsättning formulär.</td>
<td>De två AX 2012-klienterna har ersatts av en enda standardbaserad webbklient som tillhandahåller en fullständig uppsättning funktioner för skrivbordsklienten tillsammans med möjligheterna i Enterprise Portal-klienten.</td>
<td>Den förhindrar att utvecklingsarbete delas upp på två UI-plattformar. Genom att använda standardwebbgränssnitt eliminerar den behovet av Terminal Server.</td>
</tr>
<tr>
<td>Bli produktiv genom att använda nya Uppgiftsregistrering.</td>
<td>Uppgiftsregistrering i AX 2012 kräver direkt åtkomst till en AOS-dator (Application Object Server) och förhöjd behörighet och tillhandahåller inga redigeringsfunktioner.</td>
<td>Nya Uppgiftsregistrering kan användas direkt från webbklienten. Åtkomst till Uppgiftsregistrering kräver inte administratörsbehörighet. Registrerade steg kan visas medan du registrerar, nya redigeringsalternativ har introducerats och Uppgiftsregistrering stöder fler scenarier förutom befintliga BPM-scenarier (Business Process Modeler).</td>
<td>Nya Uppgiftsregistrering ger en smidig upplevelse och möjliggör nya funktioner i Dynamics AX. Några av dessa funktioner är nu tillgängliga och fler kommer i framtiden.</td>
</tr>
<tr>
<td>Hjälpa användarna att få bättre förståelse för sina kommande arbeten med arbetsytor.</td>
<td>Ett rollcenter ger en översikt över informationen som gäller användarens jobbfunktion i företaget eller organisationen.</td>
<td>Arbetsytor är ett nytt koncept i Dynamics AX som är avsedda att ersätta rollcenter som det primära sättet att navigera till aktiviteter och specifika sidor. De ger en översikt (en sida) av en affärsaktivitet och hjälper användarna att förstå aktuell status, kommande arbetsbelastning och prestandan för den processen eller användaren. Arbetsytor är mer grundläggande än AX 2012-rollcenter och en användare kan ha tillgång till flera arbetsytor.</td>
<td>Arbetsytor är avsedda att öka användarproduktiviteten. Utvecklare måste skapa en arbetsyta för varje betydande "aktivitet" som stöds i produkten. Ett äldre rollcenter från AX 2012 kommer normalt att ersättas av flera arbetsytor i den aktuella versionen av Dynamics AX.</td>
</tr>
<tr>
<td>Anpassa formulär efter webbläsarens visningsområde eller enhetens storlek.</td>
<td>I AX 2012 visades formulärinnehållet i kolumner och formulärets totala höjd och bredd fastställdes till stor del av kontrollerna i formuläret.</td>
<td>I och med bytet till webben i senaste Dynamics AX anpassas formulärets storlek nu efter webbläsarens visningsområde eller enhet. Kontroller och layoutparametrar har ändrats eller lagts till för att bättre anpassas efter ändringar av visningsområdets storlek.</td>
<td>Formulärets innehåll måste vara mer anpassningsbart för att den tillgängliga höjden och bredden hos webbläsare och enheter ska kunna utnyttjas optimalt. Anpassningsbarhet kan kräva att modelleringen av formulär ändras.</td>
</tr>
<tr>
<td>Använd mönster för att göra utvecklingen av formulär mer effektiv.</td>
<td>Det fanns formulärmallar som utgångspunkt för utveckling av formulär i AX 2012 som var baserade på ett formulärformat. Det valfria tillägget Form Style Checker gav information om på vilket sätt ett formulär avvek från motsvarande mall.</td>
<td>I den aktuella versionen av Dynamics AX har formulärmönster införts. Formulärmönster är en kombination av formulärmallar och Form Style Checker som är integrerade i utvecklingsmiljön. Mönster har definierats på formulärnivå (till exempel AX 2012) med ytterligare delmönster som nu är tillgängliga på grupp- och sidnivå.</td>
<td>Formulär som följer mönster har många fördelar. De ger ett mer enhetligt användargränssnitt, enklare utvecklingsmiljö, enklare uppgraderingsväg för formuläret och ökad tillförlitlighet när det gäller anpassningen av formulärets layout.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Hjälp

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Komma åt guidad procedurbaserad hjälp (uppgiftsguider) och begreppsbaserade avsnitt genom att klicka på <strong>Hjälp</strong>.</td>
<td>AX 2012-hjälpsystemet pekar på HTML-avsnitt som lagras på en lokal webbserver. Kunder och partner kan skapa sin egen hjälp.</td>
<td>Hjälpsystemet i den aktuella versionen av Dynamics AX visar uppgiftsguider som lagras i BPM för Microsoft Dynamics Lifecycle Services (LCS). Hjälpsystemet visar också avsnitt från webbsidan för Microsoft-dokument. Mer information finns i <a href="help-overview.md" data-raw-source="[Help system](help-overview.md)">hjälpsystem</a> och <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides (February 2016)](new-task-guides-available-february-2016.md)">nya uppgiftsguider (februari 2016)</a>.</td>
<td>Uppgiftsguider tillhandahåller en guidad, interaktiv upplevelse som leder dig genom stegen för en uppgifts- eller affärsprocess. Du kan hämta och anpassa uppgiftsguider som Microsoft tillhandahåller. Det här avsnittet låter dig skapa, distribuera och uppdatera produktinformation på ett snabbare och mer flexibelt sätt. Därför garanterar den att du har tillgång till den senaste tekniska informationen.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Administration av humankapital

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dela kunskaper och utfärda intyg till kursdeltagare vid avslutad kurs.</td>
<td>Det här är en manuell process.</td>
<td>När en kurs är avslutad blir ett nytt alternativ tillgängligt för att uppdatera en deltagares poster med de nya färdigheterna och intyg.</td>
<td>Det är ett nytt och effektivt sätt att uppdatera personalposter.</td>
</tr>
<tr>
<td>Kontrollera snabbt anställning.</td>
<td>Det här är en manuell process.</td>
<td>Din HR-avdelning kan snabbt verifiera anställning genom att använda en arbetsyta eller sidan för anställda.</td>
<td>HR-avdelningen behöver inte längre öppna flera sidor för att kontrollera startdatum, chef, månader i tjänsten och kompensationsuppgifter.</td>
</tr>
<tr>
<td>Låt medarbetare visa, uppdatera och ta bort information i systemet.</td>
<td>Tillgänglig, men med begränsade visnings- och uppdateringsmöjligheter.</td>
<td>Den här funktionen är aktiverad och låter medarbetare och leverantörer visa en mängd personliga uppgifter. Om du vill kan du också använda ett arbetsflöde när informationen skapas, uppdateras eller tas bort.</td>
<td>Den låter medarbetare ta kontrollen över sin information, oavsett om det gäller att uppdatera adress- eller kontaktinformation, söka ett jobb, svara på en enkät eller uppdatera deras bild. När arbetsflödet är aktiverat kan informationen granskas av en godkännare eller godkännas automatiskt, baserat på dina affärsprocesser.</td>
</tr>
<tr>
<td>Låt chefer visa eller redigera medarbetarinformation.</td>
<td>Tillgänglig, men med begränsade visnings- och uppdateringsmöjligheter.</td>
<td>Beroende på konfigurationsinställningar och säkerhet kan chefer visa eller redigera medarbetarinformation.</td>
<td>Det innebär att chefer kan komma åt viktig information om medarbetare så att de kan fatta bättre beslut om resurstillsättning, prestanda och medarbetarutveckling.</td>
</tr>
<tr>
<td>Utnyttja funktionen Självbetjäning för chefer.</td>
<td>Inte tillgänglig</td>
<td>Chefer kan nu skicka förfrågningar om nyanställningar (medarbetare och leverantörer), överföringar och uppsägningar (avslutad anställning). Chefer kan även begära nya positioner, utöka varaktigheten för positioner eller begära ändringar av positioner.</td>
<td>Dessa scenarier har tidigare endast kunnat hanteras av personalavdelningen. Om dessa scenarier aktiveras får cheferna inom organisationen kraftfulla verktyg. Valfria arbetsflöden kan aktiveras för att ge rätt nivå för granskning och godkännanden.</td>
</tr>
<tr>
<td>Få åtkomst till resultaten för kompensationsbearbetning.</td>
<td>Resultatet är bara tillgängligt vid tidpunkten för bearbetning.</td>
<td>Nu kan du komma åt resultaten från kompensationsbearbetningen när som helst när processen har körts.</td>
<td>Den ger en utmärkt granskning av processen och resultatet av processen. Den ger också en omfattande vy av data innan medarbetarposterna uppdateras.</td>
</tr>
<tr>
<td>Få åtkomst till resultaten för förmånsbearbetning.</td>
<td>Resultatet är bara tillgängligt vid tidpunkten för bearbetning.</td>
<td>Nu kan du komma åt resultaten från förmånsbearbetningen när som helst när processen har körts.</td>
<td>Du får en omfattande vy av data som uppdateras efter förmånsregistrering och kostnadsändringar.</td>
</tr>
<tr>
<td>Visa tidsändringar av typen ”Gäller från”.</td>
<td>Inte tillgänglig</td>
<td>Det här jämförelseverktyget är tillgängligt för medarbetare, befattningar och jobb. Det ger en omfattande vy av ändringar från en version av en post till en annan.</td>
<td>Det sparar tid när du visar ändringar som har gjorts över tid för medarbetare, befattningar och jobbposter. Det låter dig snabbt jämföra två versioner av en post eller alla poster över tid.</td>
</tr>
<tr>
<td>Visa anställda efter företag.</td>
<td>Det här är en manuell process som utförs genom filtrering.</td>
<td>Medarbetar- och leverantörlistor filtreras automatiskt av företaget som du är inloggad på.</td>
<td>Du får en filtrerad vy över medarbetare som är anställda på det inloggade företaget. För en ofiltrerad vy över alla medarbetare och leverantörer är arbetarlistan fortfarande tillgänglig. I den aktuella versionen av Dynamics AX ändrar inte systemet företag baseras på den medarbetare som valts i listan.</td>
</tr>
<tr>
<td>Uppdatera kursdeltagarlistan.</td>
<td>Inte tillgänglig</td>
<td>Kursdeltagare kan tas bort från deltagarlistan.</td>
<td>Det är ett enkelt sätt att uppdatera kursdeltagare som registrerat sig av misstag.</td>
</tr>
<tr>
<td>Hantera kompensationshändelser i en grupp.</td>
<td>Inte tillgänglig</td>
<td>Den här funktionen effektiviserar bearbetningen av kompensationsändringar för medarbetare.</td>
<td>Den ger en enkel, effektiv process för att uppdatera medarbetarposter via kompensationsarbetsytan och relaterade sidor.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Lagerhantering

Inga nya funktioner har lagts till.

## <a name="localization"></a>Lokalisering

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Konfigurera och skapa elektroniska handlingar för att uppfylla lagkraven i olika länder/regioner.</td>
<td>Elektroniska dokument är hårdkodade i X++ eller som XSLT:er (Extensible Stylesheet Language Transformation). Vissa formatjusteringar kräver insatser av utvecklare. Åtkomst till data och formatering är inte isolerad. En justerad formatdistribution kräver en ny Microsoft Dynamics AX-snabbkorrigering som åsidosätter det befintliga formatet. Anpassade ändringar av respektive format måste porteras manuellt till källkoden i ett nytt Microsoft Dynamics AX-snabbkorrigeringspaket.</td>
<td>Elektronisk rapportering (ER) är ett nytt verktyg för att konfigurera och skapa elektroniska dokument som är avsett för affärsanvändare i stället för utvecklare. Med hjälp av ER kan du ställa in datamodeller som är domänspecifika och oberoende av Microsoft Dynamics AX-databasen som datakällor för dokumentformat. En affärsanvändare kan konfigurera format som baseras på dessa domänspecifika datamodeller (exempelvis för betalningar, Intrastat-rapporter eller momsrapporter). Användaren konfigurerar formaten genom att använda enkla visuella verktyg som liknar Excel. ER har stöd för generering av elektroniska dokument i text-, XML- och Excel-format. Dessa dokument kan skapas samtidigt och packas i ZIP-filer. Datamodeller och format stöder versionshantering. Formatversioner kan ha giltighetsperioder. Varje version av datamodellen eller formatet lagras i en separat konfiguration och distribueras till partner och kunder via LCS. Partner och kunder kan anpassa Microsofts datamodeller och format, eller skapa sina egna. ER sparar partner- och kundkonfigurationsändringar som deltaförändringar till Microsoft-konfigurationer, vilket förenklar uppgraderingar till nya versioner av Microsofts konfigurationer. Genom att använda LCS kan partners också dela sina konfigurationer av datamodellen och format med andra partners och kunder, som i sin tur kan anpassa och dela dem vidare. Deltaanpassning och enkel uppgradering stöds genom hela anpassningskedjan.</td>
<td>ER förenklar skapandet, underhållet och uppgraderingen av elektroniska dokumentformat för att uppfylla juridiska krav i olika länder/regioner. ER gör processen för att skapa eller ändra elektroniska dokumentformat snabbare och enklare. Dessa ändringar kan göras av affärsanvändare i stället för utvecklare. ER gör det snabbare och enklare för partners och kunder att uppgradera sina formatanpassningar till nya versioner av format som släpps av Microsoft eller andra partner. ER tillhandahåller en gemensam metod (via LCS) för Microsoft och partners att distribuera konfigurationer av elektroniska dokument till andra partner och kunder. ER gör det också enklare för partners och kunder att anpassa, uppgradera och distribuera format för elektroniska dokument för sina specifika affärsbehov.</td>
</tr>
<tr>
<td>(MEX) Skapa lagstadgade rapporter för mexikansk mervärdesskatt.</td>
<td>Du måste skapa rapporter över <strong>försäljnings- och inköpsmoms</strong> genom att använda funktionen för orealiserad skatt, så att användarna kan identifiera transaktioner som tillhör de realiserade och orealiserade avsnitten baserat på status.</td>
<td>Rapporterna över <strong>försäljnings- och inköpsmoms</strong> ändrades och tar nu endast hänsyn till funktionen för villkorsstyrd skatt genom att använda specifika kvittningsperioder för definitionen av orealiserade och realiserade momskoder.</td>
<td>Ändringar i konfigurationen av momskoder krävs innan användarna kan skapa dessa rapporter korrekt. En funktion för villkorsstyrd moms krävs, och användaren måste konfigurera separata kvittningsperioder, orealiserade och realiserade, för att identifiera transaktionerna i de relaterade avsnittområdena.</td>
</tr>
<tr>
<td>(JPN) Hantera det japanska dokumentet för deklaration av accelererad avskrivning av anläggningstillgångar.</td>
<td>Inte tillgänglig</td>
<td>Viktig deklarationsinformation lagras centralt i ett enda dokument för bättre underhåll.</td>
<td>Dokumentefterlevnad och enkel hantering minskar problem vid revisioner och andra granskningar.</td>
</tr>
<tr>
<td>(JPN) Kontrollera JBA-tecken på bankkontot.</td>
<td>Inte tillgänglig</td>
<td>Du kan kontrollera att kana-namnfält bara innehåller de tecken som tillåts för JBA-bankformatet.</td>
<td>Det gör det enklare att minska avbrott för användarna under genereringen av betalningsfiler på grund av ogiltiga tecken.</td>
</tr>
<tr>
<td>(JPN) Kompensera för den japanska penningskillnaden för anläggningstillgångar vid räkenskapsårets slut.</td>
<td>Inte tillgänglig</td>
<td>På sidan <strong>Parametrar för anläggningstillgångar</strong> kan du välja att kompensera i slutet av räkenskapsperioden eller räkenskapsåret.</td>
<td>Det ger bättre flexibilitet att matcha lokala rutiner.</td>
</tr>
<tr>
<td>(JPN) Skapa de japanska bifogade tabellerna (serie 16) för momsdeklaration för företag till ett summerat belopp efter huvudtyp för anläggningstillgång.</td>
<td>Inte tillgänglig</td>
<td>I värdemodellerna för en anläggningstillgång kan du välja att summera efter huvudtyp. Som standard används den här funktionen för nyligen skapade anläggningstillgångar.</td>
<td>För stora företag som har tusentals anläggningstillgångar minskar de summerade rapporterna kraftigt storleken på rapporten som skapas.</td>
</tr>
<tr>
<td>(JPN) Börja allokera en reserv för speciell avskrivning från nästa räkenskapsår för japanska anläggningstillgångar.</td>
<td>Inte tillgänglig</td>
<td>I värdemodellerna för en anläggningstillgång som har en lämplig profil för extraordinär avskrivning kan du välja att börja allokera från nästa räkenskapsperiod eller nästa räkenskapsår.</td>
<td>Det ger bättre flexibilitet att matcha lokala rutiner.</td>
</tr>
<tr>
<td>(JPN) Skapa en rapport om japansk konsumtionsskatt som innehåller de reviderade skattesatserna.</td>
<td>Förbrukningsmomsrapporten är tillgänglig för en momssats på 5 procent.</td>
<td>Rapporten innehåller ett avsnitt för den granskade momssatsen (exempelvis 8 procent).</td>
<td>Layouten tillkännagavs nyligen av regeringen.</td>
</tr>
<tr>
<td>(EU) Konfigurera inställningar för avrundning i listan över försäljning inom EU.</td>
<td>Avrundning i inställningarna för EU-försäljningslistan för olika länder är hårdkodad i X++ eller i Extensible Stylesheet Language Transformations (XSLT:er).</td>
<td>Inställningar för avrundning läggs till i Utländska handelsparametrar. Du kan konfigurera avrundning, avrundningsmetod, utdataprecision och beteendet för belopp som är mindre än avrundningsprecisionen.</td>
<td>Detta förenar och förenklar konfigurationen för rapportering av EU-försäljningslistan. Justering av avrundningsinställningar kräver inte längre något utvecklingsarbete.</td>
</tr>
<tr>
<td>(EU) Konfigurera tillämpningsreglerna för återfört tillägg.</td>
<td>Tillämpningsreglerna för återfört tillägg är hårdkodat för det inhemska återföringsscenariot. Tillämplighetströskeln kan konfigureras per artikelgrupp. Funktionen är enbart tillgänglig i Storbritannien.</td>
<td>Du kan konfigurera tillämpningsreglerna för återfört tillägg per dokumenttyp (inköps-/försäljningsorder, leverantörsfaktura, fritextfaktura osv.) och grupp för återfört tilläggen som kombinerar artiklar, artikelgrupper och inköps-/försäljningskategorier. Tillämpningsreglerna är giltighetsdatumberoende. Du kan också markera enskilda momskoder i momsgrupper som gäller för återfört tillägg. Försäljningsfakturarapporten är justerad för att visa information om den tillämpade återförda tillägg. Funktionen är tillgänglig i alla europeiska länder/regioner.</td>
<td>Den här ändringen förenar konfigurationen av tillämpningsreglerna för återfört tillägg och stöder antagandet av inhemska regler för återfört tillägg i europeiska länder/regioner.</td>
</tr>
<tr>
<td>(DE) Skapa den tyska granskningsfilen – GDPdUGoBD</td>
<td>Användarna kan ställa in definitionen av tabeller som innehåller ekonomiska data som ska exporteras i ett format som accepteras av tyska revisorer och myndigheter.</td>
<td>Den här funktionen har implementerats som en elektronisk rapporteringskonfiguration. Funktionen är enbart tillgänglig i Tyskland och Österrike.</td>
<td>Den här ändringen ger användaren mycket fler möjligheter vid dataformatering och transformationer och ger även alla fördelar med livscykelhanteringskonfiguration för elektronisk rapportering såsom enkel överföring av konfiguration, versionshantering osv.</td>
</tr>
<tr>
<td>(FR) Rapport över saldolista med gruppsaldokonton.</td>
<td>Saldolista med gruppsaldokonton implementeras som en SSRS-rapport (LedgerAccountSum_FR).</td>
<td>Rapporten över saldolistan med gruppsaldokonton implementeras som en Management Reporter-rapport som är tillgänglig i LCS Asset-katalogens rapportmapp.</td>
<td>På så sätt kan användarna få alla fördelar och frihet vid anpassningar av ekonomiska rapporter i Management Reporter.</td>
</tr>
<tr>
<td>(EU) Betalningsavi, Notering om deltagande och Kontrollrapporter för betalningar.</td>
<td>Dessa rapporter har implementerats och SSRS-rapporter.</td>
<td>Dessa rapporter har implementerats som Open XML-mallar som ska användas i Microsoft Excel.</td>
<td>Konfigurationer för elektronisk betalning innehåller inställningar för betalningsfilformat och mallar. På så sätt kan användarna få alla fördelar och frihet vid anpassningar av rapporter från elektronisk rapportering.</td>
</tr>
<tr>
<td>(EU) Konfigurera inställningar för avrundning för Intrastat.</td>
<td>Inställningar för avrundning i Intrastat-rapportering för olika länder/regioner är hårdkodad i X++ eller i Extensible Stylesheet Language Transformations (XSLT:er).</td>
<td>Inställningar för avrundning har lagts till i Utländska handelsparametrar. Du kan konfigurera avrundning, avrundningsmetod, utdataprecision och beteendet för belopp som är mindre än avrundningsprecisionen.</td>
<td>Detta förenar och förenklar konfigurationen av Intrastat-rapportering. Justering av avrundningsinställningar kräver inte längre något utvecklingsarbete.</td>
</tr>
<tr>
<td>(EU) Ställa in varukoder för Intrastat i kategorihierarkier.</td>
u<td>Varukoder för Intrastat är en separat lista. Dessa varukoder kan vara standard i HQent (butik) och försäljningskategorier medan kategorihierarkin är av typen Varukod.</td>
<td>Separat lista över varukoder för Intrastat slås samman med produkthierarkin av typen Varukod.</td>
<td>Detta förenar tillvägagångssättet för att tilldela varukoder till frisläppta produkter och kategorier i försäljnings- och inköpsdokument.</td>
</tr>
<tr>
<td>(EU) Rapportera kvantitet i ytterligare enheter för Intrastat med hjälp av inställningen för enhetskonvertering.</td>
<td>Intrastat-varukoden har ett textfält för att identifiera ytterligare enheter och kortet <strong>Produkt</strong> har ett fält för att identifiera antalet ytterligare enheter i kg.</td>
<td>Ytterligare enheter för Intrastat-varukoden väljs i listan Enheter. Kvantiteten för ytterligare enheter beräknas genom inställningar för enhetskonverteringar.</td>
<td>Detta förenar tillvägagångssätt för omräkning från enheter för transaktionen till ytterligare enheter.</td>
</tr>
<tr>
<td>(EU) Tilldela standardtransportmetod till leveransmetod.</td>
<td>Inte tillgänglig</td>
<td>Ett fält för standardtransportmetod har lagts till i Leveransmetod.</td>
<td>Detta förenklar beredning av Intrastat-rapportering.</td>
</tr>
<tr>
<td>(EU) Markera frisläppt produkt som inte ska rapporteras i Intrastat.</td>
<td>Inte tillgänglig</td>
<td>Ett alternativ för att utesluta artikeln från Intrastat-rapportering har lagts till i frisläppt produkt.</td>
<td>Detta förenklar beredning av Intrastat-rapportering.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Tillverkning

| Vad kan du göra? | Dynamics AX 2012 |
|------------------|------------------|
| Utföra en kontroll av materialtillgänglighet för tillverkningsorder på en separat sida som öppnas från arbetsytan **Produktionsgolvsledning**. | Inte tillgänglig |
| Starta och rapportera utvecklingen för produktionsjobb genom att använda den nya sidan **Jobbkortenhet**. | Formuläret **Jobbregistrering** är främst avsett för stora terminalskärmar, och användargränssnittet nås normalt via musklickningar. |

## <a name="master-planning-and-forecasting"></a>Huvudplanering och prognosticering

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Varnar användaren om en försäljningsorder eller produktionsorder inte är klar för leverans på det tidsplanerade datumet. | Varningarna som skapas av huvudplaneringen kallas *leveransplansmeddelanden*. *Leveransplaner* är ett avtal mellan två parter om att köpa eller sälja en tillgång till ett överenskommet pris (*leveransplanspriset*) även om leverans och betalning görs i framtiden (*leveransdatumet*). | *Leveransplansmeddelanden* och *leveransplansdatum* har bytt namn till *beräknade förseningar* och *försenade datum*. | Terminologin som används i AX 2012 var inkorrekt och ledde till felaktiga översättningar. |
| Få snabb inblick i statusen för en huvudplaneringskörning, brådskande planerade order och planerade order som orsakar förseningar. | Informationen är tillgänglig, men är utspridd över flera formulär. | Arbetsytan **Huvudplanering** ger snabb information om när den senaste huvudplaneringskörningen slutfördes, huruvida eventuella fel uppstod, vilka brådskande planerade order som finns och vilka planerade order som orsakar förseningar. | Du har nytta av översikten som arbetsytan innehåller. Relevant information sammanställs för att styra huvudplaneringen och förbättra produktiviteten. |
| Använd Excel för att uppdatera efterfrågeprognoser. | Inte tillgänglig | Du kan dra fördel av sömlös integration med Excel när du anger efterfrågeprognoser, gör uppdateringar och tar bort efterfrågeprognoser. | Det hjälper dig att öka effektivitet och produktivitet. |
| Uppskatta framtida efterfrågan och skapa efterfrågeprognoser baserat på historiska transaktionsdata. | I Microsoft Dynamics AX 2012 R3 används prognosmodeller i Microsoft SQL Server Analysis Service för att skapa prognostiserade förutsägelser om efterfrågeprognoser. | Uppskatta framtida efterfrågan genom att använda kraften och skalbarheten i molntjänsten Microsoft Azure Machine Learning. Det är enkelt att använda och utöka prognosmodellerna i Machine Learning för att uppfylla kundkrav. Tjänsten väljer den modell som matchar bäst och tillhandahåller KPI:er som kan användas för att beräkna prognosprecision. | Skapa mer exakta prognoser genom att använda Machine Learning-teknikerna. |
| Optimera orderdatumet och kvantiteten baserat på en visuell översikt över relaterade åtgärder från huvudplaneringskörningen. | Översikten över åtgärdsdiagrammet är tillgänglig men visar alla relaterade åtgärder. När åtgärder tillämpas försvinner de genast från vyn. | Åtgärdsdiagrammet ger en bättre översikt. Här finns alternativ som låter dig visa bara tillämpade åtgärder och direkt relaterade åtgärder. När åtgärder används visas de som nedtonade, men visas fortfarande. Därför finns översikten kvar. Mer information har lagts till för åtgärderna i diagrammet som visar data på en enda sida. | Du kan dra fördel av produktivitetsförbättring eftersom du bara fokuserar på de relevanta åtgärderna. |

## <a name="procurement-and-sourcing"></a>Anskaffning och källa

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Använd arbetsytan **Inköpsorderförberedelse** när du vill få en snabb inblick i statusen för inköpsorder som förbereds. | Stöds ej | Arbetsytan **Inköpsorderförberedelse** ger en översikt över order från den tidpunkt då de skapas som utkast och spåras genom godkännandetillstånd för arbetsflöde och fram till bekräftelse. | Din inköpsavdelning behöver inte längre leta efter information från flera sidor utan kan använda översikten som arbetsytan tillhandahåller. |
| Använd arbetsytan **Inleverans av inköpsorder och uppföljning** när du vill få snabb inblick i inköpsorder som väntar på inleverans, för enklare uppföljning. | Stöds ej | Arbetsytan **Inleverans av inköpsorder och uppföljning** ger en översikt över bekräftade inköpsorder som har väntande inleveranser eller försändelser. Arbetsytan inkluderar listor med förfallna inleveranser och väntande inleveranser och möjliggör en proaktiv granskning och uppföljning av leverantören. Arbetsytan visar också inköpsorder för vilka införselregistrering har skett på lagerstället, för att garantera att inleveransen bokförs. Inköpsorderreturer som ännu inte har skickats är också tillgängliga för granskning. | Inköpsavdelningen kan dra fördel av översikten som arbetsytan tillhandahåller. Relevant information sammanställs för att vägleda uppföljningen och förbättra produktiviteten. |
| Skicka inköpsorder för bekräftelse till en leverantörsportal som Dynamics AX-klienten är värd för. Låt leverantören bekräftar eller avvisa. | Stöds ej | Leverantörsportalens gränssnitt låter leverantörer ta emot inköpsorder som ska bekräftas eller avvisas. Den låter också leverantören ha en översikt över alla bekräftade inköpsorder för ett konto. Inköpsagenten kan skicka en inköpsorder som behöver bekräftas av leverantören. Leverantören måste vara en registrerad Microsoft Azure Active Directory (Azure AD)-användare i AX, en kontaktperson för leverantören och ha en dedikerad säkerhetsroll. | Inköpsavdelningen får mindre pappersarbete och behöver inte manuellt hålla reda på svar relaterade till inköpsorder eftersom allt flödar direkt in i systemet. Med en enda källa minskar risken för missförstånd mellan kund och leverantör. |

## <a name="projects"></a>Projekt

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Boka arbetare som resurser i projekt. | På samma sätt som resurser bokas arbetare direkt i projekt utöver resurserna. | Arbetsställeregistret där resurser för tillverkning och produktion lagras kan nu användas för att boka arbetare som resurser för ett projekt. | När du bokar projekt behöver du bara boka resurser. |

## <a name="retail-sales-marketing-and-customer-service"></a>Butiksförsäljning, marknadsföring och kundtjänst

### <a name="retail-hq"></a>Administration för detaljhandel

Microsoft Azure-baserad administration för detaljhandeln erbjuder centraliserad hantering av och fullständig insyn i alla aspekter av handelsaktiviteterna via en webbklient.

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Utför marknadsföringsaktiviteter.</td>
<td>Användarna måste få åtkomst till flera formulär för att hantera dessa data:
<ul>
<li>Kategorihantering</li>
<li>Produkthantering</li>
<li>Kanalproduktattribut</li>
<li>Sortiment</li>
<li>Hantering av produktkatalog</li>
<li>Paket</li>
<li>Priser &amp; rabatter</li>
</ul></td>
<td>Arbetsytan <strong>Kategori- och produkthantering</strong> aktiverar följande funktioner:
<ul>
<li>Sortimenthantering.</li>
<li>Spårning av sortimentets livscykel.</li>
<li>Hantering av frisläppta produkter.</li>
</ul>
Arbetsytan <strong>Priser och rabatthantering</strong> har följande funktioner:
<ul>
<li>Pris- och rabatthantering för en given kanal och kategori.</li>
<li>Hantering av kategoriprisregel.</li>
<li>Pris - och rabattprioriteter, som gör att du kan tilldela prioritet till prisgrupper och rabatter, så att du kan kontrollera i vilken ordning de tillämpas.</li>
<li>Hantering av anknytning och katalograbatt.</li>
</ul>
Arbetsytan <strong>Kataloghantering</strong> aktiverar följande funktioner:
<ul>
<li>Sammanfattning av aktiva kataloger</li>
<li>Spårning av katalogens livscykel på en enstaka plats</li>
</ul></td>
<td><ul>
<li>Arbetsytor förbättrar effektiviteten och produktiviteten för arbetare genom att låta dem hantera uppgifter och åtgärder relaterade till marknadsföringsrollen på ett enda ställe.</li>
<li>Funktionen för pris- och rabattprioritet ger kunder mer kontroll över hur priser och rabatter används. Funktionen möjliggör också nya situationer där högre butikspriser vinner över standardpriser.</li>
</ul></td>
</tr>
<tr>
<td>Hantera användning och aktiviteter i detaljhandelskanalen.</td>
<td>Användaren måste få åtkomst till flera formulär för att utföra följande uppgifter:
<ul>
<li>Skapa och konfigurera nya kanaler och relaterade enheter.</li>
<li>Hantera dagliga butiksaktiviteter.</li>
<li>Bearbeta butikstransaktioner i Microsoft Dynamics AX, generera butiksutdrag och uppdatera Microsoft Dynamics AX lager och ekonomi.</li>
</ul>
</td>
<td>Arbetsytan <strong>Kanalgruppering</strong> låter dig utföra följande uppgifter:
<ul>
<li>Skapa nya kanaler och relaterade enheter.</li>
<li>Följa förloppet för butikkonfigurationer.</li>
<li>Ta de nödvändiga stegen för att utföra en uppgift eller ange information om att genomföra uppgiften.</li>
<li>Följa status för enheter och direkt validera och hämta programinstallationen för Retail Modern POS (MPOS) i butiker.</li>
<li>Få åtkomst till alla relaterade sidor.</li>
</ul>På arbetsytan
<strong>Butikshantering</strong> kan du utföra följande uppgifter:
<ul>
<li>Hantera arbetare och arbetarnas POS-behörighet (Point of Sale).</li>
<li>Följa skiftstatus för en viss butik eller grupp av butiker.</li>
<li>Direkt validera och hämta MPOS-programinstallationen i butiker.</li>
<li>Skriva ut rapporter och komma åt relaterade sidor.</li>
</ul>På arbetsytan 
<strong>Butiksekonomi</strong> kan du utföra följande uppgifter:
<ul>
<li>Skapa, beräkna och bokföra utdrag för en viss kanal.</li>
<li>Tidsplanera batchjobb för att uppdatera lagret och beräkna och bokföra utdrag.</li>
<li>Spåra öppna utdrag.</li>
<li>Följa skiftstatus för en viss butik eller grupp av butiker.</li>
<li>Skriva ut rapporter och snabbt komma åt alla relaterade sidor.</li>
</ul></td>
<td>Arbetsytor förbättrar effektiviteten och produktiviteten för arbetare genom att låta dem hantera de flesta uppgifter och åtgärder relaterade till kanalanvändning, butikshantering och ekonomi på ett enda ställe.</td>
</tr>
<tr>
<td>Hantera IT-relaterade butiksaktiviteter.</td>
<td>Användaren måste få åtkomst till flera formulär.</td>
<td>Arbetsytan <strong>Retail IT</strong> möjliggör förfrågningar om Commerce Data Exchange på samma plats för en viss kanal, så att du kan utföra följande uppgifter:
<ul>
<li>Hämta sessioner.</li>
<li>Ladda upp sessioner.</li>
<li>Spåra misslyckade sessioner och initiera om eller köra dem igen.</li>
<li>Visa eller köra kommande jobb.</li>
</ul></td>
<td>Arbetsytor förbättrar effektiviteten och produktiviteten för arbetare genom att låta dem hantera uppgifter och åtgärder som rör IT-relaterade butiksaktiviteter på ett enda ställe.</td>
</tr>
<tr>
<td>Importera/exportera data med hjälp av datatabeller.</td>
<td>AX 2012 stöder färdig Microsoft Dynamics Retail Management System (RMS) genom ramverket för dataimport/-export.</td>
<td>Butiksdatatabellerna har expanderats för att ge stöd för alla huvud- och referensdata som är relaterade till detaljhandeln. Det finns även förbättrat stöd för datatabeller i hela Dynamics AX-lösningen.</td>
<td>Datatabeller låter kunderna utföra metadatabaserad import och export av data. OData-enheter låter också kunder integrera Dynamics AX med tredjepartsprogram.</td>
</tr>
<tr>
<td>Utför intelligent analys genom att använda BI-rapporter från Dynamics Microsoft AX- och POS-klienten.</td>
<td>Mer än 25 back office-rapporter och 5 rapporter på kanalsidan är tillgängliga.</td>
<td>Mer än 30 back office-rapporter och 10 rapporter på kanalsidan är tillgängliga.</td>
<td>Rapporterna ger kunder mer BI för att förutsäga trender, få insikter och hela tiden arbeta med topprestanda.</td>
</tr>
<tr>
<td>Analysera försäljningsdata från butikskanaler med hjälp av innehållet ”Övervaka Retail Channel performance” för Power BI.</td>
<td>Inte tillgänglig</td>
<td>På PowerBI.com, välj <strong>Hämta data</strong> och väljer sedan innehållspaketet <strong>Dynamics AX – Retail Channel performance</strong>. Ange URL:en för din Dynamics AX-slutpunkt för att visa dina data på instrumentpanelen.</td>
<td>Me bara tre eller fyra klick kan organisationer distribuera en Power BI-instrumentpanel som innehåller viktiga ekonomiska data. Innehållet kan anpassas av organisationen. Dessutom kan användarna bädda in Power BI-instrumentpanelsrutor på sina anpassade arbetsytor i Dynamics AX, så att de snabbt kan visa analytisk information.</td>
</tr>
<tr>
<td>Konfigurera konsumentbehörighet.</td>
<td>Inte tillgänglig</td>
<td>Kunder kan välja om POS-åtgärder kan vara tillgängliga för konsumenter. Retail Server använder behörigheter för API-anrop (Application Programming Interface).</td>
<td>Det ger möjlighet att konfigurera behörigheter på konsumentnivå.</td>
</tr>
<tr>
<td>Hantera och verifiera enhetskonfigurationer.</td>
<td>Inte tillgänglig</td>
<td>Konfigurationshanteraren och verifieringsfunktionen ger tillgång till följande funktioner:
<ul>
<li>Överföring av konfigurationsdata i grupp</li>
<li>Validering av företagsenhet</li>
</ul></td>
<td>Det ger möjlighet att initiera konfigurationen och att validera status och fullbordan av konfigurationen för de olika konfigurationselementen.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Retail Hardware Station

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Låt POS-enheter ansluta till kringutrustning som skrivare, kassaapparater eller betalningsenheter. | MPOS-maskinvaruprofilen används för att ange de enheter som används. | En ny maskinvaruprofil stöder mer diversifierad maskinvara från en station till en annan. En ny maskinvarustationsprofil stöder ett unikt terminal-ID för varje maskinvarustation när EFT (överföring av elektronisk betalning) bearbetas. EFT-stöd har integrerats i maskinvarustationen för att minska involveringen av MPOS i EFT-betalningsbearbetningen. | Det ger större flexibilitet för implementeringar. Det ger också bättre säkerhet och mindre exponering av kreditkortsdata. |

### <a name="retail-server-and-data-management"></a>Retail Server och datahantering

Retail Server och datahantering låter konsumenter och företag skapa en shoppingupplevelse i flera kanaler över online-, butiks- och kundtjänstkanaler.

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Anslut till en CRT-databas (Commerce Runtime) som lagrar affärsdata för kanalen genom att använda CRT-tjänster.</td>
<td>OData V3 stöds.</td>
<td>OData V4 stöds.</td>
<td>Det underlättar för kunden att hålla sig uppdaterad med OData-standarder. Det skapar också en robust upplevelse över flera kanaler genom att integrera försäljning över butiks-, mobil- och onlinekanaler.</td>
</tr>
<tr>
<td>Ge stöd för butikstjänster som en uppsättning tjänster som kan ligga hos en värd.</td>
<td>E-handels-API:t stöds inte genom Retail Server.</td>
<td>E-handels-API:t är nu tillgängligt via Retail Server för att ge stöd för onlinescenarier.</td>
<td>Det ger tillgång till värdbaserade och skalbara e-handelstjänster som kan användas med onlinebutiker från tredje part.</td>
</tr>
<tr>
<td>Flytta data mellan Microsoft Dynamics AX backoffice och kanaler med Commerce Data Exchange.</td>
<td>Commerce Data Exchange är ett system som överför data mellan Microsoft Dynamics AX och detaljhandelskanaler, till exempel onlinebutiker eller fysiska butiker. Mer information finns i <a href="https://technet.microsoft.com/library/dn741440.aspx">Commerce Data Exchange [AX 2012]</a>.</td>
<td>Det är samma funktioner med Microsoft Dynamics AX 2012 CU8. Observera dock följande information:
<ul>
<li>Commerce Data Exchange har anpassats för molnet.</li>
<li>Async-tjänsten använder direkt databasåtkomst till kanaldatabasen.</li>
<li>Commerce Data Exchange: Real-time Service finns som en Microsoft Dynamics AX anpassad tjänst.</li>
<li>MPOS hanterar synkroniseringen mellan offlinedatabaser och Retail Server.</li>
</ul></td>
<td>Commerce Data Exchange har anpassats för molnplattformen. Det fortsätter att hantera överföringen av data mellan Microsoft Dynamics AX och detaljhandelskanaler, till exempel onlinebutiker eller fysiska butiker.</td>
</tr>
<tr>
<td>Ge stöd för Plug-and-Play-aktiverad, halvintegrerad betalningsbearbetning mellan kanaler med hjälp av betalnings-SDK.</td>
<td>AX 2012 innehåller följande funktioner:
<ul>
<li>Stöd för alla kanaler: kassa, e-handel och kundtjänst.</li>
<li>Stöd för kort som finns och kort som inte finns.</li>
<li>Sida för att ta emot betalning.</li>
<li>Kringutrustningsstöd för LS5300 och MX925 som exempelkod i Retail SDK.</li>
</ul></td>
<td>Den aktuella versionen av Dynamics AX stöder alla befintliga kredit- och betalkortsfunktioner i Microsoft Dynamics AX för detaljhandeln 2012 och fyra nya förbättringar.</td>
<td>Det gör att kunden kan bearbeta kredit- och betalkortstransaktioner för betalningar.</td>
</tr>
<tr>
<td>Aktivera enheter med hjälp av ett Microsoft-konto (Microsoft Azure Active Directory (Azure AD)).</td>
<td>Inte tillgänglig</td>
<td>Följande funktioner tillhandahålls:
<ul>
<li>Förbättrad säkerhet efter Azure AD-baserad aktivering för molnet</li>
<li>Förbättrad säkerhet för tokenhantering.</li>
<li>Förbättrad tillförlitlighet, felsökning och felmeddelanden under aktiveringen</li>
<li>Förenklade IT-administrationsuppgifter som är relaterade till aktivering.</li>
<li>Granskad hotmodell och åtgärdade säkerhetsproblem.</li>
</ul></td>
<td>Den ger följande fördelar:
<ul>
<li>Säkerheten har förbättrats via Azure AD och enhetstoken/ID (RS-anrop som använder en token, användarspecifik programlagring).</li>
<li>Den stoppar obehörig fjärranvändning av MPOS (fysisk enhet).</li>
<li>Den spårar MPOS-enheter för PCI-efterlevnadssyften.</li>
<li>Den mappar fysiska enheter med en affärsenhet (register) genom att använda en token.</li>
<li>Den initierar inställningar för smidiga MPOS-funktioner (nummerserier och maskinvaruprofiler) som den första kontaktpunkten för MPOS.</li>
<li>Den rapporterar enhetsinformation från huvudkontor.</li>
</ul></td>
</tr>
<tr>
<td>Hantera avancerat medieinnehåll för redigering och tjänster via Mediagalleriet.</td>
<td>Inte tillgänglig</td>
<td><ul>
<li>Ge stöd för överföring av bilder och visa, hantera och ta bort från Media Gallery för både externt lagrade och Retail-lagrade bilder.</li>
<li>Ge stöd för överföring av bilder och visa från enhetssidor (<strong>Produkter</strong>, <strong>Kataloger</strong> osv.) genom att länka en bild från galleriet och överföra en bild från skrivbordet.</li>
<li>Optimera bilderna för miniatyr, anpassad storlek och original.</li>
<li>Masslänka enheter med en mall och bakgrundsjobb för massassociation.</li>
<li>Microsoft Excel-integrationen skriver över attributgruppsbegränsningen för namngivningskonventioner och fördefinierade sökvägar.</li>
<li>Ge stöd för offlinebilder och säkra bilder för innehåll med personligt identifierbar information, till exempel personal- och kundbilder i Retail.</li>
</ul></td>
<td><ul>
<li>Den hanterar sårbarheter som har att göra med externt lagrade bilder, så att du kan undvika att gå fram och tillbaka och i stället hantera allt på samma plats.</li>
<li>Den ger kraftfull innehållshantering via Media Gallery för överförda och externt lagrade bilder och erbjuder också filtrering för att hjälpa dig att hitta bilder.</li>
<li>Du kan enkelt skapa massassociationer mellan externt lagrade bilder och enheter såsom produkter och kataloger.</li>
<li>Bildlagring i Retail stöds samt Excel-integrering för enkla uppdateringar.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Heltäckande klientupplevelse

Retail erbjuder integrerade mobilupplevelser överallt, när som helst och på valfri enhet. Den här funktionen ger bättre shopping- och butiksupplevelser i alla kanaler.

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Sök, bläddra, leta upp eller skanna produkter, lägg till produkter i en vagn, godkänn en betalning och checka ut med hjälp av en intuitiv, touch-aktiverad, heltäckande och integrerad användarupplevelse på MPOS.</td>
<td>AX 2012 möjliggör följande funktioner:
<ul>
<li>Utför försäljning, returer och annulleringar.</li>
<li>Skapa, ändra och plocka upp kundorder.</li>
<li>Utför skift- och kassaaktiviteter.</li>
<li>Plocka och ta emot order och utför lagerinventeringar.</li>
<li>Visa rapporter i butiken.</li>
</ul></td>
<td>Samma funktioner som i AX 2012 MPOS tillhandahålls. Det omfattar följande funktioner:
<ul>
<li>Kundsökning över butiker/kanaler.</li>
<li>Möjlighet att skapa kundorder utan att öppna realtidstjänsten.</li>
<li>Förbättrade enhetsaktiveringsarbetsflöden, status och felmeddelanden.</li>
<li>Utökningsförbättringar, till exempel utlösare före/efter och aktivitetsstöd för bättre anpassning.</li>
</ul></td>
<td>Försäljningspersonalen kan bearbeta försäljningstransaktioner och kundorder samt utföra dagliga uppgifter och lagerhantering genom att använda mobila enheter någonstans i butiken.</td>
</tr>
<tr>
<td>Starta POS som en webbapp via POS i molnet.</td>
<td>Inte tillgänglig</td>
<td>Samma funktioner som i MPOS tillhandahålls. Det omfattar följande funktioner:
<ul>
<li>Enhetsaktivering genom att använda AAD</li>
<li>Responsiv layoutdesign</li>
<li>Stöd för webbläsarna Edge, Internet Explorer och Chrome.</li>
</ul></td>
<td>Den ger tillgång till POS i en webbapp som har funktioner som är kompatibla med MPOS och som kan användas mellan plattformar och webbläsare utan distributionskostnad.</td>
</tr>
<tr>
<td>Integrera med innehållshanteringssystem (CMS) om du vill skapa en e-handelswebbplats över flera kanaler.</td>
<td>Microsoft SharePoint och tredjepartsbutiker stöds.</td>
<td>En e-handelsplattform tillhandahålls som stöder tredjepartsbutiker. Plattformen innehåller följande funktioner:
<ul>
<li>Ett omfattande konsument-API.</li>
<li>Autentiseringsintegration till tredjepartsleverantörer av öppna ID:n.</li>
<li>Betalningsintegration.</li>
</ul></td>
<td>Kunder har nu möjligheten att använda det innehållshanteringssystem de vill.</td>
</tr>
<tr>
<td>Nå ut till kunder via e-post eller postorderkataloger och effektivisera aktiviteter genom snabbare orderregistrering, assisterad försäljning och uppfyllelse med hjälp av Call Center.</td>
<td><ul>
<li>Kundtjänstkanal</li>
<li>Postorderkataloger</li>
<li>Snabb orderregistrering och assisterad försäljning</li>
<li>Förbättrad orderuppfyllelse</li>
<li>Kundtjänst</li>
<li>Integrerad prissättning och rabatter/erbjudanden</li>
</ul></td>
<td>Samma funktioner som i AX 2012 Call Center är tillgängliga, med undantag för prisåsidosättningar.</td>
<td>Kundtjänst är en typ av butikskanal som låter anställda ta order från kunder över telefon och skapa försäljningsorder.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Grundläggande om handel

Ett butiks- och handelsfokuserat konfigurationsalternativ effektiviserar detaljhandelsspecifika distributioner.

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Använd instrumentpanelen Grundläggande om handel. | En områdessida med länkar till menykommandon är tillgänglig. | Instrumentpanelen Grundläggande om handel innehåller länkar till vanliga uppgifter, inklusive länkar till arbetsytor, Power BI-webbkontrollen, favoriter, senaste sidor och aktuella arbetsobjekt. | Den förbättrade instrumentpanelen gör att arbetare kan bli mer effektiva och ger en flexibel utgångspunkt för alla detaljhandelsspecifika uppgifter. |
| Använd datatabeller för att komma åt kontoändringar. | Kontoändringar exporteras till en mapp i filsystemet. | Kontoändringar är tillgängliga via datatabeller. | Den här funktionen ger större flexibilitet när du flyttar data mellan olika system. Den här funktionen kan också förbättras via OData-tillämpningar. |
| Använd molnbaserad POS och MPOS. | Endast Enterprise POS (EPOS) stöds från början. | MPOS och molnbaserad POS ersätter EPOS-klienten. E-handelskanalen har också lagts till på Grundläggande om handel som standard. | Den här funktionen ger bättre inbyggt kanalstöd med snabbt distribuerbara POS-klienter. |
| Implementera och underhålla arkitektur i två nivåer. | Ramverket för dataimport/-export ger möjlighet att flytta data mellan AX 2012 och tredjepartssystem. | Datatabeller har skapats för att förbättra stödet för en arkitektur med två nivåer. | Datatabeller och OData-program tillhandahåller ett abstraktionsskikt som gör scenarier med två nivåer enklare att implementera och underhålla. |
| Förenkla formulär. | Anpassad kod krävs för att förenkla användargränssnittet. | Formulär- och menytillägg tillhandahåller standardiserad UI-förenkling. | Den här funktionen är ett snabbare och enklare sätt att finjustera formulär baserat på återförsäljarens behov. |

### <a name="pos-task-recorder"></a>POS-uppgiftsregistrering

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Skapa och dela uppgiftsguider och dokument för modern POS.</td>
<td>Inte tillgänglig</td>
<td>MPOS-uppgiftsregistrering stöder följande funktioner:
<ul>
<li>Skapa uppgiftsregistreringar för olika uppgifter som utförs i MPOS.</li>
<li>Skapa ett dokument som innehåller steg och skärmbilder och associera det med en nod i affärsprocessmodellen.</li>
</ul></td>
<td>Partner och oberoende programförsäljare (ISV:er) kan anpassa MPOS och tillhandahålla stöddokument för att utbilda deras användare.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Utbyggbarhet

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ge stöd för skalbara och lättdistribuerade Retail-komponenter över administration, kundtjänst, e-handel och kassa.</td>
<td>Komponenterna kan utökas med hjälp av Retail SDK. Inga förpacknings- och distributionsfunktioner stöds.</td>
<td>Utökningsmöjligheterna har förbättrats i flera komponenter för att ge bättre stöd för kodisolering och användbarhet. Här är några funktioner som ingår:
<ul>
<li>Arbetsflöde, aktivitet och åtgärd.</li>
<li>Utlösare före/efter som gör det enkelt att utöka ett arbetsflöde.</li>
<li>Program- och åtgärdsutlösare.</li>
</ul>
Dessutom är ett ramverk tillgängligt som låter dig bygga och paketera dessa komponenter med hjälp av MSBuild och sedan sömlöst distribuera anpassningen via Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>Återförsäljare har mycket särskilda krav som baseras på vertikaler och geografiska områden. Genom att tillhandahålla en enkel skalbar plattform möjliggör vi användning mellan vertikaler och marknader. Eftersom Retail också har en mycket distribuerad arkitektur förbättras produktiviteten rejält tack vare möjligheten att distribuera sömlöst.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Livscykelhantering

Lifecycle Services (LCS) tillhandahåller ett antal tjänster som kunder och partner kan använda för att hantera livscykeln för systemet från registrering till dagliga uppgifter.

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Hantera programmet via molndistributionstjänster.</td>
<td>Inte tillgänglig</td>
<td>Följande topologier kan distribueras till molnet:
<ul>
<li>Retail utvärderingstopologi (en box)</li>
<li>Retail topologi med hög tillgänglighet (flera boxar).</li>
<li>Utvecklartopologi med Retail SDK.</li>
</ul>
Det finns en förbättrad ”low-touch”-klientkomponentinstallation via självbetjäningsinstallation:
<ul>
<li>Retail Modern POS</li>
<li>Retail Hardware Station.</li>
<li>Stöd för överföring och distribution av anpassade paket via självbetjäningsinstallation.</li>
</ul></td>
<td>Molndistributionstjänsterna tillhandahåller följande fördelar:
<ul>
<li>Mycket mindre distributionsarbete och komplexitet för komponenter för Administration för detaljhandel.</li>
<li>Ursprunglig distribution till det offentliga Microsoft Azure-molnet</li>
<li>Förbättrad självbetjäningsinstallation av butikskomponenter som gör konfigurationen enklare och mer intuitiv</li>
</ul></td>
</tr>
<tr>
<td>Övervaka systemhälsa och diagnostisera fel och problem.</td>
<td>Den här funktionen kräver <a href="https://www.microsoft.com/download/details.aspx?id=42636">System Center 2012 Management Pack för Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>Övervakning och diagnostik för Retail-komponenter är nu tillgängliga via instrumentpanelen <strong>Insikt i driften</strong> i LCS.</td>
<td>Instrumentpanelen <strong>Insikt i driften</strong> är en molnbaserad övervakningsportal som ersätter behovet av att installera SCOM-infrastrukturen (System Center Operations Manager).</td>
</tr>
<tr>
<td>Skapa, konfigurera, hämta och installera Retail Hardware Station och enheter med hjälp av självbetjäning.</td>
<td>Genom att använda installationspaketeraren och Enterprise Portal kan en användare utföra en automatiserad installation och konfiguration av alla komponenter som krävs på en viss dator baserat på en definierad topologi.</td>
<td>Eftersom det bara finns två installationspaket, ett för MPOS-klienten och det andra för Retail Hardware Station-komponenten, har självbetjäningen minskat mängden arbete som krävs på varje nivå för att installera dessa klientkomponenter.</td>
<td>Självbetjäning syftar på att minimera kraven och göra det enklare för en användare att utföra en installation.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Försäljning

<table>
<thead>
<tr>
<th>Vad kan du göra?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Varför är detta viktigt?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Få en snabb överblick över leveransalternativ när du lovar order till kunder.</td>
<td>När det finns produkttillgänglighetsbegränsningar, och kundens begärda leveransdatum för en eller flera produkter på ordern inte kan uppfyllas, blir orderlöftesuppgiften en utmaning. Om du vill hitta alternativ som kan åsidosätta tillgänglighets- och leveranstidsproblem så att kundens begärda datum kan uppfyllas, eller för att erbjuda kunder en leveranslösning som de kan acceptera och lita på, kanske orderbehandlaren måste öppna flera formulär, som vart och ett endast erbjuder en delmängd av den nödvändiga informationen. Mer specifikt visar ett formulär lagerbehållningen mellan platser, ett annat formulär visar lagerbehållningen i de koncerninterna inställningarna, ett tredje formulär låter användarna beräkna det tidigaste datumet för en plats/variant i taget och ett fjärde formulär visar leveransorder. Därför känner sig inte användarna säkra på att de har haft alla relevanta alternativ i åtanke jämfört med att bara välja en snabb men bristfällig lösning. Användarna känner sig inte heller effektiva eftersom flera avbrott uppstår under orderlöftesflödet när de öppnar och stänger flera sidor, och kombinerar insikterna och alternativen.</td>
<td>Baserat på de befintliga algoritmerna för beräkning av leveransdatum erbjuder sidan <strong>Leveransalternativ</strong> en ny användarupplevelse för orderlöften:
<ul>
<li>Den konsoliderar relevant information från flera formulär på samma plats.</li>
<li>Den erbjuder leveranspaket med ”färdiga” alternativ, till exempel ett kombinerat läge för plats/lagerställe/variant/transport, baserat på kriteriet för snabbast leverans (tidigaste tillgänglighetsdatum) som användaren kan välja från.</li>
<li>Den låter användaren välja alternativ från simuleringsgränssnittet och överföra dem till försäljningsorderraden.</li>
</ul></td>
<td>Företag med en ambition att leverera riktigt bra kundtjänst och att underhålla en lageroptimeringsstrategi måste kunna lova order på ett tillförlitligt och konkurrenskraftigt sätt. När allt kommer omkring kräver deras kunders verksamhet att produkterna finns tillgängliga i tid. Uppgiftssidan <strong>Leveransalternativ</strong> gör orderlöftesuppgiften snabbare, enklare och mer systematisk genom att identifiera och rekommendera de bästa alternativa orderleveransdatumen på en interaktiv plats.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Tjänstehantering

Inga nya funktioner har lagts till.

## <a name="transportation-management"></a>Transporthantering

Inga nya funktioner har lagts till.

## <a name="travel-and-expense"></a>Resor och utgifter

Inga nya funktioner har lagts till.

## <a name="warehouse-management"></a>Lagerstyrning

| Vad kan du göra? | Dynamics AX 2012 | Dynamics AX 7.0 | Varför är detta viktigt? |
|------------------|------------------|-----------------|------------------------|
| Hämta, installera och konfigurera Warehouse Mobile Devices Portal. | Du kan hämta, installera och konfigurera portalen under Microsoft Dynamics AX-installationsprocessen genom en standardinstallation. Den har utformats för automatisk lokal distribution och konfiguration. | Du kan hämta ett fristående installationsprogram via ett menykommando i Lagerstyrning. Den har utformats för automatisk lokal distribution och konfiguration. | När du ställer in användningen av funktioner för mobila enheter måste du installera och konfigurera Mobile Devices Portal lokalt och upprätta en anslutning till Dynamics AX-programmet i molnet. |

## <a name="additional-resources"></a>Ytterligare resurser

[Nyheter och ändringar på hemsidan för Finance and Operations](whats-new-changed.md)

[Nya uppgiftguider (februari 2016)](new-task-guides-available-february-2016.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]