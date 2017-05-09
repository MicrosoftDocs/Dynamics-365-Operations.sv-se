---
title: "Mobil arbetsyta för tillgängligt lager för programmet Microsoft Dynamics 365 for Operations"
description: "Den mobila arbetsytan för tillgängligt lager ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobil arbetsyta för tillgängligt lager för programmet Microsoft Dynamics 365 for Operations

Den mobila arbetsytan för tillgängligt lager ger dig mobil insyn i reserverat och tillgängligt lager, när som helst och var som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om den mobila plattformen Microsoft Dynamics 365 for Operations | [Den mobila plattformen Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | En miljö med Microsoft Dynamics 365 for Operations version 1611 och plattformsuppdatering 3 för Microsoft Dynamics for Operations (november 2016) |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigeringen om du vill aktivera de arbetsytor som finns i ditt Microsoft Dynamics 365 for Operations.                                       |
| Mobil enhet med programmet Dynamics 365 for Operations installerat | Hämta programmet Dynamics 365 for Operations från din mobilappsbutik.                                                                           |

## <a name="introduction"></a>Introduktion
Normalt har företag flera in- och flera utleveranser av lager varje dag. Dessa transporter ändrar konstant tillgänglig lagerstatus. Den mobila arbetsytan för tillgängligt lager låter dig se tillgänglig lagerstatus för hela företaget, vilket ger dig senaste information om lagerdata på valfri mobil enhet. Oavsett om du arbetar i på lagerstället, inom inköp, försäljning, tillverkning, administration eller har andra roller, kan du använda datan för tillgängligt lager när som helst och var som helst. Den mobila arbetsytan ger omedelbar insikt i tillgänglig lagerstatus över flera anläggningar, och låter dig se tillgängligt lager, aktuella materialreservationer samt icke-reserverat, tillgängligt lager. Du kan också ange artikelnummer till en förfrågan om lagerbehållning och söka filtrerat efter produkter i lager eller varianter. Närmare bestämt erbjuder den mobila arbetsytan följande funktioner:

-   Du kan söka efter produktnummer och produktnamn för att hitta produkter att visa lagerbehållningsstatusen för.
-   Du kan visa följande information för valda produkter:
    -   Lagerbehållning efter plats
    -   Lagerbehållning efter lagerställe
    -   Lagerbehållning efter plats
    -   Lagerbehållningen per batch (för batchstyrda produkter)
    -   Lagerbehållning efter lagerstatus

<!-- -->

-   Lagerbehållning för produkt visas på följande sätt:
    -   Genom fysiskt lager (denna vy representerar den totala mängden.)
    -   Genom fysiskt reserverat (denna vy representerar den reserverade mängden.)
    -   Genom fysiskt disponibelt (den här vyn representerar tillgänglig mängd utan reservationer.)

## <a name="get-started"></a>Kom igång
Komma igång med din mobila enhet:

1.  Hämta och installera appen Microsoft Dynamics 365 for Operations från din mobilappsbutik.
2.  Starta appen på din enhet.
3.  Ange din webbadress för Dynamics 365.
4.  Ange ett företag att logga in på. Ange till exempel **USMF**.
5.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor i din mobilapp måste du först publicera önskade arbetsytor i appen Dynamics 365 for Operations app.

1.  Starta Dynamics 365 for Operations.
2.  Navigera till **Systemadministration** &gt; **Inställningar** &gt; **systemparametrar**.
3.  Välj **Hantera mobilapp**.
4.  Markera arbetsytan att publicera i den mobila plattformen.
5.  Välj **Publicera arbetsyta**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-the-onhand-inventory-for-a-product"></a>Visa lagerbehållningen för en produkt
1.  På din mobila enhet väljer du arbetsytan **Lagerbehållning**.
2.  Välj **Kontrollera lagerbehållning för en artikel**. Du kan se en lista över de produkter som laddas i ditt program för användning offline. 50 objekt laddas som standard, men du kan ändra detta antal. Mer information finns i förstudiehandboken.
3.  Om objektet inte finns i listan väljer du **Sök fler** för att utföra en onlinesökning i Dynamics 365 for Operations. Sök efter produktnummer eller växla till en sökning efter produktnamn.
4.  Välj en produkt. Om artikeln har en bild, visas bilden.
5.  Välj ett av följande alternativ för att visa lagerbehållningens status:
    -   Visa lagerbehållning per plats
    -   Visa lagerbehållning per lagerställe
    -   Visa lagerbehållning efter plats
    -   Visa lagerbehållning per batch (för batchstyrda produkter)
    -   Visa lagerbehållning per lagerstatus

    Lagerbehållning för produkt visas på följande sätt:
    -   Genom fysiskt lager (denna vy representerar den totala mängden.)
    -   Genom fysiskt reserverat (denna vy representerar den reserverade mängden.)
    -   Genom fysiskt disponibelt (den här vyn representerar tillgänglig mängd utan reservationer.)




