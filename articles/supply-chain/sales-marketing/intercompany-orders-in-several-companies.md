---
title: Skapa koncerninterna inköps- och försäljningsorder i flera företag
description: I det här avsnittet beskrivs hur du skapar koncerninterna inköpsorder eller försäljningsorder i flera företag
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5d756a82abb7e7b19080128353d863f29837fc5b
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548534"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Skapa koncerninterna inköps- och försäljningsorder i flera företag

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management är inte begränsat till att bara hantera ett produktionsföretag och flera försäljningsföretag. Alla företag som anges för koncernintern kan både vara handelsföretag och produktionsföretag.

Om flera företag kan leverera samma artikel kan du välja varifrån du vill köpa den, och uppdateringar bearbetas även om en försäljningsorder blir flera inköpsorder.

På samma sätt som du automatiskt skapar en koncernintern inköpsorder kan du skapa en ursprunglig försäljningsorder i företaget och låta flera koncerninterna leverantörsföretag utföra ordern genom att skapa fler än en koncernintern inköpsorder. Microsoft Dynamics 365 Supply Chain Management skapar automatiskt koncerninterna försäljningsorder i leverantörsföretagen.

För att kunna göra detta måste alla företag ställas in som handelsrelationer. Leverantörsföretagen måste vara inställda i Microsoft Dynamics 365 Supply Chain Management som koncerninterna leverantörer och de måste vara primär leverantör av den relevanta artikeln. I försäljningsordern, i **huvudvyn**, måste du välja fältet **Skapa koncerninterna order automatiskt** och fältet **Direktleverans** på snabbflikarna **Koncerninterna inställningar**. Det här är standardinställningen.

Du skapar försäljningsraderna på vanligt sätt. När du lämnar posten visas ett meddelande om att koncerninterna inköpsorder och koncerninterna försäljningsorder har skapats. Meddelandet innehåller länkar till nya order. Om du vill visa de koncerninterna försäljningsorder som skapats i dina leverantörsföretag öppnar du den ursprungliga försäljningsordern på fliken **Allmänt** i gruppen **Relaterad information** och väljer **Referenser**.

Om du öppnar de koncerninterna inköpsorderna för leverantörerna ser du att Microsoft Dynamics 365 Supply Chain Management automatiskt fyller i numren på den ursprungliga försäljningsordern och den koncerninterna försäljningsordern för varje leverantör.

På liknande sätt, om du öppnar de koncerninterna försäljningsorderna för leverantörerna ser du att Microsoft Dynamics 365 Supply Chain Management automatiskt fyller i numren på den ursprungliga försäljningsordern och den koncerninterna inköpsordern för varje leverantör.

> [!NOTE]
> Om artiklarna som beställs finns i ett av de koncerninterna leverantörsföretagen men inte det andra skapar Microsoft Dynamics 365 Supply Chain Management de koncerninterna orderna för leverantörsföretaget där artikeln finns men slutar skapa ordern för det andra företaget. Ett meddelande visas när detta inträffar.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
