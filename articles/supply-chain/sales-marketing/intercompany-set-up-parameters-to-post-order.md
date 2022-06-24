---
title: Ställa in parametrar för bokföring av en koncernintern order
description: Denna artikel förklarar hur du konfigurerar parametrar för att bokföra en koncernintern order
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
ms.openlocfilehash: 97ea0061d57beede6350eecfd497c12dd37aea31
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900808"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Ställa in parametrar för bokföring av en koncernintern order

[!include [banner](../../includes/banner.md)]

När en koncernintern kundfaktura bokförs kan du konfigurera den för att bokföra både den koncerninterna försäljningsordern och den ursprungliga kundfakturan automatiskt.

> [!NOTE]
> Innan du utför den här proceduren måste du konfigurera utskriftshanteringen i organisationen så att den pekar på rätt fakturaskrivare. Då ser du till att fakturan för den ursprungliga försäljningsordern skrivs ut på rätt skrivare.

Du måste konfigurera följande parametrar:

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**. Välj vilken försäljningsorder du vill arbeta med.
1. På försäljningsordern i åtgärdsfönstret, välj **Huvudvy** och sedan snabbfliken **Koncerninterna inställningar** och öppna den.
1. Klicka sedan på fliken **Försäljningsorder** i åtgärdsfönstret och välj **Redigera**.
1. Gå tillbaka till snabbfliken **Koncerninterna inställningar** och välj **Direktleverans** för att aktivera direktleverans genom den koncerninterna kedjan (alla order).
1. Välj **Spara** om du vill spara försäljningsordern med de nya inställningarna. Välj sedan **Stäng** för att stänga försäljningsordern.
1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**. Välj **koncernintern** på fliken **Allmänt**.
1. På sidan **Koncernintern** välj länken **Inköpsorderpolicyer**. I fältgruppen **Koncernintern inköpsorder (direktleverans)**, välj **Bokför faktura automatiskt** och ta bort kryssmarkeringen från fältet **Skriv ut faktura automatiskt**.
1. I fältgruppen **Ursprunglig försäljningsorder (direktleverans)**, välj fältet **Bokför faktura automatiskt** och fältet **Skriv ut faktura automatiskt**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
