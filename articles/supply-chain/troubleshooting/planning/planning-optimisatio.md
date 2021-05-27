---
title: Planerad inköpsorder skapas när det finns ett inköp inom negativa dagar
description: Om disponeringskoden är Min/max skapas en planerad inköpsorder med planeringsoptimering när det finns ett inköp inom negativa dagar.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026921"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="0cd00-103">Planerad inköpsorder skapas när det finns ett inköp inom negativa dagar</span><span class="sxs-lookup"><span data-stu-id="0cd00-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="0cd00-104">KB-nummer: 4614298</span><span class="sxs-lookup"><span data-stu-id="0cd00-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="0cd00-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="0cd00-105">Symptoms</span></span>

<span data-ttu-id="0cd00-106">Om disponeringskoden är *Min/max* skapas en planerad inköpsorder med planeringsoptimering när det finns ett inköp inom negativa dagar.</span><span class="sxs-lookup"><span data-stu-id="0cd00-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="0cd00-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="0cd00-107">Resolution</span></span>

<span data-ttu-id="0cd00-108">Planeringsoptimering har inte stöd för negativa dagar.</span><span class="sxs-lookup"><span data-stu-id="0cd00-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="0cd00-109">Det garanterar alltid att planerade order inte schemaläggs inom produktionstiden i förhållande till det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="0cd00-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="0cd00-110">Inköpsstiden är till exempel 10 dagar och en inköpsorder förväntas komma in åtta dagar från idag.</span><span class="sxs-lookup"><span data-stu-id="0cd00-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="0cd00-111">I det här fallet används inköpsordern som tillgång för efterfrågan som är fem dagar från idag.</span><span class="sxs-lookup"><span data-stu-id="0cd00-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="0cd00-112">Därför rekommenderar vi att du justerar dina produktionstider för att täcka alla (eller nästan alla) av dina scenarier.</span><span class="sxs-lookup"><span data-stu-id="0cd00-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
