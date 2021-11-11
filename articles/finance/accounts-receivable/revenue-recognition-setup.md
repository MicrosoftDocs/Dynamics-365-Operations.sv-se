---
title: Inställning för intäktsredovisning
description: I det här avsnittet beskrivs inställningsalternativen för intäktsredovisning och deras konsekvenser.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b5ffd86d736cb7b6b5c270663c2b774e14556a6b
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675211"
---
# <a name="revenue-recognition-setup"></a>Inställning för intäktsredovisning
[!include [banner](../includes/banner.md)]

En ny modul för **intäktsredovisning** har lagts till, inklusive menyartiklar för alla inställningar som krävs. I det här avsnittet beskrivs inställningsalternativen och deras konsekvenser.

> [!NOTE]
> Intäktsredovisningsfunktionen är nu aktiverad som standard via Funktionshantering. Om din organisation inte använder den här funktionen kan du stänga av den i arbetsytan **Funktionshantering**.
>
> Intäktsredovisning, inklusive buntfunktionen, stöds inte i Commerce-kanaler (e-handel, kassa och callcenter). Artiklar som konfigureras för intäktsredovisning ska inte läggas till på order eller transaktioner som skapades i Commerce-kanaler.

Modulen för **intäktsredovisning** har följande inställningsalternativ:

- Intäktsredovisningsjournaler
- Parametrar för intäktsredovisning
- Intäktsplaner 
- Lagerinställning

    - Artikelgrupper och frisläppta produkter
    - Definiera intäktsschema
    - Definiera intäktspris
    - Lagerinställning

        - Definiera intäktsschema
        - Definiera intäktspris

    - Bokföringsprofiler
    - Buntar

        - Bunta ihop komponenter
        - Bunta artikel

- Projektinställningar

## <a name="revenue-recognition-journals"></a>Intäktsredovisningsjournaler

En ny journaltyp har införts för intäktsredovisning. Journalen är obligatorisk och används i två scenarier.

Det första scenariot inträffar när alla avtalade förpliktelser har uppfyllts, när den periodiserade intäkten känns igen genom att en journal för intäktsredovisning skapas som baseras på detaljerna i intäktsplanen. Journalen innehåller en redovisningspost som flyttar saldot från huvudbokskontot för periodiserade intäkter till huvudbokskontot för intäkter.

Det andra scenariot inträffar när en journal skapas efter omallokeringen. Omallokering sker när en försäljningsorderrad läggs till i en tidigare fakturerad försäljningsorder, eller när en ny försäljningsorder skapas som innehåller en rad som ingår i det ursprungliga kontraktet. Om en faktura har bokförts innan den nya försäljningsorderraden har lagts till måste en korrigerande redovisningstransaktion skapas för den bokförda kundfakturan.

Journalen ställs in på sidan **Journalnamn** (**Intäktsredovisning \> Inställningar \> Journalnamn**). Journaltypen måste ställas in på **Intäktsredovisning**. Med hjälp av journalen för intäktsredovisning väljer du vilket bokföringsskikt som ska bokföras.

## <a name="parameters-for-revenue-recognition"></a>Parametrar för intäktsredovisning

Inställningarna för intäktsredovisning konfigureras på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**). Följande inställningar är tillgängliga:

- **Journalnamn för intäktsredovisning** – välj den journal som skapades för intäktsredovisning. Journalen är nödvändig när intäkten redovisas i intäktsplanen eller när du omallokerar en försäljningsorder som redan har fakturerats.
- **Aktivera metod för rabattfördelning** – Ställ in det här alternativet på **Ja** för att fastställa intäktspriset via allokering av det marknadsmässiga värde som har definierats i intäktspriset för varje frisläppt produkt. Den här allokeringen inkluderar allokering av radrabatter för alla artiklar. Om det här alternativet är inställt på **Nej**, använder systemet det medianpris som har definierats i intäktspriset för varje frisläppt produkt. Om det här alternativet är inställt på **Nej**, men inget medianpris har angetts för de frisläppta produkterna, sker ingen allokering av intäktspriset.
- **Inkludera rubrikrabatter** – ställ in det här alternativet på **Ja** för att fastställa intäktspriset genom att fördela rubrikrabatter mellan produkter. Om det här alternativet är inställt på **Nej** inkluderas inte rubrikrabatten i allokeringen av intäktspris.
- **Inaktivera kontraktsvillkor** – ställ in det här alternativet på **Ja** om du vill att produkter som har en intäkt av typen **stöd för kontraktsartikel** ska kunna frisläppas även om kontraktets start- och slutdatum inte har definierats för dem. Normalt krävs kontraktets start-och slutdatum för artiklar av intäktstypen **stöd för kontraktsartikel**. När kontraktets start- och slutdatum inte har definierats, beräknas detaljerna för intäktsplanen för bokföringen med hjälp av antalet förekomster och fakturadatumet.
- **Bokför fakturakorrigeringar i kundreskontra vid omallokering** – när du omallokerar fakturor som redan har bokförts måste redovisningsposten för den bokförda fakturan korrigeras. Använd det här alternativet för att ange hur korrigeringen ska göras.

    - Ställ in detta alternativ på **Nej** om du vill begränsa bokföringen av korrigeringstransaktionen till redovisningen. När alternativet är inställt på **Nej**, skapas inga ytterligare dokument i kundreskontra för den interna redovisningskorrigeringen. När fakturan betalas använder kvittningsprocessen den gamla redovisningsposten för att bokföra eventuella kassarabatter eller eventuella realiserade vinster eller förluster.
    - Ställ in det här alternativet på **Ja** om du automatiskt vill skapa ett återföringsdokument och en ny faktura för korrigeringstransaktionen i kundreskontra. Eftersom den här korrigeringen är en intern redovisningskorrigering, skickas eller överförs inte de nya dokumenten till kunden. Återföringsdokumentet kvittas mot originalfakturan och den nya korrigerade fakturan betalas av kunden. Observera att alla tre dokumenten visas i rapporter, t. ex. kundutdraget.

[![Inställningsinformation.](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Intäktsplaner

En intäktsplan måste skapas för varje förekomst som intäkten kan periodiseras för. Om din organisation till exempel erbjuder support över perioder på sex månader, 12 månader, 18 månader och 24 månader, måste du skapa en intäktsplan för varje period. Inställningen av intäktsplanen avgör hur intäktspriset fördelas över antalet perioder som du väljer. Det bestämmer också de standarddatum som anges för intäktsplanen som skapas när fakturan bokförs.

Om du identifierar intäkter efter milstolpe, rekommenderar vi att du skapar en intäktsredovisningsplan för antalet milstolpar, oavsett datum för redovisningen. När du har skapat planerna kan du redigera dem så att de återspeglar de förväntade milstolpedatumen. Dessa poster kan spärras tills du meddelas att milstolpen har uppfyllts och intäkterna kan redovisas.

Intäktsplaner skapas på sidan **Intäktsplaner** (**Intäktsredovisning \> Inställningar \> Intäktsplaner**).

[![Intäktsplaner.](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Ange beskrivande värden i fälten **Intäktsplan** och **Beskrivning**. Följande inställningar används för att skapa intäktsplanen när fakturan bokförs.

- **Förekomster** – ange antalet månader eller förekomster för periodisering av intäkt.
- **Spärra automatiskt** – markera den här kryssrutan om alla rader i intäktsplanen ska spärras automatiskt när fakturan bokförs. Spärren måste tas bort manuellt från varje rad i planen innan radens periodiserade intäkt kan redovisas.
- **Automatiska kontraktsvillkor** – markera den här kryssrutan om kontraktets start- och slutdatum ska anges automatiskt. Dessa datum ställs automatiskt in för frisläppta produkter i intäktstypen **stöd för kontraktsartikel**. Kontraktets startdatum ställs automatiskt in på försäljningsorderradens begärda transportdatum och slutdatumet för kontraktet ställs automatiskt in på startdatumet plus antalet månader eller händelser som har definierats i inställningarna för intäktsplanen. Till exempel är produkten på försäljningsorderraden ett års garanti. Standardintäktsplanen **är** 12 M (12 månader) och rutan **Automatiska avtalsvillkor** markeras för denna intäktsplan. Om försäljningsorderraden har ett begärt transportdatum på 16 december 2019 är standarddatumet för kontraktets start den 16 december 2019 och standardslutdatumet för kontraktet är 15 december 2020.
- **Redovisningsvillkor** – redovisningsvillkoret avgör hur intäktspriset fördelas över förekomsterna.

    - **Månadsvis efter dagar** – beloppet fördelas baserat på de faktiska dagarna i varje kalendermånad.
    - **Varje månad** – beloppet fördelas jämnt över det antal månader som har definierats i förekomsterna.
    - **Förekomster** – beloppet fördelas jämnt mellan förekomsterna, men kan inkludera en extra period om du väljer **Faktiskt startdatum** som redovisningsregel.
    - **Räkenskapsperiod efter dagar** – beloppet fördelas baserat på de faktiska dagarna i varje räkenskapsperiod. 

    **Månadsvis efter dagar** och **Räkenskapsperiod efter dagar** ger samma resultat när räkenskapsperioderna följer kalendermånaderna. Det enda undantaget är när redovisningsregeln är inställd som **Månadens/periodens slut** och fälten **Startdatum för kontrakt** och **Slutdatum** är tomma på en försäljningsorderrad.

- **Redovisningsregel** – redovisningsregeln fastställer datumen som anges i intäktsplanen för fakturan.

    - **Faktiskt startdatum** – schemat skapas med hjälp av antingen kontraktets startdatum (för bokföring av artiklar som stöder \[PCS-artiklar\]) eller fakturadatumet (för grundläggande och icke grundläggande artiklar).
    - **Första i månaden/perioden** – datumet på den första planraden är kontraktets startdatum (eller fakturadatum). Alla efterföljande planrader skapas emellertid för den första dagen i månaden eller räkenskapsperioden.
    - **Delning mitt i månaden** – datumet på den första planraden beror på fakturadatumet. Om fakturan bokförs från den första till den femtonde i månaden skapas intäktsplanen med hjälp av den första dagen i månaden. Om fakturan bokförs den sextonde i månaden eller senare skapas intäktsplanen med hjälp av den första dagen i nästa månad.

        **Delning mitt i månaden** kan inte väljas om redovisningsvillkoret har inställningen **Räkenskapsperiod efter dagar**.

    - **Första dagen i nästa månad/period** – det datum som planen börjar är den första dagen i nästa månad eller räkenskapsperiod.
    - **Månadens/periodens slut** – datumet på den första planraden är kontraktets startdatum (eller fakturadatum). Alla efterföljande planrader skapas emellertid för den sista dagen i månaden eller räkenskapsperioden. 

Välj knappen **Information om intäktsplan** om du vill visa de allmänna perioderna och de procentsatser som är bokförda i varje period. Som standard är värdet **Redovisa procentsats** jämt fördelat mellan antalet perioder. Om du anger redovisningsvillkoret **Varje månad** kan redovisningsprocentsatsen ändras. När du ändrar redovisningsprocentsatsen visas ett varningsmeddelande om att totalsumman inte är lika med 100 procent. När du får det meddelandet kan du fortsätta att redigera rader. Den totala procentsatsen måste dock vara lika med 100 innan du stänger sidan.

[![Information om intäktsplan.](./media/revenue-schedule-details-2nd-scrn.png)](./media/revenue-schedule-details-2nd-scrn.png)

## <a name="inventory-setup"></a>Lagerinställning

Du kan identifiera intäkter för frisläppta produkter på försäljningsorder, men inte med försäljningskategorier på försäljningsorder eller med fritextfakturor om det inte finns några artiklar i dokumentet. De val du gör när du ställer in frisläppta produkter bestämmer hur artikelns intäkt känns igen. Urvalet bestämmer t. ex. om intäkts priset fördelas och om intäkten ska periodiseras med hjälp av en intäktsplan.

Inställningen kan börja på snabbfliken **Intäktsredovisning** på sidan **Artikelgrupp** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Artikelgrupp**). Den här sidan innehåller flera inställningsfält. Dessa fält används för att ange standardvärden endast för nya frisläppta produkter som skapas i systemet. När nya produkter skapas, anges de värden du anger här automatiskt för artikelgruppen. Du kan åsidosätta standardvärdena för frisläppta produkter på sidan **Frisläppta produkter** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Frisläppta produkter**). De standardvärden som ställs in för de frisläppta produkterna överförs sedan till försäljningsordern.

## <a name="item-groups-and-released-products"></a>Artikelgrupper och frisläppta produkter

### <a name="define-the-revenue-schedule"></a>Definiera intäktsplanen

Intäkten på försäljningsorderraden periodiseras om en intäktsplan definieras för den frisläppta produkten och används som standard på försäljningsorderraden. Om inställningen ska användas som standard för produkten kan du intäktsplanen på snabbfliken **Intäktsredovisning** på sidan **Artikelgrupp** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Produktgrupp**). Du kan även definiera inställningen för den frisläppta produkten på snabbfliken **Intäktsredovisning** på sidan **Frisläppta produkter** (**Intäktsredovisning \> Inställningar \> Lagerinställningar \> Frisläppta produkter**).

I fältet **Intäktsplan** väljer du den intäktsplan som motsvarar den period som intäkten måste periodiseras för. Intäktsplansdetaljerna anges automatiskt på försäljningsorderraden och intäktsplansdetaljerna skapas när försäljningsorderfakturan bokförs.

### <a name="define-the-revenue-price"></a>Definiera intäktspriset

Artikelgrupper och frisläppta produkter kan ställas in antingen med hjälp av prismetoden median eller rabattallokering. Båda metoderna kräver olika inställningar på sidan **Frisläppta produkter**:

- **Är intäktsfördelning aktiv** – ställ in det här alternativet på **Ja** om du vill inkludera den frisläppta produkten i beräkningen av intäktsallokering. Om det här alternativet är inställt på **Nej**, använder den frisläppta produkten prismetoden om medianpriset har definierats. Om medianpriset inte är definierat används enhetspriset på försäljningsorderraden för att bokföra på intäkt eller periodiserad intäkt.
- **Intäktstyp** – välj den intäktstyp som definierar den frisläppta produkten:

    - **Grundläggande** – artikeln är en primär källa för en organisations intäkter. Det här värdet är standard.
    - **Icke‑grundläggande** – artikeln är inte en primär källa för en organisations intäkter. När inställningarna för medianpris används blir priset "utmejslat" till medianpriset och sedan allokerat. En viktig artikel har till exempel ett fast pris som måste redovisas för intäkt. Finns en rabatt kan den vara utmejslad ur den grundläggande artikelintäkten, men **endast** upp till det fasta prisbeloppet. Resten av rabatten tas från intäkten för artiklar som inte är viktiga. Alternativt kanske rabatten inte utmejslas från den grundläggande artikelintäkten.
    - **Stöd för kontraktsartikel** – artikeln stöder andra element som ingår i försäljningen till kunden. Intäktspriset fördelas på de grundläggande och icke‑grundläggande produkter som ingår i försäljningen. Beroende på inställningarna kanske inte kontorsartiklar kräver att kontraktens start- och slutdatum definieras på försäljningsorderraden.

- **Undantag från utmejsling** – ställ in det här alternativet på **Ja** om du vill att artikelns medianpris inte ska kunna justeras under den minsta procentsats som definieras eller överstiger den maximala procentsatsen. Alla intäktspriser kommer att härledas från intäktspriset för en annan frisläppt produkt som ingår i försäljningsordern. Om det här alternativet är inställt på **Nej** kan artikelns medianpris justeras eller utmejslas. Observera att om du säljer fler än en artikel som har ställts in som medianpris måste minst en frisläppt produkt ställas in där alternativet **Exkludera från utmejsling** är inställt på **Nej**. På så sätt finns det minst en artikel som eventuella skillnader i intäktspriset kan allokeras till.
- **Medianpris** – ställ in detta alternativ på **Ja** om du vill att artikelns intäktspris ska justeras så att det motsvarar medianpriset om det ligger under den minsta tolerans som du anger eller överstiger den högsta toleransen, och att det utmejslade beloppet ska allokeras till rader som har produkter där alternativet **Exkludera från utmejsling** är **inställt på Nej**.

    - **Maximal tolerans** – ange procentsatsen för det medianpris som tillåts.
    - **Minimal tolerans** – ange procentsatsen under det medianpris som tillåts.

När du har konfigurerat inställningarna för den frisläppta produkten måste du manuellt definiera intäktspriset genom att ange det verkliga värdepriset eller medianpriset (om du använder medianprismetoden) på sidan **Intäktspriser** (gå till **Intäktsredovisning \> Inställningar \> Inställningar för lager \> Frisläppta produkter** och sedan till åtgärdsrutan där du på fliken **Sälj** går till gruppen **Intäktsredovisning** och väljer **Intäktspriser**).

[![Intäktspriser.](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

Det intäktspris som definieras manuellt på den här sidan används för att bestämma allokeringen av intäktspris för varje försäljningsorder, baserat på de kriterier som definierats. Varje kriterium matchas mot försäljningsorderraden för att bestämma det intäktspris som ska användas i allokeringsprocessen.

- **Artikelkod** och **artikelrelation** – ett intäktspris kan definieras för en enskild produkt eller en grupp av produkter. Om du väljer **Tabell** i fältet **Artikelkod** ska du markera den frisläppta produkten i fältet **artikelrelation**. Om du väljer **Grupp** i fältet **Artikelkod** ska du markera artikelgruppen fältet **artikelrelation**.
- **Kontokod** och **Konto-/grupp nummer** – ett intäktspris kan definieras för alla kunder, en enskild kund eller en grupp med kunder. Om du väljer **Alla** i fältet **Kontokod** används priset för alla kunder. Om du väljer **Tabell** i fältet **Kontokod** ska du markera kunden i fältet **Konto/gruppnummer**. Om du väljer **Grupp** i fältet **Kontokod** ska du markera gruppen i fältet **Konto/gruppnummer**.
- **Valuta** – du måste ange ett separat intäktspris för varje valuta som du anger en försäljningsorder i. Om du till exempel för närvarande säljer i USD, kanadensiska dollar och euro, måste du definiera ett intäktspris i alla de tre valutorna. Intäktspriset översätts inte från en valuta, till exempel redovisningsvaluta, till andra transaktionsvalutor som du använder.
- **Belopp eller procent av listan** – ange om intäktspriset ska anges som ett belopp eller som en procentandel av listpriset. Om du väljer **Procent av lista** kan användarna ange medianpriset som en procentandel av listpriset i stället för ett belopp. Värdet **Procent av lista** används bara för frisläppta produkter som har ställts in som kontraktsartiklar.
- **Intäktsallokeringspris** – beroende på vilket värde du har valt i fältet **Belopp eller procent av lista** anger du antingen ett belopp eller en procentsats som representerar intäktspriset som används för att fördela intäkten över elementen på försäljningsordern.
- **Från datum** och **Till datum** – ange det datumintervall som intäktspriset är aktivt för. Dessa fält är valfria.

Om alternativet **Aktivera rabattfördelningsmetod** på fliken **Redovisningsparametrar** är inställt på **Ja** och om fältet **Intäktstyp** för den frisläppta produkten är inställt på **Stöd för kontraktsartikel** måste du också ange de artiklar som stöds av den frisläppta produkten. Den här inställningen görs på sidan **Inställningsbas** (gå till **Intäktsredovisning \> Inställningar \> Lagerinställningar \> Frisläppta produkter** och i åtgärdsrutan på fliken **Sälj** i gruppen **Intäktsredovisning** välj **Inställningsbas**).

På sidan **Inställningsbas** lägger du till en post för varje artikelgrupp som artikeln tillhör. När intäktsallokeringen sker fördelas intäktspriset på de grundläggande och icke-viktigaste delarna för kontraktsartikeln.

### <a name="posting-profiles"></a>Bokföringsprofiler

Tre ytterligare bokföringstyper stöder förmågan att periodisera intäkt. Dessa bokföringstyper ställs in på fliken **Försäljningsorder** på sidan **Bokföring** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Bokföring**).

- **Periodiserad intäkt** – ange huvudkontot för intäktspriset som bokförs för periodiserad intäkt (istället för intäkt). Intäktspriset periodiseras om försäljningsorderraden har en intäktsplan.
- **Uppskjuten kostnad för sålda varor** – ange huvudkontot för kostnaden för det sålda beloppet för varor som bokförs till periodiserad kostnad för sålda varor om intäkten också periodiseras.
- **Delvis clearing av fakturaintäkt** – ange huvudkontot för clearingkontot som används antingen när försäljningsordern är delvis fakturerad eller när omallokering sker. Saldot i det här kontot återgår till 0 (noll) när försäljningsorderna är helt fakturerade.

### <a name="bundles"></a>Buntar

Buntade artiklar är unika frisläppta produkter som har ställts in så att de inkluderar komponenter. Inställningen görs med hjälp av funktionen för strukturlistor. När en buntartikel anges på en försäljningsorder används de enskilda komponenterna för att fastställa intäktspriser och intäktsplaner. Utskrivna dokument för kunden, t. ex. försäljningsorder och faktura, reflekterar dock artikelns bunt.

#### <a name="bundle-components"></a>Bunta ihop komponenter

Komponenterna som ingår i bunten måste ställas in på sidan **Frisläppta produkter** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Frisläppta produkter**). Dessa komponenter är frisläppta produkter och måste ställas in på samma sätt som produkter som ingår i en strukturlista. En frisläppt produkt kan till exempel vara en artikel av antingen typen **Artikel** eller **Service**, men den måste tilldelas en artikelmodellgrupp där alternativet **Produkt i lager** är inställt på **Ja**. Mer information finns i inställningsdokumentationen för strukturlisteartiklar.

Komponenterna måste också ställas in för intäktsredovisning, på samma sätt som om de är produkter som kan säljas individuellt på en försäljningsorder. Kontrollera till exempel att korrekt intäktspris har definierats för varje komponent och att prisbasen har ställts in för kontorsartiklar.

#### <a name="bundle-items"></a>Buntade artiklar

När du ställer in en buntad artikel måste du ställa in två fält på sidan **Frisläppta produkter** (**Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Frisläppta produkter**).

- På snabbfliken **Konstruera** i fältet **Produktionstyp** måste artikeln ställas in som en strukturlisteartikel.
- På snabbfliken **Allmänt** i fältet **Bunt** måste artikeln markeras som en buntad artikel.

Komponenterna måste tilldelas den överordnade bunten/strukturlisteartikeln på sidan **BOM-versioner** (gå till **Intäktsredovisning \> Inställningar \> Inställningar för lager och produkt \> Frisläppta artiklar** och i åtgärdsrutan, på fliken **Konstruera**, väljer du sedan **BOM‑versioner** i gruppen för **strukturlistor**). Mer information finns i inställningsdokumentationen för strukturlistor.

[![Frisläppta produkter, planer för strukturlistor.](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Om buntens överordnade artikel och buntkomponenter är inställda på allokering, fördelas buntens intäktspris på komponenterna baserat på deras procentsatser för intäktsbidrag.

## <a name="project-setup"></a>Projektinställningar

Intäktsredovisning kan också användas för försäljningsorder som skapas genom ett Tid‑ och materialprojekt. För försäljningsorder som härstammar från projekt behöver du bara definiera huvudkontona i de projektbokföringsprofiler som används för att bokföra projektfakturor. Huvudkontona definieras på sidan **Inställning av redovisningsbokföring** (**Intäktsredovisning \> Inställningar \> Projektinställningar \> Inställning av redovisningsbokföring**).

- **Periodiserad fakturaintäkt** (under **Intäktskonton**) – ange huvudkontot för intäktspriset som bokförs för periodiserad intäkt (istället för intäkt). Intäktspriset periodiseras om försäljningsorderraden har en intäktsplan.
- **Periodiserad kostnad** (under **Kostnadskonton**) – ange huvudkontot för kostnaden för det sålda beloppet för varor som bokförs till periodiserad kostnad för sålda varor om intäkten också periodiseras.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
