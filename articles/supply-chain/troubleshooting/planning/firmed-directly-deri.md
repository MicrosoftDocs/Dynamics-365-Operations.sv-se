---
title: Direkt härledda bekräftade order bearbetas av ett arbetsflöde för granskning
description: Direkt härledda bekräftade order bearbetas av ett arbetsflöde med statusen Under granskning.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026923"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="4357f-103">Direkt härledda bekräftade order bearbetas av ett arbetsflöde för granskning</span><span class="sxs-lookup"><span data-stu-id="4357f-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="4357f-104">KB-nummer: 4612450</span><span class="sxs-lookup"><span data-stu-id="4357f-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="4357f-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="4357f-105">Symptoms</span></span>

<span data-ttu-id="4357f-106">Direkt härledda bekräftade order bearbetas av ett arbetsflöde med statusen *Under granskning*.</span><span class="sxs-lookup"><span data-stu-id="4357f-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="4357f-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="4357f-107">Resolution</span></span>

<span data-ttu-id="4357f-108">När ändringsspårning har aktiverats tilldelas statusen *Under granskning* till bekräftade härledda order (inköpsorder för underleverantörer).</span><span class="sxs-lookup"><span data-stu-id="4357f-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="4357f-109">Om en inköpsorder härleds (en inköpsorder för underleverantör) skickas den bara till ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="4357f-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="4357f-110">Om en inköpsorder är en bekräftad planerad inköpsorder godkänns den automatiskt för att säkerställa att planeringsmotorn inte skapar nya planerade order medan inköpsordern fortfarande har statusen *Utkast*.</span><span class="sxs-lookup"><span data-stu-id="4357f-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
