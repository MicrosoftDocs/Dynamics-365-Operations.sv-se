---
title: Kvantiteten underskrider procentsatsen för överleverans under genereringen av följesedeln
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som underskrider överleveransprocenten.
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
ms.openlocfilehash: 7cdc22eeabda6cf9f08484d698e5096f66af4a12
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920708"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a>Kvantiteten underskrider procentsatsen för överleverans under genereringen av följesedeln

Felkod: SYS24921

## <a name="symptoms"></a>Symtom

När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som underskrider överleveransprocenten.

När du försöker generera en följesedel visas följande felmeddelande i systemet:

> Underleverans av raden är %1 procent men tillåten underleverans är bara %2 procent.

Du kan därför inte generera följesedel för beläggningen.

## <a name="cause"></a>Orsak

Den plockade kvantiteten för beläggningen eller leveransen är mindre än den beställda kvantiteten och ligger inte inom intervallet för underleveransprocenten.

## <a name="resolution"></a>Lösning

Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas. Utför en eller flera av följande uppgifter för att åtgärda detta problem:

- Justera procentsats för underleverans.
- Återför och gör justeringar.

### <a name="adjust-the-under-delivery-percentage"></a>Justera procentsats för underleverans

Använd följande procedur för att justera procentsats för underleverans.

1. Gå till **Kundreskontra \> Order \> Alla order**.
1. Välj den försäljningsorder som du inte kan bokföra en följesedel för.
1. På fliken **Försäljningsorderrader** markerar du försäljningsorderraden för den artikel som överskrider underleveransens procentsats.
1. På fliken **Radinformation** väljer du **Leverans**.
1. I fältet **Underleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot generering av följesedel kan fortsätta.

### <a name="reverse-and-make-adjustments"></a>Återför och gör justeringar

Återför allt som har bokförts för lasten (till exempel följesedel, leveransbekräftelse och arbete), gör försäljningsorder justeringar, frisläpp ordern till lagerstället och slutför försändelseproceduren.

Använd följande procedur när du annullerar en följesedel.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Annullera följesedel**.

Använd följande procedur när du återför en försändelsebekräftelse.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.

Gör på följande sätt för att återföra arbete.

1. Gå till **Warehouse management \> Laster \> Alla laster**.
1. I åtgärdsfönstret, på fliken **Laster**, i gruppen **Arbete**, väljer du **återför arbete**.
