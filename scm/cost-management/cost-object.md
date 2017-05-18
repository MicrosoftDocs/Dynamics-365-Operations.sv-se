---
title: Kostnadsobjekt
description: "Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 42d7ba8a41840024dc16df6863ba5eabd9c37c09
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="cost-objects"></a>Kostnadsobjekt

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg.  

<a name="cost-objects"></a>Kostnadsobjekt
------------

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

**Obs!** Parametern **Inkludera fysiskt värde **påverkar inte de tidigare beräkningarna.

<a name="see-also"></a>Se även
--------

[Produktdimensionsgrupp](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[Lagringsdimensionsgrupp](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[Spårningsdimensionsgrupp](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[Nyheter och ändringar i Microsoft Dynamics AX](/dynamics365/operations/dev-itpro/get-started/whats-new-changed)

[Kostnadsposter](cost-entries.md)




