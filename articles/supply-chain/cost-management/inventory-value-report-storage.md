---
title: Lagervärderapporter
description: Detta ämne förklarar hur du konfigurerar, genererar och använder lagervärdesrapporter. Rapporterna innehåller information om fysiska och ekonomiska kvantiteter och belopp för lagret.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3da92c384d3074335067433120eccc97d11b6b81
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103950"
---
# <a name="inventory-value-reports"></a>Lagervärderapporter

[!include [banner](../includes/banner.md)]

Rapporterna för lagervärde innehåller information om fysiska och ekonomiska kvantiteter och belopp. Du kan visa rapporterna på många olika sätt. Du kan till exempel visa summor eller transaktioner, eller filtrera efter artiklar eller tidsintervall. Du kan visa kostnader för sålda varor (COGS) eller PIA-värden (produkter i arbete) samt ställa in andra alternativ.

Med lagervärdesrapporter kan du utföra följande uppgifter:

- Göra avstämning mellan redovisning och lager.
- Rådgöra om lagerbehållning och värden för en viss period.
- Skapa rapportkonfigurationer som är skräddarsydda efter ett specifikt syfte.
- Spara rapportkonfigurationer så att dessa kan användas flera gånger.
- Lägga till intervall för att filtrera data när du kör en rapport.

## <a name="types-of-inventory-value-report"></a>Typer av lagervärdesrapport

Det finns två typer av lagervärdesrapport: **Lagervärde** (standardrapport) och **Lagring av lagervärdesrapport**.

### <a name="standard-inventory-value-report"></a>Standardraport för lagervärde

Standardrapporten för **Lagervärde** är en enkel rapport som låter dig välja inkluderad information och som sedan visar denna information på skärmen. Den sparar inte resultaten. Den innehåller heller inga interaktiva funktioner för filtrering, detaljgranskning, sökning eller export. Därför rekommenderar vi att du istället använder rapporten för **lagring av lagervärdesrapport** i de flesta fall.

### <a name="inventory-value-report-storage-report"></a>Rapport över rapportlagring för lagervärde

Rapporten **Lagring av lagervärdesrapport** tillhandahåller utdata antingen i form av en interaktiv sida i Microsoft Dynamics 365 Supply Chain Management eller som ett exporterat dokument i ett av flera format.

När du visar rapporten i din webbläsare, justeras kolumner och aggregerade saldon dynamiskt, beroende på vilken layout som du har konfigurerat. Du kan sortera resultaten, filtrera dem, öka detaljnivån i data och mycket mer.

Rapportresultaten lagras i dataentiteten **lagervärde**. Därför kan du filtrera och exportera resultaten till ett format, t.ex. kommaavgränsade värden (CSV) eller Microsoft Excel-format.

Rapporten **Lagring av lagervärdesrapport** är användbar när utdata innehåller många rader. Du har till exempel 50 000 artiklar och 300 butiker har skapats som lagerställen. Om du i det här fallet begär lagerslutsaldon per artikel, plats och lagerställe, innehåller utflödet många rader.

> [!NOTE]
> Rapporten **Lagring av lagervärdesrapport** innehåller inga delsummor som anges i rapportlayouten. De inkluderar heller inte redovisningssaldon, även om dessa saldon definieras i rapportlayouten. Du måste göra avstämning till redovisningen med hjälp av råbalansen. Standardrapporten **Lagervärde** innehåller emellertid dessa delsummor och saldon.

## <a name="turn-the-inventory-value-report-storage-feature-on-or-off"></a>Aktivera eller inaktivera funktionen för lagring av lagervärdesrapport

Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Administratörer kan aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Lagring av lagervärderapport* i arbetsytan [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Definiera rapportkonfigurationer för lagervärde

På sidan **Lagervärdesrapporter** kan du konfigurera innehållet som ingår i de olika typerna av lagervärdesrapporter. Du kan definiera valfritt antal rapporttyper. Varje gång du genererar någon form av lagervärdesrapport väljer du en rapporttyp.

1. Gå till **Kostnadshantering \> Policyinställningar för lagerredovisning \> Lagervärdesrapporter**.
1. Gör något av följande:

    - Om du vill redigera en befintlig rapport markerar du den i listrutan och väljer sedan **Redigera** i åtgärdsfönstret.
    - Om du vill skapa en ny rapport väljer du **Ny** i åtgärdsfönstret.

1. I sidhuvudet på den nya eller valda rapporten anger du följande fält:

    - **ID** – Ange en kort identifierare för rapporten. Detta värde måste vara unikt bland alla rapportkonfigurationer för lagervärden. Värdet kan inte redigeras efter det att du har sparat en ny konfiguration.
    - **Namn** – Ange ett beskrivande namn för rapporten.

1. Om du skapar en ny rapportkonfiguration väljer du **Spara** i åtgärdsfönstret så att övriga fält blir tillgängliga.
1. På snabbfliken **Allmänt** ange följande fält:

    - **Datumintervall** – Välj ett fördefinierat datumintervall. Du kan åsidosätta detta datumintervall när du kör rapporten.
    - **Intervall** – Välj antingen *bokföringsdatum* eller *Transaktionstid* beroende på det datum och den tid som ska användas när poster hämtas för rapporten.
    - **Dimensionsuppsättning** – Välj den dimensionsuppsättning som datan ska köras för. (Dimensionerna definieras i redovisningen.) Du kan till exempel köra data för *Huvudkonto* eller för *Huvudkonto + affärsenhet*. Den dimensionsuppsättning du väljer får inte ha fler än två dimensioner. Mer information finns i [Ekonomiska dimensionsuppsättningar](../../finance/general-ledger/financial-dimension-sets.md).

1. På snabbfliken **Kolumner** anger du följande fält: Dessa fält kontrollerar de kolumner som rapporten innehåller samt de datatyper som dessa kolumner innehåller.

    - **Lager** – Ange detta alternativ som *Ja* om du vill visa lagervärdena. Du kan sedan stämma av dessa värden med saldon på redovisningskontona.
    - **PIA** – Ange detta alternativ som *Ja* om du vill visa PIA-värdena. Du kan sedan stämma av dessa värden med PIA-kontosaldon i redovisningen. När du ställer in det här alternativet på *Ja* visar rapporten endast fysiska kvantiteter och lagerbelopp med PIA-status. Tillverkningsorder med PIA-status har valts eller rapporterats som färdiga, men dessa har inte avslutats.
    - **Uppskjuten KSV** – Ange detta alternativ som *Ja* om du vill visa en kolumn som visar de fysiska kvantiteterna och beloppen i lagret för uppskjuten KSV. Uppskjuten KSV visas med hjälp av fysiska kvantiteter och belopp, detta eftersom det motbokar följesedelskvantiteter och -belopp.
    - **KSV** – Ange detta alternativ som *Ja* om du vill visa en kolumn som visar finansiella kvantiteter och belopp för KSV. KSV visas med hjälp av finansiella kvantiteter och belopp, detta eftersom det förskjuter fakturakvantiteter och -belopp.
    - **Vinst och förlust** – Ange detta alternativ som *Ja* om du vill visa en kolumn som visar det ekonomiska belopp som har bokförts på vinst- och förlustkontona för lager.
    - **Skriv ut ackumulerade kontovärden för jämförelse** – Ange det här alternativet som *Ja* om du vill visa en kolumn som visar saldot för redovisningskontot. På det här sättet behöver du inte kontrollera spårsaldot. Detta alternativ fungerar bara med standardrapporten för **lagervärde**, inte med rapporten **Lagring av lagervärdesrapport**. När du har angett detta alternativ som *Ja* måste du använda följande fält för att ange varje enskilt redovisningskonto som du vill lista, beroende på de alternativ för **Ekonomiskt läge** som du har aktiverat.

        > [!NOTE]
        > Om du väljer ett konto av typen *summa* för något av dessa fält kommer både beloppet för respektive konto som ingår i sumkontot och totalkontots summa att visas.

        - **Lagerkonto** – Ange redovisningskontot som lagerinformation ska visas för. (Både alternativet **Lager** och alternativet **Skriv ut ackumulerade kontovärden för jämförelse** måste ställas in på *Ja*.)
        - **PIA-konto** – Ange redovisningskontot som PIA-information ska visas för. (Både alternativet **PIA** och alternativet **Skriv ut ackumulerade kontovärden för jämförelse** måste ställas in på *Ja*.)
        - **Uppskjutet PIA-konto** – Ange redovisningskontot som uppskjuten PIA-information ska visas för. (Både alternativet **Uppskjuten PIA** och alternativet **Skriv ut ackumulerade kontovärden för jämförelse** måste ställas in på *Ja*.)
        - **PIA-konto** – Ange redovisningskontot som PIA-information ska visas för. (Både alternativet **COGS** och alternativet **Skriv ut ackumulerade kontovärden för jämförelse** måste ställas in på *Ja*.)

    - **Summera fysiska och ekonomiska värden** – Ange det här alternativet som *Ja* om du vill visa en kolumn som visar total lagerkvantitet och totalt lagerbelopp (en sammanfattning av både fysiska och ekonomiska värden). Om det här alternativet anges som *Nej* visar rapporten både fysiska och ekonomiska lagervärden.
    - **Inkludera ej bokförd i redovisning** Ange detta alternativ som *Ja* om du vill visa en kolumn som visar de transaktioner som aldrig bokfördes i redovisningen. Transaktioner för följande artikeltyper kanske inte bokförs i redovisningen:

        - Mottagna och ännu inte fakturerade artiklar när alternativet **Bokför fysiskt lager** frigörs för den relevanta artikelmodellgruppen.
        - Mottagna och ännu inte fakturerade artiklar när alternativet **Bokför produktinleverans i redovisning** har rensats på snabbfliken **Produktmottagning** på fliken **Allmänt** på sidan **Parametrar för leverantörsreskontra** (**Leverantörskontra \> Inställningar \> Parametrar för leverantörsreskontra**).

    - **Beräkna genomsnittlig enhetskostnad** – Ange detta alternativ som *Ja* om du vill visa genomsnittlig enhetskostnad. Den genomsnittliga enhetskostnaden är den totala kvantiteten delad med det totala beloppet.
    - **Total kvantitet och värde** – Ange detta alternativ som *Ja* för att visa kolumner som visar den totala kvantiteten för fysiskt lager (och ekonomiska kvantiteter) och den totala mängden fysiskt lager (och ekonomiska belopp). Du kan endast ange detta alternativ som *Ja* endast om alternativet **Sammanfatta fysiska och ekonomiska värden** är inställt på *Nej*.
    - **Lagerdimensioner** – I detta rutnät markerar du kryssrutan **Visa** för varje dimension som du vill visa i rapporten. Endast dimensioner där alternativet **Ekonomiskt lager** har aktiverats kommer att visa värden i rapporten. Övriga dimensioner visar bara tomma kolumner. För de dimensioner som du väljer att visa kan du också markera kryssrutan **Summa** för att även inkludera summor.
    - **Resurs-ID** – Ange alternativet **Visa** som *Ja* för att visa en kolumn som identifierar artikeln för respektive rad. Ställ in alternativet **Summa** som *Ja* för att även inkludera summor. Beroende på vilken typ av artikel som visas på varje enskild rad visas någon av följande informationstyper i kolumnen:

        - **Material** – Kolumnen visar fältvärdet `ItemID` för den relevanta materialposten.
        - **Arbete** – Kolumnen visar fältvärdet `WorkCenterID` för den relevanta arbetsposten.
        - **Indirekt kostnad** – Kolumnen visar fältvärdet `CodeID` för den relevanta kostnadsposten.

        Om alternativet **Visa** har angetts som *Nej* för både fältet **Resurs-ID** och fältet **Resursgrupp** ser du endast ett totalt lagervärde som baseras på de lagerdimensioner som du har valt.

    - **Resursgrupp** – Ange alternativet **Visa** som *Ja* för att visa en kolumn som identifierar resursgruppen för respektive rad. Ställ in alternativet **Summa** som *Ja* för att även inkludera summor. Beroende på vilken typ av artikel som visas på varje enskild rad visas någon av följande informationstyper i kolumnen:

        - **Material** – Kolumnen visar fältvärdet `ItemGroup` för den relevanta materialposten.
        - **Arbete** – Kolumnen visar fältvärdet `WorkcenterGroup` för den relevanta arbetsposten.
        - **Indirekt kostnad** – Kolumnen visar fältvärdet `CostGroup` för den relevanta kostnadsposten. (Värdet `CostGroupType` måste vara *Indirekt*.)

        Om alternativet **Visa** har angetts som *Nej* för både fältet **Resurs-ID** och fältet **Resursgrupp** ser du endast ett totalt lagervärde som baseras på de lagerdimensioner som du har valt.

1. På snabbfliken **Rader** anger du följande fält: Med hjälp av dessa fält kan du lägga till motsvarande PIA-relaterade delgrupper i rapporten eller ta bort dem.

    - **Material** – Ange detta alternativ som *Ja* om du vill visa information om material. *Material* är en standardresurstyp eftersom material måste inkluderas i alla rapportkonfigurationer för att skapa tillförlitliga utdata.
    - **Arbete** – Ställ in detta alternativ som *Ja* för att visa arbetskostnader för PIA.
    - **Indirekt kostnad** – Ange detta alternativ som *Ja* för att visa indirekta för PIA.
    - **Direktutkontraktering** – Ange detta alternativ som *Ja* för att visa PIA-kostnader för direktutkontraktering. Denna information är praktisk för legotillverkning.
    - **Detaljnivå** – Välj ett visningsalternativ för rapporten:

        - *Transaktioner* – Visa alla relevanta transaktioner i rapporten. Observera att du kan komma att uppleva prestandaproblem när du visar rapporter som omfattar ett stort antal transaktioner. Om du vill använda detta visningsalternativ rekommenderar vi därför att du använder rapporten **Lagring av lagervärdesrapport**.
        - *Summor* – Visa det totala resultatet.

    - **Inkludera ingående saldo** – Ange det här alternativet som *Ja* för att visa ingående saldo. Detta alternativ är endast tillgängligt om fältet **Detaljnivå** anges som *Transaktioner*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Generera en rapport för lagring av lagervärderapport

Följ dessa steg för att skapa och lagra en rapport för **Lagring av lagervärderapport**.

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>Lagring av lagervärdesrapport**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Lagervärde** anger du följande fält på snabbfliken **Parametrar**:

    - **Namn** – Ange ett unikt namn för rapporten.
    - **ID** – Välj den [konfiguration för lagervärdesrapport](#report-configuration) som ska användas för rapporten. Konfigurationen etablerar alternativ för de kolumner och rader som ska omfattas av rapporten.
    - **Datumintervall** – Använd fälten i det här avsnittet för att definiera de poster som inkluderas i rapporten. Om du vill definiera datumintervallet kan du antingen välja ett förinställt intervall (relativt rapportens genereringsdatum) i fältet **datumintervallkod** eller välja särskilda datum i fälten i fälten **Från datum** och **Till datum**.

1. På snabbfliken **Poster som ska ingå** kan du konfigurera filter och begränsningar för att definiera vilka data som ska ingå i rapporten. Välj **Filter** för att öppna en standarddialogruta för Power Query-redigeraren, där du kan ange urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som för andra typer av frågor i Supply Chain Management. Alla dessa filter tillämpas på lagertransaktionerna men inte på redovisningssaldot. Beakta detta beteende när du konfigurerar filtren. I annat fall kan en avvikelse mellan lager och redovisning komma att visas.
1. På snabbfliken **kör på snabbfliken bakgrund** anger du hur, när och hur ofta rapporten ska genereras. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.

    > [!NOTE]
    > Den här rapporten körs alltid som en del av ett batchjobb.

1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan.

Efter att batchjobbet är slutfört kommer rapporten att listas på sidan **Lagring av lagervärdesrapport**. Du kanske måste uppdatera sidan för att kunna se rapporten.

> [!IMPORTANT]
> I vald konfiguration för lagervärdesrapport får du eventuellt ett felaktigt ingående saldo om du väljer samma datum i både fältet **Från datum** och i fältet **Till datum**, samt om du även anger alternativet **Inkludera ingående saldo** som *Ja*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Utforska en rapport för lagring av lagervärdesrapport

När du har genererat en rapport kan du visa och utforska den genom att följa dessa steg.

1. Gå till **kostnadshantering \>förfrågningar och rapporter \>Lagring av lagervärdesrapport**.
1. Välj en rapport i listan. På sidan visas information om den [konfiguration för lagervärdesrapport](#report-configuration) som användes för att generera den valda rapporten.
1. I åtgärdsfönstret väljer du **Visa detaljer** för att visa rapportinnehållet.
1. Granska rapporten på följande sätt:

    - Som för de flesta standardsidor i Supply Chain Management kan du välja nästan vilken kolumnrubrik som helst för att sortera eller filtrera rutnätet efter värdena i den kolumnen.
    - Använd fältet **filter** om du vill filtrera rapporten efter vilket värde som helst i flera tillgängliga kolumner.
    - Använd visa-menyn (ovanför fältet **filter**) för att spara och läsa in dina favoritkombinationer av sorterings- och filteralternativ.

## <a name="export-an-inventory-value-report-storage-report"></a>Exportera en rapport för Lagring av lagervärderapport

Varje rapport som du skapar lagras i dataenheten **Lagringsrapport**. Du kan använda de standardiserade datahanteringsfunktionerna i Supply Chain Management för att exportera data från den här enheten till alla dataformat som stöds inklusive CSV eller Excel-format.

I följande exempel visas hur du exporterar en rapport för **Lagring av lagervärderapport**.

1. Gå till **Systemadministration \> Arbetsytor \> Datahantering**.
1. I välj **Import/export**, välj panelen **Export**.
1. På sidan **export** som visas ska du ställa in exportjobbet. Ange först ett gruppnamn för jobbet.
1. I avsnitt **Vald entiteter**, välj **Lägg till entitet**.
1. Ställ in följande fält i dialogrutan som visas:

    - **Enhetsnamn** – Välj *Lagervärde*.
    - **Måldataformat** – Välj vilket format du vill exportera data till.

1. Välj **Lägg till** för att lägga till den nya raden och välj sedan **Stäng** för att stänga dialogrutan.
1. Vanligtvis exporterar du en rapport i taget. Om du vill exportera en enda rapport skapar du ett filter för den rad som du just har lagt till i dialogrutan **förfrågan**. På det här sättet kan du definiera vilken rapport från enheten **Lagervärde** som ska tas med i exporten. Följ stegen för att ange följande filteralternativ för att exportera en enskild rapport:

    1. På fliken **Intervall**, välj **Lägg till** om du vill lägga till en rad.
    2. Ange fältet **Tabell** till *Lagervärde*.
    3. Ange fältet **härlett register** till *Lagervärde*.
    4. Ställ in **fältet** till det fält som du vill filtrera efter. Vanligtvis använder du fältet **körningsnamn** och/eller fältet **körningstid**.
    5. Ställ in fältet **Kriterier** till det värde som du vill söka efter i det valda fältet. (Om du har valt fältet **körningsnamn** i föregående steg är det här värdet som är namnet på rapporten. Om du har valt fältet **körningstid** kommer det att vara den tidpunkt då rapporten genererades.)
    6. Lägg till fler rader till tabellen **Intervall** som du önskar till tills du har identifierat den rapport som du söker efter, om det behövs.

1. Välj **OK** om du vill spara inställningarna och stänga dialogrutan.
1. Välj **Spara** om du vill spara dina exportinställningar.
1. PÅ fliken **exportalternativ** välj **exportera nu** för att generera exportfilen.
1. På sidan **körningssammanfattning** som visas kan du se statusen för exportjobbet och en lista över de enheter som har exporterats. I avsnittet **Bearbetningsstatus för entitet**, välj **Lagervärde** i listan och välj sedan **Hämta fil** för att hämta de data som exporteras från den enheten.

Mer information om hur du använder datahantering för att exportera data finns i [översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Generera en standardrapport för lagervärde

Använd följande procedur när du genererar en standardrapport för **lagervärde**.

1. Gå till **Kostnadshantering \> Förfrågningar och rapporter \> Lagerredovisning – statusrapporter \> Lagervärde**.
1. I dialogrutan **Lagervärdesraport** anger du följande fält på snabbfliken **Parametrar**:

    - **Namn** – Ange ett unikt namn för rapporten.
    - **ID** – Välj den [konfiguration för lagervärdesrapport](#report-configuration) som ska användas för rapporten. Konfigurationen etablerar alternativ för de kolumner och rader som ska omfattas av din rapport.
    - **Datumintervall** – Använd fälten i det här avsnittet för att definiera de poster som inkluderas i rapporten. Om du vill definiera datumintervallet kan du antingen välja ett förinställt intervall (relativt rapportens genereringsdatum) i fältet **datumintervallkod** eller välja särskilda datum i fälten i fälten **Från datum** och **Till datum**.

1. På snabbfliken **Poster som ska ingå** kan du konfigurera filter och begränsningar för att definiera vilka data som ska ingå i rapporten. Välj **Filter** för att öppna en standarddialogruta för Power Query-redigeraren, där du kan ange urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som för andra typer av frågor i Supply Chain Management.
1. På snabbfliken **kör på snabbfliken bakgrund** anger du hur, när och hur ofta rapporten ska genereras. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** om du vill använda inställningarna och stänga dialogrutan. Rapporten visas.

## <a name="reading-inventory-value-reports"></a>Läsa lagervärdesrapporter

Detta avsnitt innehåller information om hur du läser och förstår en lagervärdesrapport.

Supply Chain Management stöder följande två viktiga koncept som är relaterade till lagerstatus:

- **Ekonomiskt uppdaterat** – Detta koncept anger att lagertransaktioner redan har fakturerats. För tillverkningsorder visar det slutet på en tillverkningsorder.
- **Fysisk uppdatering** – Detta koncept visar att lagertransaktionerna ännu inte har fakturerats, men däremot att de har tagits emot eller levererats. För tillverkningsorder indikerar det att material har plockats eller att tillverkningsordern har rapporterats som färdig.

När du förstår dessa två begrepp bör det vara lätt att förstå följande kolumner i rapportens utdata:

- **Lager: Ekonomisk kvantitet** – Den kvantitet som har uppdaterats finansiellt.
- **Lager: Ekonomiskt belopp** – Beloppvärdet för lager som har uppdaterats ekonomiskt.
- **Lager: Fysiskt bokförd kvantitet** – Den kvantitet som har uppdaterats fysiskt.
- **Lager: Fysiskt bokfört belopp** – Beloppvärdet för lager som har uppdaterats fysiskt.
- **Lager: Fysisk kvantitet som inte bokförts** – Den kvantitet som har lagertransaktioner men som inte har bokförts i redovisningen. Du har till exempel en artikelmodellgrupp där alternativen **Bokför fysiskt lager** och **Bokför ekonomiskt lager** har rensats och du har en artikel som är kopplad till den gruppen. Sedan skapar du en inköpsorder, tar emot den och fakturerar den. Om du nu granskar lagervärdesrapporten för artikeln kommer du att se att kvantiteten och värdet på inköpsordern visas i kolumnerna **Lager: Fysisk ej bokförd kvantitet** och **Lager: Fysiskt belopp ej bokfört**.
- **Lager: Fysiskt belopp som inte har bokförts** – Du kan konfigurera dina rapporter så att de visar icke-bokförda belopp. Om du använder rapporten för lageravstämning ska du däremot inte använda det här värdet. I annat fall kommer beloppet inte att bokföras i redovisningen.
- **Lager: Kvantitet** – Den totala kvantiteten för alla kvantitetskolumner i rapporten.
- **Lager: Belopp** – Den totala kvantiteten för alla beloppskolumner i rapporten. När du utför lageravstämning ska du inte använda den här kolumnen om rapporten innehåller kolumnen **Lager: Fysiskt belopp ej bokfört**. I det här fallet måste du exkludera beloppet för **Lager: Fysiskt belopp som ej har bokförts** från det totala beloppet.
- **Genomsnittlig enhetskostnad** – Det totala beloppet delat med total kvantitet.

Vanligtvis används en lagervärdesrapport när du visar lagervärde och kvantitet. Ibland visar rapporten emellertid inte alla relevanta lagerdimensioner. Om du inte ser de dimensioner som du förväntar dig ska du validera följande inställningar:

- Granska grupper för artikellagring och spårningsdimensioner. Endast dimensioner där alternativet **Ekonomiskt lager** har aktiverats kan visas i rapporten.
- Gå till **Kostnadshantering \> Konfiguration av policyer för lagerredovissning \> Lagervärdesrapporter**, välj den rapportkonfiguration som du använde för att generera rapporten, och se till att erforderliga lagerdimensioner har valts i kolumnen **Visa**.

Du har till exempel en artikel med artikelnumret *A0001*. I lagringsdimensionsgruppen är endast webbplatsen aktiverad för ekonomiskt lager. Både webbplats och lagerställe har aktiverats för fysiskt lager. I dimensionsgruppen för spårning aktiveras batchnumret för fysiskt lager men inte för ekonomiskt lager. Du använder sedan en rapportkonfiguration där webbplats, lagerställe och batchnummer väljs. När du visar rapporten visas bara ett värde för webbplatsen. Kolumnerna för lagerställe och batchnummer är tomma. Som det här exemplet visar kan lagervärdesrapporter endast visa lagerdimensioner som är aktiverade för ekonomiskt lager.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
