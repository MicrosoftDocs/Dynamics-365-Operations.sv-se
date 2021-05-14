---
title: Arbetet kan inte avbrytas eftersom det är spärrat
description: Arbetet kan inte avbrytas eftersom det är spärrat
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924289"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>Arbetet kan inte avbrytas eftersom det är spärrat

Felkod: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Arbete %1 kan inte avbrytas eftersom det spärrats på grund av orsakstyp %2. Arbetet måste frisättas innan det kan avbrytas.

## <a name="cause"></a>Orsak

Arbetet har spärrats och kan inte avbrytas.

På sidan **Arbete**, på fliken **Allmänt**, är alternativet **Spärrat** inställt på *Ja*. Denna inställning visar att arbetet är spärrat. Fliken **Spärrorsaker** anger varför arbetet spärrats.

## <a name="resolution"></a>Upplösning

För att frisätta arbetet väljer du **Spärrorsaker** och gör sedan på följande sätt:

- Om fältet **Orsak till arbetsspärr** har ställts in på *Odefinierad orsak*: I åtgärdsfältet, på fliken **Arbete** i gruppen **Arbete**, väljer du **Frisätt arbete**.
- Om fältet **Orsak till arbetsspärr** är inställt på *Bearbetning av cykel*: I åtgärdsfältet, på fliken **Relaterad information** i gruppen **Relaterad information**, väljer du **Cykel**. På sidan **Cykler** väljer du sedan i åtgärdsfältet, på fliken **Cykel**, i gruppen **Cykel**, **Rensa cykeldata**.

## <a name="workaround"></a>Lösning

Om de föregående stegen inte åtgärdat problemet kan du avbryta arbetet genom att följa stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).
