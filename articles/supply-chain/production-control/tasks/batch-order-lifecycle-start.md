---
title: Batchorderlivscykel för början till start
description: I den här proceduren får du hjälp med den första delen av livscykeln för en batchorder.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e57cd9254185b73f544e8ff4f7658cf743b672f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437399"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a>Batchorderlivscykel för början till start

[!include [banner](../../includes/banner.md)]

I den här proceduren får du hjälp med den första delen av livscykeln för en batchorder.

Från skapande, kostnadsberäkning och över produktionsjobb tidsplanering till den verkliga början av en batchorder.



Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. 



Följande förutsättningar gäller för körning av proceduren med en annan datauppsättning är en frisläppt produkt med aktiv formel och flödesversion.


## <a name="create-a-batch-order"></a>Skapa en batchorder
1. Gå till Alla produktionsorder.
2. Klicka på Ny batchorder.
3. Ange eller välj ett värde i fältet Artikelnummer.
4. Klicka på Skapa.
5. Använd snabbfiltret för att filtrera på fältet Produktion med värdet ”b”.

## <a name="view-production-formula-and-expected-co-products"></a>Visa produktionsformeln och förväntade samprodukter
1. Klicka på Produktionsorder i åtgärdsfönstret.
2. Klicka på Recept.
3. Stäng sidan.
4. Klicka på Samprodukter.
5. Stäng sidan.

## <a name="estimate-the-batch-order"></a>Uppskatta batchordern
1. Klicka på Uppskattning.
2. Klicka på OK.
3. Klicka på Hantera kostnader i åtgärdsfönstret.
4. Klicka på Visa beräkningsuppgifter.
5. Stäng sidan.

## <a name="release-the-batch-order"></a>Frisläpp batchordern
1. Klicka på Produktionsorder i åtgärdsfönstret.
2. Klicka på Frisläpp.
3. Klicka på OK.

## <a name="schedule-production-jobs"></a>Schemalägg produktionsjobb
1. Klicka på Tidsplanera i åtgärdsfönstret.
2. Klicka på Tidsplanera jobb.
3. Välj Nej i fältet Begränsad kapacitet.
4. Välj Nej i fältet Begränsat material.
5. Klicka på OK.
6. Klicka på Produktionsorder i åtgärdsfönstret.
7. Klicka på Alla jobb.
8. Stäng sidan.

## <a name="start-the-batch-order"></a>Starta batchordern
1. Klicka på Start.
2. Klicka på fliken Allmänt.
3. Välj Nej i fältet Bokför plocklista nu.
4. Klicka på OK.
5. Klicka på Visa i åtgärdsfönstret.
6. Klicka på Plocklista.
7. Klicka på länken på den valda raden i listan.
8. Stäng sidan.
9. Stäng sidan.
10. Klicka på Flödeskort.
11. Klicka på länken på den valda raden i listan.
12. Stäng sidan.
13. Stäng sidan.

