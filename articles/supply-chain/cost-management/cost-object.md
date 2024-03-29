---
title: Kostnadsobjekt
description: Det här avsnittet innehåller information om kostnadsobjekt och en beskrivning av hur kostnader och kvantiteter ackumuleras. Ett kostnadsredovisning är ett objekt som kostnader och kvantiteter ackumuleras för. En kostnadsobjektenhet kan vara antingen en produkt eller produktvarianter såsom varianter för stil och färg.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93220208384ccb1a3cc8ff43d83577293e1f029e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672470"
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

## <a name="additional-resources"></a>Ytterligare resurser

[Produktdimensionsgrupp](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[Lagringsdimensionsgrupp](/dynamicsax-2012//storage-dimension-groups-form)

[Spårningsdimensionsgrupp](/dynamicsax-2012//tracking-dimension-groups-form)

[Nyheter eller ändringar](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[Kostnadsposter](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]