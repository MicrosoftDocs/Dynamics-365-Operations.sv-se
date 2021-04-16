---
title: KPI:er för tillgång
description: I det här avsnittet beskrivs tillgångs-KPI:er i tillgångshantering.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectKPI
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 90759931fcbdb1e5acbd62f8a40e5b37b918f31a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813879"
---
# <a name="asset-kpis"></a>KPI:er för tillgång

[!include [banner](../../includes/banner.md)]

 

I tillgångshantering kan du beräkna olika nyckeltal (KPI:er, Key Performance Indicators) för tillgångar och tillgångstyper. Du använder KPI:er för att få en översikt över prestanda för tillgångar i relation till exempelvis driftstid, driftstopp, reparationstid och genomsnittstid mellan misslyckande (MTBF, Mean Time Between Failure).

1. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **KPI:er för tillgång**.

2. I dialogrutan **Beräkna KPI:er för tillgång** väljer du **tidsskalan** som ska användas i beräkningen, och en period i fälten **Från datum** och **Till datum**. 

3. På de snabbfliken **Poster som ska ingå** kan du välja specifika tillgångar och tillgångstyper som ska inkluderas i beräkningen om det behövs.

4. Klicka på **OK** för att starta beräkningen.

5. På snabbfliken **Översikt** visas resultatet av beräkningen i rutnätsvy. Varje tillgång visas på en separat rad.

6. På snabbfliken **KPI:er för vald rad** visas beräkningar för den tillgång som valts på snabbfliken **Översikt**. KPI-värdena är kategoriserade avseende **tid**, **tillgänglighet**, **arbetsorder**, **underhåll**, **fel**, **underhållsstopp** och **kostnad**.

I tabellen nedan finns en beskrivning av fälten på sidan **KPI:er för tillgång**.

| Fält                   | Beskrivning                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tillgång                   | Tillgångs-ID.                                                                                                                                                                                                                                                                                             |
| Total tid              | Total tid som ställts in i kalendern som används i beräkningen. Om tillgången är relaterad till en resurs, används den relaterade resurskalendern. Om tillgången inte är relaterad till en resurs, används den kalender som valts i fältet **Standardkalender** i **Parametrar för tillgångshantering**. |
| Drifttid                  | Total tid minus avbrott.                                                                                                                                                                                                                                                                            |
| Driftstopp                | Registreringar av underhållsstopp görs för till gången under den valda perioden.                                                                                                                                                                                                                              |
| Reparationstid             | Totalt antal arbetstimmar som förbrukas på reparationsarbetsorder.                                                                                                                                                                                                                                            |
| Tillgänglighet %          | Drifttid delad med total tid och multiplicerat med 100.                                                                                                                                                                                                                                                   |
| Antal fel        | Antal felorsaker som registreras vid felsymptom på tillgången under den valda perioden.                                                                                                                                                                                                             |
| GTMF                    | Genomsnittstid mellan fel, vilket är den totala tiden dividerat med antalet fel som registrerats för tillgången under den valda perioden. Om antalet fel är noll ställs MTBF in på total tid.                                                                                                                   |
| Felfrekvens               | 1 delat med MTBF.                                                                                                                                                                                                                                                                                    |
| MRT                     | Genomsnittlig reparationstid (Mean Repair Time), vilket är reparationstiden dividerat med antalet fel som registrerats för tillgången under den valda perioden. Om antalet fel är noll ställs MRT in på reparationstid.                                                                                                                           |
| Antal stopp         | Antalet registreringar för underhållsstopp skapade på tillgången.                                                                                                                                                                                                                                     |
| GTMS                    | Genomsnittstid mellan stopp, vilket är den totala tiden delat med antalet underhållsstopp i registreringarna. Om antalet registreringar av underhållsstopp är noll i den valda perioden ställs GTMS-värdet in på total tid.                                                                                      |
| Förebyggande kostnad         | Kostnader som har bokförts på tillgången som hör till kostnadstypen "Förebyggande" i den valda perioden. Kostnadstyper ställs in på arbetsordertyper.                                                                                                                                                                       |
| Korrigerande kostnad         | Kostnader som har bokförts på tillgången relaterad till kostnadstypen "Korrigerande" i den valda perioden. Kostnadstyper ställs in på arbetsordertyper.                                                                                                                                                                       |
| Ersättningsvärde       | Värde som definieras på tillgången som ersättningskostnad.                                                                                                                                                                                                                                                  |
| Tillgångstyp             | Identifiering av tillgångstypen som valts på tillgången.                                                                                                                                                                                                                                             |
| Tillverkare           | Identifiering av tillverkaren som valts på tillgången.                                                                                                                                                                                                                                                 |
| Modell                   | Identifiering av tillverkarmodellen som valts på tillgången.                                                                                                                                                                                                                                           |
| Från-datum               | Startdatum för beräkning av KPI. Om tillgången har skapats efter det startdatum som har valts för beräkningen visas startdatumet för tillgången i det här fältet.                                                                                                                                  |
| Till-datum                 | Slutdatum för beräkning av KPI. Om tillgången har registrerats som inaktiv före det slutdatum som valts för beräkningen visas det datum då tillgången inte längre var aktiv i det här fältet.                                                                                               |
| Tidsskala              | Under beräkningen av KPI:er väljer du en tidsskala som ska användas: timmar, dagar eller veckor.                                                                                                                                                                                                            |
| Tillgänglighet            | Drifttid delad med total tid.                                                                                                                                                                                                                                                                         |
| Arbetsorder             | Totalt antal arbetsorder som ingår i KPI-beräkningen.                                                                                                                                                                                                                                          |
| Arbetsordertid         | Totalt antal arbetstimmar som förbrukas på arbetsorder.                                                                                                                                                                                                                                               |
| Primära arbetsorder     | Antal primära arbetsorder som ingår i KPI-beräkningen.                                                                                                                                                                                                                                        |
| Sekundära arbetsorder   | Antal sekundära arbetsorder som ingår i KPI-beräkningen.                                                                                                                                                                                                                                      |
| Underhållsarbetsorder | Antal underhållsarbetsorder som ingår i KPI-beräkningen. En underhållsarbetsorder är en arbetsorder utan relaterade felorsaker.                                                                                                                                                             |
| Underhållstid        | Totalt antal arbetstimmar som förbrukas på underhållsarbetsorder.                                                                                                                                                                                                                                       |
| Order för reparationsarbete      | Antal reparationsarbetsorder som ingår i KPI-beräkningen. En reparationsarbetsorder är en arbetsorder med en relaterade felorsak.                                                                                                                                                                        |
| Tillförlitlighet %           | Beräkning baserad på den förväntade exponentiella utvecklingen vid felregistreringar på en tillgång, vilket innebär att tillgången blir mindre tillförlitlig på grund av slitage. Beräkningen av denna KPI baseras på MTBF och den totala tiden.                                                            |
| GTUS                    | Genomsnittstid för produktionsstopp, vilket är underhållsstopptiden tiden delat med antalet underhållsstopp i registreringarna. Om antalet registreringar av underhållsstopp är noll i den valda perioden ställs MTPS-värdet in på noll.                                                                               |
| Totalkostnad              | Totala kostnader som har bokförts på tillgången under den valda perioden.                                                                                                                                                                                                                                              |
| Investeringskostnad         | Kostnader som har bokförts på tillgången relaterad till kostnadstypen "Investering" i den valda perioden. Kostnadstyper ställs in på arbetsordertyper.                                                                                                                                                                       |

Bilden nedan visar en skärmbild av en KPI-beräkning för fyra till gångar.

![Skärmbild av en KPI-beräkning för fyra tillgångar](media/11-controlling-and-reporting.png)

- Du kan välja flera till gångar i **Alla tillgångar** och klicka på knappen **KPI:er för tillgång** på fliken **Allmänt**. Klicka sedan på **OK** i dialogrutan **Beräkna KPI:er för tillgång** för att beräkna KPI:er för de valda tillgångarna.  
- Resultat från en KPI-beräkning kan eventuellt inte inkludera [registreringar av underhållsstopp](../work-orders/maintenance-downtime.md), beroende på de orsakskoder för underhåll som ställs in och används. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]