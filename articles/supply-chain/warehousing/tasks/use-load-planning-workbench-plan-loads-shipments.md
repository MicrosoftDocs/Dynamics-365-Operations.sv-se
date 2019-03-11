---
title: Planera laster och utleveranser med workbench för lastplanering
description: I den här proceduren visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "343913"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planera laster och utleveranser med workbench för lastplanering

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du använder workbench för lastplanering om för att skapa en beläggning för en försäljningsorder. Som en förutsättning skapar vi försäljningsordern först. Den här proceduren utgör en del av det dagliga arbetet för transportkoordinatorn. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-sales-order"></a>Skapa en försäljningsorder
1. Gå till Leverantörsreskontra > Order > Alla försäljningsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Välj kontot US-004.
5. Klicka på OK.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
7. Välj artikel A0001.
    * A0001 har aktiverats för transporthantering.  
8. Klicka på länken på den valda raden i listan.
9. Ange ett tal i fältet Kvantitet.
10. Skriv "24" i fältet Lagerställe.
    * Välj lagerställe 24 i det här exemplet. Lagerstället aktiveras för transportledning och avancerad lagerstyrning.  
11. Klicka på Spara.
12. Stäng sidan.

## <a name="create-a-new-load"></a>Skapa en ny beläggning.
1. Gå till Transporthantering > Planering > Workbench för lastplanering.
2. Klicka på fliken Försäljningsrader.
    * Nu skapar du beläggningen för den försäljningsorder som du precis skapade. Beläggningar kan skapas med utgångspunkt i tillgång och efterfrågan från inköpsorder, överföringsorder och försäljningsorder.  
3. Klicka på Tillgång och efterfrågan i åtgärdsfönstret.
4. Klicka på Till ny beläggning.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Beläggningsmall-ID.
    * Beläggningsmallen definierar maximala mått för vikt och volym för hela beläggningen. Beläggningsmallen kan till exempel representera storleken på en behållare eller en lastbil.  
6. Klicka på länken på den valda raden i listan.
7. Klicka på OK.

## <a name="rate-and-route-the-load"></a>Tariff och rutt för beläggningen
1. Klicka på Värdering och rutt.
2. Klicka på Ruttworkbench för tariff.
3. Klicka på Tariffbutik.
4. Hitta och markera önskad post i listan.
5. Klicka på Tilldela.
6. Stäng sidan.
7. Stäng sidan.

