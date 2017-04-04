---
title: "Rapportering av EU-säljlista"
description: "Det här avsnittet innehåller information om rapportering av försäljningslista för Europeiska unionen (EU)."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12811
ms.assetid: 89ffb659-b4a1-450a-9485-d56dd72829bb
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 1270c04262f66a38863a1938fa32195bfe0d2bbd
ms.lasthandoff: 03/31/2017


---

# <a name="eu-sales-list-reporting"></a>EU-säljlistrapportering

Det här avsnittet innehåller information om rapportering av försäljningslista för Europeiska unionen (EU).

<a name="eu-sales-list-reporting"></a>Rapportering av EU-säljlista
-----------------------

En leverantör som utför gemenskapsinterna leveranser av varor eller tjänster till företag som är etablerade inom Europeiska unionen (EU) måste lämna in en försäkran om fläskkött förbrukningsmaterial (lista över försäljning inom EU, eller ESL). I allmänhet ESL måste lämnas till skattemyndigheten senast den sista dagen i månaden efter den kalendermånad som ESL omslag. Leverantören skall ange sin mervärdesskatt (moms) identifikationsnummer på ESL och måste också staten, kund, följande information:

-   Momsregistreringsnummer i EU kund
-   Det totala värdet av gemenskapsinterna leveranser av varor och tjänster som görs till EU kunden under denna period. Leverantören måste också separata allmänna leveranser av varor från triangelhandel förbrukningsmaterial. En triangelhandel transaktion innefattar direkt leverans av varor från leverantörens leverantör till kund när båda parter är registrerade i andra medlemsstater i EU.

Genom att använda ESL, skattemyndigheterna i varje EU-medlemsstat kan kontrollera om mervärdesskatten har betalats för varje gemenskapsinterna transaktioner. Kombinationen av listor och momsdeklarationer låt EU-medlemsstaterna utbyta information om flödet av varor i hela EU.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>Översikt över EU:s försäljning lista rapporteringen
Du kan utföra följande uppgifter för försäljning i EU listan rapportering:

-   Samla information om gemenskapsintern handel. En gemenskapsintern handel transaktion kan vara en faktura, fri text faktura, fakturera projekt, eller säljaren fakturan. En transaktion är identifierade som baseras på det land/den region av motparten. Handeln inom gemenskapen transaktioner av olika slag samlas in i lista över försäljning inom EU tabell, där de är representerade i den gemensamma blankett. Varje post i ESL tabellen representerar en enda transaktion och består av moms-id för en motpart och det sammanlagda värdet av de varor och tjänster som levereras.
-   (Valfritt) Förhandsgranska en **lista över försäljning inom EU** . Du kan förhandsgranska och godkänn **försäljningslista för EU-** rapport för en given period i form av en Microsoft Excel arbetsboken.
-   Generera **försäljning i EU-lista** . **EU:s lista över försäljning** rapport genereras i form av en elektronisk fil av ett särskilt format som är specifika för varje medlemsstat i EU. I allmänhet är en **lista över försäljning inom EU** rapport innehåller grundläggande information om rapportering och värdena för leveranser av varor och tjänster. Informationen grupperas av land och momsnummer för en motpart.
-   Stäng försäljningslista för EU rapportperioden. Efter den **lista över försäljning inom EU** rapport genereras och skickas till myndigheterna, kan du markera de poster i ESL tabell som **stängt**. Dessa transaktioner inte ingår i ytterligare rapporter.

## <a name="prerequisites"></a>Krav
Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategori</th>
<th>Förutsättning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Inställning:</strong> Juridisk person</td>
<td>Den primära adressen för den juridiska personen måste ligga i ett EU-land. På den <strong>juridiska personer</strong> sidan (klicka på <strong>Organisationsadministration</strong>&gt;<strong>organisationer</strong>&gt;<strong>juridiska personer</strong>), Välj en juridisk person. På <strong>Adresser</strong> snabbfliken, skapa en adress, välj land/region och andra adress komponenter, och markera denna adress som <strong>primär</strong>. På <strong>Momsregistrering</strong> snabbfliken i <strong>Momsregistreringsnummer</strong> fältet, ange momsregistreringsnummer för ditt företag.</td>
</tr>
<tr class="even">
<td><strong>Inställning:</strong> Momsbefrielseidentifieringsparametrar</td>
<td>Ställ in Momsparametrar undantagna identifiering på de <strong>parametrar för land/region</strong> sida (klickar du på <strong>moms</strong>&gt;<strong>inställningar</strong>&gt;<strong>moms</strong>&gt;<strong>parametrar för land/region</strong>). För varje land/region där du har motparter, skapa en post på sidan och ange följande information:
<ul>
<li><strong>Land/region</strong> – Välj land/region för att associera till en momsbefriad identifiering.</li>
<li><strong>Moms</strong> – ange momsbefrielseinformation identifieringsnummer (dvs. momsregistreringsnummer prefix) för valt land/region.</li>
<li><strong>Kontrollera momsregistreringsnummer</strong> – Markera den här kryssrutan om du vill validera momsbefrielseinformation identifiering för valt land/region.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Inställning: </strong>Momsbefrielsenummer</td>
<td>Skapa momsregistreringsnummer för ditt motparter på den <strong>momsregistreringsnummer</strong> sida (klickar du på <strong>skattemässiga</strong>&gt;<strong>inställningar</strong>&gt;<strong>moms</strong>&gt;<strong>momsregistreringsnummer</strong>). För varje momsregistreringsnummer, skapa en post på sidan och ange följande information:
<ul>
<li><strong>Land/region – </strong>Välj land/region för skatt registrering av motparten.</li>
<li><strong>Momsregistreringsnummer</strong> – Ange momsregistreringsnummer av motparten.</li>
<li><strong>Företagsnamn</strong> – (valfritt) Ange namnet på motparten.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Inställning: </strong>Momsregistrering av motparter</td>
<td>Registrera skatteinformation för din motparter antingen konfigurera den <strong>alla kunder</strong> sida (klickar du på <strong>försäljnings- och</strong>&gt;<strong>kunder</strong>&gt;<strong>alla kunder</strong>, välja en kundpost och klicka sedan på <strong>alternativ</strong>&gt;<strong>ändra vyn</strong>&gt;<strong>detaljvy</strong>) eller <strong>leverantörer</strong> sida (klickar du på <strong>anskaffning och källa</strong>&gt;<strong>leverantörer</strong>&gt;<strong>leverantörer</strong>, markerar en leverantörspost och klickar <strong>alternativ</strong>&gt;<strong>ändra</strong>&gt;<strong>detaljvy</strong>). På <strong>Faktura och leverans</strong> snabbfliken, i <strong>momsregistreringsnummer</strong> fältet, välj momsregistreringsnummer.</td>
</tr>
<tr class="odd">
<td><strong>Inställning: </strong>Moms</td>
<td>Ställa in momskoder som ska inkluderas i den <strong>listan över försäljning inom EU</strong> rapport om den <strong>momskoder</strong> sida (klickar du på <strong>moms</strong>&gt;<strong>indirekta skatter</strong>&gt;<strong>moms</strong>&gt;<strong>momskoder</strong>). På <strong>Rapportinställningar</strong> snabbfliken, för varje momskod som ska inkluderas i rapporten, avmarkera <strong>Exkluderad </strong>rutan. Ställ in Momsparametrar för artiklar på den <strong>artikel momsgrupper</strong> sida (klickar du på <strong>moms</strong>&gt;<strong>indirekta skatter</strong>&gt;<strong>moms</strong>&gt;<strong>artikel momsgrupper</strong>). För varje artikelmomsgrupp välj ett värde i <strong>Rapporteringstyp</strong> fältet. Det värde som du väljer bestämmer ESL beloppskolumnen som beloppet kommer att ingå i.
<ul>
<li><strong>Tom</strong> – Radbelopp ingår i <strong>Ej tilldelat värde</strong> kolumnen.</li>
<li><strong>Objekt</strong> – Radbelopp ingår i <strong>Artikelvärde</strong> kolumnen.</li>
<li><strong>Tjänst</strong> – Radbelopp ingår i <strong>Tjänstvärde</strong> kolumnen.</li>
<li><strong>Investering</strong> – Radbelopp ingår i <strong>Investeringsvärde</strong> kolumnen. Den här kolumnen är bara relevant för Belgien.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Inställning:</strong> ESL rapporteringskonfigurationer</td>
<td>Importera eller skapa elektronisk rapportering konfigurationer för ESL. För information om hur du skapar och bevarar elektronisk rapportering konfigurationer, se Elektronisk rapportering dokumentation.</td>
</tr>
<tr class="odd">
<td><strong>Inställning: </strong>Allmänna parametrar</td>
<td>Ställ in ESL rapporteras parametrar i den <strong>Utländska handelsparametrar</strong> sida (klickar du på <strong>moms</strong>&gt;<strong>inställningar</strong>&gt;<strong>Utlandshandel</strong>&gt;<strong>Utländska handelsparametrar</strong>). Ange följande parametrar:
<ul>
<li><strong>Lista över försäljning inom EU</strong> flik:
<ul>
<li><strong>Rapporten kassarabatt</strong> – Markera den här kryssrutan om kassarabatt ska tas med i värde när en transaktion ingår i ESL.</li>
<li><strong>Överför inköp</strong> – Markera den här kryssrutan om du vill inkludera inköp på ESL.</li>
<li><strong>Filformatet kartläggning</strong> – välj den elektroniska rapporteringen format att använda när en elektronisk fil genereras för ESL.</li>
<li><strong>Rapportformat kartläggning</strong> – välj den elektroniska rapporteringen format att använda när en förhandsgranskning genereras rapporten för ESL.</li>
<li><strong>Avrundning</strong> – ange en riktig nummer för avrundning. ESL belopp avrundas till multiplar av detta nummer.</li>
<li><strong>Avrundning metod</strong> – Välj avrundning metod att använda när ESL Beloppen är avrundade (<strong>Normal</strong>, <strong>nedåt</strong>eller <strong>avrundning</strong>).</li>
<li><strong>Använd lägsta värde</strong> – Markera den här kryssrutan om du vill att belopp som är mindre än den <strong>avrundning regel</strong> nummer ska avrundas uppåt till <strong>avrundning regel</strong> nummer.</li>
<li><strong>Antal decimaler</strong> – ange antalet decimaler som du vill visa i ESL belopp (både i elektroniska filer och på <strong>ESL förhandsgranska</strong> rapport).</li>
</ul></li>
<li><strong>Land/regionparametrar</strong> fliken: Identifiera EU:s medlemsstater. För varje medlemsstat i EU, skapa en post på sidan och ange följande information:
<ul>
<li><strong>Land/region</strong> – Välj land/region.</li>
<li><strong>Land/region ange</strong> – Om <strong>land/region</strong> värde är det land/den region där företaget är registrerat i, välj <strong>inhemska</strong>. Om <strong>land/region</strong> är en EU-medlemsstat än det land/den region där företaget är registrerat i, välj <strong>EU</strong>. Om <strong>land/region</strong> värde är inte en EU-medlemsstat, välj <strong>tredje land/region</strong>.</li>
</ul></li>
<li><strong>Nummersekvenser</strong> fliken: På raden där <strong>referensvärdet</strong> är <strong>EU-försäljningslista</strong>, välj en nummersekvenskod.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Relaterade transaktioner</strong></td>
<td><ul>
<li>Registrera en försäljning till en kund i en annan EU-medlemsstat.</li>
<li>Registrera fri text faktura till en kund i en annan EU-medlemsstat.</li>
<li>Registrera ett projekt faktura till en kund i en annan EU-medlemsstat.</li>
<li>Registrera en faktura från en leverantör i en annan EU-medlemsstat.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Arbeta med ESL
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Samla information om gemenskapsintern handel

Transaktioner av följande typer kan anses handeln transaktioner:

-   Försäljningsfakturor
-   Fritextfakturor
-   Projektfakturor
-   Leverantörsfakturor

En transaktion anses en gemenskapsintern handel transaktion om leveransadressen för transaktionen är i en medlemsstat i EU. För dessa länder/regioner, en post ska finnas på **land/region fliken Parametrar** i **utrikeshandeln parametrar sidan**och **land/region typ**värdet sättas till**EU**. Handeln inom gemenskapen transaktioner markeras i **listan** . Med det här fältet kan du även separat gemenskapsintern handel från triangelhandel transaktioner. Kan du samla information om handel gemenskapsinterna transaktioner på den **listan över försäljning inom EU** sida (klickar du på **moms**&gt;**deklarationer**&gt;**Utlandshandel**&gt;**listan över försäljning inom EU**) med hjälp av den **överför** funktion. Denna funktion låter dig inkludera transaktioner som har mängder av olika typer av rapportering (dvs. objekt eller tjänster), enligt punkt moms grupper som är angivna på transaktionsraderna. Du kan även tillämpa andra filter för att definiera transaktioner som ska inkluderas. **Överföringsfunktionen** skapar en post på **lista över försäljning inom EU** sida för varje handeln inom gemenskapen transaktion som ingår och anger en motpart kontonummer, land/region, ett momsregistreringsnummer, ett fakturanummer, datum, och den totala summan av rader per typ av rapportering. Dessutom kopierar **listan kodvärdet** från transaktionen. Du kan manuellt ändra listan for en transaktion på **lista över försäljning inom EU** . **Överföringsfunktionen** skapar poster där **rapportering status** värdet **ingår**. Du kan verifiera den information som samlas in på **EU-lista över försäljning på **sidan genom att använda **funktionen godkänn** .

### <a name="generating-the-eu-sales-list-report"></a>Generera försäljning i EU listan rapport

Du kan generera en **lista över försäljning inom EU** rapport genom att använda **funktionen Produktionsrapportering **på **lista över försäljning inom EU **. Funktionen kan du välja en rapporteringsperiod och tillämpa filter för att definiera ESL poster ska ingå. Du kan dessutom ange andra parametrar som är specifika för varje land/region. Du kan även välja att förhandsgranska rapporten, en elektronisk fil, eller båda. **Rapportering **funktion använder rapporten och filformatet inställningar som anges på **utrikeshandeln parametrar sidan **. I allmänhet är en **lista över försäljning inom EU** rapport består av separata rader som visar de totala belopp för leveranser per motpart land/region, momsregistreringsnummer och rapportering (triangelhandeln transaktioner ingår). När du genererar en **lista över försäljning inom EU** rapport för en viss period, kan du markera ESL poster som ingår i rapporten genom att **rapporteringen statusvärde**som**rapporteras**. För att ställa denna status, använd **markera som rapporteras **på **lista över försäljning inom EU **sidan.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Stängning av försäljningslista för EU rapporteringsperioden

När du har slutfört rapporteringen för en specifik period (exempelvis när skattemyndigheten har godtagit **EU-försäljningslista** rapporten), kan du markera ESL poster som ingår i rapporten för perioden genom inställning av **rapporteringsstatusvärdet** som **stängd**. För att ställa denna status, använd **markera som avslutad **funktion på **EU-lista över försäljning **sida. Om du återställer periodslutet kan du markera ESL poster genom att ställa in **rapporteringsstatus**till **Inkluderad**. Dessa poster kan sedan ingå i en **lista över försäljning inom EU** rapport igen. För att ställa denna status, använd **markera som** **ingår **i **EU:s lista över försäljning** sida.


