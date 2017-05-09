---
title: "Mobil arbetsyta för kostnadsstyrning för programmet Microsoft Dynamics 365 for Operations"
description: "Med den kostnadsstyrande mobila arbetsytan kan chefer på kostnadsställen se kostnadsställets effektivitet när som helst och var som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobil arbetsyta för kostnadsstyrning för programmet Microsoft Dynamics 365 for Operations

Med den kostnadsstyrande mobila arbetsytan kan chefer på kostnadsställen se kostnadsställets effektivitet när som helst och var som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om den mobila plattformen Microsoft Dynamics 365 for Operations | [Den mobila plattformen Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Se till att använda en miljö med Microsoft Dynamics 365 for Operations version 1611 och plattformen Microsoft Dynamics for Operations med uppdatering 3 (november 2016). |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigeringen om du vill aktivera de arbetsytor som finns i Microsoft Dynamics 365 for Operations.                                                                       |
| Mobil enhet med programmet Dynamics 365 for Operations installerat | Hämta programmet Dynamics 365 for Operations från din mobilappsbutik.                                                                                                      |

## <a name="introduction"></a>Introduktion
Den kostnadsstyrande mobila arbetsytan ger en omedelbar översikt över aktuell prestanda för kostnadsställen genom att jämföra faktiska kostnader mot budgeterade kostnader. Du kan gå ända ner till statusen för enskilda kostnadselement.

### <a name="example"></a>Exempel

En medarbetare får en inbjudan till en internationell konferens. Organisationen måste täcka alla resekostnader. Medarbetaren frågar sin chef om han/hon kan delta i konferensen. Chefen öppnar chefen snabbt sen mobila arbetsytan för kostnadsstyrning i sin mobiltelefon för att se om budgeten tillåter att medarbetaren deltar i konferensen.

### <a name="data-security"></a>Datasäkerhet

Datan i arbetsytan för kostnadsstyrning skyddas av användarens autentiseringsuppgifter. Chefen för ett kostnadsställe får endast se data för eget kostnadsställe. Säkerheten för åtkomstnivå hanteras inom kostnadsredovisningsmodulen. Kostnadsrevisorerna definierar konfigurationen för den mobila arbetsytan för kostnadsstyrning i kostnadsredovisningsmodulen. När arbetsytan publiceras i programmet Microsoft Dynamics 365 for Operations, blir den tillgänglig i mobilappen Dynamics 365 for Operations. Detta säkerställer att alla chefer för kostnadsställen ser data i samma format.

### <a name="actions-views-and-links"></a>Åtgärder, vyer och länkar

Den mobila arbetsytan för kostnadskontroll för programmet Dynamics 365 for Operations innehåller följande åtgärder, vyer och länkar:

-   Åtgärder 
    -   Välj **Konfigurationer** för att välja en layout.
    -   Välj **Kostnadsobjekt** för att välja kostnadsställen där du vill filtrera data. **Obs!** Listan visas efter den åtkomst som medgetts i modulen Kostnadsredovisning.

<!-- -->

-   Utifrån vad som har markerats under **Åtgärder** och vad som konfigureras i modulen Kostnadsredovisning kan du visa följande information på korten. Tänk på att beloppet visas i samma format: Faktiskt, Budget, Avvikelse samt Avvikelseprocent. 
    -   Faktiskt kontra Budget (aktuell period)
    -   Faktisk kontra reviderad budget (aktuell period)
    -   Faktiskt kontra Budget (föregående period)
    -   Faktisk kontra reviderad budget (föregående period)
    -   Faktiskt kontra budget (hittills i år)
    -   Faktisk kontra reviderad budget (hittills i år)

<!-- -->

-   Länkar
    -   Information om aktuell period.
    -   Information om föregående period.
    -   Information om hittillsvarande år.

När du väljer någon av länkarna visas ett element för Kort per kostnad. Beloppet på kortet visas i följande format: Faktiskt, Budget, Budgetavvikelse, Budgetavvikelseprocent, Reviderad budget, Reviderad budgetavvikelse samt Reviderad budgetavvikelseprocent.  [![kostnadsstyrande](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Kom igång
Följ dessa steg för att komma igång med mobilappen för kostnadsstyrning på din mobila enhet.

1.  Hämta och installera appen Microsoft Dynamics 365 for operations från din mobilappsbutik.
2.  Starta appen på din enhet.
3.  Ange din webbadress för Dynamics 365.
4.  Ange ett företag att logga in på. Ange till exempel **USMF**.
5.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor i din mobilapp måste du först publicera önskade arbetsytor i appen Dynamics 365 for Operations app.

1.  Starta Dynamics 365 for Operations.
2.  Navigera till **Systemadministration** &gt; **Inställningar** &gt; **systemparametrar**.
3.  Välj **Hantera mobilapp**.
4.  Markera arbetsytan **Kostnadsstyrning **för att publicera i den mobila plattformen.
5.  Välj **Publicera arbetsyta**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-the-performance-of-your-cost-center"></a>Visa prestanda för ditt kostnadsställe
1.  På din mobila enhet väljer du arbetsytan **Kostnadsstyrning**.
2.  Välj **Styrning av kostnadsobjekt**.
3.  Klicka på **Åtgärder**.
4.  Klicka på **Välj konfiguration** för att välja en layout för kostnadsstyrning.
5.  Klicka på **Klart**.
6.  Klicka på **Åtgärder**.
7.  Klicka på **Välj kostnadsobjekt** för att välja de kostnadsställen för vilka du har beviljats åtkomst.
8.  Klicka på **Klart**.
9.  Visa total prestanda för ditt kostnadsställe.
10. Klicka på **Information för aktuell period**.
11. Visa prestandan för enskilda kostnadselement.
12. Du kan också söka efter specifika kostnadselement.



