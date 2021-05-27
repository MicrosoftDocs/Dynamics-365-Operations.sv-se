---
title: En återföring av rapportering som färdig skapar en oväntat öppen transaktion
description: Återföring av rapportering som färdig som har markering skapar en öppen transaktion där den återförda kvantiteten har samma lagerdimensioner som den återförda transaktionen.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026927"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="f2186-103">En återföring av rapportering som färdig skapar en oväntat öppen transaktion</span><span class="sxs-lookup"><span data-stu-id="f2186-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="f2186-104">KB-nummer: 4612469</span><span class="sxs-lookup"><span data-stu-id="f2186-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="f2186-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f2186-105">Symptoms</span></span>

<span data-ttu-id="f2186-106">Om du återför rapportering som färdig som har markering skapar systemet en öppen transaktion där den återförda kvantiteten har samma lagerdimensioner som den återförda transaktionen.</span><span class="sxs-lookup"><span data-stu-id="f2186-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="f2186-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="f2186-107">Resolution</span></span>

<span data-ttu-id="f2186-108">När du återför en rapportera som färdig-åtgärd initieras lagerdimensionen från produktionsjournalen.</span><span class="sxs-lookup"><span data-stu-id="f2186-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="f2186-109">Därför hämtar det batchnumret.</span><span class="sxs-lookup"><span data-stu-id="f2186-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="f2186-110">På grund av markering ärver försäljningsordertransaktionerna batchnumret.</span><span class="sxs-lookup"><span data-stu-id="f2186-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="f2186-111">Dimensionen kan återställas när rapportering som färdigt bokförs.</span><span class="sxs-lookup"><span data-stu-id="f2186-111">The dimension can be reset when the reporting as finished is posted.</span></span>
