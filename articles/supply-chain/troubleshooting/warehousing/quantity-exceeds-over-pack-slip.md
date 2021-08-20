---
title: Kvantiteten överskrider procentsatsen för överleverans under genereringen av följesedeln
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider överleveransprocenten.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 00e3da7767b80e16f9351f59b109765bffc0128fe149cefafc1edda3a6cbcb96
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781355"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a>Kvantiteten överskrider procentsatsen för överleverans under genereringen av följesedeln

Felkod: SYS24920

## <a name="symptoms"></a>Symtom

När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider överleveransprocenten.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Överleverans av raden är %1 procent men tillåten överleverans är bara %2 procent.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Den plockade kvantiteten för beläggningen eller leveransen är större än den beställda kvantiteten och ligger inte inom intervallet för överleveransprocenten.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Justera kvantiteten för beläggningsrad.
- Justera procentsats för överleverans.
- Återför och gör justeringar.

### <a name="adjust-the-load-line-quantity"></a>Justera kvantiteten för beläggningsrad

Använd följande procedur för att justera lastradkvantiteten.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. Välj den beläggning som följesedel inte kan genereras för.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.
1. På fliken  **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleveransens procentsats.
1. Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.
1. På fliken  **Radinformation** väljer du **Order**.
1. I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att generering av följesedel kan fortsätta.

### <a name="adjust-the-over-delivery-percentage"></a>Justera procentsats för överleverans

Använd följande procedur för att justera procentsats för överleverans.

1. Gå till **Kundreskontra \> Order \> Alla order**.
1. Välj den försäljningsorder som du inte kan bokföra en följesedel för.
1. På fliken  **Försäljningsorderrader** markerar du försäljningsorderraden för den artikel som överskrider överleveransens procentsats.
1. På fliken  **Radinformation** väljer du **Leverans**.
1. I fältet **Överleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot generering av följesedel kan fortsätta.

### <a name="reverse-and-make-adjustments"></a>Återför och gör justeringar

Återför allt som har bokförts för lasten (till exempel följesedel, leveransbekräftelse och arbete), gör försäljningsorder justeringar, frisläpp ordern till lagerstället och slutför försändelseproceduren.

Använd följande procedur när du annullerar en följesedel.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Annullera följesedel**.

Använd följande procedur när du återför en försändelsebekräftelse.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.

Gör på följande sätt för att återföra arbete.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken  **Laster**, i gruppen  **Arbete**, väljer du  **återför arbete**.
