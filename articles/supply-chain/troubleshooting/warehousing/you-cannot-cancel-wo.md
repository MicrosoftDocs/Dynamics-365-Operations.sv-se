---
title: Du kan inte avbryta arbete som tilldelats en användare
description: Du kan inte avbryta arbete som tilldelats en användare
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924411"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Du kan inte avbryta arbete som tilldelats en användare

Felkod: WAX708

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Du kan inte avbryta ett arbete som ligger på en användare.

## <a name="cause"></a>Orsak

Arbetet har spärrats av en användare och kan inte avbrytas. Om du vill bekräfta detta öppnar du arbets-ID:t och sedan fliken **Allmänt**. Om arbetet är spärrat kommer fältet **Arbetsstatus** att ställas in som *Pågår* och fältet **spärrat av** erhåller ett användar-ID.

## <a name="resolution"></a>Upplösning

Om du vill avbryta arbetet följer du stegen nedan.

1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.
1. I fältet **Arbets-ID** anger du ID-numret för det arbete som du vil avbryta.
1. Välj **OK**.
1. Välj **Ja** för att bekräfta att du vill avbryta arbetet.

Mer information finns i [Avbryt lagerarbete för undantagshantering](../../warehousing/cancel-warehouse-work.md).
