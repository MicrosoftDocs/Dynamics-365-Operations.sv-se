---
title: "Rapporten strukturlista som färdig"
description: "Den här artikeln innehåller information om rapportera en strukturlista som färdig."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMReportFinish, BOMReportFinishMax
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53251
ms.assetid: 510d05a3-0073-438d-b0c4-b6a6df1882ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 318c88f88277a8300b1fcda5056a9a92c9a81eae
ms.lasthandoff: 03/31/2017


---

# <a name="report-boms-as-finished"></a>Rapporten strukturlista som färdig

Den här artikeln innehåller information om rapportera en strukturlista som färdig.

Sidorna **Rapportera som färdig** och **Max. antal rapporterat som färdigt** används för att rapportera strukturlistor (BOM) som färdiga. Rent konceptuellt är processen för rapportering av en strukturlista som färdig samma som processen för rapportering av en produktionsorder som färdig. Den här processen kan till exempel användas i processer för enkel montering och paketering där mer avancerade funktioner för tillverkningsorder inte krävs. Sidan **Rapportera som färdig** låter dig rapportera flera strukturlistor som färdiga samtidigt. Den **Max. Rapportera som färdig** på sidan kan du rapportera bara en Strukturlista som färdig i taget. Den **rapportera som färdig** sida tillgänglig från ett menyalternativ i Lagerhantering och båda sidorna är tillgängliga menyalternativen på de **frisläppta produkter** sida.

## <a name="report-as-finished-page"></a>Sidan Rapportera som färdig
Om du öppnar sidan **Rapportera som färdig** från en frisläppt produkt föreslår sidan att du rapporterar standardkvantiteten för standardlagret som färdig. Som standard visas den aktiva strukturlisteversionen, men du kan ändra strukturlisteversionen om det finns andra godkända versioner. På sidan kan du också ta bort poster och skapa nya poster för frisläppt produkter som ska rapporteras som färdiga. Klicka på menykommandot **Välj** för att använda en fråga för att välja produkter. Du kan manuellt bekräfta rapportering som färdig för de valda produkterna genom att klicka på **OK**. Alternativt kan du ställa in processen att köra i en batch. När processen för Rapportera som färdig har bekräftats genererar systemet en strukturlistejournal där bokföringen till lagret bearbetas. Den här journalen består av en radartikel för den färdiga produkten och en radartikel för varje strukturlisterad. Du kan kontrollera om journalen bokförs automatiskt eller om den lämnas öppen för ytterligare justeringar.

## <a name="max-report-as-finished-page"></a>Max. Rapportera som färdig sida
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

Som tabellen ovan visar bara artikelnumret dator betraktas som dras av i journalen. Artikelnumret RM som tillhör dator ned inte till journalraden och två tillgängliga enheter av dator beaktas inte. **Nedbrytning: Alltid**

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

