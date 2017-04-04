---
title: Manuell avskrivning
description: "Det här avsnittet innehåller en översikt över den manuella avskrivningsmetoden."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 96d0ae3be15c792b04eae901577b160d1532801c
ms.lasthandoff: 03/31/2017


---

# <a name="manual-depreciation"></a>Manuell avskrivning

Det här avsnittet innehåller en översikt över den manuella avskrivningsmetoden.

När du ställer in en avskrivningsprofil för anläggningstillgångar och väljer **Manuellt** i fältet **Metod** på sidan **Avskrivningsprofiler** avgörs avskrivningen av anläggningstillgångar som är tilldelade till den här avskrivningsprofilen av procenten som du anger för varje intervall under kalenderåret. Intervallen som du ställer in procenttal för bokförs enligt det värde du valt i fältet **Periodfrekvens** på snabbfliken **Allmänt** på sidan **Avskrivningsprofiler**. Du kan välja följande värden:

-   Årligen
-   Varje månad
-   Varje kvartal
-   Halvårsvis
-   Dagligen

När du har valt periodfrekvens klickar du på **Manuella tidsplaner**och ställer in procenttal frö varje bokföringsintervall. Tillsammans definierar de manuella tidsplanerna och bokföringsintervallen avskrivningsbeloppet, enligt exemplen senare i den här artikeln. Manuell avskrivning beräknas alltid i procent av anskaffningspriset. För manuell avskrivning behöver de avskrivningsintervall du anger inte utgöra 100 procent. Manuell avskrivning är en flexibel avskrivningsmetod som ofta används för att definiera en extraordinär avskrivningsprofil på sidan **Books**, till exempel en icke-periodisk avskrivning av speciella skäl (kanske skatteskäl).

## <a name="examples"></a>Exempel
Anskaffningspris: 11 000,00 Förväntat skrotvärde: 1 000,00 Följande tabell visar de intervall och procentsatser som du ställer in på sidan **Tidsplaner för anläggningstillgångens avskrivningsprofil**.

| Intervallnummer | Procent |
|-----------------|------------|
| 1               | 10,00      |
| 2               | 50,00      |
| 3               | 8,00       |

Följande tabell visar hur avskrivningen för varje intervall beräknas.

|  Intervallnummer | Beräkning av årligt avskrivningsbelopp | Bokfört nettovärde i slutet av intervallet |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11 000–1 000) × 10 % = 1 000                | 10 000 (11 000–1 000)                   |
| 2                | (11 000–1 000) × 50 % = 5 000                | 5 000 (10 000–5 000)                    |
| 3                | (11 000–1 000) × 8 % = 800                   | 4 200 (5 000–800)                       |

Om du väljer **Varje månad** i fältet ** Periodfrekvens** ställer du in 12 manuella schemaintervall. Följande tabell visar avskrivningsbeloppen för de två första intervallen.

| Intervall | Avskrivningsbelopp            |
|----------|--------------------------------|
| Januari  | (11 000–1 000) × 10 % = 1 000 |
| Februari | (11 000–1 000) × 50 % = 5 000 |

Om du väljer **Halvårsvis** i den *** perioden frekvens ** fältet ** du ställa in två intervall för manuella tidsplaner. Följande tabell visar avskrivningsbeloppen för de två intervallen.

| Intervall    | Avskrivningsbelopp            |
|-------------|--------------------------------|
| 30 juni     | (11 000–1 000) × 10 % = 1 000 |
| 31 december | (11 000–1 000) × 50 % = 5 000 |

Sammanlagt procentsatsen för alla intervall måste inte vara 100. Emellertid ett felmeddelande om värdet i den **ackumulerad procent** på de **fast avskrivning av anläggningstillgångar tidsplaner** sidan inte är **100**.


