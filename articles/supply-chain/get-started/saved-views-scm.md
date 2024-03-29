---
title: Standardvyer för Supply Chain Management
description: I denna artikel beskrivs de standardvyer som finns tillgängliga, samt information om hur du aktiverar dem.
author: kamaybac
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f94fffb9aa2c208b8c2c0005a2892853eda66a01
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334848"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Standardvyer för Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management innehåller flera sparade vyer som du kan aktivera och använda efter behov. Vissa av dessa standardvyer optimeras och namnges för en viss roll eller uppgift (till exempel "Kvalitetskontroll" eller "Mottagning"). Andra optimeras så att de bara inkluderar de fält och inställningar som Microsofts användningsstatistik anger används oftast av kunder. Dessa sparade vyer kallas vanligtvis för *förenklade* vyer. I denna artikel beskrivs de standardvyer som finns tillgängliga, samt information om hur du aktiverar och anpassar dem.

Detaljerad information om hur du arbetar med sparade vyer, bland annat standardvyerna, finns i [Sparade vyer](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Anpassa sparade standardvyerna

Du kan anpassa standardvyerna, på samma sätt som du kan anpassa dina egna sparade vyer. När du anpassar en sparad standardvy rekommenderar vi starkt att du sparar din anpassade version med ett nytt namn. Annars kan dina anpassningar skrivas över när du uppdaterar Supply Chain Management.

Mer information om hur du anpassar och byter namn på sparade vyer finns i [Sparade vyer](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Tillgängliga sparade vyer och hur du aktiverar dem

För att använda funktionen sparade vyer, oavsett om du använder standard sparade vyer, måste du aktivera funktionen *Sparade vyer* i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (från och med version 10.0.21 är den här funktionen aktiverad som standard).

I de återstående avsnitten i denna artikel finns register som beskriver de standardvyer som för närvarande är tillgängliga för respektive relevant modul. Varje tabell visar namnet på varje sparad vy, sidan där du kan hitta den och en beskrivning av den. Varje tabell visar även namnet på funktionen som inkluderar den sparade vyn. Om du vill se en sparad standardvy i systemet måste du aktivera den angivna funktionen i [Funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Från och med version 10.0.25 aktiveras alla vyer i listan som standard.

## <a name="saved-views-for-the-inventory-management-module"></a>Sparade vyer för modulen Lagerhantering

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Lagerhantering.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Lista med behållning | Ekonomi | Med denna förenklade vy kan du fokusera på ekonomisk information medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Lista med behållning | Kvalitetskontroll | Med denna förenklade vy kan du fokusera på kvalitetskontroll medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Lista med behållning | Mottagning | Med denna förenklade vy kan du fokusera på mottagningsåtgärder medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Lista med behållning | Leverans | Med denna förenklade vy kan du fokusera på leveransåtgärderna medan du hanterar lagerbehållning. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Transaktioner | Förenklad | Med den här förenklade vyn kan du granska lagerstatusen utan att bli distrakterad av ekonomisk information och andra fält som används mindre ofta. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Överföringsorder | Leverans | Med denna förenklade vy kan du fokusera på leveransåtgärderna medan du hanterar överföringsorder. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Överföringsorder | Mottagning | Med denna förenklade vy kan du fokusera på mottagningsåtgärder medan du hanterar överföringsorder. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Överföringsorder | Kvalitetskontroll | Med denna förenklade vy kan du fokusera på kvalitetskontroll medan du hanterar överföringsorder. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Överföringsorder | Ekonomi | Med denna förenklade vy kan du fokusera på ekonomisk information medan du hanterar överföringsorder. | Sparade vyer för lagerhantering<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-master-planning-module"></a>Sparade vyer för modulen Huvudplanering

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Huvudplanering.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Planerad order: Detaljsida för planerade order | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används för att arbeta med detaljer för en enskild planerad order. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för planerade order<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Planerad order: Listsida för planerade order | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används för att arbeta med listan över planerade beställningar. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för planerade order<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Sparade vyer för modulen Anskaffning och inköp

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Anskaffning och inköp.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Inköpsorderdetaljer | Order skapande | Den här förenklade vyn är optimerad för att skapa nya inköpsorder. | Sparade vyer för inköpsorder<br><br>På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Inköpsorderdetaljer | Lagerhantering | Denna förenklade vy är optimerad för att utföra lagerrelaterade aktiviteter, såsom att följa upp lager som har mottagits, ta emot lager, kontrollera nettobehov och justera orderkvantiteter. | Sparade vyer för inköpsorder<br><br>På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Inköpsorderdetaljer | Ekonomistyrning | Denna förenklade vy är optimerad för att utföra ekonomirelaterade aktiviteter, till exempel fakturera och kontrollera priser, summor och avgifter. | Sparade vyer för inköpsorder<br><br>På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Inköpsorderdetaljer | Ordergodkännande | Den här förenklade vyn är optimerad för att godkänna inköpsorder. | Sparade vyer för inköpsorder<br><br>På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-product-information-management-module"></a>Sparade vyer för modulen Produktinformationshantering

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Produktinformationshantering.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Lista med frisläppta produkter | Produktgenerering | En förenklad sidvy som endast innehåller fälten som oftast används vid skapande av produkter. | Sparade vyer för frisläppta produkter<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Information om frisläppt produkt | Produktgenerering | En förenklad sidvy som endast innehåller fälten som oftast används vid skapande av produkter. | Sparade vyer för frisläppta produkter<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Information om frisläppt produkt | Hantering av logistisk information | En förenklad sidvy som endast innehåller fälten som oftast används vid hantering av logistisk information för produkter. | Sparade vyer för frisläppta produkter<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Information om frisläppt produkt | Hantering av inköpsinformation | En förenklad sidvy som endast innehåller fälten som oftast används vid hantering av inköpsinformation för produkter. | Sparade vyer för frisläppta produkter<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Information om frisläppt produkt | Hantering av försäljningsinformation | En förenklad sidvy som endast innehåller fälten som oftast används vid hantering av försäljningsrelaterad information för produkter. | Sparade vyer för frisläppta produkter<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-production-control-module"></a>Sparade vyer för modulen Produktionskontroll

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Produktionskontroll.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Strukturlistesidan för produktionsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Sidan Produktionsorderdetaljer | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Plocklistesida för tillverkningsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |
| Listsidan för produktionsorder | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparade vyer för produktionskontroll<br><br>(På som standard från version 10.0.21. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Sparade vyer för modulen Försäljning och marknadsföring

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Försäljning och marknadsföring.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Följesedelsjournal | Journalgranskning | Denna förenklade vy innehåller bara de fält som oftast används för granskning av följesedelsjournaler. | Sparade vyer för försäljning och marknadsföring<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Försäljningsorder | Ordergenerering | Denna förenklade vy innehåller bara de fält som oftast används för att skapa försäljningsorder. | Sparade vyer för försäljning och marknadsföring<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Försäljningsorder | Ordergranskning | Denna förenklade vy innehåller bara de fält som oftast används för att granska försäljningsorder. | Sparade vyer för försäljning och marknadsföring<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Försäljningsoffert | Offertgenerering | Denna förenklade vy innehåller bara de fält som oftast används för att skapa försäljningsofferter. | Sparade vyer för försäljning och marknadsföring<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |

## <a name="saved-views-for-the-warehouse-management-module"></a>Sparade vyer för modulen Hantering av distributionslager

I följande tabell beskrivs de sparade vyerna som är tillgängliga för modulen Hantering av distributionslager.

| Sida | Vynamn | Visa beskrivningen | Funktionsnamn |
|---|---|---|---|
| Alla laster | Inkommande bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta ingående laster. | Sparade vyer för lastbearbetning<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Alla laster | Utgående bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta utgående laster. | Sparade vyer för lastbearbetning<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Alla leveranser | Ingående bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta ingående leveranser. | Sparade vyer för leveransbearbetning<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Alla leveranser | Utgående bearbetning | Denna förenklade vy innehåller bara de fält som oftast används för att bearbeta utgående leveranser. | Sparade vyer för leveransbearbetning<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Alla påfyllnader | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för påfyllnadsbearbetning<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Workbench för lastplanering | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för workbench vid lastplanering<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |
| Information om arbete | Förenklad | Den här förenklade vyn innehåller bara de fält som oftast används. På det här sättet blir det en snabbare översikt och en strömlinjeformad arbetsprocess. | Sparad vy för sidan Information om arbete<br><br>(På som standard från version 10.0.25. Obligatorisk från version 10.0.29.) |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]