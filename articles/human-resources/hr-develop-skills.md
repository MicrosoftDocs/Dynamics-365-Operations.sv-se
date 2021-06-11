---
title: Konfigurera färdigheter
description: Du kan spåra arbetarens färdigheter i Dynamics 365 Human Resources. Du kan även ange de färdigheter som krävs för ett visst jobb.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076569"
---
# <a name="configure-skills"></a><span data-ttu-id="c95e3-104">Konfigurera färdigheter</span><span class="sxs-lookup"><span data-stu-id="c95e3-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="c95e3-105">Du kan spåra arbetarens färdigheter i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c95e3-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c95e3-106">Du kan även ange de färdigheter som krävs för ett visst jobb.</span><span class="sxs-lookup"><span data-stu-id="c95e3-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="c95e3-107">Exempel på färdigheter som du kan följa inkluderar:</span><span class="sxs-lookup"><span data-stu-id="c95e3-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="c95e3-108">Handledning – förmåga att handleda andra i arbetet.</span><span class="sxs-lookup"><span data-stu-id="c95e3-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="c95e3-109">Ledarskap – förmåga att leda medarbetare och affärsdomäner.</span><span class="sxs-lookup"><span data-stu-id="c95e3-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="c95e3-110">Planering – Förmåga att se framåt, att formulera visionsinstruktioner och att se till att de genomförs.</span><span class="sxs-lookup"><span data-stu-id="c95e3-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="c95e3-111">HTML – Förmågan att skriva HTML-kod.</span><span class="sxs-lookup"><span data-stu-id="c95e3-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="c95e3-112">Om du inte redan har ställt in färdighetstyper och värderingsmodeller måste du lägga till några innan du skapar färdigheter.</span><span class="sxs-lookup"><span data-stu-id="c95e3-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="c95e3-113">Följande personer kan ange färdigheter för en arbetare:</span><span class="sxs-lookup"><span data-stu-id="c95e3-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="c95e3-114">Medarbetare kan själv ange färdigheter i självbetjäning för medarbetare.</span><span class="sxs-lookup"><span data-stu-id="c95e3-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="c95e3-115">Dessa färdigheter kräver godkännande av chef.</span><span class="sxs-lookup"><span data-stu-id="c95e3-115">These skills require manager approval.</span></span>
- <span data-ttu-id="c95e3-116">Chefer kan ange färdigheter för sina anställda.</span><span class="sxs-lookup"><span data-stu-id="c95e3-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="c95e3-117">Du kan skapa ett arbetsflöde där dessa färdigheter godkänns automatiskt.</span><span class="sxs-lookup"><span data-stu-id="c95e3-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="c95e3-118">Skapa en färdighetstyp</span><span class="sxs-lookup"><span data-stu-id="c95e3-118">Create a skill type</span></span>

<span data-ttu-id="c95e3-119">Färdighetstyper är kategorier som enskilda kompetenser ingår i, t.ex. Administration eller Försäljning.</span><span class="sxs-lookup"><span data-stu-id="c95e3-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="c95e3-120">I arbetsytan **Personalutveckling**, välj **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="c95e3-121">Under **Kompetensinställningar**, välj **Färdighetstyper**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="c95e3-122">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-122">Select **New**.</span></span>

4. <span data-ttu-id="c95e3-123">Fyll i följande fält:</span><span class="sxs-lookup"><span data-stu-id="c95e3-123">Complete the following fields:</span></span>

   - <span data-ttu-id="c95e3-124">**Färdighetstyp**: Ange ett namn på färdighetstypen.</span><span class="sxs-lookup"><span data-stu-id="c95e3-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="c95e3-125">**Beskrivning**: Ange en beskrivning på färdighetstypen.</span><span class="sxs-lookup"><span data-stu-id="c95e3-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="c95e3-126">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="c95e3-127">Skapa en bedömningsmodell</span><span class="sxs-lookup"><span data-stu-id="c95e3-127">Create a rating model</span></span>

<span data-ttu-id="c95e3-128">Bedömningsmodeller gör det enklare att utvärdera en persons faktiska färdighetsnivå, den nivå de ska arbeta för att uppnå eller den färdighetsnivå som krävs för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="c95e3-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="c95e3-129">Varje nivå i en bedömningsmodell tilldelas en faktor.</span><span class="sxs-lookup"><span data-stu-id="c95e3-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="c95e3-130">I arbetsytan **Personalutveckling**, välj **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="c95e3-131">Under **Kompetensinställningar**, välj **Bedömningsmodell**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="c95e3-132">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-132">Select **New**.</span></span>

4. <span data-ttu-id="c95e3-133">Fyll i följande fält:</span><span class="sxs-lookup"><span data-stu-id="c95e3-133">Complete the following fields:</span></span>

   - <span data-ttu-id="c95e3-134">**Bedömning**: Ange ett namn på bedömningsmodellen, till exempel **Kompetenser**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="c95e3-135">**Beskrivning**: Ange en beskrivning av värderingsmodellen, till exempel **färdighetsvärderingar**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="c95e3-136">I avsnittet **Nivåer**, välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="c95e3-137">Fyll i följande fält för varje nivå du vill lägga till:</span><span class="sxs-lookup"><span data-stu-id="c95e3-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="c95e3-138">**Nivå**: Ange ett namn för nivån.</span><span class="sxs-lookup"><span data-stu-id="c95e3-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="c95e3-139">**Beskrivning**: Ange en beskrivning av nivån.</span><span class="sxs-lookup"><span data-stu-id="c95e3-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="c95e3-140">**Faktor**: Ange ett faktorvärde från 0-9.</span><span class="sxs-lookup"><span data-stu-id="c95e3-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="c95e3-141">Faktorer hjälper till att normalisera förfrågningar om partier av färdighetsluckor som använder olika värderingsmodeller.</span><span class="sxs-lookup"><span data-stu-id="c95e3-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="c95e3-142">Varje nivå måste ha en unik faktor.</span><span class="sxs-lookup"><span data-stu-id="c95e3-142">Each level must have a unique factor.</span></span> <span data-ttu-id="c95e3-143">Nivåer med högre faktorvärden innehåller mer vikt i en bedömningsmodell.</span><span class="sxs-lookup"><span data-stu-id="c95e3-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="c95e3-144">Fortsätt att lägga till nivåer om det behövs.</span><span class="sxs-lookup"><span data-stu-id="c95e3-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="c95e3-145">Du kan ange upp till 10 nivåer för varje bedömningsmodell.</span><span class="sxs-lookup"><span data-stu-id="c95e3-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="c95e3-146">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="c95e3-147">Skapa en färdighet</span><span class="sxs-lookup"><span data-stu-id="c95e3-147">Create a skill</span></span>

<span data-ttu-id="c95e3-148">Innan du kan tilldela en färdighet eller skapa en färdighetsmappningssökning eller en kompetensprofil, måste du ange information om färdigheterna på sidan **Färdigheter**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="c95e3-149">För varje kompetens kan du välja en kompetenstyp och en bedömningsmodell.</span><span class="sxs-lookup"><span data-stu-id="c95e3-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="c95e3-150">I arbetsytan **Personalutveckling**, välj **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="c95e3-151">Under **Kompetensinställningar**, välj **Färdigheter**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="c95e3-152">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-152">Select **New**.</span></span>

4. <span data-ttu-id="c95e3-153">Fyll i följande fält:</span><span class="sxs-lookup"><span data-stu-id="c95e3-153">Complete the following fields:</span></span>

   - <span data-ttu-id="c95e3-154">**Färdighet**: Ange ett namn på färdighet.</span><span class="sxs-lookup"><span data-stu-id="c95e3-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="c95e3-155">**Beskrivning**: Ange en beskrivning på färdighet.</span><span class="sxs-lookup"><span data-stu-id="c95e3-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="c95e3-156">**Bedömning**: Välj den bedömningsmodell som du vill använda för denna färdighet.</span><span class="sxs-lookup"><span data-stu-id="c95e3-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="c95e3-157">**Färdighetstyp**: Välj från listan över färdighetstyper.</span><span class="sxs-lookup"><span data-stu-id="c95e3-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="c95e3-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c95e3-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c95e3-159">Se även</span><span class="sxs-lookup"><span data-stu-id="c95e3-159">See also</span></span>

[<span data-ttu-id="c95e3-160">Ange färdigheter</span><span class="sxs-lookup"><span data-stu-id="c95e3-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="c95e3-161">Mappa kompetenser</span><span class="sxs-lookup"><span data-stu-id="c95e3-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]