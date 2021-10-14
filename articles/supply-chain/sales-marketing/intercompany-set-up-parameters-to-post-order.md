---
title: Ställa in parametrar för bokföring av en koncernintern order
description: Det här avsnittet innehåller information om hur du ställer in parametrar för att bokföra en koncernintern order
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
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548537"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Ställa in parametrar för bokföring av en koncernintern order

[!include [banner](../../includes/banner.md)]

När en koncernintern kundfaktura bokförs kan du ställa in den för att bokföra både den koncerninterna försäljningsordern och den ursprungliga kundfakturan automatiskt.

> [!NOTE]
> Innan du utför den här proceduren måste du ställa in utskriftshanteringen i organisationen så att den pekar på rätt fakturaskrivare. Då ser du till att fakturan för den ursprungliga försäljningsordern skrivs ut på rätt skrivare.

Du måste ställa in följande parametrar:

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**. Välj vilken försäljningsorder du vill arbeta med.
1. På försäljningsordern i åtgärdsfönstret, välj **Huvudvy** och sedan snabbfliken **Koncerninterna inställningar** och öppna den.
1. Klicka sedan på fliken **Försäljningsorder** i åtgärdsfönstret och välj **Redigera**.
1. Gå tillbaka till snabbfliken **Koncerninterna inställningar** och välj **Direktleverans** för att aktivera direktleverans genom den koncerninterna kedjan (alla order).
1. Välj **Spara** om du vill spara försäljningsordern med de nya inställningarna. Välj sedan **Stäng** för att stänga försäljningsordern.
1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**. Välj **koncernintern** på fliken **Allmänt**.
1. På sidan **Koncernintern** välj länken **Inköpsorderpolicyer**. I fältgruppen **Koncernintern inköpsorder (direktleverans)**, välj **Bokför faktura automatiskt** och ta bort kryssmarkeringen från fältet **Skriv ut faktura automatiskt**.
1. I fältgruppen **Ursprunglig försäljningsorder (direktleverans)**, välj fältet **Bokför faktura automatiskt** och fältet **Skriv ut faktura automatiskt**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
