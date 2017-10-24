---
title: "Spåra löpande genomsnittlig kostnad per lagerdimension"
description: "En lagerdimensionsgrupp kopplas till varje lagerartikel. Därför beräknas den löpande genomsnittliga självkostnaden för en artikel utifrån valet av lagerdimensioner som spåras ekonomiskt."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a88ec380810a9a2d7048d5a8773ebb5960e4cf86
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Spåra löpande genomsnittlig kostnad per lagerdimension

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


En lagerdimensionsgrupp kopplas till varje lagerartikel. Därför beräknas den löpande genomsnittliga självkostnaden för en artikel utifrån valet av lagerdimensioner som spåras ekonomiskt.

Det finns tre typer av lagerdimensioner: produkt, lagring och spårning. Produktdimensioner omfattar konfiguration, storlek och färg. Produktdimensioner spåras alltid ekonomiskt. Lagrings- och spårningsdimensioner omfattar site, lagerställe, placering, lagerstatus, batchnummer och serienummer. Du kan bestämma vilka lagrings- och spårningsdimensioner som spåras ekonomiskt. 

**Exempel 1** 

Om lagerdimensionsgruppen som kopplas till artikeln spåras automatiskt av lagerstället, beräknas den löpande genomsnittliga självkostnaden för respektive lagerställe. Följande inköpsorder har fakturerats:

-   En inköpsorder för kvantiteten 2 med en självkostnad på 100,00 kronor har fakturerats för lagerstället GW.
-   En inköpsorder för kvantiteten 3 med en självkostnad på 120,00 kronor har fakturerats för lagerstället GW.
-   En inköpsorder för kvantiteten 5 med en självkostnad på 150,00 kronor har fakturerats för lagerstället MW.

Den löpande genomsnittliga självkostnaden för lagerställe GW är 112,00 kronor, och den löpande genomsnittliga självkostnaden för lagerställe MW är 150,00 kronor. En försäljningsorder bokförs för lagerställe GW. Värdet på lagret och kostnader för sålda varor (före lagerstängningen och utan markering) är 112,00 kronor. En annan försäljningsorder bokförs för lagerställe MW. Värdet på lagret och kostnader för sålda varor (före lagerstängningen och utan markering) är 150,00 kronor. 

**Exempel 2** Om lagringsdimensiongruppen, som är kopplad till artikeln spåras ekonomiskt av lager och spårningsdimensiongruppen spåras ekonomiskt av batchnummer, beräknas den löpande genomsnittliga självkostnaden för respektive batch. 

**Obs!** Vi rekommenderar att du alltid visar självkostnaden med alla ekonomiska dimensioner spårade. Följande inköpsorder har fakturerats:

-   En inköpsorder för kvantiteten 2 med en självkostnad på 100,00 kronor har fakturerats för lagerstället GW och batch AAA.
-   En inköpsorder för kvantiteten 3 med en självkostnad på 120,00 kronor har fakturerats för lagerstället GW och batch AAA.
-   En inköpsorder för kvantiteten 2 med en självkostnad på 150,00 kronor har fakturerats för lagerstället GW och batch BBB.

Den löpande genomsnittliga självkostnaden för lagerställe GW och batch AAA är 112,00 kronor, och den löpande genomsnittliga självkostnaden för lagerställe GW och batch BBB är 150,00 kronor.




