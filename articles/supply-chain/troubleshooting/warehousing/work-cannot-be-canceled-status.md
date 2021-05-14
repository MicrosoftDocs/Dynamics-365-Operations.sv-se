---
title: Arbete kan inte avbrytas på grund av dess status
description: Arbete kan inte avbrytas på grund av dess status
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924265"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>Arbete kan inte avbrytas på grund av dess status

Felkod: WAX2190

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Det går inte att annullera arbetet %1 eftersom det har status %2.

## <a name="cause"></a>Orsak

Arbetet kan inte avbrytas i sitt aktuella tillstånd.

Arbetsrubriken eller arbetsraderna har inte det förväntade värdet **Arbetsstatus**. Fältet **Arbetsstatus** i arbetsrubriken är inte inställt på *Öppen* eller *Pågår*.

## <a name="resolution"></a>Upplösning

Om du vill avbryta arbetet följer du stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).
