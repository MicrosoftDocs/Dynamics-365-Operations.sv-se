---
title: Befattningsstatus för rekryteringsbegäran
description: Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126060"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="34f43-103">Befattningsstatus för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="34f43-103">Recruiting request position status</span></span>

<span data-ttu-id="34f43-104">Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="34f43-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="34f43-105">Fysiskt namn: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="34f43-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="34f43-106">Uppräkningen tillhandahåller alternativuppsättningen för statusvärdena för respektive befattning i en rekryteringsförfrågan i enheten RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="34f43-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="34f43-107">Värde</span><span class="sxs-lookup"><span data-stu-id="34f43-107">Value</span></span> | <span data-ttu-id="34f43-108">Etikett</span><span class="sxs-lookup"><span data-stu-id="34f43-108">Label</span></span> | <span data-ttu-id="34f43-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="34f43-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="34f43-110">200000000</span><span class="sxs-lookup"><span data-stu-id="34f43-110">200000000</span></span> | <span data-ttu-id="34f43-111">Öppet</span><span class="sxs-lookup"><span data-stu-id="34f43-111">Open</span></span> | <span data-ttu-id="34f43-112">Befattningen i rekryteringsförfrågan är öppen för rekrytering.</span><span class="sxs-lookup"><span data-stu-id="34f43-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="34f43-113">Detta innebär inte att det för tillfället inte finns någon aktiv befattningstilldelning för befattningen.</span><span class="sxs-lookup"><span data-stu-id="34f43-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="34f43-114">Det kan finnas en medarbetare med denna befattning vid tidpunkten för rekrytering.</span><span class="sxs-lookup"><span data-stu-id="34f43-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="34f43-115">Det anger bara att befattningen är tillgänglig för rekrytering i samband med rekryteringsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="34f43-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="34f43-116">200000001</span><span class="sxs-lookup"><span data-stu-id="34f43-116">200000001</span></span> | <span data-ttu-id="34f43-117">Tillsatt</span><span class="sxs-lookup"><span data-stu-id="34f43-117">Filled</span></span> | <span data-ttu-id="34f43-118">En medarbetare har valts ut för tilldelning till befattningen.</span><span class="sxs-lookup"><span data-stu-id="34f43-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="34f43-119">200000002</span><span class="sxs-lookup"><span data-stu-id="34f43-119">200000002</span></span> | <span data-ttu-id="34f43-120">Annullerade</span><span class="sxs-lookup"><span data-stu-id="34f43-120">Canceled</span></span> | <span data-ttu-id="34f43-121">Förfrågan om rekrytering för den här befattningen har annullerats.</span><span class="sxs-lookup"><span data-stu-id="34f43-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="34f43-122">Se även</span><span class="sxs-lookup"><span data-stu-id="34f43-122">See also</span></span>

[<span data-ttu-id="34f43-123">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="34f43-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="34f43-124">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="34f43-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
