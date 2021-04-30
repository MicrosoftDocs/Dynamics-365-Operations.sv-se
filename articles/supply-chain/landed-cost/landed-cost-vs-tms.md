---
title: Hemtagningskostnad jämfört med Transporthantering
description: Microsoft Dynamics 365 Supply Chain Management tillhandahåller två olika moduler för att arbeta med transport, Transporthantering (TMS) och Hemtagningskostnad. I det här avsnittet sammanfattas de funktioner som de två modulerna har gemensamt och skillnaderna mellan dem beskrivs.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 244d378316caf639c3520a1179dd82955d94220a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5909485"
---
# <a name="landed-cost-vs-transportation-management"></a>Hemtagningskostnad jämfört med Transporthantering

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management tillhandahåller två olika moduler för att arbeta med transport, **Transporthantering** (TMS) och **Hemtagningskostnad**. I det här avsnittet sammanfattas de funktioner som de två modulerna har gemensamt och skillnaderna mellan dem beskrivs. Du kan använda den här informationen för att avgöra vilken modul som passar bäst för din verksamhet. Du kanske tycker att vissa av affärsrutinerna fungerar bättre med TMS, medan andra fungerar bäst med hemtagningskostnad. Därefter kan du, beroende på företagets verksamhetsbehov, välja att använda en modul exklusivt, eller kombinera de två modulerna.

Detta avsnitt är en inte omfattande granskning av alla funktioner i någon av modulerna. Istället markerar det den tillgängliga funktionen som gäller för transport av varor från en leverantör till ditt företags lagerställe, där det kan förbrukas.

## <a name="terminology-reference-data-and-reporting-differences"></a>Terminologi, referensdata och rapporteringsdifferenser

### <a name="terminology-comparison"></a>Jämförelse av terminologi

TMS och hemtagningskostnad använder olika termer i liknande koncept. I följande tabell sammanfattas dessa termer och deras användning i de två modulerna.

| TMS-term | Hemtagningskostnadsterm | Anteckningar |
|----------|------------------|-------|
| **Last**<p>En *last* är en samling försändelser som transporteras samtidigt i samma transportenhet (till exempel en lastbil eller ett skepp). Laster kan vara inkommande eller utgående.</p> | **Sjötransport**<p>Vanligtvis är en *färd* ett enda fartyg som färdas i en enda *resa*. En sådan kan innehålla flera *leveransbehållare* och den kan också inkludera inkommande order från olika juridiska personer i din organisation. Färder kan bara vara inkommande.</p> | TMS använder även termen *färdnummer*, som refererar till ett informationsfält där du kan ange en identifierare. Inga funktioner är emellertid associerade med TMS-fältet och det är inte relaterat till konceptet *färd* i Hemtagningskostnad. |
| **Rutt**<p>Ett *flöde* är den fysiska vägen för en transport från ursprung till destination.</p> | **Resa**<p>En *resa* är den fysiska vägen för en transport från ursprung till destination. Varje färd en gång måste tilldelas en resa.</p> | |
| **Flödessegment**<p>Ett flöde kan ha flera *flödessegment*, som vart och ett representerar ett steg i resan. Ett flöde kan omfatta flera transportföretag eller tjänster, och vart och ett anses vara ett flödessegment.</p> | **Etapper**<p>Varje resa kan ha flera *sträckor*, som vart och ett representerar ett steg i resan. En sträcka kan ingå i transport, tullhantering eller annan aktivitet.</p> | |
| **Fraktbehållare**<p>En *behållare* kan vara en valfri förpackning eller förpackning som används av TMS.</p> | **Fraktcontainrar**<p>En *transportbehållare* är en fysisk transportbehållare från containerfartyg.</p> | |
| **Artikelkoder**<p>I TMS (och på andra ställen i Supply Chain Management), identifierar *artikelkoder* typer av handelsvaror. De kan påverka tariffer, hantering av skadliga material och så vidare.</p> | **Artikelkoder**<p>I hemtagningskostnad fastställs *artikelkoder* är etablerade på den juridiska enhetens nivå. De används för det mesta för rapportering.</p> | Hemtagningskostnad kan även använda artikelkoderna som används för TMS och andra ställen i Supply Chain Management. Artikelkoderna för hemtagningskostnad används dock endast av hemtagningskostnad. |

### <a name="some-reference-data-isnt-shared"></a>Vissa referensdata som inte har delats

TMS och hemtagningskostnad delar inte referensdata för enheter som kostnadsinställningar, osv. Om du använder båda modulerna måste du skapa om de odelade referensdata.

### <a name="intercompany-reports-dont-work-with-goods-in-transit"></a><a name="intercompany-reports"></a>Koncerninterna rapporter fungerar inte med varor på väg

Följande rapporter fungerar inte tillsammans med funktionen varor på väg som hemtagningskostnad tillhandahåller:

- [Rapporten Summor för koncerninterna varor på väg](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)
- [Rapporten Summor för koncerninterna varor på väg](/dynamicsax-2012/appuser-itpro/intercompany-goods-in-transit-totals-report-intercompanygoodsintransittotals)

Dessa rapporter förutsätter att varor sätts i transit så snart du utfärdar en följesedel och att de förs in i lagret från transit vid inleverans. Varor på väg bearbetas emellertid inte på det här sättet. Om du använder varorna på väg och koncerninterna funktioner tillsammans, blir därför resultatet för båda dessa rapporter fel.

## <a name="using-the-two-modules-together"></a>Använda de två modulerna tillsammans

Du kan använda TMS för både inkommande och utgående operationer. Trots att hemtagningskostnad har de flesta grundläggande funktioner som TMS för inkommande operationer, lägger den även till vissa funktioner. Därför bör du överväga att använda TMS för utgående operationer och hemtagningskostnad för inkommande operationer.

I allmänhet rekommenderar vi inte att du använder båda modulerna tillsammans för inkommande operationer. Du bör använda den modul som bäst uppfyller dina behov. Om du använder de två modulerna tillsammans får du inte dela källdokument mellan dem. Du ska till exempel inte använda samma inköpsorder för både en last i TMS och en färd i hemtagningskostnad. Du måste särskilt se till att du inte ställer in systemet så att inkommande laster skapas automatiskt. Om artiklar från inköpsorder inkluderas i en inköpsorder, kan de inte hanteras som en del av en last.

## <a name="goods-in-transit"></a>Varor på väg

En av de primära funktionerna för hemtagningskostnad är dess förmåga att bearbeta varor på väg. Med varor på väg kan du ta ekonomiskt ansvar för levererade artiklar innan de fysiskt tas emot i lagerstället vid destinationen. Bearbetning av varor på väg krävs ofta för den internationella handeln.

### <a name="tms-goods-in-transit-features"></a>Funktioner för TMS varor på väg

TMS stöder för närvarande inte bearbetning av varor på väg.

### <a name="landed-cost-goods-in-transit-features"></a>Funktioner för hemtagningskostnad för varor på väg

Bearbetning av varor på väg är en primär funktion för hemtagningskostnad och innehåller följande funktioner:

- **Lager för varor på väg** – Ett lager för varor på väg kan associeras med varje lagerställe i Supply Chain Management. Varor överförs till lager för varor på väg efter att den ursprungliga inköpsordern fakturerats. Artiklar som reserverats fysiskt där blir inte tillgängliga för förbrukning förrän de tas emot på sitt fysiska lagerställe. Därför kan du ta ekonomiskt ansvar för varor genom att fakturera inköpsordern.
- **Redovisningskonto varor på väg** – Hemtagningskostnad lägger till ett specifikt bokföringskonto i inköpsorderprofilen för att hantera behandling av varor på väg. Detta redovisningskonto för varor på väg fungerar som ett konto av typen "Varor som fakturerats inte mottaget". När den ursprungliga inköpsordern faktureras och ordern för varor på väg skapas, bokförs den direkta inköpsorderkostnaden på redovisningskonto för varor på väg tills varorna har inkommit vid deras slutgiltiga fysiska plats.
- **Spårningskontrolluppdateringar** – Order för varor på väg stöder spårningskontroll i hemtagningskostnad. Med spårningskontroll kan du uppdatera förväntat införseldatum för varor under transport. Spårningskontroll uppdaterar sedan färden och de tillhörande inköpsorderraderna. Det förväntade leveransdatumet är sedan tillgängligt för huvudplanering och logistik.
- **Utlösa över-/undertransaktioner** – Om det förekommer en avvikelse mellan de förväntade varorna på en färdrad och de faktiska varorna som tas emot på lagret löser hemtagningskostnad det genom att skapa över- och/eller undertransaktioner. Därefter kan du hantera transaktionerna, utifrån det sätt du vill bearbeta dem på, genom antingen en inköpsorder eller en flyttningsjournal. Över- och undertransaktionerna utgör en länk tillbaka till den ursprungliga inköpsordern, den ursprungliga inköpsordern och den nya rörelsejournalen eller inköpsordern för avvikelsen.
- **Order för varor på väg** – Hemtagningskostnad introducerar ett nytt källdokument som är känt som ett *Order för varor på väg*. Med order för varor på väg kan du fakturera den ursprungliga inköpsordern för att bli ägare till artiklarna ekonomiskt. När inköpsordern faktureras skapas det nya källdokumentet för varje inköpsorderrad som har en kombination av lagerdimensioner. Varor flyttas sedan fysiskt till ett varor på väg där de fysiskt reserveras mot varor på väg och kan inte förbrukas såvida inte varor på väg tas emot.

## <a name="miscellaneous-charges-and-shipment-costs"></a>Tillägg och leveranskostnader

En av de viktigaste aspekterna av leverans- och försändelsehanteringen för varor är att känna igen de indirekta kostnader som är associerade med leveranser. Dessa indirekta kostnader är inte de direkta lagerkostnaderna som associeras med en inköpsorder och en leverans eller färd. I stället är det ytterligare kostnader som presenteras av typen av varors rörelse från leverantören till din organisation. Kostnaderna kan innefatta fraktkostnader som är associerade med leveransen av varor från en fysisk plats till en annan, eller avgifter som är associerade med import av varor från en utländsk leverantör.

Hemtagningskostnad hanterar dessa kostnader genom att skapa en ny typ av kostnadsstruktur som kallas för *automatiska kostnader*. TMS hanterar de här kostnaderna med hjälp av tilläggsfunktionen.

### <a name="tms-charge-and-cost-features"></a>TMS funktionen för avgift och kostnad

TMS använder tillägg för att hantera ytterligare kostnader för belastning som fördelas på de relaterade källdokumentraderna. Dessa tillägg kan ställas in på nivån för inköpsorderraden eller inköpsorderrubriken.

I TMS kan tilläggen fördelas eller delas upp efter vikt, volym eller kvantitet i lagret. Avgifter kan delas med frakt eller tillägg. Ytterligare utveckling kommer att krävas för att använda ytterligare fördelningsmetoder i TMS.

### <a name="landed-cost-charge-and-cost-features"></a>Hemtagningskostnadstillägg och kostnadsfunktioner

Hemtagningskostnad tillhandahåller en uppsättning kostnadsfunktioner som hanterar ytterligare kostnader som är kopplade till leveransen av varor. Dessa kostnader kallas för automatiska kostnader och används vid tidpunkten för ursprunglig leveransfakturering genom att använda det uppskattade kostnadsbeloppet. Varje kostnadstyp hanteras i sin egen bokföring. När de faktiska fakturorna för omkostnader bokförs uppdateras de uppskattade kostnaderna automatiskt efter de faktiska kostnaderna.

Dessutom kan omkostnader som är kopplade till försändelsen av varor faktureras under perioden för leverans från ursprungsplatsen eller när varorna har inkommit. Denna kapacitet ger större flexibilitet för förbrukningen av varor.

I följande lista beskrivs några koncept för avgifts- och kostnadsfunktionerna i hemtagningskostnad:

- **Kostnadsområde** – Kostnader och avgifter kan tilldelas olika nivåer, eller *kostnadsområden*, på en gång. Kostnaden kan användas på färdnivån och delas upp på varje artikel i färden. Dessutom kan kostnader tillämpas på nivån för behållaren, inköpsordern, artikeln eller överföringsordern. Varje kostnadstillägg kan hanteras separat i olika områden och delas upp på en kostnad per artikel.
- **Fördelningsmetoder** – Flera olika betalningsmetoder finns i hemtagningskostnad. Kostnadsavgifter kan fördelas efter kvantitet, dollarbelopp, värde, vikt, volym, mått eller ett användardefinierat volymmått.
- **Clearing/avvikelsekontroll** – Kostnadsavgifter ställs in som sin egen kostnadskodtyp i hemtagningskostnad. Varje kostnadskodtyp gör att du kan definiera ett clearingkonto för uppskattade kostnader, och även konton för periodiserings- och inköpsprisavvikelser för avvikelser i uppskattade kostnader jämfört med faktiska kostnader. När de uppskattade kostnaderna bokförs inledningsvis ges clearingkontot en kredit. När de faktiska fakturorna har bokförts bokförs de faktiska kostnadsavgifterna och de uppskattade kostnaderna debiteras från clearingkontot.

## <a name="matching-freight-bills-and-invoices"></a>Matcha fraktsedlar och fakturor

### <a name="tms-bill-and-invoice-matching-features"></a>TMS fraktsedel- och fakturamatchningsfunktioner

TMS kan matcha fraktsedlar som innehåller uppskattade kostnader och fakturor med den faktiska kostnaden för frakten. Fakturor kan tas emot elektroniskt eller som pappersfaktura. Att matcha avvikelser mellan den uppskattade kostnaden och den faktiska kostnaden påverkar inte lagervärderingen.

Mer information finns i [Stäm av frakt i transporthanteringen](../transportation/reconcile-freight-transportation-management.md).

### <a name="landed-cost-bill-and-invoice-matching-features"></a>Hemtagningskostnad fraktsedel- och fakturamatchningsfunktioner

Hemtagningskostnad kan matcha fraktsedlar med uppskattade kostnadsavgifter och kan fakturera de faktiska kostnaderna till de uppskattade kostnaderna. Vid faktureringen finns fraktkostnaderna i en fakturajournal och de uppskattade kostnaderna rensas från clearingkontot. De faktiska kostnaderna bokförs också mot kostnaden för sålda varor för artikeln, tillsammans med avvikelserna mellan de uppskattade avgifterna och de faktiska avgifterna. Detta beteende medger flexibilitet i faktureringsprocessen.

## <a name="tracking"></a>Spårning

En viktig funktion för både TMS och hemtagningskostnad är möjligheten att spåra varor och identifiera var de befinner sig i resan, från ursprungsplatsen till lagerstället vid slutdestinationen. Med spårning kan du följa och uppdatera var varorna finns och när de förväntas ankomma till lagerstället för förbrukning. Förutom varustatusen under resan ger hemtagningskostnad förväntade och faktiska datum för varje steg i resan.

### <a name="tms-tracking-features"></a>TMS spårningsfunktioner

TMS ger begränsade funktioner för spårning av inkommande laster. Här visas datum och det går att skapa en integration för att hitta den exakta positionen (till exempel på sidan **Transportstatus**).

För varje flödessegment kan du ange uppskattade tidsplaner och ankomsttider.

### <a name="landed-cost-tracking-features"></a>Spårningsfunktioner för hemtagningskostnader

Hemtagningskostnad kan ge spårningskontroll för varje destination, från ursprungsporten till den slutliga destinationen. Spårningskontroll ställer in status för färden. Statusen anger om färden är beroende av händelsen, eller om den är i tullen för inspektion eller i lokal leverans på väg till det slutliga lagerstället. Statusen kan ställas in på nivån för inköpsorderraden, behållaren och huvudet för inköpsordern. Därför har du mer finkontroll.

Ett bekräftat förväntat datum som baseras på angivna ledtider associeras dessutom med varje steg i en resa. De bekräftade och förväntade leveransdatumen läggs till på inköpsorderraden och order för varor på väg och kan användas för huvudplanering och logistik. Förutom de förväntade datumen kan de faktiska datumen uppdateras. De efterföljande stegen i en resa uppdateras sedan.

## <a name="multi-leg-journeys"></a>Resor med flera etapper

Resans koncept identifierar var varorna är i processen och kontrollerar varornas status medan de är på väg. Varor kan gå genom flera sträckor i en resa och du kan associera olika kostnader med en viss sträcka. Exempel är fraktkostnader vid segling av ett fartyg och lokala transportkostnader för transport av varor från hamnen till destinationen.

### <a name="tms-multi-leg-journey-features"></a>TMS funktioner för resor med flera sträckor

I TMS kan flöden delas upp i flödessegment som representerar resor med flera sträckor. TMS kan allokera punkttariffer och tilläggsavgifter på enskilda flödessegment.

Mer information finns i [Planera frakttransportvägar med flera stopp](../transportation/plan-freight-transportation-routes-multiple-stops.md).

### <a name="landed-cost-multi-leg-journey-features"></a>Hemtagningskostnad för funktioner för resor med flera sträckor

Hemtagningskostnad utgör ett ramverk för att föra varor från ursprungsplatsen till destinationen genom en serie sträckor, som utgör stoppen eller stegen i en resa. Sträckorna kombineras för att skapa mallar som definierar hur varor förflyttas från leverantören till din organisation.

I varje sträcka på en resa kan du ytterligare definiera statusen för varje inköpsorderrad och de ledtider som är kopplade till den. Den kombinerade ledtiden för alla dessa används för att identifiera uppskattat leveransdatum. Bearbetning av varor på väg krävs för att resor med flera sträckor ska gälla. Resan för varor på en färd hanteras i en tabell som är specifik för hemtagningskostnad.

## <a name="receiving-by-container"></a>Mottagning via behållare

Det kan vara viktigt att hantera hur varor delas upp och lagras på en plats. På ett fartyg kan varor förvaras i en behållare eller flera behållare. När varor tas emot fås de i behållare och olika behållare på en färd kan tas emot på olika tider eller på olika datum.

Både TMS och en hemtagningskostnad innehåller funktioner för hantering av inleverans av varor i en behållare. TMS använder konceptet laster för att hantera varor, inköpsorder och överföringsorder som är kopplade till en leveransbehållare. TMS stöder inleverans av en förpackningsstruktur som tas emot genom en leveransavi (ASN). Hemtagningskostnad använder begreppet leveransbehållare för att bearbeta inköpsorder och kontrollera omkostnader som associeras med en behållare på ett fartyg.

### <a name="tms-receiving-by-container-features"></a>TMS inleverans med behållare, funktioner

TMS stöd för inkommande ASN, alla varianter av mottagning via mobilappen för distributionslagerhantering samt alla mottagningsmetoder via Supply Chain Management-klienten.

### <a name="landed-cost-receiving-by-container-features"></a>Hemtagningskostnad inleverans med behållare, funktioner

För att stödja mottagning av behållare skapar hemtagningskostnad poster för leveransbehållare och associerar inköpsorder med en specifik behållare genom att använda dess behållar-ID. Omkostnader kan sedan tillämpas på den leveransbehållaren och brytas ned så att de associeras med relevanta inköpsorder.

Behållare i hemtagningskostnad kan tas emot via en ny typ av inleverans som kallas för *inleverans av varor på väg*, via införseljournaler eller via mottagning av mobila enheter. När införseljournaler används kan kvantiteterna initieras från order för varorna på väg eller från de ursprungliga inköpsorderraderna i behållaren. Hemtagningskostnad tillhandahåller två arbetstyper som kan tas emot via mobilappen för distributionslagerhantering.

Hemtagningskostnad ger inte något ASN för elektronisk inleverans av varor. Det har inte stöd för flöden mobilappen för distributionslagerhantering som bearbetar inläsning, inleverans av ID-nummer eller inleverans mixat ID-nummer.

## <a name="rate-shopping-by-vendor"></a>Fraktprissökning per leverantör

Med fraktprissökning kan ett företag välja en transportleverantör baserat på lägsta pris, det snabbaste flödet eller en kombination av båda beaktandena.

### <a name="tms-rate-shopping-features"></a>TMS fraktprissökning, funktioner

TMS låter dig identifiera leverantörs- och flödeslösningar för inkommande och utgående order. Du kan till exempel identifiera det snabbaste flödet eller den minst kostsamma tariffen för en leverans.

TMS tillhandahåller fullständig prisinköp och fraktoptimering med hjälp av workbench för tariff/rutt, flexibla värderingsalternativ via värderingsmotorn, ett värderingsmotor-API för integration med externa parter och stöd för volymvikt.

Mer information finns i [Transporthanteringsmotorer](../transportation/transportation-management-engines.md).

### <a name="landed-cost-rate-shopping-features"></a>Funktioner för fraktprissökning för hemtagningskostnad

Hemtagningskostnad ger bara begränsat stöd för fraktprissökning per leverantör. Även om du kan ange värden för fraktspeditör, jämför inte hemtagningskostnad dem mellan flera leverantörer.

## <a name="driver-check-incheck-out-with-appointment-scheduling"></a>Incheckning/utcheckning av förare med transportplanering

Med funktionen för incheckning/utcheckning av förare kan systemet övervaka inkommande och förhindra att lastningsplatsen överbelastas.

### <a name="tms-driver-check-incheck-out-features"></a>TMS in- och utcheckning för förare, funktioner

TMS låter dig skapa *möten*. Ett möte representerar händelser som inträffar vid en lastningsplats för att få en inköpsorder, leverans av en försäljningsorder eller för att bearbeta en inkommande eller utgående last på ett visst datum eller en viss tid. Möten säkerställer att det finns platser för lastning och avlastning av varor, och de förhindrar situationer där flera transportföretag anländer till en plats samtidigt.

Systemet medger att förarna kan checka in på en viss lastbrygga.

### <a name="landed-cost-driver-check-incheck-out-features"></a>Hemtagningskostnad in- och utcheckning för förare, funktioner

Hemtagningskostnad kan lagra uppskattningar för datum och tid när en behållare ska levereras.

## <a name="transfer-orders-and-additional-costs"></a>Överföringsorder och ytterligare kostnader

Ofta måste företagen kunna överföra varor mellan lagerställen. När den här typen av överföring sker associeras kostnader och du kanske vill identifiera dessa kostnader. I hemtagningskostnad kan överföringsorder läggas till i en försäljningsorder eller användas för att spåra varurörelser från ett lagerställe till ett annat, uppskatta leveranstiden och det förväntade leveransdatumet och lägga till omkostnader vid överföringen av varor.

### <a name="tms-transfer-order-cost-features"></a>TMS överföringsorder, funktioner

TMS ger stöd för generering av fraktavgifter som är kopplade till överföringar. Även om de här avgifterna kan visas från överföringsordern läggs hemtagningskostnad inte till i artikelkostnaden. Fraktavstämning stöds genom att du skapar en fraktsedel som baseras på dessa avgifter. Denna fraktsedel matchas sedan mot en leverantörsfraktfaktura.

### <a name="landed-cost-transfer-order-cost-features"></a>Funktioner för hemtagningskostnad för överföringsorder

Med hemtagningskostnad kan du lägga till överföringsorder till ett fartyg eller en färd. På det här sättet kan du lägga till leveranskostnader till lagret som lagerkvittning vid inleverans av överföringsorder. Omkostnader kan faktureras för de faktiska kostnaderna och spåras mot en uppdatering av kostnaden för sålda varor. Överföringsorder använder inte bearbetning av varor på väg i standardutgåvan, men de kan läggas till i färder. Hemtagningskostnad läggs till den totala kostnaden för varje artikel.