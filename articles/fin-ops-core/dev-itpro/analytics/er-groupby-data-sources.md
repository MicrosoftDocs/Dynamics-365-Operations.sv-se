---
title: Gruppera poster och aggregera beräkningar med hjälp av GROUPBY-datakällor
description: Den här artikeln beskriver hur du kan använda datakällor av typen GROUPBY i elektronisk rapportering (ER).
author: NickSelin
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b20b5db0794157560f27f15594a84083966642f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861799"
---
# <a name="group-records-and-aggregate-calculations-by-using-groupby-data-sources"></a>Gruppera poster och aggregera beräkningar med hjälp av GROUPBY-datakällor

[!include[banner](../includes/banner.md)]

När du konfigurerar modellmappningar [Elektronisk rapportering (ER)](general-electronic-reporting.md) eller format kan du [lägga till](#AddMmDataSource2) nödvändiga datakällor av typen **GroupBy**.

Vid designtiden konfigureras en **GroupBy**-datakälla för identifiering av följande element:

- En [grunddatakälla](#BaseDataSource) som innehåller poster som ska grupperas under körning
- [Grupperingsfält](#GroupingFields) för basdatakällan, som används för postgruppering när den körs
- [Sammansatta funktioner](#AggregateFunctions) som specificerar de aggregerade beräkningar som ska utföras för varje upptäcktsgrupp vid körning

Under körning grupperar en konfigurerad **GroupBy**-datakällgrupp poster som har samma värden i grupperingsfälten och returnerar sedan en lista med poster. Varje post representerar en enskild grupp. För varje grupp visar datakällan de fältvärden som de ursprungliga posterna har grupperats efter, värdena för de beräknade sammansatta funktionerna och listan över poster i basdatakällan som tillhör gruppen.

## <a name="aggregate-functions"></a><a name="AggregateFunctions"></a>Sammansatta funktioner

Vid körning utförs alla sammanställda beräkningar för varje grupp av poster. Denna beräkning görs med hjälp av värdet för ett enskilt fält eller ett uttryck i posterna för en datakälla som valts för gruppering i den redigerbara datakällan av typen **GroupBy** . Följande typer av sammansatta funktioner stöds nu:

- **AVG** – Den här funktionen returnerar medelvärdet för värdena i en grupp. Den kan bara användas med numeriska fält.
- **COUNT** – Den här funktionen returnerar antalet artiklar som hittades i en grupp.
- **Min** – Den här funktionen returnerar det lägsta värdet bland värdena i en grupp.
- **Max** – Den här funktionen returnerar det högsta värdet bland värdena i en grupp.
- **SUM** – Den här funktionen returnerar summan av alla värdena i en grupp. Den kan bara användas med numeriska fält.

## <a name="execution-location"></a><a name="ExecutionLocation"></a>Plats för körning

När du redigerar en **GroupBy**-datakälla och anger den grunddatakälla som innehåller de poster som måste grupperas, identifierar systemet automatiskt den mest effektiva [platsen](#ExecutionLocation) för körning av den **GroupBy**-datakällan . Om grunddatakällan är [frågningsbart](er-functions-list-filter.md#usage-notes) (det vill säga om den kan köras på databasnivå), anges även appdatabasen som exekveringsplats för den redigerbara datakällan **GroupBy**. Annars anges appserverminnet som körningsplats.

Du kan manuellt ändra den plats för körning som upptäckts automatiskt genom att välja den plats som gäller för den konfigurerade datakällan. Om den valda körningsplatsen inte ska användas, beror det på ett [valideringsfel](er-components-inspections.md#i5) vid designtid.

> [!TIP]
> Vi rekommenderar att du använder databasplatsen när du vill gruppera datakällor som visar ett stort antal poster.

## <a name="memory-consumption"></a><a name="MemoryConsumption"></a>Minnesförbrukning

Om en **GroupBy**-datakälla körs i minnet används som standard programserverminnet för att lagra poster i basdatakällan som tillhör varje upptäckt grupp som poster i en enda grupp. För att minska minnesförbrukningen kan du utelämna postlagring för **GroupBy**-datakällor om de konfigurerats till att endast beräkna aggregerade funktioner och gruppens poster inte används när de körs. Du minskar minnesförbrukningen på det här sättet genom att aktivera **Minska minnesanvändningen i ER när postgruppering bara används för att beräkna sammansättningar** i arbetsytan **Funktionshantering**.

## <a name="alternatives"></a><a name="Alternatives"></a>Alternativ

Liknande aggregeringar kan beräknas med hjälp av [olika](er-data-collection-data-sources.md#if-i-have-to-calculate-running-totals-and-collect-data-what-is-the-difference-between-using-a-data-collection-data-source-and-using-the-built-in-data-collection-functions) typer av datakällor eller inbyggda funktioner för ER.

Om du vill veta mer om den här funktionen fyller du i det exempel som följer.

## <a name="example-use-a-groupby-data-source-for-aggregate-calculations-and-record-grouping"></a><a name="Example"></a>Exempel: Använd en GROUPBY datakälla för aggregera beräkningar postgruppering

I det här exemplet visas hur en användare med rollen Systemadministratör eller Funktionskonsult för elektronisk rapportering kan konfigurera en ER-modellmappning som har datakällan **GROUPBY** som används för att beräkna aggregerade funktioner och grupposter. Modellmappningen används för att skriva ut kontrollrapporten när Intrastat-deklarationen genereras. Den rapporten låter dig granska rapporterade Intrastat-transaktioner.

Procedurerna i detta exempel kan slutföras i **DEMF**-företaget DEMF i Microsoft Dynamics 365 Finance. 

### <a name="prepare-sample-data"></a>Förbered exempeldata

Kontrollera att du har Intrastat-transaktioner för rapportering på **Intrastat**-sidan. Det måste finnas transaktioner för olika transportkoder, eftersom transaktioner grupperas efter fältet **Transport** i det här exemplet.

![Förbereda Intrastat-transaktioner på Intrastat-sidan.](./media/er-groupby-data-sources-prepare-transactions.png)

### <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra de här inställningarna innan du börjar använda ER-ramverket för att designa en ER-modellmappning.

### <a name="import-the-standard-er-format-configuration"></a>Importera standardkonfiguration av ER-format

Följ stegen i [Importera standardkonfiguration för ER-format](er-quick-start2-customize-report.md#ImportERSolution1) för att lägga till ER-standardkonfigurationerna i din nuvarande instans av Dynamics 365 Finance. Importera version 1 av konfigurationen för **Intrastat-modell** från databasen.

### <a name="create-a-custom-data-model-configuration"></a>Skapa en anpassad konfiguration för datamodell

Följ stegen i [Lägg till en anpassad datamodellkonfiguration](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) för att manuellt lägga till en ny **Intrastat-modell (Litware)** ER-datamodellkonfiguration som du härleder från den importerade konfigurationen **Intrastat-modell**.

### <a name="configure-a-custom-data-model-component"></a>Konfigurera en anpassad datamodellkomponent

Följ dessa steg för att göra de nödvändiga ändringarna av den härledda **Intrastat-modell (Litware)** datamodell, så att den kan användas för att exponera transportkoder som har de nödvändiga detaljerna.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Intrastat-modell (Litware)**.
3. Välj **Designer**.
4. På sidan **Sidan Datamodelldesigner** i modellträdet, välj **Intrastat**.
5. Välj **Ny** om du vill lägga till en ny kapslad nod för den valda **Intrastat** noden. Gör så här i listrutan för att lägga till en datamodellnod:

    1. I fältet **Namn** ange **Transport**.
    2. Välj **Postlista** i fältet **Artikeltyp**.
    3. Välj **Lägg till** för att lägga till en ny nod.

6. Välj **Ny** om du vill lägga till en ny kapslad nod för den **Transport** nod som du just lagt till. Gör så här i listrutan för att lägga till en datamodellnod:

    1. I fältet **Namn**, ange **Kod**.
    2. Välj **Sträng** i fältet **Artikeltyp**.
    3. Välj **Lägg till** för att lägga till en ny nod.

7. Välj **Ny** om du vill lägga till en annan ny kapslad nod för den **Transport** nod. Gör så här i listrutan för att lägga till en datamodellnod:

    1. I fältet **Namn** anger du **TotalInvoicedAmount**.
    2. Välj **Realtal** i fältet **Artikeltyp**.
    3. Välj **Lägg till** för att lägga till en ny nod.

8. Välj **Ny** om du vill lägga till en annan ny kapslad nod för den **Transport** nod. Gör så här i listrutan för att lägga till en datamodellnod:

    1. I fältet **Namn** anger du **NumberOfTransactions**.
    2. I fältet **Artikeltyp** välj **Heltal**.
    3. Välj **Lägg till** för att lägga till en ny nod.

9. Välj **Ny** om du vill lägga till en annan ny kapslad nod för den **Transport** nod. Gör så här i listrutan för att lägga till en datamodellnod:

    1. I fältet **Namn** anger du **Transaktion**.
    2. Välj **Postlista** i fältet **Artikeltyp**.
    3. Välj **Lägg till** för att lägga till en ny nod.

10. För den **Transaktion** nod som du just lagt till, på snabbflikarna **Nod**, välj **Byt artikelreferens**.
11. I dialogrutan **Switch-artikelreferens** väljer du **CommodityRecord** i datamodellträdet. Välj sedan **OK**.

![Konfigurerad datamodell i ER-datamodelldesignern.](./media/er-groupby-data-sources-configure-data-model.png)

### <a name="complete-the-design-of-a-custom-data-model"></a>Färdigställa utformning av anpassad datamodell

Följ stegen i [Slutför design av datamodellen](er-quick-start3-customize-report.md#add-a-custom-data-model-configuration) för att slutföra utformningen av den härledda datamodellen **Intrastat-modell (Litware)**.

### <a name="create-a-new-model-mapping-configuration"></a>Skapa en ny konfiguration av modellmappning

Följ stegen i [Skapa en ny modellmappningskonfiguration](er-quick-start1-new-solution.md#CreateModelMapping) för att manuellt lägga till en ny konfiguration av **Intrastat-exempelmappning** ER-modellmappningskonfiguration för den härledda **Intrastat-modell (Litware)**.

### <a name="add-a-new-model-mapping-component"></a>Lägg till en ny komponent för modellmappning

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet expanderar du konfigurationen **Intrastat-modell**.
3. Välj konfigurationen **Intrastat-exempelmappning**.
4. Välj **designer** om du vill öppna listan över mappningar.
5. Välj **Ta bort** om du vill ta bort den befintliga mappningskomponenten.
6. Klicka på **Ny** om du vill lägga till mappningskomponent.
7. I fältet **Definition**, välj **Intrastat**.
8. Ange **Namn** i fältet **Intrastat-namn**.
9. Välj **Designer** för att konfigurera den nya mappningen.

### <a name="design-the-added-model-mapping-component"></a>Designa den tillagda modellmappningskomponent

#### <a name="add-a-data-source-to-access-an-application-table"></a><a name="AddMmDataSource1"></a>Lägg till en datakälla för att komma åt en apptabell

Konfigurera en datakälla för att komma åt apptabellerna som innehåller information om Intrastat-transaktioner.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Dynamics 365 for Operations\\Tabellregister**.
2. I fönstret **Datakällor**, välj **Lägg till rot** för att lägga till en ny datakälla som kommer att användas för att komma åt tabellen **Intrastat**. Varje post i **Intrastat**-tabell representerar en enda Intrastat-transaktion.
3. I dialogrutan **Datakällegenskaper** i fältet **Namn**, ange **Transaktion**.
4. I fältet **Tabell** ange **Intrastat**.
5. Klicka på **OK** om du vill lägga till den nya datakällan.

#### <a name="add-a-data-source-to-group-intrastat-transactions"></a><a name="AddMmDataSource2"></a>Lägga till en datakälla för att gruppera Intrastat-transaktioner

Konfigurera en **GroupBy**-datakälla om du vill gruppera Intrastat-transaktioner och beräkna sammansatta funktioner.

1. På sidan **Modellmappingsdesigner** i fönstret **Datakälltyper** väljer du **Funktioner\\gruppera efter**.
2. I fönstret **Datakällor**, välj **Lägg till rot** för att lägga till en ny datakälla som kommer att användas för att gruppera Intrastat-transaktioner och beräkna aggregerade funktioner.
3. I dialogrutan **Datakällegenskaper** i fältet **Namn**, ange **TransportRecord**.
4. Välj **Redigera grupp efter** genom att konfigurera grupperingsvillkor.
5. På sidan **Parameter redigera "Gruppera efter"** i listan med datakällor i den högra rutan, välj **Transaktion** datakälla och expandera den.
6. Välj **Lägg till fält i \> Vad du ska gruppera** för att indikera att datakällan **Transaktion** väljs som <a name="BaseDataSource">basdatakällan</a> för den konfigurerade **GroupBy**-datakällan. Posterna i datakällan **Transaktion** kommer att grupperas och fältvärdena för denna datakälla kommer att användas för beräkningar i aggregerade funktioner.
7. Välj fältet **Transaction\Transport** och välj sedan **Lägg till fält till \> Grupperat fält** för att indikera att **Transport** för basdatakällan väljs som <a name="GroupingFields">grupperingskriterium</a> för den konfigurerade datakällan **GroupBy**. Med andra ord grupperas posterna i **Transaktion** datakällan efter värdet i fältet **Transport**. Varje post i den konfigurerade **GroupBy**-datakällan representerar en enda transportkod som har hittats i poster för basdatakällan.
8. Välj fältet **Transaction\AmountMST** och gör så här:

    1. Välj **Lägg till fält till \> Aggregera fält** om du vill ange att en <a name="AggregateFunctions">aggregerad funktion</a> kommer att beräknas för det här fältet.
    2. I fönstret **Sammansättningar**, i posten som har lagts till för det valda fältet **Transaction\AmountMST** i fältet **Metod**, välj funktion **Sum**.
    3. I det valfria fältet **Namn** anger du **TotalInvoicedAmount**.

    Dessa inställningar anger att det totala beloppet i fältet **Transaction\AmountMST** ska beräknas för varje transportgrupp.

9. Välj fältet **Transaction\RecId** och gör så här:

    1. Välj **Lägg till fält till \> Aggregera fält** om du vill ange att en aggregerad funktion kommer att beräknas för det här fältet.
    2. I fönstret **Sammansättningar**, i posten som har lagts till för det valda fältet **Transaction\RecId** i fältet **Metod**, välj funktion **Count**.
    3. I det valfria fältet **Namn** anger du **NumberOfTransactions**.

    Dessa inställningar anger att för varje transportgrupp kommer antalet transaktioner i gruppen att beräknas.

10. Välj **Spara**.
11. Granska parametrarna <a name="ExecutionLocation">körning</a> för den redigerbara datakällan. Observera att **Automatisk identifiering** har valts automatiskt i fältet **Körningsplats** och fältet **Körning på** innehåller värdet **SQL**. Dessa inställningar anger att den valda basdatakällan **Transaktion** för närvarande kan frågas och du kan köra den redigerbara datakällan **GroupBy** på databasnivå.
12. Öppna sökfältet **Körningsplats** om du vill granska listan med tillgängliga värden. Lägg märke till att du kan välja **Fråga** eller **I minne** för att tvinga denna **GroupBy**-datakälla att köras på databasnivå eller i programserverminnet.
13. Välj **Spara** och stäng sidan **Redigera parametern för "Gruppera efter"**.
14. Välj **OK** för att slutföra inställningarna för datakällan **GroupBy**.

#### <a name="bind-the-groupby-data-source-to-data-model-fields"></a><a name="AddMmBindings"></a>Binda GroupBy datakälla till fält för datamodell

Binda den konfigurerade datakällan till fälten i datamodellen för att ange hur datamodellen ska fyllas i med programdata vid körning.

1. På sidan **Modellmappingsdesigner** i fönstret **Datamodell** expanderar du noden **Transport**.
2. I rutan **Datakällor**, expandera datakällan **TransportRecord**.
3. Lägg till en bindande för att visa listan med upptäckta transportgrupper:

    1. I fönstret **Datamodell** välj artikeln **Transport**.
    2. I rutan **Datakällor**, välj datakällan **TransportRecord**.
    3. Välj **bind**.

4. Lägg till en bindande för att visa transportkod för varje upptäckt transportgrupp:

    1. Välj datamodellobjektet **Transport.Code**.
    2. Välj det grupperade fältet **TransportRecord.grouped.TransportMode**.
    3. Välj **bind**.

5. Lägg till en bindande funktion för att visa värdena för beräknade sammansatta funktioner för varje upptäckt transportgrupp:

    1. Välj datamodellobjektet **Transport.NumberOfTransactions**.
    2. Välj det aggregerade fältet **TransportRecord.aggregated.NumberOfTransactions**.
    3. Välj **bind**.
    4. Välj datamodellobjektet **Transport.TotalInvoicedAmount**.
    5. Välj det aggregerade fältet **TransportRecord.aggregated.TotalInvoicedAmount**.
    6. Välj **bind**.

6. Lägg till en bindande för att exponera transaktionsposter som hör till varje upptäckt transportgrupp:

    1. Välj datamodellobjektet **Transport.Transaction**.
    2. Markera fältet **TransportRecord.lines**.
    3. Välj **bind**.

    Du kan fortsätta att konfigurera bindningar för de kapslade objekten i datamodellobjektet **Transport.Transaction** och datakällfältet  **TransportRecord.lines** för att under körning visa detaljer om Intrastat-transaktioner som tillhör varje upptäckt transportgrupp.

![Konfigurerad modellmappning i ER-modellmappningsdesignern.](./media/er-groupby-data-sources-configure-model-mapping.png)

### <a name="debug-the-added-model-mapping-component"></a>Felsöka den tillagda modellmappningskomponent

Använda [ER-datakällans felsökare](er-debug-data-sources.md) för att testa den konfigurerade modellmappningen.

1. På sidan **Modellmappningsdesigner**, välj **Starta felsökning**.
2. På sidan **Felsök datakällor** i vänstra fönstret, välj datakälla **TransportRecord** och välj sedan **Läs alla poster**.
3. Expandera datakällan **TransportRecord** och följer sedan de här stegen:

    1. Välj det grupperade datakällan **TransportRecord.grouped.TransportMode**.
    2. Välj **Hämta värde**.
    3. Välj det grupperade datakällan **TransportRecord.grouped.NumberOfTransactions**.
    4. Välj **Hämta värde**.
    5. Välj det grupperade datakällan **TransportRecord.grouped.TotalInvoicedAmount**.
    6. Välj **Hämta värde**.

4. Välj **Expandera alla** i höger fönster.

Datakällan **TransportRecord** visar två poster och visar två transportkoder. För varje transportkod beräknas antalet transaktioner och det totala fakturerade beloppet.

> [!NOTE]
> Metoden "läs" används när en **GroupBy**-datakälla anropas för att optimera databassamtal. Därför beräknas några av fältvärdena i en datakällan **GroupBy** beräknas i ER-datakällans felsökning endast när de är bundna till datamodellfält.

![Resultat från felsökningen av datakällan på sidan datakällan Felsöka.](./media/er-groupby-data-sources-debug-datasource.png)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="is-there-any-way-to-calculate-grand-totals-when-the-group-totals-are-calculated"></a>Kan slutsummor beräknas när gruppsummor beräknas?

Ja. För att beräkna totalsummor, konfigurera en annan datakälla **GroupBy** när **GroupBy** som du tidigare konfigurerat används som basdatakälla. I följande bild visas datakällan **Summor** av typen **GroupBy** som används för att beräkna funktionen **SUM** baserad på sammansättningen **SUM** för datakällan **TransportRecord** av typen **GroupBy**.

![Summa datakälla i ER-modellmappningsdesignern.](./media/er-groupby-data-sources-configure-model-mapping2.png)

I följande bild visas resultatet av felsökningen av datakällan **Summor**.

![Resultat från felsökningen av datakällan Summor på sidan datakällan Felsöka.](./media/er-groupby-data-sources-debug-datasource2.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Felsöka datakällor i ett kört ER-format för analys av dataflöde och omvandling](er-debug-data-sources.md)
- [Använd datakällor för DATAINSAMLING i elektroniska rapporteringsformat](er-data-collection-data-sources.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
