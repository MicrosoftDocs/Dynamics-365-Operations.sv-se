---
title: Hybridkundorder
description: Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 92be01210b677228f4c096ffef09d7109ba2b332
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023403"
---
# <a name="hybrid-customer-orders"></a>Hybridkundorder

[!include [banner](includes/banner.md)]

Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare.

I Retail kan du välja att antingen leverera alla produkter eller att leverera valda produkter för en kundorder. De produktrader som markerats att utföras faktureras automatiskt när ordern skapas; detsamma gäller för en order som ska hämtas upp när ordern skapas. Det förfallna beloppet i hybridorder bestäms genom att addera depositionsprocentsatsen för produktrader av typen plocka-och-leverera med hela beloppet för de rader som ska utföras. För hybridorder växlar systemet mellan läget för kundorder och läget för cash and carry enligt följande:

- Om alla produkter i vagnen bär statusen **Utför leverans**, kommer ordern att behandlas som en cash and carry-transaktion.
- Om någon rad eller alla rader i vagnen bär statusen **Plocka** eller **Skeppa leverans** kommer ordern att hanteras som en kundordertransaktion.

Om en vagnrad har valts och **Plocka valda**, **Skeppa valda** eller **Leverera valda** har markerats, kommer endast den specifika vagnraden att erhålla den leveransmetoden . I så fall fortsätter det underordnade åtgärdsflödet som vanligt. Om emellertid **Plocka valda**, **Skeppa valda** eller **Leverera valda** har valts utan att någon vagnrad har markerats, öppnas en ny sida med en lista över alla vagnrader. På denna skärm kan du välja flera olika rader samtidigt för inställning av leveransmetoden. När du använder denna metod för att välja rader, åsidosätts tidigare leveransmetod som har tilldelats raden.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kundorder](customer-orders-overview.md)
