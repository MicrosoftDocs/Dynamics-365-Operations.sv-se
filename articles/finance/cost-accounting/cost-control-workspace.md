---
title: Arbetsyta för kostnadskontroll
description: Det här avsnittet innehåller information om arbetsytan för kostnadskontroll. Den här arbetsytan är en central plats där chefer, som ansvarar för kontroll av ett kostnadsobjekt eller en uppsättning kostnadsobjekt i en dimension eller i flera dimensioner har åtkomst till rapporter.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace, CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3163975a8cc99c4b07fdbe03fa57ea6cfef53cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995225"
---
# <a name="cost-control-workspace"></a>Arbetsyta för kostnadskontroll 

[!include [banner](../includes/banner.md)]

Arbetsytan **Kostnadskontroll** är en central plats där chefer, som ansvarar för kontroll av ett kostnadsobjekt eller en uppsättning kostnadsobjekt i en dimension eller i flera dimensioner (t.ex. kostnadscenter och produktgrupper) har åtkomst till rapporter. Rapporterna i arbetsytan hanteras helt av kostnadsrevisorer, så att den layout och data som används för rapportering kan vara konsekvent över hela organisationen.

## <a name="cost-control-workspace-configuration"></a>Konfiguration av arbetsytan för kostnadsstyrning

Kostnadsrevisorer kan definiera så många rapportkonfigurationer som krävs för den önskade datasammansättningen eller layouten. En rapportkonfiguration består av sex avsnitt som var och ett bidrar till antigen valet av riktad datasammansättning eller layouten.

Om vill konfigurera en arbetsyta för kostnadskontroll  **kostnadsredovisning** \> **inställningar** \> **Konfiguration av arbetsyta för kostnadskontroll**.

### <a name="general"></a>Allmänt

På snabbfliken **allmän** kan du skapa en unik rapportlayout. Namnet på rapporten blir en unik identifierare som användarna ska kunna känna igen i arbetsytan **kostnadskontroll**. Du kan också ange om rapporten ska delas eller hållas internt för kostnadsrevisorer.

| Fält       | beskrivning |
|-------------|-------------|
| Namn        | Ange ett unikt namn på layouten. |
| beskrivning | Ange en detaljerad beskrivning. |
| Publicerad   | Om du anger fältet till **Ja**, kan en användare som tilldelas en av följande roller se rapporten i arbetsytan **kostnadskontroll**:<ul><li>Kostnadsredovisningschef</li><li>Kostnadsredovisare</li><li>Ansvarig kostnadsredovisare</li><li>Kostnadsobjektcontroller</li></ul>Om du anger fältet till **Nej**, kan endast användare som tilldelats en av följande roller se rapporten i arbetsytan **kostnadskontroll**:<ul><li>Kostnadsredovisningschef</li><li>Kostnadsredovisare</li><li>Ansvarig kostnadsredovisare</li></ul> |

### <a name="data-filtering"></a>Filtrering av data

På snabbfliken **Datafiltrering** definierar du grunden för data för rapporten. Användare av denna rapport kommer att se värden i rapporten när källdata har bearbetats.

| Fält                                                             | beskrivning |
|-------------------------------------------------------------------|-------------|
| Huvudbok för kostnadsredovisning                                            | **Huvudboken för kostnadsredovisning** som rapporten baseras på. Värdet hämtas från fältet **kostnadskontrollenhet**. |
| Kostnadsstyrenhet                                                 | Värdet som du väljer bestämmer kostnadsredovisningen och kostnadobjekten som rapporten ska baseras på. |
| Statistisk dimensionshierarki, dimensionshierarki för kostnadselement | En konfigurationspost för arbetsytan **kostnadskontroll** kan rapportera icke-monetära eller monetära värden, men inte i samma layout. Välj ett värde i fältet **Dimensionshierarki för kostnadselement** för att rapportera monetära värden. Välj ett värde i fältet **Statistisk dimensionshierarki** för att rapportera icke-monetära. Dimensionshierarkiposten som du väljer avgör strukturen för rapporterings- och aggregeringsnivåer.<blockquote>[!NOTE]<br>Om du vill visa monetära och icke-monetära värden sida vid sida kan du exportera data till Microsoft Excel för Microsoft Power BI-innehållet.</blockquote> |
| Dimensionshierarki för kostnadsobjekt                                   | Välj dimensionshierarkin av kostnadsobjektdimensionen som passar syftet med rapporteringen du definierar. |
| Ursprunglig budgetversion                                           | Välj det budgetversion-ID som utgör den ursprungliga budgeten i samband med den här rapporten. |
| Reviderad budgetversion                                            | Välj det budgetversion-ID som utgör den reviserade budgeten i samband med den här rapporten. |

### <a name="assign-calculation-records"></a>Tilldela beräkningsposter

Omkostnadsberäkningen utför stegen i beräkningen av källdata, t.ex. klassificering av kostnadsbeteende, kostnadsfördelning och kostnadsallokering. Flera omkostnadsberäkningar kan göras för samma räkenskapsperiod om källdata saknas eller om regler måste uppdateras. Varje omkostnadsberäkning sparas med ett unikt ID. Kostnadsrevisorn kan välja ett specifikt omkostnadsberäknings-ID. Användare av rapporten, till exempel chefer, kommer att se resultatet av omkostnadsberäkningen i arbetsytan **kostnadskontroll**.

| Fält                  | beskrivning |
|------------------------|-------------|
| Räkenskapskalenderperiod | Välj räkenskapskalenderperiod för att tilldela ett omkostnadsberäknings-ID.<blockquote>[!NOTE]<br>Räkenskapsperioderna som anges i fältet kommer från räkenskapskalendern som är kopplad till huvudboken för kostnadsredovisning.</blockquote> |
| Faktisk version         | Välj lämplig omkostnadsberäknings-ID. |
| Budgetversion         | Välj lämplig omkostnadsberäknings-ID. |
| Reviderad budgetversion | Välj lämplig omkostnadsberäknings-ID. |

### <a name="fiscal-periods-per-column"></a>Räkenskapsperioder per kolumn

På snabbfliken **räkenskapsperioder per kolumn** bestämmer kostnadsrevisorn vilken räkenskapsperiod som ska visas i rapportens layout.

Värdena i de markerade kolumnerna kommer att multipliceras med de valda värdena på snabbfliken **räkenskapsperioder per kolumn**.

| Fält                | beskrivning |
|----------------------|-------------|
| Aktuell period       | Saldot för den aktuella räkenskapsperioden visas.<blockquote>[!NOTE]<br>Som standard bestäms innevarande period av sessionsdatum. I arbetsytan **kostnadskontroll** kan du välja en specifik räkenskapsperiod. Det valda värdet representerar sedan innevarande perioden.</blockquote> |
| Föregående period      | Saldot för den föregående räkenskapsperioden visas. Följande formel används:<br>Innevarande räkenskapsperiod – 1<blockquote>[!NOTE]<br>Som standard härleds föregående period från sessionsdatum. I arbetsytan **kostnadskontroll** kan du välja en specifik räkenskapsperiod som innevarande period. **Föregående period** räknas sedan i enlighet med detta.</blockquote> |
| Början på året till dagens datum         | Den för hittills i år visas. Följande formel används:<br>YearToDate (innevarande räkenskapsperiod)<blockquote>[!NOTE]<br>Som standard bestäms innevarande period av sessionsdatum. I arbetsytan **kostnadskontroll** kan du välja en specifik räkenskapsperiod. Det valda värdet representerar sedan den aktuella perioden och värdet **Hittills i år** uppdateras.</blockquote> |
| Hittills i år, genomsnitt | Genomsnittet för hittills i år visas. Följande formel används:<br>(YearToDate [innevarande räkenskapsperiod]) ÷ (antal [innevarande räkenskapsperiod])<p><strong>Exempel</strong></p><ul><li>**Statistisk dimensionsmedlem:** Heltidsmedarbetare</li><li>**Aktuellt datum:** 2017-03-21</li><li>**Period:** räkenskapsperiod 1, räkenskapsperiod 2, räkenskapsperiod 3</li><li>**Storlek:** 10, 10, 12</li></ul>I det här fallet **Hittills i år, genomsnitt** = (10 + 10 + 12) ÷ 3 = 10,67<p>Värdet **Hittills i år, genomsnitt** kan beräknas för dimensionsmedlemmar för kostnadselement och statistiska dimensionsmedlemmar.</p><blockquote>[!NOTE]<br>Som standard bestäms innevarande period av sessionsdatum. I arbetsytan **kostnadskontroll** kan du välja en specifik räkenskapsperiod. Det valda värdet representerar sedan den aktuella perioden och värdet **Hittills i år** och **Hittills i år, genomsnitt** uppdateras.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Kolumner att visa för kostnader

På snabbfliken **Kolumner att visa för kostnader** avgör kostnadsrevisorn vilka kolumner som ska innehålla rapportens layout. Det finns tre kategorier: fast kostnad, variabel kostnad och oklassificerad kostnad.

| Fält                 | beskrivning |
|-----------------------|-------------|
| Fast kostnad            | Denna kolumntyp visar den fasta kostnaden baserat på det valda omkostnadsberäknings-ID:t.<blockquote>[!NOTE]<br>Den här kolumntypen visar endast ett saldo när en omkostnadsberäknings-ID har markerats för räkenskapsperioden.</blockquote> |
| Variabel kostnad         | Denna kolumntyp visar den variabla kostnaden baserat på det valda omkostnadsberäknings-ID:t.<blockquote>[!NOTE]<br>Den här kolumntypen visar endast ett saldo när en omkostnadsberäknings-ID har markerats för räkenskapsperioden.</blockquote> |
| Fast + rörlig kostnad | Denna kolumntyp visar den fasta kostnaden och variabla kostnaden baserat på det valda omkostnadsberäknings-ID:t.<blockquote>[!NOTE]<br>Den här kolumntypen visar endast ett saldo när en omkostnadsberäknings-ID har markerats för räkenskapsperioden.</blockquote> |
| Totalkostnad            | Den här kolumntypen visar den totala kostnaden (oklassificerad kostnad, fast kostnad och variabel kostnad).<blockquote>[!NOTE]<br>Kolumntypen visar saldot när som helst.</blockquote> |
| Oklassificerad kostnad     | Denna kolumntyp visar den oklassificerade kostnaden.<blockquote>[!NOTE]<br>Denna kolumnen kan användas för att verifiera om alla kostnader har klassificerats korrekt av omkostnadsberäkningen eller om kostnadsbeteendereglerna måste justeras.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Kolumner att visa för budgeterade kostnader

På snabbfliken **Kolumner att visa för budgeterade kostnader** avgör kostnadsrevisorn vilka kolumner som ska visas för valda budgetversioner. Individuella val kan göras för den ursprungliga och den reviderade budgeten.

> [!NOTE]
> Eftersom följande fält fungerar på samma sätt som för den ursprungliga budgeten och den reviderade budgeten, förklaras de bara en gång.

| Fält                     | beskrivning |
|---------------------------|-------------|
| Budget                    | Budgetsaldon visas per de markerade kolumner.<blockquote>[!NOTE]<br>Saldon ska baseras på de budgetversioner som har markerats på snabbfliken **Datafiltrering**.</blockquote> |
| Budgetavvikelse           | Beräkna och visa skillnaderna mellan budget och faktisk. Följande formel används:<br>Budgetsaldo – faktiskt saldo |
| Budgetavvikelse i %      | Beräkna och visa skillnaderna i procent mellan budget och faktisk. Följande formel används:<br>(Budgetsaldo – faktiskt saldo) / budgetsaldo |
| Tröskel för avvikelseperiod | Ange ett tröskelvärde för avvikelsen i det monetära beloppet för aktuell period. Om tröskelvärdet överskrids kommer raden att markeras med rött i arbetsytan **kostnadskontroll**.<blockquote>[!NOTE]<br>Det här fältet gäller bara för kostnadselement som representerar omkostnader.</blockquote> |
| Tröskel för avvikelseår   | Ange ett tröskelvärde för avvikelsen i det monetära beloppet för aktuellt år. Om tröskelvärdet överskrids kommer raden att markeras med rött i arbetsytan **kostnadskontroll**. |
| Avvikelsetröskel i %      | Ange ett tröskelvärde för avvikelsen i procent. Om tröskelvärdet överskrids kommer raden att markeras med rött i arbetsytan **kostnadskontroll**.<blockquote>[!NOTE]<br>Samma tröskelprocent gäller för den aktuella perioden och året.</blockquote> |

## <a name="cost-control-workspace"></a>Arbetsyta för kostnadskontroll

Arbetsytan **kostnadskontroll** har utformats som en webbrapport. Därför kan alla chefer som ansvarar för ett kostnadsobjekt beviljas åtkomst enligt vad som beskrivs i [ange åtkomstbehörigheter för kostnadsobjektcontroller](access-rights-cost-object-controller.md).

Listan över rapporter som är tillgängliga för användare, som t.ex. för chefer, styrs av inställningen av alternativet **publicerad** på sidan **Konfigurationer av arbetsyta för kostnadskontroll**.

![En rapport som användare kan visa i arbetsytan för kostnadskontroll](./media/report-cost-control.png)

En chef kan välja att visa räkenskapskalenderperioden. Sessionsdatumet används för att bestämma innevarande standardperiod.

Värdena i räkenskapskalenderperioden bestäms av rapportnamnet och räkenskapskalendern som väljs för kostnadsredovisningen är associerad med rapportnamnet på sidan **Konfigurationer av arbetsyta för kostnadskontroll**.

I dimensionshierarkin för kostnadsobjekt kan användarna välja aggregeringsnivån där saldon ska visas. Genom att aktivera säkerhet för åtkomstnivå, kontrollerar du behörigheter, så att användarna kan välja de hierarkinivåer som de har beviljats åtkomst till. Därför kan de se de sammanlagda saldon som de har beviljats åtkomst till.

### <a name="add-or-remove-columns"></a>Lägg till eller ta bort kolumner

Användare kan anpassa kolumner i rapporten så att den passar deras behov.

### <a name="view-details"></a>Visa detaljer

Användare kan gå nedåt till detaljerna bakom saldon som visas i arbetsytan. Om användare väljer en dimensionshierarkinod för kostnadselement och sedan klickar på **Visa detaljer**, visar dialogrutan **detaljer om kostnadselement** detaljerad information för noden.

Ett rutnät visar varje kostnadselement som är associerat med dimensionshierarkinoden för kostnadselement och dess värden. Kolumnerna som visas i rutnätet matchar inställningar för arbetsyta.

Två diagram visar en översikt över utfall kontra budget och budgetavvikelse per period.

![Diagram visar en översikt över utfall kontra budget och budgetavvikelse per period](./media/cost-element-details-operations.png)

Användare kan klicka på **kostnadstransaktioner** för att gå till postens detaljer som krävs.

![Kostnadsposter](./media/cost-entries.png)

Hyra är till exempel en utgift som distribueras till kostnadsställen. En användare som vill förstå om hans eller hennes kostnadsställe ska bära hyreskostnaden kan öka detaljnivån för att se hur hyra beräknas.

Om användaren klickar på **Allokeringsunderlag** på sidan **kostnadstransaktioner** visas en dialogruta. Användare kan sedan tilldela allokeringsunderlaget till regeln och visa motsvarande statistiska mätningar som är registrerade för perioden.

I följande exempel är allokeringsunderlaget av typen **Formelallokeringsunderlag** och formeln visas. De faktorer som definierar formeln visas. Dessutom visar ett rutnät beräkningen som görs per kostnadsobjekt.

![Beräkningar per kostnadsobjekt](./media/cost-entries-allocation-base.png)

Ytterligare resurser 

[Definiera åtkomsträttigheter för kostnadsobjektcontroller](access-rights-cost-object-controller.md)


