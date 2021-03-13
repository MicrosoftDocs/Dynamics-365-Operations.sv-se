---
title: Status för rekryteringsförfrågan
description: Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125964"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="241ec-103">Status för rekryteringsförfrågan</span><span class="sxs-lookup"><span data-stu-id="241ec-103">Recruiting request status</span></span>

<span data-ttu-id="241ec-104">Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="241ec-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="241ec-105">Fysiskt namn: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="241ec-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="241ec-106">Denna uppräkning utgör alternativuppsättningen för statusvärden för RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="241ec-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="241ec-107">Värde</span><span class="sxs-lookup"><span data-stu-id="241ec-107">Value</span></span> | <span data-ttu-id="241ec-108">Etikett</span><span class="sxs-lookup"><span data-stu-id="241ec-108">Label</span></span> | <span data-ttu-id="241ec-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="241ec-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="241ec-110">200000000</span><span class="sxs-lookup"><span data-stu-id="241ec-110">200000000</span></span> | <span data-ttu-id="241ec-111">Utkast</span><span class="sxs-lookup"><span data-stu-id="241ec-111">Draft</span></span> | <span data-ttu-id="241ec-112">Förfrågningen finns i utkast och är inte redo för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="241ec-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="241ec-113">200000001</span><span class="sxs-lookup"><span data-stu-id="241ec-113">200000001</span></span> | <span data-ttu-id="241ec-114">Under granskning</span><span class="sxs-lookup"><span data-stu-id="241ec-114">In Review</span></span> | <span data-ttu-id="241ec-115">Denna begäran har skickats in och skickas nu runt för godkännande via arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="241ec-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="241ec-116">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="241ec-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="241ec-117">200000002</span><span class="sxs-lookup"><span data-stu-id="241ec-117">200000002</span></span> | <span data-ttu-id="241ec-118">Väntar</span><span class="sxs-lookup"><span data-stu-id="241ec-118">Pending</span></span> | <span data-ttu-id="241ec-119">Begäran väntar på en arbetsflödesåtgärd.</span><span class="sxs-lookup"><span data-stu-id="241ec-119">The request is pending workflow action.</span></span> <span data-ttu-id="241ec-120">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="241ec-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="241ec-121">200000003</span><span class="sxs-lookup"><span data-stu-id="241ec-121">200000003</span></span> | <span data-ttu-id="241ec-122">Annullerade</span><span class="sxs-lookup"><span data-stu-id="241ec-122">Canceled</span></span> | <span data-ttu-id="241ec-123">Denna begäran har annullerats.</span><span class="sxs-lookup"><span data-stu-id="241ec-123">The request has been canceled.</span></span> <span data-ttu-id="241ec-124">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="241ec-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="241ec-125">200000004</span><span class="sxs-lookup"><span data-stu-id="241ec-125">200000004</span></span> | <span data-ttu-id="241ec-126">Nekade</span><span class="sxs-lookup"><span data-stu-id="241ec-126">Denied</span></span> | <span data-ttu-id="241ec-127">Denna begäran har avslagits.</span><span class="sxs-lookup"><span data-stu-id="241ec-127">The request has been denied.</span></span> <span data-ttu-id="241ec-128">Endast tillgängligt när arbetsflödet har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="241ec-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="241ec-129">200000005</span><span class="sxs-lookup"><span data-stu-id="241ec-129">200000005</span></span> | <span data-ttu-id="241ec-130">Aktiva</span><span class="sxs-lookup"><span data-stu-id="241ec-130">Active</span></span> | <span data-ttu-id="241ec-131">Alla arbetsflöden har slutförts och godkänts, och ansökan är klar för aktiv rekrytering.</span><span class="sxs-lookup"><span data-stu-id="241ec-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="241ec-132">200000006</span><span class="sxs-lookup"><span data-stu-id="241ec-132">200000006</span></span> | <span data-ttu-id="241ec-133">Stängda</span><span class="sxs-lookup"><span data-stu-id="241ec-133">Closed</span></span> | <span data-ttu-id="241ec-134">Rekryteringsförfrågan har avslutats.</span><span class="sxs-lookup"><span data-stu-id="241ec-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="241ec-135">Se även</span><span class="sxs-lookup"><span data-stu-id="241ec-135">See also</span></span>

[<span data-ttu-id="241ec-136">Introduktion av API för integrering av system för sökandespårning</span><span class="sxs-lookup"><span data-stu-id="241ec-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="241ec-137">Exempelfråga för rekryteringsbegäran</span><span class="sxs-lookup"><span data-stu-id="241ec-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
