---
title: Skapa en produktionsorder
description: Den här proceduren visar hur du skapar en produktionsorder.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 468465e3e82ff608d7d290b71f058cd790a0f013
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564127"
---
# <a name="create-a-production-order"></a>Skapa en produktionsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar en produktionsorder. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den första proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="create-a-production-order"></a>Skapa en produktionsorder
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
2. Klicka på Ny produktionsorder.
3. Skriv "D0001" i fältet Artikelnummer.
4. Ange ett datum i fältet Leverans.
    * Leveransdatumet anger när tillverkningsordern ska vara klar för att leverera i tid. Det här datumet kan användas i planeringsprocessen. Till exempel tidsplanering av ordern bakåt från leveransdatumet.  
5. Ställ in kvantiteten på 20.
    * Notering: Strukturlistnummerfältet visar automatiskt numret på alla aktiva strukturlistor för den aktuella artikeln, men du kan ändra strukturlistan för tillverkningsordern genom att markera en aktiv strukturlista i listan över godkända strukturlistversioner.    Flödesnummerfältet visar automatiskt numret på alla aktiva flöden för den aktuella artikeln, men du kan ändra flödet för tillverkningsordern genom att markera ett aktivt flöde i listan över godkända flödesversioner.  
6. Klicka på Skapa.

## <a name="validate-the-production-order"></a>Validera produktionsordern
1. Klicka på länken på den valda raden i listan.
    * Klicka på länken till tillverkningsordernumret som du nyss skapat. Då öppnas detaljsidan för ordern.  
2. Klicka på Redigera.
3. Ange ett datum i fältet Leverans.
    * Till exempel ändring av leveransdatumet för produktionsordern.  
4. Klicka på Spara.
5. Stäng sidan.

## <a name="update-the-bom"></a>Uppdatera strukturlistan
1. Klicka på Produktionsorder i åtgärdsfönstret.
2. Klicka på Strukturlista.
    * Öppna strukturlistsidan för att validera strukturlistdata som har kopierats från standarddata när tillverkningsordern skapades. I den här proceduren måste du uppdatera kvantiteten för en strukturlista.  
3. Klicka på Redigera.
4. Ange ett tal i fältet Kvantitet.
    * När du ändrar kvantiteten på strukturlistraden påverkar detta kostnadsuppskattningen av materialförbrukningen för tillverkningsordern.  
5. Klicka på Spara.
6. Stäng sidan.

## <a name="update-the-production-route"></a>Uppdatera produktionsflödet
1. Klicka på Produktionsorder i åtgärdsfönstret.
2. Klicka på Flöde.
    * Öppna flödessidan för att validera data i produktionsflödet som har kopierats från standarddata när ordern skapades. I den här proceduren måste du uppdatera kvantiteten för en av operationerna i produktionsflödet.  
3. Hitta och markera önskad post i listan.
4. Klicka på Redigera.
5. I Processkvantitets- fältet anger du ett tal.
    * När du ändrar processtiden påverkas den beräknade flödesförbrukningen och kostnaden för tillverkningsordern.  
6. Klicka på Spara.
7. Stäng sidan.

