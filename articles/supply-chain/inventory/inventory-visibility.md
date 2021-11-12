---
title: Översikt över tillägg för Lagersynlighet
description: Detta avsnitt förklarar vad Lagersynlighet är och beskriver dess funktioner.
author: yufeihuang
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1ea1d8c1b0e8c996ead8461005960fa756ce6ca7
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678919"
---
# <a name="inventory-visibility-add-in-overview"></a>Översikt över tillägg för Lagersynlighet

[!include [banner](../includes/banner.md)]

Tillägget för lagersynlighet (kallas även *Lagersynlighet*) är en oberoende och ytterst skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid. Därför ger det en global vy över lagret.

Externa system kommer åt tjänsten via RESTful-API:er. På så sätt kan de antingen söka efter behållningsinformation i givna dimensionsuppsättningar eller utföra lagerändringar i olika anpassade datakällor.

I egenskap av en mikrotjänst som bygger på Microsoft Dataverse erbjuder Lagersynlighet utbytbarhet. Du kan använda Power Apps för att skapa program. Du kan också använda Power BI i syfte att tillhandahålla anpassade funktioner som uppfyller företagets krav.

Du kan integrera Lagersynlighet med flera olika tredjepartssystem genom att ange konfigurationsalternativ för standardiserade lagerdimensioner och konfigurera transaktionstyper. Lagersynlighet stöder också anpassningsbar utbyggbarhet genom konfigurerbara beräknade kvantiteter.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Integrera Lagersynlighet med Dynamics 365 Supply Chain Management

Den integrerade lösningen hämtar lagerdata från Dynamics 365 Supply Chain Management och spårar lagerändringar kontinuerligt. Mer information finns i [Installera och konfigurera lagersynlighet](inventory-visibility-setup.md) och [Konfigurera lagersynlighet](inventory-visibility-configuration.md).

## <a name="get-a-global-view-of-inventory"></a>Hämta en global vy över lager

Med den integrerade lösningen kan du definiera egna datakällor och centralisera lagerdata. Mer information finns i [Konfigurera Lagersynlighet](inventory-visibility-configuration.md).

Du kan visa ditt lager på två sätt:

- Skicka en fråga via API:t för hög prestanda. Detta API kan returnera lagerdata i närapå realtid direkt från en cachelagrad instans. Du kan hitta avtal och exempel i [Allmänna API:er för lagersynlighet](inventory-visibility-api.md).
- Visa den obearbetade behållningslistan. Listan synkroniseras regelbundet från en cachelagrad instans och visas i Dataverse. Mer information finns i [appen Lagersynlighet](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Preliminära reservationer

Preliminär reservation gäller när ett företag måste reservera en viss kvantitet produkter för att till exempel stödja uppfyllelse av försäljningsorder som undviker överförsäljning. När en försäljningsorder skapas och bekräftas i Supply Chain Management eller andra orderhanteringssystem skickas en begäran om att reservera kvantiteten till Lagersynlighet. Med Lagersynlighet kan du reservera produkter med dimensionsdetaljer och specifika lagertransaktionstyper. (Mer information finns i [appen Lagersynlighet](inventory-visibility-power-platform.md).) När kvantiteten har reserverats returneras ett reservations-ID. Du kan använda detta reservations-ID för att länka tillbaka till den ursprungliga ordern i Supply Chain Management eller andra orderhanteringssystem.

Funktionen har utformats så att en reservation i Lagersynlighet inte ändrar den totala kvantiteten. Istället flaggas bara den reserverade kvantiteten. (Därför kallas det en *preliminär reservation*.) Den preliminärreserverade kvantiteten kan motbokas när produkterna förbrukas i Supply Chain Management eller ett tredjepartssystem genom att anropa API:et igen i syfte att göra ett kvantitetsavdrag och uppdatera den totala kvantiteten i Lagersynlighet. Mer information finns i [Reservationer för Lagersynlighet](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
