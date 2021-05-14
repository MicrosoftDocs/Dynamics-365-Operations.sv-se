---
title: Den senast stängda arbetsraden måste ha värdet Placera
description: Den senast stängda arbetsraden måste ha värdet Placera
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924385"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>Den senast stängda arbetsraden måste ha värdet Placera

Felkod: WAX1285

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Den senast stängda arbetsraden måste ha värdet Placera.

## <a name="cause"></a>Orsak

Arbetet kan inte avbrytas i sitt aktuella tillstånd.

På den sista arbetsraden ställs fältet **Arbetsstatus** in på *Stängd*, men fältet **Arbetstyp** är inte satt som *Placera*.

## <a name="resolution"></a>Upplösning

Om du vill avbryta arbetet följer du stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).
