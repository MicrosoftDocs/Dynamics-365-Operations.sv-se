---
title: Prisjusteringar och rabatter
description: "Den här artikeln innehåller information om prisjusteringar och rabatter i Butik och handel i Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 01f249cbdabc6febf23dcd7103d4587cecdaad08
ms.lasthandoff: 03/31/2017


---

# <a name="price-adjustments-and-discounts"></a>Prisjusteringar och rabatter

[!include[banner](includes/banner.md)]


Den här artikeln innehåller information om prisjusteringar och rabatter i Butik och handel i Microsoft Dynamics 365 for Operations.

I Butik och handel i Dynamics 365 for Operations - Retail kan du göra prisjusteringar för produkter och även ställa in rabatter som tillämpas på en radartikel eller transaktion i kassan (POS), på en försäljningsorder för kundtjänst eller på en onlineorder. Både prisjusteringar och rabatter kan länkas till prisgrupper. För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut. Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier. Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten. Butik och handel i Dynamics 365 for Operations använder automatiskt rabatten eller en kombination av rabatter som utgör det bästa priset för kunden. Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt. Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Butiksparametrar** innan du definierar en ny prisjustering eller rabatt. **Obs!** Du kan ta bort en prisjustering eller rabatt. Statistisk information går dock förlorad.

### <a name="types-of-discounts"></a>Typer av rabatter

Det finns fyra typer av butiksrabatter:

-   **Enkel rabatt** – En procentandel eller ett belopp.
-   **Rabatterad kvantitet** – En rabatt som används när två eller fler produkter köps.
-   **Mixa-och-matcha-rabatt** – En rabatt som används när en specifik kombination av produkter köps in.
-   **Tröskelrabatt** – En rabatt som används när transaktionens summa är mer än ett angivet belopp.

Både prisjusteringar och rabatter kan associeras till prisgrupper. Prisgrupper kan sedan associeras till kanaler, kataloger, anknytningar och bonusprogram.




