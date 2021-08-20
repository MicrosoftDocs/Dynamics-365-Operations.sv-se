---
title: Kvantiteten kan inte reduceras när en försäljningsorder annulleras
description: Kvantiteten kan inte reduceras när en försäljningsorder annulleras.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3453c83b5e8ead4269a6054167d73a0cd12381ba374b98bc407c01edaa68a1c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752644"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a>Kvantiteten kan inte reduceras när en försäljningsorder annulleras

Felkod: SYS138831

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Kvantiteten kan inte reduceras. Antalet lagertransaktioner för order är för lågt eftersom kvantiteten eller en del av denna refereras till av en utleveransorder eller en tillverkningsorder, eller är markerad mot andra transaktioner.

## <a name="cause"></a>Orsak

Om arbete associeras med en försäljningsorder kan du inte annullera försäljningsordern förrän arbetet har annullerats och återförts. Detta krav gäller även om det arbete som är kopplat till försäljningsordern stängs.

## <a name="resolution"></a>Lösning

Utför följande uppgifter för att åtgärda detta problem:

1. Avbryt det öppna arbetet.
1. Ta bort lasten.
1. Minska plockad kvantitet.

### <a name="cancel-open-work"></a>Avbryt det öppna arbetet

Om du vill avbryta det öppna arbetet följer du stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

### <a name="delete-the-load"></a>Ta bort beläggningen

Följ dessa steg om du vill ta bort en beläggning:

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Öppna relevant försäljningsordern.
1. På snabbfliken **Försäljningsorderrader** väljer du **Lagerställe \> Arbetsdetaljer**.
1. I fönstret **Arbete**, på sidan Åtgärder > fliken **Arbete** > gruppen **Arbete** väljer du **Annullera arbete**.
1. Bekräfta att fältet **Arbetsstatus** är inställt *Annulerat*.
1. Stäng sidan **Arbete**.
1. På sidan för försäljningsorderdetaljer, på snabbfliken **Försäljningsorderrader**, väljer du **Lagerställe \> Beläggningsinformation**.
1. Välj sedan **Ta bort** i åtgärdsfönstret.
1. Välj **Ja** för att bekräfta att du vill ta bort beläggningen.
1. Stäng sidan **Beläggning**.

### <a name="reduce-the-picked-quantity"></a>Minska plockad kvantitet

När allt arbete har annullerats följer du dessa steg för att minska den plockade kvantiteten.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Öppna relevant försäljningsordern.
1. På snabbfliken **Försäljningsorderrader** väljer du **Uppdatera rad \> Plock** i verktygsfältet.
1. På sidan **Plock**, i avsnittet **Transaktioner**, markerar du raden där ut fältet **Ärendestatus** är inställt på *Plockad*.
1. I avsnittet **Transaktioner** väljer du **Lägg till plockrad** i verktygsfältet.
1. I avsnittet **Plockrader** väljer du **Bekräfta Plocka alla** i verktygsfältet.
1. Stäng sidan **Plock**.
1. På sidan försäljningsorderdetaljer i åtgärdsfönstret väljer du på fliken **Försäljningsorder** > gruppen **Underhåll** > **Annullera**.
1. Välj **Ja** för att bekräfta att du vill annullera försäljningsordern.
