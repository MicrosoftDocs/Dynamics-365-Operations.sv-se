---
title: Ej blockerat arbete
description: Ej blockerat arbete
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924214"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="f3f81-103">Ej blockerat arbete</span><span class="sxs-lookup"><span data-stu-id="f3f81-103">Work isn't blocked</span></span>

<span data-ttu-id="f3f81-104">Felkod: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="f3f81-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="f3f81-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f3f81-105">Symptoms</span></span>

<span data-ttu-id="f3f81-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="f3f81-106">The system shows the following error message:</span></span>

> <span data-ttu-id="f3f81-107">Arbete med ID %1 är inte spärrat.</span><span class="sxs-lookup"><span data-stu-id="f3f81-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="f3f81-108">Orsak</span><span class="sxs-lookup"><span data-stu-id="f3f81-108">Cause</span></span>

<span data-ttu-id="f3f81-109">Alternativet **Spärrad cykel** på cyklen ställs in som *Nej*.</span><span class="sxs-lookup"><span data-stu-id="f3f81-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="f3f81-110">Arbetet kan inte frisättas eftersom det i nuläget inte är spärrat.</span><span class="sxs-lookup"><span data-stu-id="f3f81-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="f3f81-111">Upplösning</span><span class="sxs-lookup"><span data-stu-id="f3f81-111">Resolution</span></span>

 <span data-ttu-id="f3f81-112">Endast arbete där alternativet **Blockerad cykel** är inställt på *Ja* kan frisättas.</span><span class="sxs-lookup"><span data-stu-id="f3f81-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
