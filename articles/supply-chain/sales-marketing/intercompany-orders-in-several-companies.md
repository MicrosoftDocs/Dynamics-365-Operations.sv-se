---
title: Skapa koncerninterna inköps- och försäljningsorder i flera företag
description: I denna artikel beskrivs hur du skapar koncerninterna inköpsorder eller försäljningsorder i flera företag
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6dce419126d60199bc11d4bd3209185ad779e979
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873562"
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
