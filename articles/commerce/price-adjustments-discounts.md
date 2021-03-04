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
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0c2adaa5cd935d5b593bfbb3215d3466fcafab7b
ms.sourcegitcommit: 1d74636bf9db5fb33e998322899504b709b4f89f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "4584325"
---
# <a name="price-adjustments-and-discounts"></a>Prisjusteringar och rabatter

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om prisjusteringar och rabatter i Dynamics 365 Commerce.

I Handel kan du justera priset på produkter och även ställa in rabatter som används på en radartikel eller en transaktion i kassan, en försäljningsorder i kundtjänst eller på en beställning online. Både prisjusteringar och rabatter kan länkas till prisgrupper. För både prisjusteringar och rabatter kan du ange ett enskilt datum för startdatum och slutdatum eller en återkommande period, en rabatt kod och eventuella ytterligare attribut. 

Prisjusteringar och rabatter kan användas för produkter, varianter eller kategorier. Om mer än en rabatt gäller för en produkt, kan en kund ta emot antingen en av rabatterna eller en kombinerad rabatt, beroende på konfigurationen av rabatten. Handel använder automatiskt rabatten eller en kombination av rabatter som ger kunden det bästa priset. Kontrollera att du bekräftar att prisgruppen tilldelas de korrekta kanalerna, katalogerna, anknytningarna eller bonusprogrammen som du vill att rabatten ska gälla för när du konfigurerar en prisjustering eller rabatt. Om du vill skapa rabatt-ID automatiskt kan du ställa in nummerserier på sidan **Handelsparametrar** innan du definierar en ny prisjustering eller rabatt.

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