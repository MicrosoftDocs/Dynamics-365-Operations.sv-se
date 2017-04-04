---
title: "Inventera lagerbehållning mobil arbetsytan för Microsoft Dynamics 365 för operationer app"
description: "Lager i behållning mobil arbetsytan hjälper dig att få mobila insyn i lager reserveras och tillgängliga när som helst och var som helst."
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

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Inventera lagerbehållning mobil arbetsytan för Microsoft Dynamics 365 för operationer app

Lager i behållning mobil arbetsytan hjälper dig att få mobila insyn i lager reserveras och tillgängliga när som helst och var som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om Microsoft Dynamics 365 för operationer | [Dynamics 365 för operationer](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 för operationer                                          | En miljö med Microsoft Dynamics 365 för operationer version 1611 och Microsoft Dynamics-datorer operationer uppdatering 3 (2016 November) |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigering om du vill aktivera arbetsytor som finns i din Microsoft Dynamics 365 för operationer.                                       |
| Mobil enhet med Dynamics 365 för operationer program installerat | Hämta mobiltelefonprogrammet lagringsplatsen Dynamics 365 för operationer app.                                                                           |

## <a name="introduction"></a>Introduktion
Normalt har företag flera in- och flera utleveranser av lager varje dag. Transporterna ändra ständigt status lagerbehållning. Lager i behållning mobil arbetsytan kan du se statusen korsföretags lagerbehållning så att du kan få de senaste insyn i lagerdata på den mobila enheten du väljer. Oavsett om du arbetar i lagerställe, inköp, försäljning, tillverkning eller hantering eller har andra roller kan använda du lagerbehållning data när som helst och var som helst. Mobil arbetsytan kan du Visa lagerbehållning i lokaler och aktuella reservationerna material oreserverade lagerbehållning och ger en översikt över lagerbehållning status över lokaler. Du kan också ange artikelnummer till frågan lagerbehållning och filtrerade söka efter produkter i lager eller varianter. Närmare bestämt innehåller mobil arbetsytan dessa funktioner:

-   Du kan söka efter produktnummer och produktnamn hitta produkter att visa status för lagerbehållningen.
-   Du kan visa följande information för de valda produkterna:
    -   Lagerbehållningen per site
    -   Lagerbehållning per lagerställe
    -   Lagerbehållning per lagerställe
    -   Lagerbehållningen per parti (för batch-styrd produkter)
    -   Lagerbehållningen per lagerstatus

<!-- -->

-   Produkt i lager visas på följande sätt:
    -   Med fysiskt lager (vyn representerar det totala beloppet.)
    -   Med fysiskt reserverat (vyn motsvarar beloppet som reserverats.)
    -   Med fysiskt disponibelt (den här vyn representerar Disponibelt belopp som har inga reservationer.)

## <a name="get-started"></a>Kom igång
Komma igång med din mobila enhet:

1.  Hämta och installera Microsoft Dynamics 365 for app operationer från lagringsplatsen för mobiltelefonprogrammet.
2.  Starta programmet för enheten.
3.  Ange en Webbadress för Dynamics 365.
4.  Ange att logga in på företaget. Till exempel anger **USMF**.
5.  Första gången du loggar in, uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 för operationer. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor på din mobiltelefonprogrammet måste du publicera önskade arbetsytor till Dynamics 365 for app operationer.

1.  Starta Dynamics 365 för operationer.
2.  Gå till **systemadministration**&gt;**inställningar**&gt;**systemparametrar**.
3.  Välj **hantera mobiltelefonprogrammet**.
4.  Markera arbetsytan för att publicera på en mobil plattform.
5.  Välj **publicera arbetsytan**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-the-onhand-inventory-for-a-product"></a>Visa behållningen lager för en produkt
1.  På din mobila enhet väljer du den **lagerbehållning** arbetsytan.
2.  Välj **Kontrollera lagerbehållning för en artikel**. Du kan se en lista över produkter som laddas i ditt program för användning offline. 50 objekten läses som standard, men du kan ändra detta värde. Mer information finns i förväg läsa handboken.
3.  Om objektet inte finns i listan, väljer du **söka mer** behöver en online letar i Dynamics 365 operationer. Sök efter produktnummer eller växla till en sökning efter produktnamn.
4.  Välj en produkt. Om artikeln har en bild, visas bilden.
5.  Välj ett av följande alternativ för att visa lagerbehållningen status:
    -   Visa behållning per site
    -   Visa lagerbehållning per lagerställe
    -   Visa lagerbehållning per lagerställe
    -   Visa behållning per parti (för batch-styrd produkter)
    -   Visa behållning per lagerstatus

    Produkt i lager visas på följande sätt:
    -   Med fysiskt lager (vyn representerar det totala beloppet.)
    -   Med fysiskt reserverat (vyn motsvarar beloppet som reserverats.)
    -   Med fysiskt disponibelt (vyn representerar det tillgängliga beloppet som har inga reservationer.)




