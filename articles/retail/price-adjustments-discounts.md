---
title: Prisjusteringar och rabatter
description: "Den här artikeln innehåller information om prisjusteringar och rabatter i Microsoft Dynamics 365 for Retail."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 9220cc12abf7134d425e088939d20ea03239a75a
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="price-adjustments-and-discounts"></a>Prisjusteringar och rabatter

[!include [banner](includes/banner.md)]

Den här artikeln innehåller information om prisjusteringar och rabatter i Microsoft Dynamics 365 for Retail.

I Dynamics 365 for Retail kan du göra prisjusteringar för produkter och även ställa in rabatter som tillämpas på en radartikel eller transaktion i kassan (POS), på en försäljningsorder för kundtjänst eller på en onlineorder. Både prisjusteringar och rabatter kan länkas till prisgrupper. För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut. Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier. Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten. Dynamics 365 for Retail använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset. Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt. Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Butiksparametrar** innan du definierar en ny prisjustering eller rabatt. **Obs!** Du kan ta bort en prisjustering eller rabatt. Statistisk information går dock förlorad.

### <a name="types-of-discounts"></a>Typer av rabatter

Det finns fyra typer av butiksrabatter:

-   **Enkel rabatt** – En procentandel eller ett belopp.
-   **Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.
-   **Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.
-   **Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.

Både prisjusteringar och rabatter kan associeras till prisgrupper. Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.




