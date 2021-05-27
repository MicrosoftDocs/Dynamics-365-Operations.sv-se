---
title: Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto
description: Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026914"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a><span data-ttu-id="381bb-103">Endast en etikett skrivs ut för flera arbetsrubriker på ett enda kvitto</span><span class="sxs-lookup"><span data-stu-id="381bb-103">Only one label is printed for multiple work headers on a single receipt</span></span>

<span data-ttu-id="381bb-104">KB-nummer: 4614667</span><span class="sxs-lookup"><span data-stu-id="381bb-104">KB number: 4614667</span></span>

## <a name="symptoms"></a><span data-ttu-id="381bb-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="381bb-105">Symptoms</span></span>

<span data-ttu-id="381bb-106">Flera arbetsrubriker skapas för samma mål-ID-nummer som en del av en enda mottagningshändelse för distributionslagerapp.</span><span class="sxs-lookup"><span data-stu-id="381bb-106">Multiple work headers are created for the same target license plate as part of a single warehouse app receiving event.</span></span> <span data-ttu-id="381bb-107">Endast en ID-nummersetikett skrivs dock ut när produkten tas emot.</span><span class="sxs-lookup"><span data-stu-id="381bb-107">However, only one license plate label is printed when the product is received.</span></span>

## <a name="resolution"></a><span data-ttu-id="381bb-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="381bb-108">Resolution</span></span>

<span data-ttu-id="381bb-109">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="381bb-109">The system is behaving as designed.</span></span>

<span data-ttu-id="381bb-110">I den aktuella designen genereras alltid en enda ID-nummersetikett, oavsett antalet kombinationer av arbetsrubriker och arbetsrader som finns.</span><span class="sxs-lookup"><span data-stu-id="381bb-110">In the current design, a single license plate label is always generated, regardless of the number of work header and work line combinations that exist.</span></span> <span data-ttu-id="381bb-111">Den genererade etiketten innehåller informationen för endast en kombination.</span><span class="sxs-lookup"><span data-stu-id="381bb-111">The generated label includes the information for only one combination.</span></span>

<span data-ttu-id="381bb-112">För att lösa problemet kontrollerar du att skapandet av arbetsrubriker alltid mappas till bara ett mål-ID-nummer.</span><span class="sxs-lookup"><span data-stu-id="381bb-112">To work around this issue, make sure that work header creation is always mapped to just one target license plate.</span></span>
