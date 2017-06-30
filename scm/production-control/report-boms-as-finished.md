---
title: Rapportera strukturlistor som avslutade
description: "Den här artikeln innehåller information om att rapportera strukturlistor som avslutade."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMReportFinish, BOMReportFinishMax
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 26b5029068904d4af5849eab9135f50b3291f642
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="report-boms-as-finished"></a>Rapportera strukturlistor som avslutade

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om att rapportera strukturlistor som avslutade.

Sidorna **Rapportera som färdig** och **Max. antal rapporterat som färdigt** används för att rapportera strukturlistor (BOM) som färdiga. Rent konceptuellt är processen för rapportering av en strukturlista som färdig samma som processen för rapportering av en produktionsorder som färdig. Den här processen kan till exempel användas i processer för enkel montering och paketering där mer avancerade funktioner för tillverkningsorder inte krävs. Sidan **Rapportera som färdig** låter dig rapportera flera strukturlistor som färdiga samtidigt. På sidan **Max. antal rapporterat som färdigt** kan du rapportera endast strukturlista i taget som färdig. Sidan **Rapportera som färdig** är tillgänglig från ett menyalternativ i Lagerhantering, och båda sidorna är tillgängliga som menyalternativ på sidan **Frisläppta produkter**.

## <a name="report-as-finished-page"></a>Sidan Rapportera som färdig
Om du öppnar sidan **Rapportera som färdig** från en frisläppt produkt föreslår sidan att du rapporterar standardkvantiteten för standardlagret som färdig. Som standard visas den aktiva strukturlisteversionen, men du kan ändra strukturlisteversionen om det finns andra godkända versioner. På sidan kan du också ta bort poster och skapa nya poster för frisläppt produkter som ska rapporteras som färdiga. Klicka på menykommandot **Välj** för att använda en fråga för att välja produkter. Du kan manuellt bekräfta rapportering som färdig för de valda produkterna genom att klicka på **OK**. Alternativt kan du ställa in processen att köra i en batch. När processen för Rapportera som färdig har bekräftats genererar systemet en strukturlistejournal där bokföringen till lagret bearbetas. Den här journalen består av en radartikel för den färdiga produkten och en radartikel för varje strukturlisterad. Du kan kontrollera om journalen bokförs automatiskt eller om den lämnas öppen för ytterligare justeringar.

## <a name="max-report-as-finished-page"></a>Sidan Max. antal rapporterat som färdigt
På sidan **Max. antal rapporterat som färdigt** anger varje strukturlisterad antalet enheter av produkten som kan rapporteras som färdig. Den här beräkningen baseras på den tillgängliga fysiska lagerbehållningen för varje materialrad. I följande exempel förbrukar en del av artikelnumret FG två delar av råmaterial RM10 och en del av råmaterial RM20. Eftersom det bara finns tio delar av RM10 i lager är den största kvantiteten av FG som kan rapporteras som färdig fem enheter. Det här värdet visas i fältet **Max. antal rapporterat som färdigt**.

| Nivå | Artikelnummer | Kvantitet | Behållning | Max. Rapportera som färdig |
|-------|-------------|----------|---------|-------------------------|
| 0     | FG          |  1       | 0       | 5                       |
| 1     | RM10        | -2       | 10      | 5                       |
| 1     | RM20        | -1       |  8      | 8                       |

## <a name="boms-that-have-multiple-levels"></a>Strukturlistor som har flera nivåer
När en strukturlista innehåller flera nivåer kan du styra hur material tas med för alla nivåer med hjälp av fältet **Nedbrytning** hjälp av fältet. Det här fältet är tillgängligt på både sidan **Rapportera som färdig** och **Max. antal rapporterat som färdigt**. Följande alternativ är tillgängliga:

-   **Aldrig** – underliggande strukturlistor bryts inte ned när det blir brist på material.
-   **Alltid** – alla underliggande strukturlistor bryts ned. Eventuell lagerbehållning för halvfärdiga komponenter används därför inte.
-   **Vid brist** – underliggande strukturlistor bryts bara ned om den fullständiga kvantiteten av materialet inte är tillgänglig.

### <a name="example"></a>Exempel

I det här exemplet är tre delar av den färdiga produkten (artikelnumret FG) klara att rapporteras som färdiga. Det finns en strukturlista med två nivåer, som visas här.

| Nivå | Artikelnummer | Kvantitet på strukturlisterad | Behållning |
|-------|-------------|-------------------|---------|
| 0     | FG          |                   |         |
| 1     | COMP        | 1                 | 2       |
| 1     | RM          | 1                 |         |

Följande tabell visar hur inställningen i fältet **Nedbrytning** påverkar hur strukturlistejournalrader genereras. **Nedbrytning: Aldrig**

| Nivå | Artikelnummer | Kvantitet |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -3       |

Som tabellen ovan visar betraktas bara artikelnumret COMP som avdraget i journalen. Artikelnumret RM, som ingår i COMP, är inte uppdelat till journalraden, och de två tillgängliga enheter av COMP beaktas inte. **Nedbrytning: Alltid**

| Nivå | Artikelnummer | Kvantitet |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | RM          | -3       |

I det här fallet bryts artikelnummer COMP ned till dess råmaterial, artikelnummer RM. De två tillgängliga delarna av COMP räknas inte i kvantiteten för RM att förbruka. **Nedbrytning: Vid brist**

| Nivå | Artikelnummer | Kvantitet |
|-------|-------------|----------|
| 0     | FG          | 3        |
| 1     | COMP        | -2       |
| 1     | RM          | -1       |

I det här fallet beaktas de två tillgängliga delarna av artikelnummer COMP. Men, eftersom tre delar av artikelnumret FG krävs, krävs också en del av artikelnummer RM för att tillverka den ytterligare enheten av COMP.




