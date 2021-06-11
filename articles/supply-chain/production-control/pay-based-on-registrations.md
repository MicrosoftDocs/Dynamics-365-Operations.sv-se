---
title: Lön baserat på registreringar
description: Det här avsnittet beskriver hur lön beräknas utifrån arbetarregistreringar.
author: johanhoffmann
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 39786323e1ea11a960332e6e0a01f6ef8de1838d
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2021
ms.locfileid: "6103009"
---
# <a name="pay-based-on-registrations"></a>Lön baserat på registreringar

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver i detalj hur lön beräknas utifrån arbetarregistreringar. Det innehåller exempel som visar hur resultatet påverkas av de olika kombinationerna av de inställningsalternativ som är tillgängliga för beräkningen. Nedan följer några av de områden som omfattas:

- Flextid
- Övertid
- Raster
- Växlingskoder
- Löneposter
- Löneavtal
- Beräkningsparametrar Tid och närvaro
- Frånvaro

## <a name="the-use-of-flex-time"></a>Användning av flextid

Perioder av flextid ställs in i tidsprofilerna som används i Tid och närvaro. Det finns två flexprofiltyper: **Flex+** och **Flex-**. När en anställd registrerar tid i en Flex+-period, ökar arbetarens flexsaldo med de timmar som har arbetats. Arbetaren får inte någon kompensation för de timmar som arbetades under Flex+-perioden. Arbetaren kan emellertid ta ledigt under Flex-perioderna och ersättas med timmarna från sitt flexsaldo. Därför beaktas ledig tid under flexperioderna som frånvaro av systemet.

## <a name="scenarios-based-on-flex-periods"></a>Scenarier baserat på flexperioder

Två scenarier som följer baseras på en flexprofil som representerar en arbetsdag. I båda scenarier beräknas lön enligt flexperioden där arbetaren stämplar in och ut.

### <a name="flex-profile-for-one-workday"></a>Flexprofil för en arbetsdag

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Scenario 1: En arbetare stämplar in under en Flex+-period och stämplar ut under en Flex--period

Arbetarens registreringar för dagen ser ut så här.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 06:30 | 06:30 |
| Produktionsjobb            | 06:30 | 14:45 |
| Stämpla ut                 | 14:45 | 14:45 |

Arbetarens registreringar för dagen beräknas och överförs till betalning på sidan **Godkänn** (**Tid och närvaro**&gt;**Granska och godkänna**&gt;**Godkänn**). När registreringarna har räknats visas resultatet av beräkningen på fliken **Tider**. 

För att förstå det här scenariot, se följande fält.

| Flex + | Flex - | Tid | Betald tid |
|--------|--------|------|----------|
| 0.50   | 0.75   | 8,25 | 8,50     |

#### <a name="calculation-of-flex"></a>Beräkning av Flex+

Enligt flexprofilen är tiden mellan 06:00 och 07:00 Flex+-period. Om arbetaren därför stämplar in klockan 06:30 tjänar han eller hon 0,5 timmar. Denna tid läggs till i arbetarens flexkonto.

#### <a name="calculation-of-flex-"></a>Beräkning av Flex-

Enligt flexprofilen börjar Flex--perioden kl. 14:30 och slutar 15:30. Om arbetaren därför stämplar ut kl. 14:45 kommer de 45 minuter (0,75 timmar) som finns kvar i Flex--perioden att registreras som betald tid och samma tidsmängd dras av från arbetarens flexkonto. De 45 minuterna inkluderas i betald tid eftersom arbetaren beviljas lön för återstående 45 minuter i Flex--perioden. Om arbetaren är frånvarande under Flex--perioden kommer de 45 minuterna att dras av från hans flexkonto.

#### <a name="calculation-of-time"></a>Beräkning av tid

Tiden beräknas som tiden mellan instämpling och utstämpling, det vill säga 06:30 till 14:45 med motsvarande 8,25 timmar.

#### <a name="calculation-of-pay-time"></a>Beräkning av betald tid

Betald tid är den tid som en arbetare beviljas betalning för. I det här scenariot är arbetaren är på arbetet 8,25 timmar (**Tid**). Men **Betald tid** beräknas som 8,50 timmar, eftersom han eller hon beviljas lön under Flex--perioden efter att han stämplade ut. Den betalda tiden är lika med den planerade arbetstiden eftersom Flex+-tid läggs till i arbetarens flexkonto, inte till den betalda tiden. Frånvarotiden under Flex--perioden kompenseras av den betalda tiden och dras av från arbetarens flexkonto.

| Tid              | Registreringstyp | Betald tid (timmar)      |
|-------------------|-------------------|-----------------------|
| 06:30 - 07:00 | Flex+             | 0                     |
| 07:00 - 14:45 | Standardtid     | 7,75                  |
| 14:45 – 15:30 | Flex-             | 0,75 (frånvaroperiod) |
|                   | Totalt             | 8,50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Scenario 2: En anställd arbetar under hela Flex--perioden och arbetar även övertid

Arbetarens registreringar för dagen ser ut så här.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 06:30 | 06:30 |
| Produktionsjobb            | 06:30 | 17:00 |
| Stämpla ut                 | 17:00 | 17:00 |

När du har beräknat journalregistreringarna på sidan **Godkänn** kan du visa resultatet av beräkningsresultat på fliken **Gånger**. För att förstå det här scenariot, se följande fält.

| Flex + | Flex - | Tid  | Betald tid | Betald övertid |
|--------|--------|-------|----------|--------------|
| 0.50   | 0,00   | 10,50 | 10,00    | 1.50         |

#### <a name="calculation-of-flex"></a>Beräkning av Flex+

Enligt flexprofilen är tiden mellan 06:00 och 07:00 Flex+-period. Om arbetaren stämplar in klockan 06:30, får hon därför 0,5 timmars Flex+-tid på sitt flexsaldot.

#### <a name="calculation-of-flex-"></a>Beräkning av Flex-

Eftersom arbetaren arbetar under Flex+-perioden beräknas inte Flex-. Flex- beräknas endast om arbetaren är frånvarande under Flex--perioden. Från ett betalningsperspektiv beviljas arbetaren den lönesats som har definierats för standardtid om hon arbetar under Flex--perioden. Om arbetaren är frånvarande under Flex--perioden kommer de 45 minuterna att dras av från hennes flexkonto.

#### <a name="calculation-of-time"></a>Beräkning av tid

Tiden beräknas som tiden mellan instämpling kl. 06:30 och utstämpling kl. 17:00, eller 10,50 timmar.

#### <a name="calculation-of-pay-time"></a>Beräkning av betald tid

I det här scenariot arbetar arbetaren 10,50 timmar (**Tid**). Men **Betald tid** beräknas som 10,00 timmar eftersom arbetaren inte beviljats lön under Flex+-perioden.

#### <a name="calculation-of-pay-overtime"></a>Beräkning av betald övertid

| Tid               | Registreringstyp | Betald tid (timmar) |
|--------------------|-------------------|------------------|
| 06:30 - 07:00  | Flex+             | 0                |
| 07:00 - 14:30  | Standardtid     | 7,50             |
| 14:30 – 15:30  | Flex-             | 1,00             |
| 15:30 – 17:00 | Övertid          | 1.50             |
|                    | Totalt             | 10,00            |

### <a name="generation-of-pay-items"></a>Generering av löneposter

Arbetarregistreringar för dagen kan överföras från sidan **Godkänn**. Under överföringsprocessen genereras löneposter och överförda registreringar. Löneposter representerar en uppdelning av betalningstid i standardtid, övertid, betald rasttid och så vidare.

Om du vill öppna listan över löneposter, välj **Tid och närvaro**&gt;**Granska och godkänna**&gt;**Godkänn**. Välj **Förfrågan**&gt;**Överförda registreringar**.

Betalningsposter ligger till grund för en arbetares lön. Du kan generera en fil som innehåller informationen från löneposterna och överföra filen till ett lönesystem.

Som en del av överföringsprocessen överförs tid och kostnad från produktions- och projektaktiviteter till produktions- och projektjournaler för att beräkna tid och kostnad som har spenderats. De överförda registreringarna utgör grunden för tids- och självkostnad per timme för tillverkningsorder och projekt. Du kan öppna de överförda registreringarna via menyn **Förfrågan** på sidan **Godkänn**.

För exempelvis scenario 2 genereras följande löneposter.

| Lönetyp     | Lönetyp | Löneantal | Kurs  | Totalkostnad |
|---------------|----------|-----------|-------|------------|
| Standardtid | 1 201     | 10,0      | 10    | 100        |
| Övertid      | 1301     | 1.50      | 5     | 7,50       |
|               |          |           | Totalt | 107,50     |

Löneposten för standardtid har en löneantal på 10 timmar som täcker standardtid, Flex--tid och övertid. Standardtid, övertid och Flex--tid konsolideras i en lönepost eftersom alla typer beräknas som standardtid, baserat på standardinställningen av en parameter på sidan **Beräkningsparametrar** (**Tid och närvaro**&gt;**Inställningar**&gt;**Beräkningsparametrar**). Övertiden beräknas ovanpå standardtiden med hjälp av en ytterligare sats på 5.

Om du vill klart särskilja på standardtid och övertid, så att löneantalet för lönetyperna endast omfattar den faktiska tid som spenderats på standardtid och övertid, måste löneantalet för standardtid beräknas som 8,50 och löneantal för övertid måste beräknas som 1,50.

Om du vill konfigurera systemet för att tydligt skilja standardtid och övertid, måste du utesluta övertid från standardtiden. Du måste också ändra inställningarna för lönetypen för övertid så att lönesatsen för övertid täcker alla betalningar för de timmar som har spenderats på övertid.

### <a name="exclude-overtime-from-the-standard-time"></a>Utesluta övertid från standardtiden

På sidan **Beräkningsparametrar**, välj **Övertid** som profilspecifikationstypen och ange alternativet **Betald tid** till **Nr**, som visas här.

| Reg.specifikation | Typ av profilspecifikation | Beräkning   | Inställning | Betald         | Inställning |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Arbetstid       | Övertid                   | Standardtid | Ja | Betald tid     | Nr  |
|                    |                            | Betald tid      | Ja | Betald övertid | Ja |

När du har justerat beräkningsparametrarna genereras följande löneposter.

| Lönetyp     | Lönetyp | Löneantal | Kurs  | Totalkostnad |
|---------------|----------|-----------|-------|------------|
| Standardtid | 1 201     | 8,50      | 10    | 85,0       |
| Övertid      | 1301     | 1.50      | 15    | 22,50      |
|               |          |           | Totalt | 107,50     |

> [!NOTE]
> Beräkningsparametrarna har en rekommenderad standardinställning. I allmänhet bör du vara försiktig när du ändrar parametrarna. För att återställa de rekommenderade standardinställningarna väljer du sidan **Beräkningsparametrar** och sedan **Återställ värden**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Tillåt en avvikelse från standardbetalningsprofilerna

På sidan **Profiler** (**Tid och närvaro**&gt;**Inställningar**&gt;**Tidsprofiler**&gt;**Profiler**) kan du ställa in profiltyper som innehåller växlingskoder och raster.

### <a name="switch-codes"></a>Växlingskoder

Du kan använda växlingskoder för att tillåta arbetarna avvika från sin profiltyp genom att ändra en annan profiltyp. Exempelvis kan en arbetare att ändra av Flex+-tid till övertid. En arbetare kan lägga till en växlingskod under registreringen eller du kan tilldela uppgiften att lägga till en växlingskod till godkännaren av registreringarna.

Innan du kan använda en växlingskod måste du definiera den som en typ av indirekt aktivitet. Du måste sedan lägga till växlingskoden till tidsprofilen för perioden som du vill tillåta en ändring av profiltypen för. Följ exempelvis dessa steg för att skapa en växlingskod där Flex+-perioden ändras från kl. 06:00 till 07:00 till övertid.

1. Skapa en växlingskod som heter **OTBCI (konvertera flex till övertid före instämpling)**. Välj **Tid och närvaro**&gt;**Hantera indirekta aktiviteter**&gt;**Indirekta aktiviteter**.
2. I kolumnen **växlingskod**, lägg till OTBCI till Flex+-raden i tidsprofilen.
3. I kolumnen **Sekundär**, lägg till profiltypen **Övertid**.

Överväg följande flexprofil som representerar en arbetsdag.

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

Här följer arbetarens registreringar för dagen.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 06:30 | 06:30 |
| Produktionsjobb            | 06:30 | 14:45 |
| Stämpla ut                 | 17:00 | 17:00 |

Följande löneposter genereras efter överflyttningen.

| Lönetyp     | Lönetyp | Löneantal | Kurs  | Totalkostnad |
|---------------|----------|-----------|-------|------------|
| Standardtid | 1 201     | 8,50      | 10    | 85,0       |
| Övertid      | 1305     | 1.50      | 15    | 22,50      |
|               |          |           | Totalt | 107,50     |

På sidan **Godkänn** ångra överföringen och använd sedan menyn **Växlingskod** för att lägga till växlingskoden **OTBCI**. När du överför registreringar en andra gång genereras följande betalningsposter.

| Lönetyp     | Lönetyp | Löneantal | Kurs  | Totalkostnad |
|---------------|----------|-----------|-------|------------|
| Standardtid | 1 201     | 8,50      | 10    | 80,0       |
| Övertid      | 1305     | 2.00      | 15    | 30,0       |
|               |          |           | Totalt | 107,50     |

> [!NOTE]
> När du använder växlingskoden ökas övertiden med 0,5 timme från 1,50 till 2,00. 0,5 timme är konverteringen av Flex+-tiden som har registrerats mellan 06:30 till 07:00 till övertid.

### <a name="breaks"></a>Raster

Raster från arbetet påverkar beräkningen av arbetarens lön. Raster definieras som en typ av indirekt aktivitet. Men kan även definieras som antingen **Betald** för att tillåta rasten att läggas till arbetarens lön eller **Obetald** för att förhindra att lägga till den till arbetarens lön. En rast kan också definieras som antingen **planerad** eller **registrerad**.

#### <a name="planned-breaks"></a>Planerade raster

Om ett företag har en fast rasttid, t.ex. en fast lunchrast, kan rasten vara fördefinierade i tidsprofilen. Då behöver arbetaren inte registrera rasten på jobbkortsidorna. Däremot kan rasten beräknas automatiskt när arbetarens registreringar beräknas på sidan **Godkänn**.

#### <a name="registered-breaks"></a>Registrerade raster

Om ett företag inte använder planerade raster kan arbetare registrera raster under arbetsdagen. Registrerade raster kan t.ex. användas om en arbetare arbetar mot en flextidsprofil som inte har definierat instämplings- och utstämplingstider. Registrerade raster är en typ av indirekt aktivitet. Arbetaren registrerar rasten på terminalsidan **Jobbkort** på enhetssidan **Jobbkort**. På båda dessa sidor kan användaren kan välja typ av rast i en lista med fördefinierade rastaktiviteter.

#### <a name="paid-and-unpaid-breaks"></a>Betalda och obetalda raster

Rastaktiviteter kan fungera som **betalda** eller **obetalda**. En betald rast inkluderas i beräkningen av betald tid och systemet använder den betalningstyp som definieras i löneavtalet för registreringstypen **Rast**.

### <a name="example-of-a-planned-break"></a>Exempel på en planerad rast

Överväg följande tidsprofil som inkluderar en obetald lunchrast.

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 12:00 | Måndag  |
| Rast         | 12:00 | 12:30 | Måndag  |
| Standardtid | 12:30 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

Här följer arbetarens registreringar för dagen.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 06:30 | 06:30 |
| Produktionsjobb            | 06:30 | 14:45 |
| Stämpla ut                 | 17:00 | 17:00 |

När du har beräknat journalregistreringarna på sidan **Godkänn** kan du visa resultatet av beräkningsresultat på fliken **Gånger**. För att förstå det här scenariot, se följande fält.

| Flex + | Flex - | Tid  | Betald tid | Obetald rasttid | Betald övertid |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1.50         |

> [!NOTE] 
> Systemet beräknar 0,5 timmars obetald rasttid och tiden ingår i den betalda tiden.

### <a name="example-of-a-registered-break"></a>Exempel på en registrerad rast

Överväg följande tidsprofil som intet inkluderar planerade raster.

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

Här följer arbetarens registreringar för dagen.

| Journalregistreringstyp | Start    | Slut      |
|---------------------------|----------|----------|
| Stämpla in                  | 06:30 | 06:30 |
| Produktionsjobb            | 06:30 | 17:00 |
| Rast                     | 12:03 | 12:32 |
| Stämpla ut                 | 17:00 | 17:00 |

När registreringarna beräknas, beräknas tiden för aktiviteterna.

| Journalregistreringstyp | Start    | Slut      | Tid  |
|---------------------------|----------|----------|-------|
| Stämpla in                  | 06:30 | 06:30 |       |
| Produktionsjobb            | 06:30 | 17:00 | 10,00 |
| Rast                     | 12:03 | 12:32 | 0.50  |
| Stämpla ut                 | 17:00 | 17:00 |       |

> [!NOTE]
> Tiden för rasten körs parallellt med tiden för aktiviteten (ett produktionsjobb, i det här exemplet). Detta beteende används alltid för rastaktiviteter. När registreringarna beräknas kontrollerar dras rasttiden av från aktivitetstiden. I det här fallet har produktionsjobbet en varaktighet på 10,50 timmar, men tiden beräknas som 10 eftersom 0,5 timmars rasttid dras från aktivitetstid.

När du har beräknat journalregistreringarna på sidan **Godkänn** kan du visa resultatet av beräkningsresultat på fliken **Gånger**. För att förstå det här scenariot, se följande fält.

| Flex + | Flex - | Tid  | Betald tid | Obetald rasttid | Betald övertid |
|--------|--------|-------|----------|---------------------|--------------|
| 0.50   | 0,00   | 10,50 | 9,50     | 0,5                 | 1.50         |

Om den planerade rasten i stället hade betalats av obetald, hade beräkningsresultatet sett ut så här.

| Flex + | Flex - | Tid  | Betald tid | Betald rasttid | Betald övertid |
|--------|--------|-------|----------|-----------------|--------------|
| 0.50   | 0,00   | 10,50 | 10,00    | 0,5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Löneposter och betalda raster

När du överför registreringar på sidan **Godkänn** genereras löneposter. En separat lönepost genereras för betalda raster.

Lönesatsen för betald rast bestäms av lönetypen som anges i löneavtalet för rasterna. Du kan ställa in självkostnad per timme för rasten för ett bestämt datumintervall istället för att använda en lönetyp.

Beakta följande tidsprofil.

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

Här följer arbetarens registreringar för dagen.

| Journalregistreringstyp | Start    | Slut      | Tid |
|---------------------------|----------|----------|------|
| Stämpla in                  | 07:00 | 07:00 |      |
| Produktionsjobb            | 07:00 | 15:00 | 7,5  |
| Rast (betald)              | 12:00 | 12:30 | 0,5  |
| Stämpla ut                 | 15:00 | 15:00 |      |

I det här exemplet ställs betalningstyp för standardtid in på **1201**, och en lönesats på **10** har ställts in i löneavtalet. Den betalda rasten har en lönetyp på **1301** och en lönesats på **8**. När registreringarna överförs genereras följande betalningsposter.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 7,50      | 10   |
| Flex-         | 1 201     | 0.50      | 10   |
| Rast (betald)  | 1301     | 0.50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Hur kostnaden för betalda raster tilldelas projekt och produktionsorder

Timkostnaden för projektaktiviteter och produktionsjobb kan ställas in så att de bestäms antingen genom lönesatser som beräknas i Tid och närvaro eller genom de kostnadskategorier som definieras för aktiviteterna.

Om du vill skapa kostnadskategorin, välj **Produktionskontroll**&gt;**Inställningar**&gt;**Tillverkningskörning**&gt;**Standarder för produktionsorder** och ange fältet **Kostnadskategori** till antingen **Ja** eller **Nej**.

- **Nej** – kostnad beräknas baserat på de lönesatser som definieras för registreringstyperna Tid och närvaro.
- **Ja** – kostnaden beräknas baserat på kostnadskategorier för produktions- och projektaktiviteter.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Kostnadsberäkning baseras på lönesatser som beräknas i Tid och närvaro

I följande exempel visas hur timkostnaden beräknas när kostnaden har ställts in så att den beräknas baserat på lönesatser.

Timkostnaden som används för tillverkningsorder och projekt beräknas under överföringsprocessen. Om du vill visa timkostnaden, öppna sidan **Godkänn** i Tid och närvaro och markera **Förfrågan**&gt;**Överförda registreringar**. Du hittar timkostnaden per registrering på fliken **Självkostnader**.

Överväg följande registreringar som använder samma tidsprofil som i föregående exempel.

| Journalregistreringstyp | Start    | Slut      | Tid |
|---------------------------|----------|----------|------|
| Stämpla in                  | 07:00 | 07:00 |      |
| Bearbeta (Order: 4711)     | 07:00 | 11:00 | 4    |
| Bearbeta (Order: 4712)     | 11:00 | 15:00 | 3,50 |
| Rast (betald)              | 12:00 | 12:30 | 0.50 |
| Stämpla ut                 | 15:00 | 15:00 |      |

Efter att du har överfört registreringarna genereras följande överförda registreringar.

| Registreringstyp     | Tid | Självkostnad per timme |
|-----------------------|------|---------------------|
| Instämpling              | 0,00 | 0,00                |
| Bearbeta (Order: 4711) | 4,00 | 10,00               |
| Bearbeta (Order: 4712) | 3,50 | 11,14               |
| Rast (betald)          | 0.50 | 0,00                |
| Stämpla ut             | 0,00 | 0,00                |

Beräkningen av självkostnaden per timme för betald rast beror på inställningen för direkta lönekostnader. Välj **Tid och närvaro**&gt;**inställningar**&gt;**Parametrar i tid och närvaro**. På fliken **Självkostnad** och **Direkta lönekostnader** på fältet **Standardtid** kan du välja **Ja**, **Nej**, eller **Allokering**.

- **Ja** – detta värde används för föregående exempel. Kostnaderna fördelas till den produktions- eller projektaktivitet som ska köras parallellt med den betalda rastaktiviteten. I exemplet är den här aktiviteten produktionsjobbet för 4712. Som du ser är självkostnaden per timme för betald rast 0 (noll) och tilldelas jobbet som körs parallellt med rasten.

    Den betalda rasten har en varaktighet på 0,5 timme och lönesatsen är 8. Därför är den totala kostnaden för den betalda rasten 4. Den totala kostnaden fördelas sedan till 3,5 timmars processjobb. Därför bidrar betald rast till 1,14 per timme till kostnaden (4 ÷ 3,5 = 1,14).

- **Allokering** – Betald rast fördelas jämnt mellan jobben som är registrerade för dagen. Om det här värdet används för föregående exempel genereras följande överförda registreringar.

    | Registreringstyp     | Tid | Självkostnad per timme |
    |-----------------------|------|---------------------|
    | Instämpling              | 0,00 | 0,00                |
    | Bearbeta (Order: 4711) | 4,00 | 10,53               |
    | Bearbeta (Order: 4712) | 3,50 | 10,53               |
    | Rast (betald)          | 0.50 | 0,00                |
    | Stämpla ut             | 0,00 | 0,00                |

    Den totala behandlingstiden för de två produktionsjobben är 7,5 timmar och den totala kostnaden för betald rast är 4. Därför beräknas kostnaden för rasten som 0,53 (= 4 ÷ 7,5).

- **Nej** – kostnaden för betald rast ökar inte timkostnaden för processaktiviteter.

    | Registreringstyp     | Tid | Självkostnad per timme |
    |-----------------------|------|---------------------|
    | Instämpling              | 0,00 | 0,00                |
    | Bearbeta (Order: 4711) | 4,00 | 10,00               |
    | Bearbeta (Order: 4712) | 3,50 | 10,00               |
    | Rast (betald)          | 0.50 | 0,00                |
    | Stämpla ut             | 0,00 | 0,00                |

## <a name="absence"></a>Frånvaro

En frånvarokod används för att registrera perioden för en arbetares frånvaro. Liksom raster och växlingskoder är en frånvarokod en typ av en indirekt aktivitet. Frånvarotid kan antingen vara planerad eller registrerad och frånvaro kan vara giltig eller ogiltig. Exempel på giltig frånvaro är ett läkarbesök, seminarium eller jurytjänst. Ogiltig frånvaro är frånvaro som inte har någon bra anledning, som till exempel när en arbetare kommer försent till jobbet. Vanligtvis medför giltig frånvaro inte avdrag lön för en anställd, medan ogiltig frånvaro medför avdrag.

### <a name="planned-absence"></a>Planerad frånvaro

Du kan skapa planerad frånvaro för anställda på sidan **Skapa planerad frånvaro** (**Tid och närvaro**&gt;**Skapa planerad frånvaro**). Planerad frånvaro registreras som ett frånvarojobb för ett angivet datum och tidsintervall.

Jobbet baseras på en fråga. Du kan därför skapa planerad frånvaro för flera arbetare, t.ex. arbetare som tillhör samma beräkningsgrupp. Om den planerade frånvaron är för en enskild arbetare kan registreringen anges antingen från sidan **Närvaro** eller sidan **Tidsregistreringsarbetare**.

- För att ange en frånvaroregistrering från sidan **Närvaro**, välj **Tid och närvaro** &gt; **Förfrågningar och rapporter** &gt; **Närvaro** &gt; **Närvaro** och välj sedan **Frånvaroregistrering**.
- Ange en frånvaroregistrering från sidan *<strong><em>Tidsregistreringsarbetare</em></strong>*, välj <strong>Tidsregistreringsarbetare</strong> &gt; <strong>Inställningar</strong> &gt; <strong>Tidsregistreringsarbetare</strong>, välj fliken <strong>Tid</strong> under <strong>Tidstilldelning</strong> och välj <strong>Frånvaroregistreringar</strong>.

Du kan använda rapporten **Planerad frånvaro** för att visa en översikt över planerad frånvaro för anställda. Om du vill öppna rapporten, välj **Tid och närvaro**&gt;**Förfrågningar och rapporter**&gt;**Frånvarorapporter**&gt;**Planerad frånvaro**.

### <a name="registered-absence"></a>Registrerad frånvaro

I allmänhet anses arbetare vara frånvarande om de inte är på arbetet under någon period mellan deras planerade instämplingstid och deras planerade utstämplingstid. Om arbetarestämplar in senare än planerat eller om de stämplar ut tidigare än planerat, uppmanas de att välja en frånvarokod för att ange orsaken till frånvaron. En frånvarokod kan ställas in så att den är tillämplig för registrering. Endast tillämpliga koder blir tillgängliga att välja i listan.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Scenarier baserade på olika kombinationer av registrering av arbetstimme

Följande scenarier visar löneposter och transaktionerna för godkännande som genereras för arbetare utifrån deras registreringar. Alla scenarier baseras på följande tidsprofil.

| Profiltyp  | Start    | Slut      | Dag     |
|---------------|----------|----------|---------|
| Övertid     | 00:00 | 06:00 | Måndag  |
| Flex+         | 06:00 | 07:00 | Måndag  |
| Stämpla in      | 07:00 | 07:00 | Måndag  |
| Standardtid | 07:00 | 14:30 | Måndag  |
| Flex-         | 14:30 | 15:30 | Måndag  |
| Stämpla ut     | 15:30 | 15:30 | Måndag  |
| Övertid     | 15:30 | 06:00 | Tisdag |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Scenario 1: Arbetaren stämplar in senare än planerat

Arbetaren stämplar in klockan 08:30 Eftersom hans planerade instämplingstid är 07:00 kommer han 1,50 timme för sent till jobbet. Eftersom 1,50 timme anses vara frånvarotid uppmanas arbetaren att välja en frånvarokod. Arbetaren lämnar arbetet kl. 15:30, vilket är den planerade utstämplingstiden. När arbetarens registreringar beräknas och godkänns kommer frånvaroregistreringen tillsammans med frånvarokoden som arbetaren valde vid instämplingen, visas för tiden mellan kl. 07:00 och 08:30.

I tidsprofil kan du konfigurera registreringstypen **Instämpling** så att det finns en tolerans när arbetaren kommer sent till jobbet. Exempelvis om du har skapat en tolerans på högst 5, uppmanas arbetaren att endast ange en frånvarokod om han stämplar ut senast kl 07:05.

I detta fall, eftersom arbetaren inte har en bra anledning till att komma för sent till jobbet, väljer han en frånvarokod som har definierats för ogiltig frånvaro. En frånvarokod betraktas som tillämplig på ogiltig frånvaro om inställningen övertidsavdrag har aktiverats för den frånvarogrupp som frånvarokoden tillhör. För att ange inställningen, markera **Tid och närvaro**&gt;**Inställningar**&gt;**Grupper**&gt;**Frånvarogrupper** och markera sedan kryssrutan **Dra av övertid**.

Här visas arbetarens registreringar för dagen på sidan **Godkänn** efter beräkningen.

| Journalregistreringstyp         | Start    | Slut      | Tid |
|-----------------------------------|----------|----------|------|
| Frånvaro (ogiltigt - sent till jobbet) | 07:00 | 08:30 | 1.5  |
| Stämpla in                          | 08:30 | 08:30 |      |
| Produktionsjobb                    | 07:30 | 15:30 | 7.0  |
| Stämpla ut                         | 15:30 | 15:30 |      |

Här följer den resulterande löneposten när registreringarna har överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 07:00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Scenario 2: Medarbetaren stämplar ut före den planerade utstämplingstiden under en standardperiod

Arbetaren stämplar in klockan 8:00 och stämplar ut tidigare kl. 13:00. Eftersom 13:00 infaller före den planerade utstämplingen kl. 15:30 och 13:00 är i en standardtidsperiod uppmanas arbetaren att välja en frånvarokod. Arbetaren väljer en frånvarokod för läkarbesök som definieras som en giltig frånvaro. Lönesatsen för giltig frånvaro anges i löneavtalen för registreringstypen **Frånvaro** (**Tid och närvaro**&gt;**Inställningar**&gt;**Lön**&gt;**Löneavtal**).

Här visas arbetarens registreringar för dagen på sidan **Godkänn** efter beräkningen.

| Journalregistreringstyp              | Start    | Slut      | Tid |
|----------------------------------------|----------|----------|------|
| Stämpla in                               | 07:00 | 07:00 |      |
| Produktionsjobb                         | 07:00 | 13:00 | 4.0  |
| Stämpla ut                              | 13:00 | 13:00 |      |
| Frånvaro (giltig – läkarbesök) | 13:00 | 15:30 | 3.5  |

Här följer den resulterande löneposten när registreringarna har överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 7,50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Scenario 3: Medarbetaren stämplar ut före den planerade utstämplingstiden under en Flex--period

Arbetaren stämplar in klockan 07:00 och stämplar ut 14:15, d.v.s. mellan den planerade Flex--perioden. Tiden mellan faktisk utstämplingstid och planerad utstämplingstid beaktas inte som frånvaro och arbetaren uppmanas inte till att välja en frånvarokod. Beloppet dras från arbetarens flexkonto och arbetaren beviljas lön under den återstående delen av Flex--perioden från kl. 14:15 till 15:30.

Här visas arbetarens registreringar för dagen på sidan **Godkänn** efter beräkningen.

| Journalregistreringstyp | Start    | Slut      | Tid |
|---------------------------|----------|----------|------|
| Stämpla in                  | 07:00 | 07:00 |      |
| Produktionsjobb            | 07:00 | 14:15 | 7,25 |
| Stämpla ut                 | 14:15 | 14:15 |      |

Här följer den resulterande löneposten när registreringarna har överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 8,50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Scenario 4: Arbetaren stämplar in sent och stämplar ut efter den planerade utstämplingstiden under en övertidsperiod

Arbetaren stämplar in sent klockan 09:30 och sedan för att kompensera sin sena närvaro arbetar övertid och stämplar ut kl. 17:00. Eftersom arbetaren kom sent och kompenserar genom att arbeta längre vill företaget inte ge arbetaren övertidsbetalning för de timmar som han har arbetat mellan den planerade utstämplingen kl. 15:30 och den faktiska utstämpling kl. 17:00 även om denna period definieras som övertid i tidsprofilen.

För att kunna hantera det här scenariot kan frånvarokoden ställas in för att minska övertidstimmar genom det antal timmar med ogiltig frånvaro som arbetaren har samma dag. Markera kryssrutan **Tid och närvaro**&gt;**Inställningar**&gt;**Grupper**&gt;**Frånvarogrupper** och markera sedan kryssrutan **Dra av övertid** för att dra av övertid från timmar av ogiltig frånvaro.

Här visas arbetarens registreringar för dagen på sidan **Godkänn** efter beräkningen.

| Journalregistreringstyp         | Start    | Slut      | Tid |
|-----------------------------------|----------|----------|------|
| Frånvaro (ogiltigt - sent till jobbet) | 07:00 | 09:30 | 1.5  |
| Stämpla in                          | 09:30 | 09:30 |      |
| Produktionsjobb                    | 09:30 | 17:00 | 7,5  |
| Stämpla ut                         | 17:30 | 17:30 |      |

Om kryssrutan **Dra av övertid** är markerad för den valda frånvarokoden, dras övertidsersättning av efter de timmar som arbetaren har ogiltig frånvaro. I det här fallet genereras följande löneposter efter det att registreringarna överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 09:00      | 10   |
| Övertid      | 1301     | 0,5       | 15   |

Här drar de 1,5 timmarna av ogiltig frånvaro, från 07:00 till 09:30, av 2,0 timmars övertid, från 15:30 till 17:30. Resultatet av registreringen är 1,5 timmar standardtid och 0,5 timmars övertid.

Om däremot kryssrutan **Dra av övertid** avmarkeras för den valda frånvarokoden tilldelas övertidsersättning till arbetaren, trots att han var sen och har en ogiltig frånvaro. I det här fallet genereras följande löneposter efter det att registreringarna överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 7,50      | 10   |
| Övertid      | 1301     | 2,0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Scenario 5: Arbetaren stämplar ut före den planerade utstämplingstiden och frånvaroperioden kan konvertera till en Flex--period

I följande exempel visas hur en arbetares flexkonto kan minskas genom att konvertera frånvaroperioden till en Flex--period.

Arbetaren stämplar in klockan 07:00 och stämplar ut 13:00. Arbetaren har ett avtal som de kan gå hem för veckoslutet om de drar av dessa timmar från flexkontot. När medarbetaren stämplar ut klockan 13:00 uppmanas hon att välja en frånvarokod eftersom perioden för frånvaron för den återstående delen av arbetsdagen som påverkas är inte inom en planerad flexperiod. Om du vill konvertera den återstående delen av arbetsdagen till en Flexperiod kan arbetaren välja en frånvarokod som har ställts in för att minska sitt flexkonto.

För att minska saldot för flextimmar för arbetare som registrerar frånvaro på en arbetsdag, markera **Tid och närvaro**&gt;**Inställningar**&gt;**Grupper**&gt;**Frånvarogrupper** och markera kryssrutan **Minska flex**.

Här visas arbetarens registreringar för dagen på sidan **Godkänn** innan beräkningen.

| Journalregistreringstyp | Start    | Slut      | Tid |
|---------------------------|----------|----------|------|
| Stämpla in                  | 07:00 | 07:00 |      |
| Produktionsjobb            | 07:00 | 13:00 | 6,0  |
| Stämpla ut                 | 13:00 | 13:00 |      |

Om medarbetaren väljer en frånvarokod för ogiltig frånvaro, är här hur den resulterande löneposten ser ut när registreringen har överförts.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 6,00      | 10   |

Om medarbetaren väljer en frånvarokod för giltig frånvaro och frånvarokoden har ställts in för att minska sitt flexkonto, är här hur de resulterande löneposterna ser ut när registreringar överförs.

| Lönetyp     | Lönetyp | Löneantal | Kurs |
|---------------|----------|-----------|------|
| Standardtid | 1 201     | 8,50      | 10   |

Arbetarens flexsaldo minskas då med timmarna mellan den faktiska utstämplingstiden och den planerade utstämplingstiden (det vill säga de 2,5 timmarna från 13:00 till 17:30).

> [!NOTE]
> Vi rekommenderar inte att markera både kryssrutan **Dra av flex** och **Dra av övertid** för en frånvarokod eftersom denna inställning drar av de ogiltiga timmarna från arbetarens övertidstimmar och samtidigt minskar arbetarens flexkonto.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Scenario 6: Det finns ingen planerad frånvaro för dagen och ingen arbetarnärvaro för dagen

Om arbetaren inte går till jobbet en arbetsdag och det inte finns någon planerad frånvaro för arbetaren den dagen, används en standardfrånvarokod för beräkning av arbetarens registreringar. Om du vill definiera standardfrånvarokoder markerar du **Tid och närvaro**&gt;**Parametrar i tid och närvaro**. Du kan välja en frånvarokod i följande fält:

- Infoga Flex- automatiskt
- Infoga frånvaro automatiskt

När dagliga registreringar beräknas för en arbetare som är aktiverad för flextid används frånvarokoden som anges på fältet **Infoga flex- automatiskt** som en standardfrånvarokod. Om arbetaren inte har aktiverats för flextid används den frånvarokod som anges på fältet **Infoga frånvaro automatiskt**. Om ett företag har en kombination av arbetare som är aktiverade för flextid och som inte är aktiverade för flextimmar, måste båda parametrarna ställas in.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]