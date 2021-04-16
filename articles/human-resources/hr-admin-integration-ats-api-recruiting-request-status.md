---
title: Status för rekryteringsförfrågan
description: Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 888fbc511bffbecd837c929049006266191da5ba
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806052"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="786e1-103">Status för rekryteringsförfrågan</span><span class="sxs-lookup"><span data-stu-id="786e1-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="786e1-104">Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="786e1-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="786e1-105">Fysiskt namn: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="786e1-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="786e1-106">Denna uppräkning utgör alternativuppsättningen för statusvärden för RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="786e1-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="786e1-107">Värde</span><span class="sxs-lookup"><span data-stu-id="786e1-107">Value</span></span> | <span data-ttu-id="786e1-108">Etikett</span><span class="sxs-lookup"><span data-stu-id="786e1-108">Label</span></span> | <span data-ttu-id="786e1-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="786e1-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="786e1-110">200000000</span><span class="sxs-lookup"><span data-stu-id="786e1-110">200000000</span></span> | <span data-ttu-id="786e1-111">Utkast</span><span class="sxs-lookup"><span data-stu-id="786e1-111">Draft</span></span> | <span data-ttu-id="786e1-112">Förfrågningen finns i utkast och är inte redo för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="786e1-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="786e1-113">200000001</span><span class="sxs-lookup"><span data-stu-id="786e1-113">200000001</span></span> | <span data-ttu-id="786e1-114">Under granskning</span><span class="sxs-lookup"><span data-stu-id="786e1-114">In Review</span></span> | <span data-ttu-id="786e1-115">Denna begäran har skickats in och skickas nu runt för godkännande via arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="786e1-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="786e1-116">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="786e1-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="786e1-117">200000002</span><span class="sxs-lookup"><span data-stu-id="786e1-117">200000002</span></span> | <span data-ttu-id="786e1-118">Väntar</span><span class="sxs-lookup"><span data-stu-id="786e1-118">Pending</span></span> | <span data-ttu-id="786e1-119">Begäran väntar på en arbetsflödesåtgärd.</span><span class="sxs-lookup"><span data-stu-id="786e1-119">The request is pending workflow action.</span></span> <span data-ttu-id="786e1-120">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="786e1-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="786e1-121">200000003</span><span class="sxs-lookup"><span data-stu-id="786e1-121">200000003</span></span> | <span data-ttu-id="786e1-122">Annullerade</span><span class="sxs-lookup"><span data-stu-id="786e1-122">Canceled</span></span> | <span data-ttu-id="786e1-123">Denna begäran har annullerats.</span><span class="sxs-lookup"><span data-stu-id="786e1-123">The request has been canceled.</span></span> <span data-ttu-id="786e1-124">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="786e1-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="786e1-125">200000004</span><span class="sxs-lookup"><span data-stu-id="786e1-125">200000004</span></span> | <span data-ttu-id="786e1-126">Nekade</span><span class="sxs-lookup"><span data-stu-id="786e1-126">Denied</span></span> | <span data-ttu-id="786e1-127">Denna begäran har avslagits.</span><span class="sxs-lookup"><span data-stu-id="786e1-127">The request has been denied.</span></span> <span data-ttu-id="786e1-128">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="786e1-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="786e1-129">200000005</span><span class="sxs-lookup"><span data-stu-id="786e1-129">200000005</span></span> | <span data-ttu-id="786e1-130">Aktiva</span><span class="sxs-lookup"><span data-stu-id="786e1-130">Active</span></span> | <span data-ttu-id="786e1-131">Alla arbetsflöden har slutförts och godkänts, och ansökan är klar för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="786e1-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="786e1-132">200000006</span><span class="sxs-lookup"><span data-stu-id="786e1-132">200000006</span></span> | <span data-ttu-id="786e1-133">Stängda</span><span class="sxs-lookup"><span data-stu-id="786e1-133">Closed</span></span> | <span data-ttu-id="786e1-134">Rekryteringsförfrågan har avslutats.</span><span class="sxs-lookup"><span data-stu-id="786e1-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="786e1-135">Se även</span><span class="sxs-lookup"><span data-stu-id="786e1-135">See also</span></span>

[<span data-ttu-id="786e1-136">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="786e1-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="786e1-137">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="786e1-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]