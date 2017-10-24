---
title: "Justera personalfärdigheter med verksamhetens behov"
description: "Du kan spåra de färdigheter som anställda, sökanden eller kontaktpersoner har eller bör ha för att genomföra deras roller på ett effektivt sätt. Du kan även ange de färdigheter som krävs för ett visst jobb."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b76064049daccdcdff04c9f2fdde9a8b9c9e8e0
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="align-workforce-skills-with-business-needs"></a><span data-ttu-id="8a858-104">Justera personalfärdigheter med verksamhetens behov</span><span class="sxs-lookup"><span data-stu-id="8a858-104">Align workforce skills with business needs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8a858-105">Du kan spåra de färdigheter som anställda, sökanden eller kontaktpersoner har eller bör ha för att genomföra deras roller på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="8a858-105">You can track the skills that workers, applicants, or contact persons have, or should have, to fulfill their roles effectively.</span></span> <span data-ttu-id="8a858-106">Du kan även ange de färdigheter som krävs för ett visst jobb.</span><span class="sxs-lookup"><span data-stu-id="8a858-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="8a858-107">Exempel på färdigheter som du kan följa inkluderar följande:</span><span class="sxs-lookup"><span data-stu-id="8a858-107">Examples of skills you can track include the following:</span></span>
-   <span data-ttu-id="8a858-108">Handledning - förmåga att handleda andra i arbetet.</span><span class="sxs-lookup"><span data-stu-id="8a858-108">Supervisory – Ability to supervise the work of others.</span></span>
-   <span data-ttu-id="8a858-109">Ledarskap – förmåga att leda medarbetare och affärsdomäner.</span><span class="sxs-lookup"><span data-stu-id="8a858-109">Leadership – Ability to lead employees and business domains.</span></span>
-   <span data-ttu-id="8a858-110">Planering – Förmåga att se framåt, att formulera visioner och att se till att de genomförs.</span><span class="sxs-lookup"><span data-stu-id="8a858-110">Planning – Ability to look ahead, to form visions, and to see them through.</span></span>
-   <span data-ttu-id="8a858-111">HTML – Förmågan att skriva HTML-kod.</span><span class="sxs-lookup"><span data-stu-id="8a858-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="8a858-112">Innan du kan tilldela en färdighet till en person eller ett jobb, skapa en färdighetsmappningssökning eller skapa en kompetensprofil, måste du ange information om färdigheterna på sidan **Färdigheter**.</span><span class="sxs-lookup"><span data-stu-id="8a858-112">Before you can assign a skill to a person or a job, create a skill-mapping search, or create a skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="8a858-113">För varje kompetens kan du välja en kompetenstyp och en värderingsmodell.</span><span class="sxs-lookup"><span data-stu-id="8a858-113">For each skill, you can select a skill type and a rating model.</span></span>

## <a name="rating-models"></a><span data-ttu-id="8a858-114">Bedömningsmodeller</span><span class="sxs-lookup"><span data-stu-id="8a858-114">Rating models</span></span>
<span data-ttu-id="8a858-115">Bedömningsmodeller gör det enklare att utvärdera en persons faktiska färdighetsnivå, den nivå de ska arbeta för att uppnå eller den färdighetsnivå som krävs för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="8a858-115">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill that is required for a job.</span></span> <span data-ttu-id="8a858-116">Du kan ange upp till 10 nivåer för en värderingsmodell.</span><span class="sxs-lookup"><span data-stu-id="8a858-116">You can enter up to 10 levels for a rating model.</span></span>  <span data-ttu-id="8a858-117">Varje nivå i en värderingsmodell tilldelas en faktor.</span><span class="sxs-lookup"><span data-stu-id="8a858-117">Each level in a rating model is assigned a factor.</span></span>  <span data-ttu-id="8a858-118">Faktorvärdet ska användas för att normaliserar förfrågningar om partier av färdighetsluckor som använder olika värderingsmodeller.</span><span class="sxs-lookup"><span data-stu-id="8a858-118">The factor value will be used to normalize the scores of skills that use different rating models.</span></span>  <span data-ttu-id="8a858-119">Faktorn måste vara ett nummer mellan 0-9, och varje nivå måste ha en unik faktor.</span><span class="sxs-lookup"><span data-stu-id="8a858-119">The factor must be a number between 0-9 and each level must have a unique factor.</span></span>  <span data-ttu-id="8a858-120">Nivåer med högre faktorvärden innehåller mer vikt i en värderingsmodell.</span><span class="sxs-lookup"><span data-stu-id="8a858-120">Levels with higher factor values carry more weight in a rating model.</span></span>

## <a name="specify-job-skills"></a><span data-ttu-id="8a858-121">Ange jobbfärdigheter</span><span class="sxs-lookup"><span data-stu-id="8a858-121">Specify job skills</span></span>
<span data-ttu-id="8a858-122">När du anger information om ett jobb, kan du ange de färdigheter som en person måste ha för att arbeta med jobbet.</span><span class="sxs-lookup"><span data-stu-id="8a858-122">When you enter information about a job, you can specify the skills that a person should have to perform the work required for the job.</span></span>  <span data-ttu-id="8a858-123">Dessutom kan du ange önskad nivå för varje färdighet samt hur viktig färdigheten är.</span><span class="sxs-lookup"><span data-stu-id="8a858-123">In addition you can specify the desired level for each skill as well the level of importance of the skill.</span></span> <span data-ttu-id="8a858-124">Olika jobb kan kräva olika nivåer av betydelse för samma färdighet.</span><span class="sxs-lookup"><span data-stu-id="8a858-124">Different jobs can require different levels of importance for the same skill.</span></span>

## <a name="enter-skills-for-workers-applicants-or-contacts"></a><span data-ttu-id="8a858-125">Ange kompetenser för arbetstagare, sökande eller kontakter</span><span class="sxs-lookup"><span data-stu-id="8a858-125">Enter skills for workers, applicants, or contacts</span></span>
<span data-ttu-id="8a858-126">Du kan ange eller målfärdigheter verkliga färdigheter för anställd, sökande eller kontakter.</span><span class="sxs-lookup"><span data-stu-id="8a858-126">You can enter target skills or actual skills for workers, applicants, or contacts.</span></span> <span data-ttu-id="8a858-127">En målfärdighet är en färdighet som en person planerar att uppnå.</span><span class="sxs-lookup"><span data-stu-id="8a858-127">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="8a858-128">En faktisk färdighet är en färdighet som en person redan har.</span><span class="sxs-lookup"><span data-stu-id="8a858-128">An actual skill is a skill that a person currently has.</span></span>

## <a name="skill-mapping-and-skill-mapping-profiles"></a><span data-ttu-id="8a858-129"> Färdighetsmappning och Profiler för färdighetsmappning</span><span class="sxs-lookup"><span data-stu-id="8a858-129">Skill mapping and Skill mapping profiles</span></span>
<span data-ttu-id="8a858-130">Du kan skapa en färdighetsmappning för att hitta en anställd, sökande eller kontaktperson som är kvalificerad för en viss typ av uppgift.</span><span class="sxs-lookup"><span data-stu-id="8a858-130">You can create a skill-mapping search to find a worker, applicant, or contact person who is qualified to perform a specific type of task.</span></span> <span data-ttu-id="8a858-131">Färdighetsmappning letar genom färdigheter, utbildning, certifikat, förtroendeuppdrag eller projekterfarenhet och returnerar ett resultat som matchar de villkor som angetts.</span><span class="sxs-lookup"><span data-stu-id="8a858-131">Skill-mapping searches look across skills, education, certificates, positions of trust and project experience and return a results that match the criteria entered.</span></span>  <span data-ttu-id="8a858-132">Exempelvis kan det vara bra att veta vilka arbetare i organisationen som har fått sina CPA.</span><span class="sxs-lookup"><span data-stu-id="8a858-132">For example, it might be useful to know which workers in your organization earned their CPA.</span></span>

<span data-ttu-id="8a858-133">Färdighetsmappningsprofiler låter dig hitta nuvarande anställda eller kandidater med kvalifikationer som direkt motsvarar verksamhetens behov.</span><span class="sxs-lookup"><span data-stu-id="8a858-133">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>  <span data-ttu-id="8a858-134">Exempelvis kan du skapa en kompetensmappningsprofil för en öppen befattning i företaget.</span><span class="sxs-lookup"><span data-stu-id="8a858-134">For example, you could create a skill-mapping profile for an open position in your organization.</span></span> <span data-ttu-id="8a858-135">Genom att skapa en profil för ett visst jobb och kopiera färdigheter, intyg och utbildning från det jobbet till profilen, kan du snabbt söka anställda, sökande och kontaktpersoner som matchar en eller flera av de kriterier som har angetts i profilen och visa en lista över de kandidater som har färdigheter som bäst matchar de färdigheter som krävs för jobbet.</span><span class="sxs-lookup"><span data-stu-id="8a858-135">By creating a profile for a particular job and copying the skills, education and certificates from that job to the profile, you can quickly search workers, applicants and contact persons who match one or more of the criteria entered on the profile and view a list of the candidates whose skills most closely match the skills required for the job.</span></span>

><span data-ttu-id="8a858-136">**Obs!** Endast anställda, sökande och kontaktpersoner som valts för inkludering i sökningar efter kompetensmappning kan visas i resultatlistan från en kompetensmappning eller inkluderas i kompetensprofil.</span><span class="sxs-lookup"><span data-stu-id="8a858-136">**Note** Only workers, applicants, and contact persons who are selected to be included in skill mapping searches can be displayed in a skill-mapping results list, or included in a skill profile.</span></span> <span data-ttu-id="8a858-137">Om du vill ta med en anställd, sökande eller kontaktperson i färdighetsmappningsökningar markerar du Ja i alternativet **Inkludera i färdighetsmappning** på följande sidor:</span><span class="sxs-lookup"><span data-stu-id="8a858-137">To include a worker, applicant, or contact person in skill mapping searches, set the **Include in skill mapping** selection to Yes in the following pages:</span></span>

> + <span data-ttu-id="8a858-138">Arbetare</span><span class="sxs-lookup"><span data-stu-id="8a858-138">Worker</span></span>
> + <span data-ttu-id="8a858-139">Medarbetare</span><span class="sxs-lookup"><span data-stu-id="8a858-139">Employee</span></span>
> + <span data-ttu-id="8a858-140">Sökande</span><span class="sxs-lookup"><span data-stu-id="8a858-140">Applicant</span></span>
> + <span data-ttu-id="8a858-141">Kontakter</span><span class="sxs-lookup"><span data-stu-id="8a858-141">Contacts</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="8a858-142">Analys av färdighetsluckor och analys av kompetensprofil</span><span class="sxs-lookup"><span data-stu-id="8a858-142">Skill gap analysis and skill profile analysis</span></span>
<span data-ttu-id="8a858-143">Du kan skapa en analys till färdighetsmappning profil som du vill visa en lista med kompetenserna för en anställd, sökande eller kontaktperson för ett visst datum.</span><span class="sxs-lookup"><span data-stu-id="8a858-143">You can create a skill profile analysis to view a list of the competencies of a worker, applicant, or contact person as of a specific date.</span></span> <span data-ttu-id="8a858-144">Du kan skapa en analys för luckor i kompetens om du vill jämföra en persons kompetenser med de kompetenser som krävs för ett visst jobb.</span><span class="sxs-lookup"><span data-stu-id="8a858-144">You can create a skill gap analysis to compare a person’s skills and the skills that are required for a specific job.</span></span>  



<a name="see-also"></a><span data-ttu-id="8a858-145">Se även</span><span class="sxs-lookup"><span data-stu-id="8a858-145">See also</span></span>
--------

[<span data-ttu-id="8a858-146">Personal</span><span class="sxs-lookup"><span data-stu-id="8a858-146">Human resources</span></span>](index.md)




