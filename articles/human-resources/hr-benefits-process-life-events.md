---
title: Bearbeta livshändelse
description: Under medarbetarens livscykel i Microsoft Dynamics 365 Human Resources kan varje medarbetare stöta på olika ändringar av livshändelser.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 42b7e2606bca4bb5eda1c9bfc7940f9067c4b943
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114261"
---
# <a name="process-life-events"></a><span data-ttu-id="9fd41-103">Bearbeta livshändelse</span><span class="sxs-lookup"><span data-stu-id="9fd41-103">Process life events</span></span>

<span data-ttu-id="9fd41-104">Under medarbetarens livscykel i Microsoft Dynamics 365 Human Resources kan varje medarbetare stöta på olika ändringar av livshändelser.</span><span class="sxs-lookup"><span data-stu-id="9fd41-104">During the employee lifecycle in Microsoft Dynamics 365 Human Resources, each employee may encounter various life event changes.</span></span> <span data-ttu-id="9fd41-105">Till exempel, äktenskap, nytt jobb eller beroendeändringar.</span><span class="sxs-lookup"><span data-stu-id="9fd41-105">For example, marriage, change in employment, or dependent/beneficiary change.</span></span> <span data-ttu-id="9fd41-106">Om du vill använda livshändelser måste du aktivera livshändelser i formuläret förmånsparametrar, ställa in livhändelsetyper och ställa in livshändelsealternativ för plantyper.</span><span class="sxs-lookup"><span data-stu-id="9fd41-106">To use life events, you must enable life events in the benefits parameters form, set up life event types, and set up life event options for plan types.</span></span>

<span data-ttu-id="9fd41-107">Innan du kan bearbeta livshändelser måste du redan ha kört öppna registreringar minst en gång under en anställningstidsram.</span><span class="sxs-lookup"><span data-stu-id="9fd41-107">Before you can process life events, you must have already run open enrollment at least once during a hiring time frame.</span></span> <span data-ttu-id="9fd41-108">I USA är det vanligt att öppna anmälningen en gång per år.</span><span class="sxs-lookup"><span data-stu-id="9fd41-108">In the United States, open enrollment is typically once per year.</span></span> <span data-ttu-id="9fd41-109">Utanför USA kan öppen registrering utföras vid anställningstiden.</span><span class="sxs-lookup"><span data-stu-id="9fd41-109">Outside the United States, open enrollment may be run at the time of hire.</span></span> <span data-ttu-id="9fd41-110">En arbetstagare behöver inte välja en förmånsplan för att livshändelser ska bearbetas, men de måste ha inkluderats i öppen registreringsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="9fd41-110">A worker does not need to select a benefit plan in order for life events to be processed, but they need to have been included in open enrollment processing.</span></span> 

<span data-ttu-id="9fd41-111">Använd bearbetning av livhändelse när du har arbetare med livhändelser som inträffar på ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="9fd41-111">Use life event processing when you have workers who have life events that take place on a future date.</span></span> <span data-ttu-id="9fd41-112">Den här händelsen bearbetar alla livshändelser som inte har bearbetats (som framtida livshändelser eller livshändelser som inte är specifika för någon arbetstagare – ett exempel är en ny förmån).</span><span class="sxs-lookup"><span data-stu-id="9fd41-112">This event will process all life events that have not been processed (like future life events, or life events that have been added that are not specific to any one worker – one example is a new benefit).</span></span> <span data-ttu-id="9fd41-113">Livshändelser i realtid döljs.</span><span class="sxs-lookup"><span data-stu-id="9fd41-113">Real-time life events are hidden.</span></span>

<span data-ttu-id="9fd41-114">Om till exempel dagens datum är 1 februari och den 14 februari är arbetare Johan Svensson schemalagd att ändra juridiska personer, bearbetas alla livshändelser fram till 15 februari i systemet.</span><span class="sxs-lookup"><span data-stu-id="9fd41-114">For example, if today is February 1, and on February 14 worker Joe Smith is scheduled to change legal entities, if you run life event processing for February 15, the system processes all events up until February 15.</span></span> 

1. <span data-ttu-id="9fd41-115">I arbetsytan **Förmånshantering** under **bearbetar**, välj **bearbeta livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="9fd41-115">In the **Benefits management** workspace, under **Processing**, select **Life event processing**.</span></span>

2. <span data-ttu-id="9fd41-116">I dialogrutan **Kör process för livshändelse** ange värden för följande fält:</span><span class="sxs-lookup"><span data-stu-id="9fd41-116">In the **Run life event process** dialog box, specify values for the following fields:</span></span>

   | <span data-ttu-id="9fd41-117">Fält</span><span class="sxs-lookup"><span data-stu-id="9fd41-117">Field</span></span> | <span data-ttu-id="9fd41-118">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9fd41-118">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="9fd41-119">**Anmälningsperiod**</span><span class="sxs-lookup"><span data-stu-id="9fd41-119">**Enrollment period**</span></span> | <span data-ttu-id="9fd41-120">Anmälningsperiod för bearbeta livshändelse.</span><span class="sxs-lookup"><span data-stu-id="9fd41-120">The enrollment period to process life events for.</span></span> |
   | <span data-ttu-id="9fd41-121">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="9fd41-121">**Legal entity**</span></span> | <span data-ttu-id="9fd41-122">Juridisk person för bearbeta livshändelse.</span><span class="sxs-lookup"><span data-stu-id="9fd41-122">The legal entity to process life events for.</span></span> |
   | <span data-ttu-id="9fd41-123">**Datum för livshändelse**</span><span class="sxs-lookup"><span data-stu-id="9fd41-123">**Life event date**</span></span> | <span data-ttu-id="9fd41-124">Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum.</span><span class="sxs-lookup"><span data-stu-id="9fd41-124">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="9fd41-125">**Arbetare**</span><span class="sxs-lookup"><span data-stu-id="9fd41-125">**Worker**</span></span> | <span data-ttu-id="9fd41-126">Arbetare för bearbeta livshändelse.</span><span class="sxs-lookup"><span data-stu-id="9fd41-126">The worker to process life events for.</span></span> <span data-ttu-id="9fd41-127">Om du lämnar det här fältet livshändelser bearbetas för alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="9fd41-127">If you leave this field blank, life events will be processed for all workers.</span></span> |

3. <span data-ttu-id="9fd41-128">Om du vill köra processen i bakgrunden väljer du **Kör i bakgrunden** och utför följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="9fd41-128">If you want to run the process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="9fd41-129">Ange information för processen.</span><span class="sxs-lookup"><span data-stu-id="9fd41-129">Enter information for the process.</span></span>

   2. <span data-ttu-id="9fd41-130">Om du vill ställa in ett återkommande jobb väljer du **återkommande**, anger upprepningsinformationen och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd41-130">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="9fd41-131">Ställ in en jobbsignal genom att välja **notifieringar**, välja de notifieringar som ska tas emot och sedan välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd41-131">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="9fd41-132">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd41-132">Select **OK**.</span></span> <span data-ttu-id="9fd41-133">Processen kommer att köras med de parametrar du angett.</span><span class="sxs-lookup"><span data-stu-id="9fd41-133">The process will run with the parameters you set.</span></span>

4. <span data-ttu-id="9fd41-134">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fd41-134">Select **OK**.</span></span>
