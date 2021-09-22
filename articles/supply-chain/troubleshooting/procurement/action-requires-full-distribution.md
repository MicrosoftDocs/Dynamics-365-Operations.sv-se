---
title: Det går endast att slutföra en inköpsorderåtgärd för fullständigt distribuerade radnummer
description: Det går endast att slutföra en åtgärd för ett inköp efter att radnumret är fullständigt distribuerat
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
ms.openlocfilehash: 1ef2a938a2a17bc2dbf38d09918eabdbccca8a28
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477670"
---
# <a name="you-can-only-complete-a-purchase-order-action-for-fully-distributed-line-numbers"></a>Det går endast att slutföra en inköpsorderåtgärd för fullständigt distribuerade radnummer

## <a name="symptom"></a>Symptom

Det går endast att slutföra en åtgärd för ett inköp efter att radnumret är fullständigt distribuerat.

## <a name="cause"></a>Orsak

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

## <a name="resolution"></a>Lösning

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
