---
title: Bearbetning av berättigande för anmälan
description: I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4dd63e755f0afdbce411b3001410d2e56036e432
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054270"
---
# <a name="process-enrollment-eligibility"></a><span data-ttu-id="8619d-103">Bearbetning av berättigande för anmälan</span><span class="sxs-lookup"><span data-stu-id="8619d-103">Process enrollment eligibility</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8619d-104">I den här artikeln beskrivs hur du kör bearbetning av berättigande för anmälan.</span><span class="sxs-lookup"><span data-stu-id="8619d-104">This article explains how to run the enrollment eligibility process.</span></span>

1. <span data-ttu-id="8619d-105">I arbetsytan **Förmånshantering** under **bearbetar**, välj **Bearbetning av berättigande för anmälan**.</span><span class="sxs-lookup"><span data-stu-id="8619d-105">In the **Benefits management** workspace, under **Processing**, select **Enrollment eligibility processing**.</span></span>

2. <span data-ttu-id="8619d-106">I dialogrutan **Kör bearbetning av berättigande för förmånsanmälan** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="8619d-106">In the **Run benefit enrollment eligibility process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="8619d-107">Fält</span><span class="sxs-lookup"><span data-stu-id="8619d-107">Field</span></span> | <span data-ttu-id="8619d-108">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8619d-108">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8619d-109">**Anmälningsperiod**</span><span class="sxs-lookup"><span data-stu-id="8619d-109">**Enrollment period**</span></span> | <span data-ttu-id="8619d-110">Anmälningsperiod för att bearbeta av berättigande för anmälan.</span><span class="sxs-lookup"><span data-stu-id="8619d-110">The enrollment period to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="8619d-111">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="8619d-111">**Legal entity**</span></span> | <span data-ttu-id="8619d-112">Juridisk person att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="8619d-112">The legal entity to process enrollment eligibility for.</span></span> |
   | <span data-ttu-id="8619d-113">**Arbetare**</span><span class="sxs-lookup"><span data-stu-id="8619d-113">**Worker**</span></span> | <span data-ttu-id="8619d-114">Arbetare att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="8619d-114">The worker to process enrollment eligibility for.</span></span> <span data-ttu-id="8619d-115">Om du lämnar det här fältet tomt bearbetas en berättigande för anmälan för alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="8619d-115">If you leave this field blank, enrollment eligibility will be processed for all workers.</span></span> |
   | <span data-ttu-id="8619d-116">**Förmånsplan**</span><span class="sxs-lookup"><span data-stu-id="8619d-116">**Benefit plan**</span></span> | <span data-ttu-id="8619d-117">Förmånsplan att bearbeta berättigande för anmälan för.</span><span class="sxs-lookup"><span data-stu-id="8619d-117">The benefit plan to process enrollment eligibility for.</span></span>

3. <span data-ttu-id="8619d-118">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="8619d-118">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="8619d-119">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="8619d-119">Enter information for the process.</span></span>

   2. <span data-ttu-id="8619d-120">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8619d-120">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="8619d-121">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="8619d-121">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="8619d-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8619d-122">Select **OK**.</span></span> <span data-ttu-id="8619d-123">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="8619d-123">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="8619d-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8619d-124">Select **OK**.</span></span>

## <a name="view-process-results"></a><span data-ttu-id="8619d-125">Visa processresultat</span><span class="sxs-lookup"><span data-stu-id="8619d-125">View Process Results</span></span>

<span data-ttu-id="8619d-126">I den här artikeln beskrivs hur du visar berättigande processresultat.</span><span class="sxs-lookup"><span data-stu-id="8619d-126">This article explains how to view eligibility process results.</span></span>

1.  <span data-ttu-id="8619d-127">I arbetsytan **Förmånshantering** under **bearbetar**, välj **processresultat**.</span><span class="sxs-lookup"><span data-stu-id="8619d-127">In the **Benefits management** workspace, under **Processing**, select **Process results**.</span></span>

2.  <span data-ttu-id="8619d-128">I formuläret **processresultat** anges följande fält:</span><span class="sxs-lookup"><span data-stu-id="8619d-128">In the **Process results** form, the following fields are specified:</span></span>

   | <span data-ttu-id="8619d-129">Fält</span><span class="sxs-lookup"><span data-stu-id="8619d-129">Field</span></span> | <span data-ttu-id="8619d-130">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8619d-130">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8619d-131">**Process-ID**</span><span class="sxs-lookup"><span data-stu-id="8619d-131">**Process ID**</span></span> | <span data-ttu-id="8619d-132">Unikt ID för kombinationen av arbetare, juridisk person och processkörning.</span><span class="sxs-lookup"><span data-stu-id="8619d-132">The unique ID for the combination of Worker, Legal entity, and process run.</span></span> |
   | <span data-ttu-id="8619d-133">**Processtyp**</span><span class="sxs-lookup"><span data-stu-id="8619d-133">**Process type**</span></span> | <span data-ttu-id="8619d-134">Detta anger vilken process som kördes.</span><span class="sxs-lookup"><span data-stu-id="8619d-134">This identifies the process that was run.</span></span> <span data-ttu-id="8619d-135">Till exempel: Anmälan.</span><span class="sxs-lookup"><span data-stu-id="8619d-135">For example:  Enrollment.</span></span> |
   | <span data-ttu-id="8619d-136">**Tidstämpel**</span><span class="sxs-lookup"><span data-stu-id="8619d-136">**Time stamp**</span></span> | <span data-ttu-id="8619d-137">Den tidpunkt då berättigandeprocessen kördes.</span><span class="sxs-lookup"><span data-stu-id="8619d-137">The time that the eligibility process was run.</span></span> |
   | <span data-ttu-id="8619d-138">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="8619d-138">**Legal entity**</span></span> | <span data-ttu-id="8619d-139">Den juridiska person som anges under anmälningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8619d-139">The legal entity specified during the enrollment process.</span></span> |
   | <span data-ttu-id="8619d-140">**Arbetare**</span><span class="sxs-lookup"><span data-stu-id="8619d-140">**Worker**</span></span> | <span data-ttu-id="8619d-141">Arbetaren som bearbetades.</span><span class="sxs-lookup"><span data-stu-id="8619d-141">The worker who was processed.</span></span> |
   | <span data-ttu-id="8619d-142">\*\*Plan</span><span class="sxs-lookup"><span data-stu-id="8619d-142">\*\*Plan</span></span> | <span data-ttu-id="8619d-143">Den förmånsplan som anmälan gjordes för.</span><span class="sxs-lookup"><span data-stu-id="8619d-143">The Benefit plan that enrollment was attempted for.</span></span> |
   | <span data-ttu-id="8619d-144">**Berättiganderegel**</span><span class="sxs-lookup"><span data-stu-id="8619d-144">**Eligibility rule**</span></span> | <span data-ttu-id="8619d-145">Den berättiganderegel som bearbetades.</span><span class="sxs-lookup"><span data-stu-id="8619d-145">The eligibility rule that was processed.</span></span> <span data-ttu-id="8619d-146">Om ett fel påträffades innan berättigandet kördes är detta tomt.</span><span class="sxs-lookup"><span data-stu-id="8619d-146">If an error was encountered before eligibility was run, this will be blank.</span></span> <span data-ttu-id="8619d-147">Exempel: om kompensationen inte har definierats för en arbetare körs inte berättigandeprocessen och detta fält lämnas tomt.</span><span class="sxs-lookup"><span data-stu-id="8619d-147">For example: If compensation hasn't been defined for a worker, the eligibility process won't run, and this field will be left blank.</span></span> |
   | <span data-ttu-id="8619d-148">**Resultatstatus**</span><span class="sxs-lookup"><span data-stu-id="8619d-148">**Result status**</span></span> | <span data-ttu-id="8619d-149">Detta är berättigat eller inte berättigat.</span><span class="sxs-lookup"><span data-stu-id="8619d-149">This will be Eligible or Ineligible.</span></span> <span data-ttu-id="8619d-150">Resultatstatusen är inte giltig om medarbetaren inte uppfyller villkoren för berättiganderegler, om personen saknar nödvändig information, t.ex. lönefrekvens eller en fast kompensation, eller om det saknas information om förmånsplanen som förhindrar att arbetare registreras.</span><span class="sxs-lookup"><span data-stu-id="8619d-150">The result status will be Ineligible if the worker didn’t meet the eligibility rule criteria, if the worker is missing required information such as a pay frequency or fixed compensation, or if there is information missing on the benefit plan that prevents workers from being enrolled.</span></span> |
   | <span data-ttu-id="8619d-151">**Resultatmeddelande**</span><span class="sxs-lookup"><span data-stu-id="8619d-151">**Result message**</span></span> | <span data-ttu-id="8619d-152">Anger varför en arbetare är berättigad till en förmånsplan eller om berättiganderegler har överförts.</span><span class="sxs-lookup"><span data-stu-id="8619d-152">Indicates why a worker is ineligible for a benefit plan or if the eligibility rule passed.</span></span> |



[!INCLUDE[footer-include](../includes/footer-banner.md)]