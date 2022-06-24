---
title: Tidsplanera en produktionsorder med åtgärder och jobbplanering
description: Denna artikel fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d82d5439e57c02ddc9db4222a946bd15f4ed67e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903939"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Tidsplanera en produktionsorder med åtgärder och jobbplanering

[!include [banner](../../includes/banner.md)]

Denna artikel fokuserar på tidsplanering av en produktionsorder med grovplanering och finplanering. Inga jobb skapas med grovplanering medan jobb skapas med finplanering. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här proceduren är avsedd för produktionschefen, produktionsplaneraren eller butikens arbetsledare som arbetar i en miljö med diskret tillverkning.


## <a name="create-a-production-order"></a>Skapa en produktionsorder
1. I Navigeringsfönster, gå till **Moduler > Produktionskontroll > Produktionsorder > Alla produktionsorder**.
2. Välj **Ny produktionsorder**.
3. I fältet **artikelnummer** anger du eller väljer ett värde. Välj artikelnummer **D0001**.  
4. Markera **Skapa**.

## <a name="schedule-operations-for-the-production-order"></a>Tidsplanera åtgärder för produktionsordern.
1. Markera den nyss skapade raden.      
2. I åtgärdsfönstret, välj **Tidsplan**.
3. Välj **Tidsplanera åtgärder**.
4. Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.
5. Ange ett datum i fältet **Planeringsdatum**. Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
6. Välj **OK**.
7. Markera vald rad i listan. Observera att statusen ändras till **Tidsplanerad**. 
8. Välj **Alla jobb**. Observera att inga jobb skapas med grovplanering.  
9. Stäng sidan.

## <a name="schedule-jobs-for-the-production-order"></a>Tidsplanera jobben för produktionsordern
1. I åtgärdsfönstret, välj **Tidsplan**.
2. Välj **Tidsplanera jobb**.
3. Välj **Framåt från tidsplaneringsdatum** i fältet **Planeringsriktning**.
4. Ange ett datum i fältet **Planeringsdatum**. Välj ett framtida datum, till exempel idag plus en vecka. Med den valda planeringsriktningen kommer produktionsordern att tidsplaneras framåt från det här datumet.  
5. Välj **OK**.
6. Välj **Produktionsorder** i åtgärdsfönstret.
7. Välj **Alla jobb**. Observera att 5 jobb skapas med jobbplanering baserat på den aktiva rutten.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]