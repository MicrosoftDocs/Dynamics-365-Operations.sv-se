---
title: Periodiseringstransaktioner i Prenumerationsfakturering
description: Detta ämne beskriver de olika transaktioner som kan användas i periodiseringstransaktioner som en del av intäkts- och utgiftsperiodiseringar inom prenumerationsfakturering.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f66c538afc732caf3faed3cfea6c695ff7f16273
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2022
ms.locfileid: "8558117"
---
# <a name="deferral-default-transactions"></a>Standard-periodiseringstransaktioner

I detta ämne beskrivs de transaktioner som tillåter intäkts- och utgiftsperiodiseringar. Periodisringsplaner baseras alltid på samt beror på ett underliggande ursprungligt dokument eller en ursprunglig faktureringsplan. Periodisringsplaner skapas baserat på standardvärden och kan inte anges eller skapas separat.

## <a name="sales-order-transaction-deferral"></a>Transaktionsperiodisering för försäljningsorder

Använd sidan **Periodiseringar** eller **Skapa kreditfaktura** du vill ange eller redigera periodiseringsparametrarna för en försäljningsorderrad.

> [!NOTE]
> När en försäljningsorder skapas från en faktureringsplan är alla värden på sidorna **Periodiseringar** eller **Skapa kreditfaktura** skrivskyddade, och periodiseringsparametrarna kan inte redigeras. Om du vill redigera värdena använder du sidan **Ändra tidsplan**.

### <a name="edit-deferral-options"></a>Redigera periodiseringsalternativ

Om du vill redigera avvisningsalternativen för en rad följer du dessa steg.

1. Skapa en försäljningsordertransaktion.
2. Markera raden och välj sedan **Periodiseringar**.
3. På sidan **Transaktionsperiodisering** måste alternativet **Periodisering** ställas in som **Ja**. Redigera övriga fält efter behov.
4. Välj **Förhandsversion** för att förhandsvisa periodisringsplanen.
5. Om du har gjort ändringar i transaktionsperiodiseringen väljer du **OK** och går tillbaka till transaktionssidan.
6. Genomför och bokför transaktionen.

När transaktionen har bokförts öppnar du sidan **Alla periodisringsplaner** för att visa periodisringsplanen.

### <a name="create-a-credit-note"></a>Skapa en kreditfaktura

Gör så här om du vill skapa en kreditfaktura.

1. Skapa en försäljningsordertransaktion.
2. I avsnittet **Försäljningsorderrader** väljer du den artikel som du vill skapa en kreditfaktura för.
3. Välj **Försäljningsorderrad** \> **Ny** och välj sedan **Kreditfaktura**.
4. Välj **Periodiseringar**.
5. På sidan **Transaktionsperiodisering för försäljningsorder** anmger du alternativet för **Justera befintlig tidsplan** som **Ja** för artikeln.
6. I fältet **Justerad tidsplan** väljer du den periodiseringstidsplan som du vill tillämpa kreditfakturan på.
7. Uppdatera fälten **Omberäkna datum** och **Slutdatum** efter behov.
8. Välj **OK**.
9. Slutför bokföringen av försäljningsordertransaktionen.

### <a name="purchase-orders-and-purchase-invoices"></a>Inköpsorder och inköpsfakturor

Om du vill använda periodiseringsfunktionen för en inköpsorder måste du först generera fakturan. Använd sedan sidan **Pågående leverantörsfakturor** för att redigera eller lägga till periodiseringsartiklar. Du kan inte redigera eller lägga till periodiseringar direkt i en inköpsorder.

1. Använd sidan **Pågående leverantörsfakturor** för att ange en leverantörsfaktura.

    När du anger en rad ställs periodiseringen in automatiskt för den artikel eller anskaffningskategori som du väljer. Denna periodisering baseras på periodiseringsinställningarna för sidan **Standardinställningar för periodisering**. Periodiseringarna kan redigeras eller läggas till på distributionsnivå.

3. På inköpsraden väljer du **Ekonomi \> Distribuera belopp**.
4. För varje distributionsbelopp väljer du **Periodiseringar**. När fakturan bokförs skapas en periodiseringsplan för varje distribution som en periodisering ställs in för.

### <a name="tax"></a>Moms

I vissa fall kan momsbeloppet vara helt eller delvis icke-återbetalningsbart. Om momsbeloppet på en rad som kan periodiseras innehåller ett belopp som inte kan återställas, inkluderas det skattebelopp som inte kan skrivas av i det periodiseringsbara planbeloppet när fakturan bokförs.

### <a name="variance"></a>Avvikelse

Om beloppet på leverantörsfakturaraden är ett annat än beloppet på inköpsorderraden, skapas avvikelsefördelningar. Om raden periodiseras ställs redovisningskontot för dessa fördelningar in på periodiseringskontot, och beloppen inkluderas i det avskrivbara tidsplanerade beloppet när fakturan bokförs. Dessa fördelningar kallas **prisavvikelse** samt **kostnadsavvikelse**.

### <a name="general-journals-and-invoice-journals"></a>Allmänna journaler och fakturajournaler

Använd sidan **Periodiseringar** för att ange periodiseringsparametrar för en journalverifikationsrad. Du kan också förhandsgranska periodiseringstidsplanen för linjära periodiseringar. När du anger en rad ställs periodiseringen in automatiskt utifrån inställningarna för periodiseringskonton på sidan **Periodiseringsstandard**. Du kan ändra periodiseringsalternativen för respektive rad manuellt. När journalverifikationen bokförs skapas periodiseringstidsplanen.

#### <a name="post-and-transfer"></a>Bokföra och överföra

Om du vill bokföra journalverifikationen använder du kommandot **Bokför och överför**. Periodiseringsalternativen följer den rad som verifikationen gäller för. För verifikationer som inte har några fel skapas en tidsplan för periodiseringar. För en verifikation som har ett fel och som överförs, överförs även eventuella periodiseringsalternativ.

#### <a name="tax"></a>Moms

I vissa fall kan momsbeloppet vara helt eller delvis icke-återbetalningsbart. Om momsbeloppet på en rad som kan periodiseras innehåller ett belopp som inte kan återställas, inkluderas det skattebelopp som inte kan skrivas av i det periodiseringsbara planbeloppet när fakturan bokförs.

## <a name="free-text-invoice-transaction-deferral"></a>Transaktionsperiodisering för fritextfaktura

Använd sidan **Periodiseringar** för att ange periodiseringsparametrar för en raddistribution för fritextfaktura. När du anger en distribution ställs periodiseringen in automatiskt utifrån inställningarna för periodisering på sidan **Periodiseringsstandard**.

## <a name="fields"></a>Fält

Sidan **Transaktionsperiodisering** innehåller följande fält.

| Fält | Beskrivning |
|-------|-------------|
| Uppskjutet | <p>Ange om raden är en periodisering:</p><ul><li>**Ja** – Raden är en periodisering.</li><li>**Nej** – Raden är inte en periodisering.</li></ul><p>När detta alternativ är inställt på **Ja** är alternativet **Justera befintligt schema** inte tillgänglig. För artiklar och avgifter som redan har ställts in som periodiserade anges detta alternativ som **Ja**. För artiklar och avgifter som inte har ställts in som periodiserade som standard anges detta alternativ som **Ja**.</p> |
| Justera befintligt schema | <p>Ange om raden är en justering av en befintlig periodiseringstidsplan:</p><ul><li>**Ja** – Den nya försäljningsraden är en justering av en befintlig periodiseringstidsplan. I det här fallet kan du välja en periodiseringstidsplan i fältet **Justerad tidsplan**.</li><li>**Nej** – Den nya försäljningsraden är inte en justering av en befintlig periodiseringstidsplan.</li></ul><p>När detta alternativ är inställt på **Ja** är alternativet **Periodiserad** inte tillgänglig.</p> |
| Justerat schema | <p>Välj den periodiseringstidsplan som raden justerar. Alla värden på sidan uppdateras sedan med värdena i det ursprungliga periodiseringsschemat. Dessa värden kan inte redigeras.</p><p>Detta fält är endast tillgängligt när alternativet för **Justera befintlig tidsplan** är inställt på **Ja**.</p> |
| Omberäkningsdatum | <p>Ange startdatumet för den period som du vill omberäkna det resterande beloppet från. Standarddatumet är datumet för nästa icke-beaktade period.</p><p>Detta fält är endast tillgängligt när alternativet för **Justera befintlig tidsplan** är inställt på **Ja**.</p> |
| Slutdatum | <p>Beroende på typen av periodisering kan slutdatumet komma att uppdateras/inte uppdateras:</p><ul><li>Ange det nya slutdatumet för tidsplanen för en linjär periodisering. Det befintliga slutdatumet för periodiseringstidsplanen är standardvärdet.</li><li>Ange slutdatum för kredithändelseraden för en händelsebaserad periodisering. Detta datum får vara tomt.</li></ul><p>Detta fält är endast tillgängligt när alternativet för **Justera befintlig tidsplan** är inställt på **Ja**.</p> |
| Fakturaschemanummer | <p>Faktureringens tidsplansnummer.</p><p>Detta fält är bara tillgängligt för återkommande faktureringstidsplaner för kontrakt.</p> |
| Justeringsmetod för periodisering | <p>Metoden för uppskjuten justering. Värdet matchar värdet på sidan **Bearbetning av massuppsägning** för den återkommande faktureringstidsplanen för kontrakt.</p><p>Detta fält är bara tillgängligt för återkommande faktureringstidsplaner för kontrakt.</p> |
| **Konton – Intäkt** | |
| Periodiseringskonto | <p>Periodiseringskontot, som är bokföringskontot som visas på sidan **Försäljningsorder**.</p><p>Om raden inte periodiseras är detta fält tomt. I detta fall är bokföringskontot standardintäktskontot.</p> |
| Redovisningskonto | <p>Ange det konto som används när en periodisering beaktas. Detta konto måste vara ett annat än periodiseringskontot.</p><p>När alternativet **Periodiserad** ställs in på **Ja** kopieras de dimensionsvärden som används i periodiseringskontot till redovisningskontot. Om dimensionen i periodiseringskontot inte finns för redovisningskontot ignoreras den.</p> |
| Konto för första redovisningstillfälle | <p>Välj konto för den ursprungliga intäktsredovisningen. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är endast tillgängligt om fältet **Periodiseringsmetod** är inställt på **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust**.</p> |
| Motkonto för redovisning | <p>Välj konto för motbokning av intäktsredovisning. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är endast tillgängligt om fältet **Periodiseringsmetod** är inställt på **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust**.</p> |
| **Konton – Rabatt** | Detta avsnitt visas bara för periodiserade artiklar. Det är dolt för periodiserade avgifter. |
| Periodiseringskonto | <p>Ange kontonummer för rabattperiodisering. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är bara tillgängligt när fältet **Alternativ för rabattperiodisering** har angetts till **Separat tidsplan för rabatt** på sidan **Periodiseringsparametrar för vinst och förlust** och en rabatt tillämpas på raden.</p> |
| Redovisningskonto | <p>Ange kontonummer för rabattredovisning. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är bara tillgängligt när fältet **Alternativ för rabattperiodisering** har angetts till **Separat tidsplan för rabatt** på sidan **Periodiseringsparametrar för vinst och förlust** och en rabatt tillämpas på raden.</p> |
| Konto för första redovisningstillfälle | <p>Välj konto för den ursprungliga rabattredovisningen. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är bara tillgängligt när fältet **Bokföringsmetod för periodisering** har angetts till **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust** och en rabatt tillämpas på raden.</p> |
| Motkonto för redovisning | <p>Välj konto för motbokning av intäktsredovisning. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är bara tillgängligt när fältet **Bokföringsmetod för periodisering** har angetts till **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust** och en rabatt tillämpas på raden.</p> |
| **Konton – Förbrukning** | Detta avsnitt visas bara för periodiserade artiklar. Det är dolt för periodiserade avgifter. |
| Periodiseringskonto | <p>Ange kontonummer för förbrukningsperiodisering.</p><p>För standardprodukter skapas två periodiseringsscheman:</p><ul><li>**Standardförsäljning** – En intäktsplan med ett kreditsaldo. I det här fallet väljer du periodiseringskontot för förbrukning.</li><li>**Förbrukning** – En utgiftsplan för förbrukning (kostnader för sålda varor \[COGS\]) som har ett debetsaldo. I det här fallet väljer du redovisningskontot för förbrukning.</li></ul><p>När fakturan bokförs, bokförs förbrukningsbeloppet på det angivna periodiseringskontot för förbrukning. Dessa fält är inte tillgängliga för serviceartiklar.</p> |
| Redovisningskonto | Ange kontonummer för förbrukningsredovisning. |
| Konto för första redovisningstillfälle | <p>Ange kontot för det ursprungliga beloppet för förbrukningsredovisning. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är endast tillgängligt om fältet **Periodiseringsmetod** är inställt på **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust**.</p> |
| Motkonto för redovisning | <p>Ange kontot för motbokningsbeloppet för förbrukningsredovisning. Standardvärdet kommer från sidan **Standardinställningar för periodisering**.</p><p>Detta fält är endast tillgängligt om fältet **Periodiseringsmetod** är inställt på **Vinst och förlust** på sidan **Periodiseringsparametrar för vinst och förlust**.</p> |
| **Tidsplan** | |
| Typ av tidsplan | <p>Välj typ av periodiseringstidsplan: **Linjär** (standard) eller **Händelsebaserad**.</p><p>Alternativen som visas på sidan baseras på typen av periodiseringstidsplan som du väljer.</p><p>Om standardmallen ställs in på sidan **Standardinställningar för periodisering** för transaktionsraden, baseras typen av periodiseringstidsplan på den typ av mall som väljs.</p> |
| **Tidsplan – linjär** | |
| Konsolidera föregående perioder | <p>Ange om du vill konsolidera rader för periodiseringstidsplaner för tidigare perioder:</p><ul><li>**Ja** – Konsolidera raderna för periodiseringstidsplan för tidigare perioder.</li><li>**Nej** – Konsolidera inte rader för periodiseringstidsplan för tidigare perioder.</li></ul><p>Standardvärdet kommer från sidan **Periodiseringsparametrar för intäkt och utgift**.</p> |
| Lika per period | <p>Ange om antalet dagar i respektive period är lika med eller varierande efter period:</p><ul><li>**Ja** – Varje period har samma antal dagar.</li><li>**Nej** – Perioder har inte samma antal dagar.</li></ul><p>När det här alternativet ställs in på **Nej** beaktas antalet dagar i en period när beloppet i respektive period beräknas för ett periodiseringsschema.</p><p>Standardvärdet kommer från sidan **Periodiseringsparametrar för intäkt och utgift**.</p> |
| Schema från mall | <p>Ange huruvida periodiseringsschemat skapas baserat på en mall eller ett slutdatum:</p><ul><li>**Ja** – Periodiseringstidsplanen skapas utifrån en mall.</li><li>**Nej** – Periodiseringstidsplanen skapas utifrån ett slutdatum.</li></ul> |
| Mall | Välj periodiseringsmall. |
| Åsidosätt startdatum | <p>Ange om du vill åsidosätta startdatumet:</p><ul><li>**Ja** – Åsidosätt startdatumet med det datum som du anger i fältet **Startdatum**.</li><li>**Nej** – Startdatumet är den regel för **Förvalt standarddatum för periodisering** som används för det fakturadatum som anges på sidan **Bokföring av faktura**. Denna regel kan ställas in på sidan **Periodiseringsparametrar för intäkt och utgift**.</li></ul> |
| Startdatum för periodisering | Ange startdatum för periodiseringen. Standardvärdet är transaktionsdatumet. |
| Periodiseringsslutdatum | <p>Slutdatum för periodiseringen.</p><p>Detta datum beräknas automatiskt baserat på periodiseringsmallen. Om ingen mall har valts måste du ange datumet manuellt.</p> |
| **Tidsplan – Händelsebaserad** | |
| Mall | <p>Välj den händelsebaserade mallen. Detta fält är valfritt.</p><p>Om du väljer en mall skriver värdena från mallen över alla händelsebaserade data och händelserader.</p> |
| Allokeringstyp | <p>Välj allokeringstyp för händelseraderna:</p><ul><li>**Variabla belopp** – Ett specifikt allokeringsbelopp anges för varje rad.</li><li>**Lika stora belopp** – Beloppet fördelas jämnt mellan varje rad.</li><li>**Procent** – Ett belopp allokeras baserat på den procentsats som anges för respektive rad.</li><li>**Slutförandeprocent** – Ett ackumulerat slutförandevärde angess för respektive rad.</li><p>**Variabel kvantitet** – En specifik kvantitet anges för respektive rad som anges.</li></ul><p>**Observera:** Om du vill välja **Slutförandeprocent** måste datumen vara i stigande ordning.</p> |
| **Skapa separata händelser per enhet** | |
| Beskrivning | <p>Ange om du vill separera händelser efter enhet:</p><ul><li>**Ja** – Separera händelseraderna så att det finns en rad per kvantitet.<p>Det finns till exempel tre händelserader, och fakturan har en kvantitet på fyra. I detta fall finns det 12 rader i det resulterande periodiseringsschemat.</p></li><li>**Nej** – Separera inte händelseraderna.</li></ul> |
| Utgångskonto | <p>Välj det konto som används för redovisade utgångna rader. Du kan välja kontot efter att periodiseringstidsplanen har skapats.</p><p>Om ett utgångsdatum anges för en händelse flyttas igenkänningsbeloppet till utgångskontot under igenkänningsprocessen istället för till redovisningskontot.</p> |
| **Tidsplan - Händelsebaserade rader** | |
| Beskrivning | En beskrivning av händelsen. |
| Periodiseringsslutdatum | <p>Välj händelsens slutdatum.</p><p>**Obs!** Om du väljer ett slutdatum avmarkeras fältet **Utgångsdatum**. Du kan inte använda både ett slutdatum och ett utgångsdatum.</p> |
| Utgångsdatum | <p>Välj händelsens utgångsdatum.</p><p>**Obs!** Om du väljer ett slutdatum avmarkeras fältet **Utgångsdatum**. Du kan inte använda både ett slutdatum och ett utgångsdatum.</p> |
| Antal | <p>Ange kvantiteten som ska allokeras. Standardvärdet för alla rader är **0** (noll). Om du uppdaterar kvantiteten måste den totala kvantiteten på alla rader vara lika med eller mindre än den kvantitet som har angetts för radartikeln på försäljningsordern.</p><p>Detta fält är endast tillgängligt om fältet **Allokeringstyp** anges till **Variabel kvantitet**.</p><p>Om kvantiteten för radartikeln på försäljningsordern ändras så att den är mindre än den ursprungliga kvantiteten och fakturan skapas, skapas färre händelsebaserade rader. Den totala allokerade kvantiteten överskrider inte kvantiteten som anges på den ursprungliga försäljningsordern eller det ursprungliga faktureringsschemat.</p> |
| Allokeringsprocent | <p>Ange procentsatsen för allokering. Om fältet **Allokeringstyp** är inställt på **Procentsats** eller **Slutförandeprocent**, kan du manuellt ange en procentsats. I annat fall beräknas det automatiskt.</p><p>Om fältet **Allokeringstyp** anges som **Procentsats** måste summan av procentsatserna uppgå till 100.</p> |
| Belopp | <p>Ange allokeringsbeloppet. Om fältet **Allokeringstyp** är inställt på **Variabla belopp** eller **Slutförandeprocent** kan du ange ett belopp manuellt.</p><p>Om fältet **Allokeringstyp** ställs in på **Slutförandeprocent** och du anger ett belopp här, beräknas värdet för fältet **Slutförandeprocent** automatiskt.</p><p>På grund av avrundning kanske det beräknade beloppet inte exakt matchar det som anges manuellt. Om du behöver ett exakt belopp ställer du in fältet **Allokeringstyp** på **Variabla belopp**.</p> |
| Slutförandeprocent | <p>Ange slutförandeprocenten. Värdet måste vara mellan 0 (noll) och 100.</p><p>Detta fält är endast tillgängligt om fältet **Allokeringstyp** anges som **Slutförandeprocent**.</p> |
| Slutförandebelopp | <p>Den beräknade summan för alla rader i periodiseringstidsplanen.</p><p>Om fältet **Allokeringstyp** är inställt på **Slutförandeprocent** kan du ange ett belopp manuellt. I det här fallet beräknas värdet i fältet **Slutförandeprocent** baserat på beloppet du anger.</p><p>På grund av avrundning kanske det beräknade beloppet inte exakt matchar det som anges manuellt.</p><p>Detta fält är endast tillgängligt om fältet **Allokeringstyp** anges som **Slutförandeprocent**.</p> |
| Redovisa vid bokföring | <p>Ange om raden redovisas automatiskt så snart transaktionen bokförs:</p><ul><li>**Markerad** – Raden redovisas så fort transaktionen bokförs.</li><li>**Avmarkerad** – Raden redovisas inte så fort transaktionen bokförs.</li></ul> |
| Redovisningskonto | <p>Ange igenkänningskontot för händelsen, om kontot skiljer sig från det konto som används i hela periodiseringstidsplanen.</p><p>Du kan använda detta fält tillsammans med alternativet **Redovisa vid bokföring**.</p> |
