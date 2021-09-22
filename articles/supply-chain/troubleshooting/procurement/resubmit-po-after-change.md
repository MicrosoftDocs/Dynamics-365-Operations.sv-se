---
title: Fel vid skicka en inköpsorder på nytt till ett arbetsflöde efter en ändring
description: Fel vid skicka en inköpsorder på nytt till ett arbetsflöde efter en ändring
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477679"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Fel vid skicka en inköpsorder på nytt till ett arbetsflöde efter en ändring


## <a name="symptoms"></a>Symtom

Följande fel uppstår i arbetsflödet när en inköpsorder skickas igen efter en ändring:

> Stoppat (fel): X ++, undantag: ändringar av inköpsordern PO0000569 tillåts endast i utkast när ändringshantering aktiveras på<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Det här problemet uppstår endast om inköpsordern har statusen *bekräftat* innan du begärde ändringar. Om du begär ändringar medan inköpsordern är i ett tillstånd *godkänt* kan arbetsflödet bearbetas.

## <a name="resolution"></a>Lösning

Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.

Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**. Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Problemet kommer att åtgärdas genom [den här artikeln i Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).
