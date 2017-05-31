---
title: Hybridkundorder
description: "Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: eb6ba7cfdf098671192d4d6e73119f96b287c437
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="hybrid-customer-orders"></a>Hybridkundorder

[!include[banner](includes/banner.md)]


Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare.

I Microsoft Dynamics 365 for Operations - Butik kan du välja att antingen leverera alla produkter eller att leverera valda produkter för en kundorder. De produktrader som markerats att utföras faktureras automatiskt när ordern skapas; detsamma gäller för en order som ska hämtas upp när ordern skapas. Det förfallna beloppet i hybridorder bestäms genom att addera depositionsprocentsatsen för produktrader av typen plocka-och-leverera med hela beloppet för de rader som ska utföras. För hybridorder växlar systemet mellan läget för kundorder och läget för cash and carry enligt följande:

-   Om alla produkter i vagnen bär statusen **Utför leverans**, kommer ordern att behandlas som en cash and carry-transaktion.
-   Om någon rad eller alla rader i vagnen bär statusen **Plocka** eller **Skeppa leverans** kommer ordern att hanteras som en kundordertransaktion.

Om en vagnrad har valts och **Plocka valda**, **Skeppa valda** eller **Leverera valda** har markerats, kommer endast den specifika vagnraden att erhålla den leveransmetoden . I så fall fortsätter det underordnade åtgärdsflödet som vanligt. Om emellertid **Plocka valda**, **Skeppa valda** eller **Leverera valda** har valts utan att någon vagnrad har markerats, öppnas en ny sida med en lista över alla vagnrader. På denna skärm kan du välja flera olika rader samtidigt för inställning av leveransmetoden. När du använder denna metod för att välja rader, åsidosätts tidigare leveransmetod som har tilldelats raden.

<a name="see-also"></a>Se även
--------

[Kundorderöversikt](customer-orders-overview.md)




