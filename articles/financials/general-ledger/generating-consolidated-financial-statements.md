---
title: Generera konsoliderade bokslut
description: Det här avsnittet beskrivs de olika situationer där du kan skapa konsoliderade bokslut.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 55c5d02ca4e487782f020aa5eb85e6ebb36d4ce8
ms.sourcegitcommit: 9b4c3fff2f30006b7bb491ef6ffe89d41bcbfa11
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2019
ms.locfileid: "1863710"
---
# <a name="generate-consolidated-financial-statements"></a>Generera konsoliderade bokslut

[!include [banner](../includes/banner.md)]

Det här avsnittet beskrivs de olika situationer där du kan skapa konsoliderade bokslut.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Konsolideringar på en nivå och flera nivåer över juridiska personer
Den enklaste metoden för att konsolidera data med hjälp av ekonomisk rapportering är att använda rapportträd för att samla in data mellan företag som har samma kontoplan och räkenskapsperioder. Nedan följer stegen på hög nivå för att konsolidera hjälp av ett rapporteringsträd.

1. Skapa en raddefinition och se till att alla lämpliga konton i alla företag ingår i rader.
2. Skapa en kolumndefinition som innehåller de kolumner som krävs för den rapport som du skapar.
3. Skapa ett rapporteringsträd som innehåller en rapporteringsnod för varje företag som du använder på konsoliderade rapporter.

> [!TIP]
> Mer information om hur du skapar och hanterar raddefinitioner och kolumndefinitioner och rapporteringsträd, se[Komponenter för ekonomisk rapport](../../dev-itpro/analytics/financial-report-components.md).

Följande bild visar hur du kan använda rapporteringsträdsdefinitioner i ekonomisk rapportering för att identifiera varje företag som du ska konsolidera.

![Rapporteringsträddefinitioner](./media/reporting-tree-definition.png "Rapporteringsträddefinitioner")

Som den konsoliderade rapporten i följande illustration visar, när du använder rapporteringsträdet tillsammans med en rapportdefinition kan du se varje företag separat. Konsoliderade belopp visas på sammanfattningsnivån.

![Konsolidera belopp sammanfattningsnivå](./media/consolidate-amount-summary-level.png "Konsolidera belopp sammanfattningsnivå")

Du kan också skapa rapporteringsträd på flera nivåer som innehåller så många nivåer som behövs. Följande bild visar rapporteringsträdsdefinitioner på flera nivåer med översikter av världsomspännande region.

![Rapporteringsträdsdefinitioner på flera nivåer med översikt per region](./media/multilevel-reporting-tree-definition-roll-ups-worldwide-region.png "Rapporteringsträdsdefinitioner på flera nivåer med översikt per region")

Följande bild visar rapporteringsträdsdefinitioner på flera nivåer med översikter per funktion.

![Rapporteringsträdsdefinitioner på flera nivåer med översikt per funktion](./media/multilevel-reporting-tree-definition-roll-ups-by-function.png "Rapporteringsträdsdefinitioner på flera nivåer med översikt per funktion")

### <a name="viewing-companies-side-by-side"></a>Visa företag sida vid sida
Många kunder föredrar rapporter där företagen visas sida vid sida och där en kolumn visar den konsoliderade summan. Det här formatet är lätt att uppnå när du har skapat rapporteringsträdet. Nedan följer högnivåsteg för att visa företag sida vid sida på konsoliderade bokslut.

1. Skapa en kolumndefinition som omfattar en **Ekonomisk dimension** för respektive företag.
2. Använd fältet **rapporteringsenhet** för att välja trädet och rapporteringsenheten för varje kolumn.
3. Valfritt: Lägg till rubriker och totala kolumner.

Följande bild visar en kolumndefinition i formatet sida vid sida.

![Kolumndefinition i formatet sida vid sida](./media/column-definition-side-by-side-format.png "Kolumndefinition i formatet sida vid sida")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Konsolideringar som använder organisationsstrukturer som skapas från juridiska personer
Organisationshierarkier med dimensioner eller juridiska personer som dynamiskt skapar rapportträdsdefinitioner i ekonomiska rapporter. Ett enkelt sätt att förenkla konsolideringar är att lägga till en organisationshierarki i rapporten i ekonomisk rapportering. Baserat på rapportdatumet väljer ekonomisk rapportering organisationshierarkin på eller före giltighetsdatumet enligt följande bild.

![Dynamiskt skapa rapportträdsdefinition](./media/dynamically-create-reporting-tree-definitions.png "Dynamiskt skapa rapportträdsdefinition")

## <a name="consolidations-that-involve-eliminations"></a>Konsolideringar som involverar elimineringar
Elimineringstransaktioner är en vanlig del av konsolideringsprocessen. I det här exemplet tas fem konton bort under konsolideringen: 142600, 211400, 401420, 401180 och 510820. Företag kan ställa in sina koncerninterna konton på olika sätt. Vissa företag ställer t.ex. in den sista siffran på 9 om kontot används i koncerninterna transaktioner. Oavsett vilken metod, om du känner till det koncerninterna konton, kan du visa elimineringar på de konsoliderade bokslut.

Följande bild visar en kolumndefinition för en konsoliderad resultaträkning. Tre koncerninterna resultatkonton definieras med hjälp av dimensionsfiltret för varje företag. Kolumn D innehåller konton för eliminering endast för USMF-företagets och kolumn E innehåller elimineringar endast för DEMF-företaget. Både kolumn D och E är inställda så att de **inte** skrivs ut i bokslutet.

![Kolumndefinition för konsoliderad resultaträkning](./media/column-definition-consolidated-income-statement.png "Kolumndefinition för konsoliderad resultaträkning")

När rapporten genereras beräknas elimineringsbeloppen i kolumn F, G och H och de summeras i kolumn I. Kolumn J visar konsoliderade belopp. Dessa konsolideringsbelopp är exklusive elimineringar för USMF-, USRT- och DEMF-företag.

> [!TIP]
> Skapa en andra rapport som endast visar elimineringsposter och använd dem i en rapportgrupp som innehåller en konsoliderad rapport. På så sätt har du all information som behövs för att skapa eventuella journaltransaktioner som krävs.

Följande illustration visar konsoliderad rapport.

![Konsoliderad rapport resultaträkning](./media/consolidated-report-income-statement.png "Konsoliderad rapport resultaträkning")

Om du använder konton, dimensioner eller båda kan du med, ekonomisk rapportering filtrera ut elimineringsposter med dimensionsfiltreringsmöjligheterna.

## <a name="minority-interest"></a>Minoritetsränta
Ett företag kan äga bara en procentandel av ett annat företag. I denna situation, när du skapar en konsoliderad rapport, är det viktigt att du ta hänsyn till procentsatsen som företaget äger. Ekonomisk rapportering har flera sätt att visa minoritetsränta beroende på användarpreferens. Ett sätt är att använda sammanslagningsprocentsatsen i rapportträdsdefinitionen. Ett annat sätt är att visa minoritetsägare som en separat rad i en rapport.

### <a name="using-the-reporting-tree-definition"></a>Använda rapportträdsdefinition
I rapportträdsdefinitionen, ange procentandelen av ägarskap i kolumnen **sammanslagning %** (kolumn H) enligt följande bild. När rapporten har genererats används denna procentsats för att beräkna det konsoliderade beloppet. I detta exempel äger Contoso endast 80 procent av Contoso Tyskland. Du kan antingen ange **80** eller **,8** i kolumnen **sammanslagning %** och 80 procent ska slås samman till konsoliderad nivå.

> [!NOTE]
> Du kan använda denna ägarskapsprocentandel för rapporteringsenheten, inte bara på företagsnivå. 

![Använda procentsatsen i rapportträddefinition](./media/Using-reporting-tree-definition-percentage.png "Använda procentsatsen i rapportträddefinition")

När rapporten skapas, visar Contoso Tyskland-rapporten 100 procent av det totala försäljningsbeloppet och 80 procent av beloppet ska fördelas och slås samman med den konsoliderade nivån för försäljning.

Om du äger mindre än 1 procent av ett företag kan du markera kryssrutan **Tillåt sammanslagning lägre än 1%** på fliken **ytterligare alternativ** på sidan **rapportinställningar** enligt följande illustration. I det här fallet behandlas värden i kolumnen **sammanslagning %** i rapportträdet som mindre än 1 procent. Om du till exempel anger **.8**, kommer 0,8 procent slås samman upp till den konsoliderade nivån, inte 80 procent. Alternativt kan du uppnå samma resultat genom att lämna kryssrutan **Tillåt sammanslagning lägre än 1%** tom och ange **,008** i kolumnen **sammanslagning %**.

![Alternativ för rapportinställning](./media/reporting-setting-options.png "Alternativ för rapportinställning")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>Visa ägarskap som en separat rad i den konsoliderade rapporten
Ett annat alternativ för minoritetsränta är att visa 100 procent av dotterbolaget för varje rad på rapporten men subtrahera den icke-bestämmande räntan från nettoresultatet.

Som illustrationen visar kan ett **IF THEN ELSE**-utdrag och kolumnbegränsning i raddefinitionen användas vid beräkning av minoritetsränta i ekonomiska rapporter.

![Visa ägarskap som en separat rad i den konsoliderade rapporten](./media/Showing-ownership-separate-row-consolidated-report.png "Visa ägarskap som en separat rad i den konsoliderade rapporten")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Flera kontoplaner över juridiska personer
Ofta har olika juridiska enheter olika kontoplaner men vill skapa konsoliderade bokslut. I det här fallet kan ekonomisk rapportering användas för att konsolidera data, så att du kan skapa konsoliderade ekonomirapporter. Nedan följer stegen på hög nivå för att konsolidera när olika kontoplaner existerar över juridiska personer.

1. Skapa en raddefinition som har flera länkar till ekonomiska dimensioner. Det bör finnas en länk till respektive Kontoplan.
2. Använd rapportenhet för begränsning i kolumndefinitionen för att tilldela varje företag till lämplig kolumn.


Flera länkar till ekonomiska dimensioner kan läggas till varje rad i raddefinition för varje företags unika kontoplan. I följande illustration använder USMF-företaget uppsättningen konton i den första kolumnen **länk till ekonomiska dimensioner** (kolumn J) och DEMF-företaget använder kontona i andra kolumnen **länk till ekonomiska dimensioner** (kolumn K).

> [!TIP]
> Mer information om cellen **Länk till Ekonomiska dimensioner** finns i Ange länk till ekonomiska dimensioner.

![Ange kontons första länk till ekonomiska dimensioner](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Ange kontons första länk till ekonomiska dimensioner")

Du kan använda rapportträd för att definiera vilken länk till ekonomiska dimensioner från raddefinitionen som används för varje företag. Välj raddefinitionen i kolumn E och välj sedan lämplig radlänk i kolumn F, vilket visas i följande illustration.

![Raddefinitionen länka ekonomiska dimensioner används](./media/link-financial-dimensions-row-definition-used.png "Raddefinitionen länka ekonomiska dimensioner används")

> [!TIP]
> När du skapar länkar till ekonomiska dimensioner, använd beskrivningen för att identifiera de företag som varje länk gäller för. På så sätt kan du enklare välja rätt företag när du skapar ett rapportträd. I kolumndefinitionen kan du i fältet **rapporteringsenhet** begränsa varje kolumn till en enhet i rapportträdet så att du kan se informationen sida vid sida. Om du inte anger ett visst företag för en kolumn, visas konsoliderade data för alla företag.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Olika räkenskapskalendrar över flera juridiska personer
Olika juridiska enheter kan ha olika räkenskapskalendrar men måste fortfarande skapa konsoliderade bokslut. Det finns två sätt att konsolidera när olika räkenskapsperioder finns över juridiska personer:

- Skapa en kolumndefinition och använd period och år för att mappa lämpliga perioder för varje företag.
- Vid **inställningar**\>**andra**\>**ytterligare alternativ**, välj om du vill konsolidera med periodens slutdatum eller periodnumret.

När du utformar kolumndefinitionen för flera företag som har olika räkenskapsperioder är det viktigt att du noggrant överväger vilket företag som ska tilldelas till fältet **företagsnamn** i rapportdefinitionen. Räkenskapskalendern som ska användas som räkenskapsårets baskalendern för rapportdefinitionen. Tabellen nedan visar inställningen för räkenskapsperiod för USMF- och INMF-företag. För konsoliderade rapporter vill du använda räkenskapskalendern som USMF använder. Kolumnen ”mappning” visar motsvarande perioder och år för varje företag om en rapport genererats för 30 juni 2018.

| Företag   | Räkenskapsår                                  | Mappning                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Räkenskapsår 1 juli till och med 30 juni          | Period 12, räkenskapsår 2018 | 
| INMF      | Kalenderår, 1 januari till 31 december | Period 6, räkenskapsår 2018  |

I följande exempel anges USMF-företaget i fältet **företagsnamn** i rapportdefinitionen. Därför ska USMF-företagets räkenskapskalender användas som räkenskapsårets baskalender. I det här exemplet när en rapport har genererats för 30 juni 2018 använder USMF-företaget BASE-perioden som definieras som period 12 i rapportdefinitionen. INMF-företag använder BASE-6, d.v.s. period 6. Båda kolumnerna innehåller data för juni 2018.

![Rapportens basperiod](./media/report-base-period.png "Rapportens basperiod")

I följande illustration visas alternativen i rapportdefinitionen som låter dig välja om periodnumret eller periodens slutdatum används för konsolideringen.

![Alternativ för periodnummer för rapportdefinition](./media/options-report-definition-period-number.png "Alternativ för periodnummer för rapportdefinition")

## <a name="business-unit-consolidations"></a>Konsolideringar av affärsenhet
Det här avsnittet har fokuserat på rapportträdsdefinitioner och organisationshierarkier i ekonomisk rapportering för konsolidering. Du kan också använda rapportträdet för att skapa konsolideringsrapporter för affärsenhet såsom rapporter om internationell försäljning eller operationer. Dessa rapporter är obligatoriska. För att skapa dem, markera ett företag och en dimension för varje enhet som du vill konsolidera på. I bilden nedan utförs exempelvis uppföljning av affärsenhet genom att upprepa varje företag i kolumnen **företag** (kolumn A) och identifierar en grupp av avdelningsdimensionsvärden per företag i kolumnen **dimensioner** (kolumn D).

![Konsolideringsrapporter för affärsenhet](./media/business-unit-consolidation-reports.png "Konsolideringsrapporter för affärsenhet")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Konsolideringar som involverar flera rapportvalutor
Ekonomisk rapportering ger större flexibilitet när du visar faktisk, budget, budgetkontroll och budgetplaneringsdata i flera valutor. Du behöver inte göra några ytterligare inställningar i ekonomisk rapportering för att visa eventuella rapporter i vilken valuta som helst, när som helst för alla användare genom att föra över viktig inställningsdata.

### <a name="prerequisites"></a>Krav
För att korrekt beräkna konverterade saldon, kräver ekonomisk rapportering att kategorin **konto för balanserade vinstmedel** tilldelas till kontot för balanserade vinstmedel i listan **huvudkonto**. Ekonomisk rapportering stöder inte bokföring till balanserad vinst eller förlust. Om transaktioner bokförs till kontot för balanserade vinstmedel beräknas inte konverterade saldona korrekt. Vi rekommenderar att användare ställer in ett ytterligare konto för balanserad vinst eller förlust för att bokföra justeringar för balanserad vinst eller förlust.

På huvudkontot måste fälten **Valutakurstyp för ekonomisk rapportering** och **Valutakonverteringstyp** på snabbfliken **ekonomisk rapportering** måste anges för varje konto enligt följande illustration. Du kan göra detta på grundval av konto för konto eller använda mallarna för att enkelt flytta ned ändringar.

- I fältet **Valutakurstyp för ekonomisk rapportering** välj den valutakurstyp som innehåller de valutor och växelkurser som gäller för kontot. Den här tabellen med valutor och valutakurser tillämpas på verkliga data i redovisning.
- I fältet **Valutaregistreringstyp**, välj metoden som används för att beräkna kontots valutakurs. Denna valutametod används för både faktiska och budgetdata i ekonomisk rapportering.

![Ekonomisk rapportering huvudkonton](./media/Financial-reporting-main-accounts.png "Ekonomisk rapportering huvudkonton")

För budget, budgetkontroll och budgetplaneringsdata definieras växelkurstyp på sidan **redovisning**. Den tabellen används för att hämta valutakurser och valutakonverteringstyp som tilldelas kontot som kommer att användas.

### <a name="currency-translation-methods"></a>Valutaregistreringsmetoder
Det finns fyra alternativ för att beräkna valutakurser i ekonomisk rapportering:

- **Viktat medelvärde** – den här metoden används oftast för resultatkonton. Det använder följande formel:

    (Valutakurs × gällande dagar) / dagar i period

- **Medelvärde** – den här metoden är en alternativ metod för resultatkonton. Det använder följande formel:

    Summan av valutakurser / antal valutakurser

- **Aktuella** – den här metoden används oftast för balansräkningskonton. Valutakursen som används är kursen på eller före datumet för rapporten eller kolumnen i ekonomiska rapporter.
- **Transaktionsdatum** – den här metoden används för konton för anläggningstillgångar. Valutakursen som används är kursen den dag då anläggningstillgången förvärvades. Om en kurs inte anges för detta datum, används den föregående kursen som angavs närmast anskaffningsdatumet för tillgången.

### <a name="report-designer-options-for-currency-translation"></a>Rapportdesigneralternativ för valutaomräkning
I ekonomisk rapportering kan alla rapporter visas i ett antal rapporteringsvalutor Följande fält i rapportdefinitionen stöder denna funktion:

- Avsnittet **valutainformation** på sidan **rapportdefinition**. Det här avsnittet beskriver den valuta värdena visas i när en rapport har genererats.
- En ny kryssruta **Ta med alla rapporteringsvalutor**. När den här kryssrutan är markerad läggs en rapport för varje rapportvaluta till i rapportkön in när rapporten som använder företagets funktionella valuta har genererats. Om kryssrutan är avmarkerad kan du fortfarande välja rapportvaluta i Webbvisning. I det här fallet bearbetas rapporteringsvalutan endast om du markerar den.

Alternativen i rapportdefinitionen låter dig enkelt konvertera en rapport till rapporteringsvalutor. Därför måste du kanske eliminera dubbla rapportdefinitioner som bara skiljer sig åt i de valutor som används. Om du vill ha en rapport som visar flera valutor sida vid sida, kan du fortsätta att använda fältet **valutavisning** på sidan **kolumndefinition** för att konvertera aktuella kolumnen i rapporten till en alternativ rapporteringsvaluta.

### <a name="currency-translation-adjustment"></a>Justering av valutakonvertering
Justeringen av valutakonvertering (CTA) är skillnaden mellan de kurser som används för att beräkna balanskonton och den kurs som används för resultatkonton. Den här skillnaden gör att balansräkningen inte är i balans. Du kan använda ekonomisk rapportering för att beräkna CTA på två sätt:

- Använd sidan **Avrundningsjusteringar** i raddefinitionen som visas i följande bild.

    ![Avrundningsjustering för justering av valutakonvertering](./media/Currency-translation-adjustment-rounding-adjustments.png "Avrundningsjustering för justering av valutakonvertering")

    När du anger den rad som ska visa avrundningsjusteringen (CTA), raden för summa tillgångar, summa skulder och kapital och det tröskelvärde du är bekväm med, kommer ekonomisk rapportering beräkna skillnaden och placera den på önskad rad. En rad som heter **avrundningsjustering** skapas och visas vid detaljgranskning, enligt följande illustration.

    ![Detaljgranskning av avrundningsjustering](./media/rounding-adjustment-drill-down.png "Detaljgranskning av avrundningsjustering")

- Placera alla konton i ett intervall från tillgångar som utgifter. I följande illustration visas att skillnaden kommer att vara samma som avrundningsjustering (CTA). Du kan därför använda den som en kontrollera total och kontrollera att sidan för avrundningsjustering inte innehåller några kontosaldon som har missats.

    ![Kontroll av avrundningsjusteringsform](./media/rounding-adjustment-form-check.png "Kontroll av avrundningsjusteringsform")

### <a name="balance-calculation-approach"></a>Beräkningsmetod för saldon
För att få korrekt konverterade belopp när valutor används, använder ekonomisk rapportering följande beräkningsmetoder för saldon:

- **Viktat medelvärde och genomsnitt** – varje period beräknas för viktat medelvärde och summeras för kolumner såsom kvartal och år till dagens datum.
- **Historisk** – alla konton som använder den historiska konverteringsmetoden återgår alltid till transaktionsdatum. Om ett anskaffningsdatum är kopplat till transaktionen, används detta datum för att få valutakursen. Varje period summeras sedan och lagras för att förbättra beräkningstiden.
- **Aktuella** – beräknade och totala kolumner, till exempel kolumner för varje kvartal och år till dags dato, beräknas till punkttariffen som anges i kolumnen eller i rapporten. Till exempel kolumnen **kvartal 1** använder kursen 31 mars om ett kalenderår används.

## <a name="additional-resources"></a>Ytterligare resurser

Mer information om konsolidering och valutaöversättning finns i det överordnade avsnittet i det här avsnittet [Ekonomisk konsolidering och valutaomräkning](./financial-consolidations-currency-translation.md).

Information om hur du anger information om onlinekonsolideringar finns i [konsolidera online](./consolidate-online.md).
