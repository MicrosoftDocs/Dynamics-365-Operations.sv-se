---
title: Periodiska uppgifter i Återkommande kontraktsfakturering
description: Det här ämnet beskriver de periodiska uppgifter som är tillgängliga vid Återkommande kontraktsfakturering.
author: JodiChristiansen
ms.date: 04/29/2022
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
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786978"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Periodiska uppgifter i Återkommande kontraktsfakturering

Det här ämnet beskriver de periodiska uppgifter som är tillgängliga vid Återkommande kontraktsfakturering.

## <a name="generate-invoice"></a>Generera faktura

Använd sidan **Generera faktura** för att skapa månatliga återkommande massfakturor från informationen som du ställer in på sidan **Alla faktureringsscheman** och **Visa faktureringsdetaljer**. När en faktura skapas uppdateras artikelbeskrivningen för försäljningsorderbearbetningsraden med artikelbeskrivningen och faktureringsstart- och slutdatum för schemaraden som faktureras.

## <a name="generate-invoice-batch-processing"></a>Generera batchbearbetning av faktura

Använd sidan **Generera batchbearbetning av faktura** för att skapa återkommande fakturor genom en återkommande batchprocess. Parametrarna som är tillgängliga är desamma som parametrarna på sidan **Generera faktura** men de kan sparas i en batchprocess som kan köras flera gånger.

## <a name="price-update"></a>Prisuppdatering

Använd verktyget Prisuppdatering för att uppdatera priserna för flera artiklar på flera faktureringsscheman i en och samma åtgärd. Priserna kan uppdateras utifrån antingen en angiven procentsats eller ett angivet belopp. I listan med rader visas bara de aktuella enhetspriserna för artiklarna. Det visar inte priserna efter prisuppdateringen.

Lägg märke till följande punkter om uppdateringsverktyget för pris:

- Om försäljningsordern för ett visst år redan har skapats (det vill säga om artiklarna har fakturerats), påverkas inte priset för radartiklarna.
- Verktyget Prisuppdatering kan användas för radartiklar som har status **Aktiv** eller **Spärrad**. För föremål som är spärrade måste alternativet **Justera tidsplan** måste ha angetts till **Nej** när spärren placerades.
- Prisuppdateringsverktyget kan inte användas för radartiklar som är förbrukningsartiklar, som använder eskalering, milstolpefakturering eller intäktsdelning.

### <a name="price-update-example"></a>Exempel på prisuppdatering

Ett faktureringsschema skapas och en objekt som specificeras läggs till. Enhetspriset är 750 $. Det första året av artikeln betalas den 15 december 2021. Faktureringsschemat skapas för perioden 1 januari till 31 december 2022.

Vid förnyelsetid skapar processen **Generera faktura** skapar försäljningsordern för år 2022. När verktyget Prisuppdatering har körts uppdateras priset från 750 $ till 800 $.

Försäljningsordern och faktureringsplanen för 2022 påverkas inte och enhetspriset kvarstår 750 $ eftersom faktureringsschemat för 2022 redan har fakturerats. Faktureringsschemaraden och raddetaljerna för 2023 uppdateras till 800 $ eftersom faktureringsplanen för 2023 ännu inte har fakturerats.

### <a name="update-prices--flat-pricing-method"></a>Uppdatera priser – Fast prissättningsmetod

När du uppdaterar priserna för artiklar som använder fastprissättningsmetod, kan du ange en procentsats eller ett belopp för att öka priset.

Följ de här stegen om du vill köra verktyget Prisuppdatering för artiklar där fastprissättningsmetoden används.

1. På verktygssidan **Prisuppdatering**, välj prissättningsmetoden **Fast**.
2. I fältet **Ökningsmetod**, välj den ökningsmetod som används för att uppdatera priset på varorna.
3. Beroende på den ökningsmetod du har valt anger du procentandelen i fältet **Procent** eller beloppet i fältet **Belopp**.
4. På snabbfliken **Poster som ska ingå**, använd knappen **Filter** för att lägga datafilter.
5. Välj **Visa förhandsgranskning** om du vill visa postintervall.
6. Om du inte vill bearbeta några av raderna, markera dem och välj sedan **Ta bort**.
7. Välj **OK**.

### <a name="update-prices--standard-pricing-method"></a>Uppdatera priser – Standard prissättningsmetod

Om priset för en artikel har ändrats i artikelposten kan det uppdateras för alla faktureringsschemarader om artikeln använder standardprissättningsmetoden.

1. På verktygssidan **Prisuppdatering**, välj prissättningsmetoden **Standard**.
2. På snabbfliken **Poster som ska ingå**, använd knappen **Filter** för att lägga datafilter.
3. Välj **Visa förhandsgranskning** om du vill visa postintervall.
4. Om du inte vill bearbeta några av raderna, markera dem och välj sedan **Ta bort**.
5. Välj **OK**.

## <a name="mass-hold-processing"></a>Bearbetar masspärr

Använd sidan **Masspärr** för att tillämpa spärralternativ på flera faktureringsscheman samtidigt.

Om du bara vill vänta med ett faktureringsschema eller en faktureringsschemarad öppnar du sidan **Alla faktureringsscheman** och väljer **Placera spärr**. Om du vill ta bort en spärr, använd sidan **Ta bort spärr**.

### <a name="put-billing-schedules-on-hold"></a>Spärra faktureringsscheman

Följ dessa steg för att spärra flera faktureringsscheman.

1. På sidan **Masspärr** ange fältet **Processalternativ** till **Använd spärr**.
2. I fältet **Orsakskod**, välj orsakskod.
3. Ställ in alternativet **Justera tidsplan**:

    - **Ja** – Om du ställer in alternativet till **Ja**, ange ett spärrdatum i fältet **Spärrdatum**. Eventuella rader i faktureringsplanen efter förfallodatumet tas bort.
    - **Nej** – Raderna i faktureringsplanen ändras inte. Endast statusen ändras. Det uppdateras till **spärrad**.

4. På snabbfliken **Poster som ska ingå**, använd knappen **Filter** för att lägga datafilter.
5. Välj **Visa förhandsgranskning** om du vill visa postintervall.
6. Om du inte vill bearbeta några av raderna, markera dem och välj sedan **Ta bort**.
7. Välj **OK**.

När du återgår till listan med faktureringsscheman bör du se till att statusen för faktureringsscheman har ändrats till **spärrad**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Ta bort en spärr från flera faktureringsscheman

1. På sidan **Masspärr** ange fältet **Processalternativ** till **Ta bort spärr**.
2. I fältet **Orsakskod**, välj orsakskod.
3. I fältet **Ta bort datum** väljer du det datum då spärren ska tas bort.
4. Ange fälten **Återupptagningsdatum** och **Periodiseringsdatum** efter behov. Periodiseringsdatum läggs till på alla rader som är de periodiserbar.
5. På snabbfliken **Poster som ska ingå**, använd knappen **Filter** för att lägga datafilter.
6. Välj **Visa förhandsgranskning** om du vill visa postintervall.
7. Om du inte vill bearbeta några av raderna, markera dem och välj sedan **Ta bort**.
8. Välj **OK**.

> [!NOTE]
> Om du vill ta bort en spärr måste du ställa in värdet **Ta bort spärr för åsidosättning av användargrupp** på sidan **Faktureringsparametrar för återkommande kontrakt**.

En faktureringsrad har till exempel startdatumet 1 februari 2022 och slutdatumet 28 februari 2022. Faktureringsbelopp är 200 $. Fältet **Spärrdatum** anges till 10 februari 2022. Därför justeras februari med undantag för eventuella datum efter den 10 februari. Den nya perioden är från 1 februari till 9 februari och beloppet sätts 64,29 $ (till och med den dagliga fördelningen). Alla rader i faktureringsplanen, den 10 februari, tas bort.

Om processen **Ta bort spärr** är slutförd och fältet **Ta bort datum** är inställt på 10 februari 2022 kommer det att finnas två faktureringsperioder. Den första faktureringsperioden är från 1 februari till 9 februari och beloppet sätts 64,29 $. Den andra faktureringsperioden är från 10 februari till 28 februari och beloppet sätts 135,71 $.

## <a name="mass-termination-processing"></a>Process för massuppsägning

Använd sidan **massuppsägning** om du vill säga upp faktureringsschemarader som visas genom att ange ett uppsägningsdatum.

Om du använder periodisering av intäkt och utgift, faktureringsscheman där fältet **Uppsägningsdatum** är inställt på **Justera tidsplan** på sidan **Alla faktureringsscheman** är berättigade till återbetalning.

Faktureringsplaner med funktionen allokering med flera element (MEA) visas inte på sidan **massuppsägning**. Du kan fortfarande avsluta en enskild faktureringsplan genom att använda uppsägningsfunktionen i faktureringsschemat.

> [!NOTE]
> Faktureringsschemarader som för närvarande ingår i batchen **Generera faktura** är inte tillgängliga för den här processen.

Mer information om respektive fält och processen finns i [Avsluta faktureringsscheman](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Massarkiveringsprocess

Använd sidan **Massarkiv** om du vill arkivera flera faktureringsscheman. Endast uppsagda faktureringsscheman kan arkiveras.

När ett faktureringsschema har arkiverats inträffar följande händelser:

- Status ändras till **Arkiverad**.
- Faktureringsscheman är permanent låsta.
- Faktureringsschemaraderna är inte längre tillgängliga på förfrågningssidor.

> [!NOTE]
> Arkivering av ett faktureringsschema är en permanent åtgärd som inte kan återföras.

Följ dessa steg för att arkivera faktureringsscheman.

1. På sidan **Massarkiv** i fältet **faktureringsslutdatum** ange ett faktureringsslutdatum. Om du vill visa alla avslutade faktureringsscheman låter du det här fältet vara tomt.
2. På snabbfliken **Poster som ska ingå** använd knappen **Filter** för att begränsa antalet poster som visas.
3. Välj **Visa förhandsversion**.
4. Om du inte vill arkivera några av posterna, markera dem och välj sedan **Ta bort**.
5. Välj **OK** för att arkivera posterna på sidan.

## <a name="mass-stubbing-process"></a>Process för masslagring

Använd sidan **masslagring** för att markera alla valda faktureringsschemarader som fakturerade (lagring) eller ofakturerade (omvänd lagring). Lagring eller omvänd lagring utförs oftast på importerade faktureringsschemarader som tidigare fakturerats i ett annat system. Fakturerade fakturaplansrader visas som debiterade och skapas ingen faktura för kunden.

### <a name="stub-records"></a>Lagringsposter

1. På sidan **Masslagring** i fältet **Processalternativ**, välj **Lagra**.
2. I fältet **Slutdatum**, ställ in ett slutdatum för att ange raderna som du vill tillämpa processen på. Endast poster där startdatumet för faktureringen är på eller före det angivna slutdatumet visas.
3. Välj **Visa förhandsgranskning** om du vill visa de rader du vill lagra.
4. Om du vill utesluta en rad från processen markerar du den och väljer **Ta bort**.
5. Välj **Process** för att lagra raderna.

### <a name="reverse-stub-records"></a>Återför lagringsposter

1. På sidan **Masslagring** i fältet **Processalternativ**, välj **Återför lagring**.
2. I fältet **Slutdatum**, ställ in ett slutdatum för att ange raderna som du vill tillämpa processen på. Endast poster där startdatumet för faktureringen är på eller före det angivna slutdatumet visas.
3. Välj **Visa förhandsgranskning** om du vill visa de rader för att återföra lagring.
4. Om du vill utesluta en rad från processen markerar du den och väljer **Ta bort**.
5. Välj **Process** för att återföra lagra raderna.

## <a name="update-completion-date-process"></a>Uppdatera process för slutförandedatum

På sidan **Uppdatera slutförandedatum** för att uppdatera slutdatumet för specifika milstolpar för flera faktureringsscheman eller användare. Du kan även uppdatera slutförandeprocenten för artiklar på milstolpemallar som använder metoden **Procent slutfört**.

1. På sidan **Uppdatera slutförandedatum**, gå till **Milstolpebearbetning** och välj **Uppdatera slutförandeprocent**.
2. I fältet **Procentbelopp**, ange den totala procentsatsen som har slutförts.
3. Välj artikelnumret som är relaterat till milstolpsmallen.
4. På snabbfliken **Poster som ska ingå** välj **Filter** för att välja ett specifikt värde för **Slutanvändarkonto**, **Faktureringsschemanummer** eller **Artikelnummer** som ett filter criterion.
5. Välj **OK** för att bearbeta ändringen. När bearbetningen är klar läggs en ny rad till i milstolpe allokeringen. Den här raden representerar den procentsats som har slutförts för milstolpemallen.

## <a name="unbilled-revenue-mass-processing"></a>Massbearbetning av ej fakturerad intäkt

Använd sidan **Massbearbetning av ej fakturerad intäkt** för att skapa den ofakturerade intäktsjournalposten eller stubba journalposten för en eller flera valda faktureringsscheman eller faktureringsdetaljrader.

- **Skapa journalpost** – Skapa journalposter för ofördelade intäkter för flera fakturaplansrader. Använd knappen **Filter** på snabbfliken **Poster som ska ingå** för att välja det antal poster som visas i listan. Listan visar bara rader i faktureringsschemat som ej fakturerade intäktsjournalposter inte har skapats för. De ursprungliga journalposterna skapas. För periodiseringsartiklar skapas även periodiseringsscheman.
- **Lagra post i redovisningsjournal –** Markera de faktureringsschemarader som de ofördelade journalposterna redan har skapats för. Det här alternativet används om den ofördelade journalposten redan har bokförts i ett annat system. Den markerar den ofördelade intäktsjournalen som nedtryckt och bokför inte en transaktion i redovisningen.
- **Återför post i redovisningsjournal för specifikation** Återför journalposter som har bearbetats. Om ett misstag gjordes under bearbetningen för **Lagra post i redovisningsjournal** kommer detta alternativ att avmarkera kryssrutan **Lagrad** för faktureringsschemaraden.
- **Lagra faktureringsdetaljrad** – Använd den här processen när ej fakturerade intäkter bearbetades i ett externt system, och en del av faktureringsdetaljraderna redan har fakturerats. Med den här processen ser du till att rätt belopp visas på kontona för ej fakturerade intäkter.
- **Återför faktureringsdetaljrad för specifikation** – Återför alla åtgärder för **Lagra faktureringsdetaljrad**.

Fältet **Journalnamn** används för att bokföra **Skapa journalpost** i redovisningen.

> [!NOTE]
> Lagringsprocessen bokför inte belopp i redovisningen. Fältet **Journalnamn** är inte tillgängligt för alla återförings- och återföringsprocesser.

### <a name="unbilled-revenue-stub-example"></a>Exempel på ofakturerad intäktslagring

Ett faktureringsschema har ställts in för ett år, från 2021 oktober till och med september 2022. De ofördelade intäkterna har redan bearbetats i ett externt system. Nio månader av faktureringsschemat har redan fakturerats. Beloppet för varje faktureringsperiod är 250 $. I början av året bokförs det totala beloppet som har bokförts till ofördelade intäkter 3 000 $. Efter nio månader har 2 250 $ redan fakturerats och i 750 $ i ofördelade intäkter återstår.

Om du vill ställa in faktureringsschemat där bara tre månaders ofördelade intäkter återstår följer du dessa steg.

1. På sidan **Visa faktureringsdetaljer** skapar du ett faktureringsschema för perioden från oktober 2021 till och med september 2022, artikelnumret S0001 och ett belopp 250 $ per månad.
2. Välj **Skapa journalpost** för faktureringsschemat. Beloppet för 3 000 $ till ej fakturerade intäkter.
3. Välj **Lagra faktureringsdetaljrad** och ange ett transaktionsdatum juni 2022 (nio månader). Raderna i faktureringsplanen visas inte i förhandsgranskningen. De rader som påverkas baseras på transaktionsdatumet.
4. Välj **OK**.

De första nio månaderna som har fakturerats får ingen tid att faktureras.

[![Visa lagra faktureringsdetaljrad.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

3 000 $ återförs från ofördelade intäkter och 750 $ i ofördelade intäkter som återstår bokförs. För att se de ofakturerade intäktsbokningarna, välj **Granska journalpost ofakturerad intäkt** på fliken **Förnyelser** på sidan med raddetaljer.

[![Granska journalpost ofakturerad intäkt.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> Posten i intäktsjournalen kan skapas för eventuella otidsenlig term, förutsatt att alla faktureringsdetaljrader från föregående period har fakturerats. En faktureringsschemarad har till exempel en månadsvis faktureringsfrekvens för en 12-månadersperiod, från januari till december 2021. Raden har tre termer: den ursprungliga termen, en andra term (januari till december 2022) och en tredje term (januari till och med december 2023). När fakturan har skapats för alla faktureringsdetaljrader från de första 12 månaderna 2021, kan journalposten för ofördelade intäkter skapas för andra perioden.
>
> För prenumerationsfakturering som använder den ofakturerade intäktsfunktionen, bearbetas faktureringsraden och rabattraderna. För dessa poster skapas den ofakturerade intäktsjournalposten och periodiseringsschemat för faktureringsraden och rabattraden.
>
> Verifikatsposterna som skapas för icke-periodiseringsbara poster och periodiseringsbara poster bokför en kredit på olika intäktskonton.
