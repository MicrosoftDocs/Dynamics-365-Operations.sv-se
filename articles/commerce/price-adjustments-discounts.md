---
title: Prisjusteringar och rabatter
description: Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f29e90e1c61792c70d4d6eaeee7758676bf193b2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972506"
---
# <a name="price-adjustments-and-discounts"></a>Prisjusteringar och rabatter

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.

I Commerce kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i POS, en försäljningsorder i kundtjänst eller på en beställning online. Både prisjusteringar och rabatter kan länkas till prisgrupper. För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut. 

Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier. Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten. Commerce använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset. Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt. Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Handelsparametrar** innan du definierar en ny prisjustering eller rabatt.

> [!NOTE]
> Du kan ta bort en prisjustering eller rabatt. Statistisk information går dock förlorad.

## <a name="types-of-discounts"></a>Typer av rabatter

Det finns många olika typer av rabatter:

- **Enkel rabatt** – En procentandel eller ett belopp.
- **Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.
- **Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.
- **Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.
- **Kassabaserad rabatt** – En rabatt som tillämpas när transaktionens totalsumma överstiger ett angivet belopp och ett visst betalsätt (t. ex. kassa, kredit eller betalkort) används för betalning.
- **Leveransrabatt** – En rabatt som tillämpas när transaktionssumman är mer än ett angivet belopp och ett specifikt leveranssätt (t. ex. två dagars leverans nästföljande dag) används på ordern.

Både prisjusteringar och rabatter kan associeras till prisgrupper. Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.


[!INCLUDE[footer-include](../includes/footer-banner.md)]