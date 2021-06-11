---
title: Status för rekryteringsförfrågan
description: Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059194"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="74267-103">Status för rekryteringsförfrågan</span><span class="sxs-lookup"><span data-stu-id="74267-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="74267-104">Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="74267-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="74267-105">Fysiskt namn: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="74267-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="74267-106">Denna uppräkning utgör alternativuppsättningen för statusvärden för RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="74267-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="74267-107">Värde</span><span class="sxs-lookup"><span data-stu-id="74267-107">Value</span></span> | <span data-ttu-id="74267-108">Etikett</span><span class="sxs-lookup"><span data-stu-id="74267-108">Label</span></span> | <span data-ttu-id="74267-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="74267-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="74267-110">200000000</span><span class="sxs-lookup"><span data-stu-id="74267-110">200000000</span></span> | <span data-ttu-id="74267-111">Utkast</span><span class="sxs-lookup"><span data-stu-id="74267-111">Draft</span></span> | <span data-ttu-id="74267-112">Förfrågningen finns i utkast och är inte redo för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="74267-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="74267-113">200000001</span><span class="sxs-lookup"><span data-stu-id="74267-113">200000001</span></span> | <span data-ttu-id="74267-114">Under granskning</span><span class="sxs-lookup"><span data-stu-id="74267-114">In Review</span></span> | <span data-ttu-id="74267-115">Denna begäran har skickats in och skickas nu runt för godkännande via arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="74267-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="74267-116">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="74267-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="74267-117">200000002</span><span class="sxs-lookup"><span data-stu-id="74267-117">200000002</span></span> | <span data-ttu-id="74267-118">Väntar</span><span class="sxs-lookup"><span data-stu-id="74267-118">Pending</span></span> | <span data-ttu-id="74267-119">Begäran väntar på en arbetsflödesåtgärd.</span><span class="sxs-lookup"><span data-stu-id="74267-119">The request is pending workflow action.</span></span> <span data-ttu-id="74267-120">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="74267-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="74267-121">200000003</span><span class="sxs-lookup"><span data-stu-id="74267-121">200000003</span></span> | <span data-ttu-id="74267-122">Annullerade</span><span class="sxs-lookup"><span data-stu-id="74267-122">Canceled</span></span> | <span data-ttu-id="74267-123">Denna begäran har annullerats.</span><span class="sxs-lookup"><span data-stu-id="74267-123">The request has been canceled.</span></span> <span data-ttu-id="74267-124">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="74267-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="74267-125">200000004</span><span class="sxs-lookup"><span data-stu-id="74267-125">200000004</span></span> | <span data-ttu-id="74267-126">Nekade</span><span class="sxs-lookup"><span data-stu-id="74267-126">Denied</span></span> | <span data-ttu-id="74267-127">Denna begäran har avslagits.</span><span class="sxs-lookup"><span data-stu-id="74267-127">The request has been denied.</span></span> <span data-ttu-id="74267-128">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="74267-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="74267-129">200000005</span><span class="sxs-lookup"><span data-stu-id="74267-129">200000005</span></span> | <span data-ttu-id="74267-130">Aktiva</span><span class="sxs-lookup"><span data-stu-id="74267-130">Active</span></span> | <span data-ttu-id="74267-131">Alla arbetsflöden har slutförts och godkänts, och ansökan är klar för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="74267-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="74267-132">200000006</span><span class="sxs-lookup"><span data-stu-id="74267-132">200000006</span></span> | <span data-ttu-id="74267-133">Stängda</span><span class="sxs-lookup"><span data-stu-id="74267-133">Closed</span></span> | <span data-ttu-id="74267-134">Rekryteringsförfrågan har avslutats.</span><span class="sxs-lookup"><span data-stu-id="74267-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="74267-135">Se även</span><span class="sxs-lookup"><span data-stu-id="74267-135">See also</span></span>

[<span data-ttu-id="74267-136">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="74267-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="74267-137">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="74267-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]