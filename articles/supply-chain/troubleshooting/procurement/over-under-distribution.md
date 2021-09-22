---
title: Redovisningsfördelningar är antingen över- eller underfördelade
description: En eller flera redovisningsfördelningar är antingen överspridda eller underfördelade.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7ff0172469df50da9e4272b3fa3f75001a4eb7eb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477630"
---
# <a name="accounting-distributions-are-either-over--or-under-distributed"></a>Redovisningsfördelningar är antingen över- eller underfördelade


## <a name="symptoms"></a>Symtom

Följande felmeddelande visas:

> En eller flera redovisningsfördelningar är antingen överfördelade eller underfördelade

## <a name="cause"></a>Orsak

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

## <a name="resolution"></a>Lösning

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
