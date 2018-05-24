---
title: Kostnadsobjekt
description: "Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d35d7971806e2f711d84f172bfacd60edf9f9225
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="cost-objects"></a>Kostnadsobjekt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg.  

## <a name="cost-objects"></a>Kostnadsobjekt

Sidan **Kostnadsobjekt** visar alla kostnadsobjekt som registreras på en produkt. Kostnadsobjekten definieras av data från följande källor:

-   Produkt
-   Produktdimensionsgrupp
-   Lagringsdimensionsgrupp
-   Spårningsdimensionsgrupp

**Notering:** Ett kostnadsobjekt motsvarar ett kostnadselement av typen **Direkt material**. Ett kostnadsobjekt och ett lagerobjekt skiljer på sättet som ett kostnadsobjekt definieras av lagerdimensionerna som har valts för ekonomiskt lager. Ett objekt har till exempel följande konfiguration:

-   **Plats:** Fysiskt lager = Ja, Ekonomiskt lager = Ja
-   **Lagerställe:** Fysiskt lager = Ja, Ekonomiskt lager = Nej
-   **Buntnr.:** Fysiskt lager = Ja, Ekonomiskt lager = Nej

Följande tabell visar vad som är ett kostnadsobjekt och vad som är ett lagerobjekt.

| Objekttyp      | Artikelnummer | Plats | Lagerställe | Buntnr. |
|------------------|-------------|------|-----------|-----------|
| Kostnadsobjekt      | §x           | §x    |           |           |
| Lagerobjekt | §x           | §x    |  §x        | §x         |

## <a name="accumulation-of-costs-and-quantities"></a>Ackumulering av kostnader och kvantiteter
-   Värdet i fältet **Värde** är en summa av följande värden:
    -   Fysiskt kostnadsbelopp
    -   Ekonomiskt självkostnadsbelopp
    -   Justeringar
-   Värdet i fältet **Kvantitet** är en summa av följande värden:
    -   Mottagen
    -   Avdraget
    -   Bokförd kvantitet
-   Fältet **Genomsnittlig enhetskostnad** är ett beräknat fält. Värdet beräknas genom att dela värdet **Värde** genom värdet **Kvantitet**.

**Obs!** Parametern **Inkludera fysiskt värde** påverkar inte de tidigare beräkningarna.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Produktdimensionsgrupp](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Lagringsdimensionsgrupp](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Spårningsdimensionsgrupp](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Nyheter eller ändringar](../../fin-and-ops/get-started/whats-new-changed.md)

[Kostnadsposter](cost-entries.md)




