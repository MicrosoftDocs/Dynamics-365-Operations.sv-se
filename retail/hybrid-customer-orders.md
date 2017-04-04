---
title: Kombinerade kundorder
description: "Kombinerade kundorder är en enstaka order som innehåller produkter som kan köras på lager av kunden, liksom produkter som plockas eller levereras senare."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Kombinerade kundorder

Kombinerade kundorder är en enstaka order som innehåller produkter som kan köras på lager av kunden, liksom produkter som plockas eller levereras senare.

I Microsoft Dynamics 365 - för återförsäljning, kan du välja antingen utföra alla produkter eller utföra de valda produkterna för kundorder. Produkten rader som är markerade som utför automatiskt faktureras när ordern skapas, på samma sätt det är samma för en order ska vara plockas upp när ordern skapas. Det förfallna beloppet på kombinerade order bestäms genom att lägga till procentsatsen insättning på Plocka och leverera produktlinjer hur antalet rader. För kombinerade växlar systemet mellan kundens order och Hämtköp läge enligt följande:

-   Om alla produkter i vagnen är **utföra leverans**, ordern ska hanteras som en transaktion i Hämtköp.
-   Om alla rader i vagnen är inställd på antingen **Välj** eller **levererar leveransen**, ordern ska hanteras som en kundtransaktion för ordern.

Överför en vagnrad och **vald plockning**, **transport som valts**, eller **utföra valda** är markerad ställs särskilda vagn raden med den leveransmetod. I så fall fortsätter underordnat flöde av operationen som vanligt. Men om **vald plockning**, **båt markerad**, eller **utföra valda** utan en vagnrad markeras, en ny sida öppnas med en lista över alla rader i vagnen. Du kan välja flera rader på en gång för att levereras på den här skärmen. När du använder denna metod för att välja rader åsidosätts tidigare leveransmetod som har tilldelats raden.

<a name="see-also"></a>Se även
--------

[Order – översikt](customer-orders-overview.md)


