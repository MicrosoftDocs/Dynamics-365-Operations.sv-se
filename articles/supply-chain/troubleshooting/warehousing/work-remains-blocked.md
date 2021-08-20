---
title: Arbetet fortsatt spärrat
description: Arbetet fortsatt spärrat
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 898390c78bb26fb8a44f77a10ad27a00720f7d1a3396cec5fff10e9d6b93364d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768580"
---
# <a name="work-remains-blocked"></a>Arbetet fortsatt spärrat

Felkod: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Arbetet %1 förblir spärrat eftersom den relaterade påfyllnaden %2 har statusvärdet %3.

## <a name="cause"></a>Orsak

Arbetet bearbetas just nu i en cykel och kan inte frisättas, enligt något av följande villkor:

- På fliken **Spärrningsorsaker** anges fältet **Orsak till arbetsspärr** för en eller flera rader som *Bearbetning av cykel*.
- När du väljer **Cykel** i gruppen **Relaterad information** på fliken **Relaterad information** på åtgärdssidan anges fältet **Cykelstatus** som *Behandlas*.

## <a name="resolution"></a>Upplösning

I åtgärdsfönstret, på fliken **Relaterad information**, i gruppen **Relaterad information**, väljer du **Cykel**. På sidan **Cykler** väljer du sedan i åtgärdsfältet, på fliken **Cykel**, i gruppen **Cykel**, **Rensa cykeldata**.

## <a name="workaround"></a>Lösning

Om de föregående stegen inte åtgärdat problemet kan du avbryta arbetet genom att följa stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).
