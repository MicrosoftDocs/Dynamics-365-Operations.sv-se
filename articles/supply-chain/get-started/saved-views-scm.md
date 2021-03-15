---
title: Standardvyer för Supply Chain Management
description: I det här avsnittet beskrivs de standardvyer som finns tillgängliga, samt information om hur du aktiverar dem.
author: kamaybac
manager: annbe
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 78cb1c5a90061af224fcd5933af81b6c5cd7e57d
ms.sourcegitcommit: 5d62c53d84f2ec27136427acfd4314d055298a7b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5123478"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Standardvyer för Supply Chain Management

Microsoft Dynamics 365 Supply Chain Management innehåller flera sparade vyer som du kan aktivera och använda efter behov. Vissa av dessa standardvyer optimeras och namnges för en viss roll eller uppgift (till exempel "Kvalitetskontroll" eller "Mottagning"). Andra optimeras så att de bara inkluderar de fält och inställningar som Microsofts användningsstatistik anger används oftast av kunder. Dessa sparade vyer kallas vanligtvis för *förenklade* vyer. I det här avsnittet beskrivs de standardvyer som finns tillgängliga, samt information om hur du aktiverar och anpassar dem.

Detaljerad information om hur du arbetar med sparade vyer, bland annat standardvyerna, finns i [Sparade vyer](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Anpassa sparade standardvyerna

Du kan anpassa standardvyerna, på samma sätt som du kan anpassa dina egna sparade vyer. När du anpassar en sparad standardvy rekommenderar vi starkt att du sparar din anpassade version med ett nytt namn. Annars kan dina anpassningar skrivas över när du uppdaterar Supply Chain Management.

Mer information om hur du anpassar och byter namn på sparade vyer finns i [Sparade vyer](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Tillgängliga sparade vyer och hur du aktiverar dem

För att använda funktionen sparade vyer, oavsett om du använder standard sparade vyer, måste du aktivera funktionen *Sparade vyer* i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

I de återstående avsnitten i det här avsnittet finns register som beskriver de standardvyer som för närvarande är tillgängliga för respektive relevant modul. Varje tabell visar namnet på varje sparad vy, sidan där du kan hitta den och en beskrivning av den. Varje tabell visar även namnet på funktionen som inkluderar den sparade vyn. Om du vill se en sparad standardvy i systemet måste du aktivera den angivna funktionen i [Funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="saved-views-for-the-inventory-management-module"></a>Sparade vyer för modulen Lagerhantering

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Lagerhantering.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Lista med behållning | Ekonomi | Med denna förenklade vy kan du fokusera på ekonomisk information medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering |
| Lista med behållning | Kvalitetskontroll | Med denna förenklade vy kan du fokusera på kvalitetskontroll medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering |
| Lista med behållning | Mottagning | Med denna förenklade vy kan du fokusera på mottagningsåtgärder medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering |
| Lista med behållning | Transport | Med denna förenklade vy kan du fokusera på leveransåtgärderna medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering |
| Transaktioner | Förenklad | Med den här förenklade vyn kan du granska lagerstatusen utan att bli distrakterad av ekonomisk information och andra fält som används mindre ofta. | Sparade vyer för lagerhantering |
| Överföringsorder | Transport | Med denna förenklade vy kan du fokusera på leveransåtgärderna medan du hanterar överföringsorder. | Sparade vyer för lagerhantering |
| Överföringsorder | Mottagning | Med denna förenklade vy kan du fokusera på mottagningsåtgärder medan du hanterar överföringsorder. | Sparade vyer för lagerhantering |
| Överföringsorder | Kvalitetskontroll | Med denna förenklade vy kan du fokusera på kvalitetskontroll medan du hanterar överföringsorder. | Sparade vyer för lagerhantering |
| Överföringsorder | Ekonomi | Med denna förenklade vy kan du fokusera på ekonomisk information medan du hanterar överföringsorder. | Sparade vyer för lagerhantering |

## <a name="saved-views-for-the-master-planning-module"></a>Sparade vyer för modulen Huvudplanering

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Huvudplanering.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Planerad order: Detaljsida för planerade order | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används för att arbeta med detaljer för en enskild planerad order. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för planerade order |
| Planerad order: Listsida för planerade order | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används för att arbeta med listan över planerade beställningar. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för planerade order |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Sparade vyer för modulen Anskaffning och inköp

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Anskaffning och inköp.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Inköpsorderdetaljer | Order skapande | Den här förenklade vyn är optimerad för att skapa nya inköpsorder. | Sparade vyer för inköpsorder |
| Inköpsorderdetaljer | Lagerhantering | Denna förenklade vy är optimerad för att utföra lagerrelaterade aktiviteter, såsom att följa upp lager som har mottagits, ta emot lager, kontrollera nettobehov och justera orderkvantiteter. | Sparade vyer för inköpsorder |
| Inköpsorderdetaljer | Ekonomistyrning | Denna förenklade vy är optimerad för att utföra ekonomirelaterade aktiviteter, till exempel fakturera och kontrollera priser, summor och avgifter. | Sparade vyer för inköpsorder |
| Inköpsorderdetaljer | Ordergodkännande | Den här förenklade vyn är optimerad för att godkänna inköpsorder. | Sparade vyer för inköpsorder |

## <a name="saved-views-for-the-production-control-module"></a>Sparade vyer för modulen Produktionskontroll

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Produktionskontroll.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Strukturlistesidan för produktionsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll |
| Sidan Produktionsorderdetaljer | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll |
| Plocklistesida för tillverkningsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll |
| Listsidan för produktionsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Sparade vyer för modulen Försäljning och marknadsföring

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Försäljning och marknadsföring.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Följesedelsjournal | Journalgranskning | Denna förenklade vy innehåller bara de fält som oftast används för granskning av följesedelsjournaler. | Sparade vyer för försäljning och marknadsföring |
| Försäljningsorder | Order skapande | Denna förenklade vy innehåller bara de fält som oftast används för att skapa försäljningsorder. | Sparade vyer för försäljning och marknadsföring |
| Försäljningsorder | Ordergranskning | Denna förenklade vy innehåller bara de fält som oftast används för att granska försäljningsorder. | Sparade vyer för försäljning och marknadsföring |
| Försäljningsoffert | Offertskapande | Denna förenklade vy innehåller bara de fält som oftast används för att skapa försäljningsofferter. | Sparade vyer för försäljning och marknadsföring |

## <a name="saved-views-for-the-warehouse-management-module"></a>Sparade vyer för modulen Hantering av distributionslager

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Hantering av distributionslager.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Alla laster | Inkommande bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta ingående laster. | Sparade vyer för lastbearbetning |
| Alla laster | Utgående bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta utgående laster. | Sparade vyer för lastbearbetning |
| Alla leveranser | Inkommande bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta ingående leveranser. | Sparade vyer för leveransbearbetning |
| Alla leveranser | Utgående bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta utgående leveranser. | Sparade vyer för leveransbearbetning |
| Alla påfyllnader | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för påfyllnadsbearbetning |
| Workbench för lastplanering | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för arbetsplaneringens workbench |
| Information om arbete | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för sidan Information om arbete |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]