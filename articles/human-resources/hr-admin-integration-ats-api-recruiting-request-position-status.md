---
title: Befattningsstatus för rekryteringsbegäran
description: Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7e59e9381fb15b339095d6a71296813e0141e9ab
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789742"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="5c33a-103">Befattningsstatus för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="5c33a-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5c33a-104">Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5c33a-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="5c33a-105">Fysiskt namn: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="5c33a-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="5c33a-106">Uppräkningen tillhandahåller alternativuppsättningen för statusvärdena för respektive befattning i en rekryteringsförfrågan i enheten RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="5c33a-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="5c33a-107">Värde</span><span class="sxs-lookup"><span data-stu-id="5c33a-107">Value</span></span> | <span data-ttu-id="5c33a-108">Etikett</span><span class="sxs-lookup"><span data-stu-id="5c33a-108">Label</span></span> | <span data-ttu-id="5c33a-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5c33a-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="5c33a-110">200000000</span><span class="sxs-lookup"><span data-stu-id="5c33a-110">200000000</span></span> | <span data-ttu-id="5c33a-111">Öppet</span><span class="sxs-lookup"><span data-stu-id="5c33a-111">Open</span></span> | <span data-ttu-id="5c33a-112">Befattningen i rekryteringsförfrågan är öppen för rekrytering.</span><span class="sxs-lookup"><span data-stu-id="5c33a-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="5c33a-113">Detta innebär inte att det för tillfället inte finns någon aktiv befattningstilldelning för befattningen.</span><span class="sxs-lookup"><span data-stu-id="5c33a-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="5c33a-114">Det kan finnas en medarbetare med denna befattning vid tidpunkten för rekrytering.</span><span class="sxs-lookup"><span data-stu-id="5c33a-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="5c33a-115">Det anger bara att befattningen är tillgänglig för rekrytering i samband med rekryteringsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="5c33a-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="5c33a-116">200000001</span><span class="sxs-lookup"><span data-stu-id="5c33a-116">200000001</span></span> | <span data-ttu-id="5c33a-117">Tillsatt</span><span class="sxs-lookup"><span data-stu-id="5c33a-117">Filled</span></span> | <span data-ttu-id="5c33a-118">En medarbetare har valts ut för tilldelning till befattningen.</span><span class="sxs-lookup"><span data-stu-id="5c33a-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="5c33a-119">200000002</span><span class="sxs-lookup"><span data-stu-id="5c33a-119">200000002</span></span> | <span data-ttu-id="5c33a-120">Annullerade</span><span class="sxs-lookup"><span data-stu-id="5c33a-120">Canceled</span></span> | <span data-ttu-id="5c33a-121">Förfrågan om rekrytering för den här befattningen har annullerats.</span><span class="sxs-lookup"><span data-stu-id="5c33a-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5c33a-122">Se även</span><span class="sxs-lookup"><span data-stu-id="5c33a-122">See also</span></span>

[<span data-ttu-id="5c33a-123">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="5c33a-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="5c33a-124">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="5c33a-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]