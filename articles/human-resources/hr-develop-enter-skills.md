---
title: Ange färdigheter
description: Medarbetare och chefer kan ange färdigheter i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076616"
---
# <a name="enter-skills"></a><span data-ttu-id="3035a-103">Ange färdigheter</span><span class="sxs-lookup"><span data-stu-id="3035a-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3035a-104">Du kan ange eller målfärdigheter verkliga färdigheter för anställd, sökande eller kontakter i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3035a-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="3035a-105">En målfärdighet är en färdighet som en person planerar att uppnå.</span><span class="sxs-lookup"><span data-stu-id="3035a-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="3035a-106">En faktisk färdighet är en färdighet som en person redan har.</span><span class="sxs-lookup"><span data-stu-id="3035a-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="3035a-107">Skapa ett arbetsflöde för att automatiskt godkänna färdigheter</span><span class="sxs-lookup"><span data-stu-id="3035a-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="3035a-108">Om du vill registrera färdigheter utan att kräva godkännande måste du skapa ett arbetsflöde för att godkänna färdigheter automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3035a-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="3035a-109">Kompetenser som anges av arbetare kräver alltid godkännande av chef.</span><span class="sxs-lookup"><span data-stu-id="3035a-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="3035a-110">Det här arbetsflödet godkänner bara färdigheter som har angetts automatiskt av chefer för deras arbetare.</span><span class="sxs-lookup"><span data-stu-id="3035a-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="3035a-111">I arbetsytan **Personalhantering** väjer du **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="3035a-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="3035a-112">Under **Inställningar**, välj **Personalarbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="3035a-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="3035a-113">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3035a-113">Select **New**.</span></span>

4. <span data-ttu-id="3035a-114">I fönstret **Skapa arbetsflöde**, välj **Kompetens för arbetare**.</span><span class="sxs-lookup"><span data-stu-id="3035a-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="3035a-115">[![Välja arbetsflöde för arbetsfärdigheter](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="3035a-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="3035a-116">I dialogrutan **Öppna denna fil**, välj **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="3035a-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="3035a-117">Ange din inloggningsuppgifter när du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="3035a-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="3035a-118">I arbetsflödesredigeraren, välj arbetsflödeselementet **Godkänn färdigheter** och dra det till arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="3035a-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="3035a-119">[![Välj Godkänn arbetsflödeselement för färdigheter](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="3035a-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="3035a-120">Anslut elementet **Start** till elementet **Godkänn färdigheter 1** och anslut till elementet **Godkänn färdigheter 1** till elementet **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="3035a-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="3035a-121">Du kanske måste rulla nedåt för att se elementet **Slut**.</span><span class="sxs-lookup"><span data-stu-id="3035a-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="3035a-122">Du kan dra den närmare de andra elementen.</span><span class="sxs-lookup"><span data-stu-id="3035a-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="3035a-123">[![Anslut arbetsflödeselement](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="3035a-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="3035a-124">Dubbelklicka på arbetsflödeselementet **Godkänn färdigheter 1** och högerklicka sedan på elementet **Steg 1**.</span><span class="sxs-lookup"><span data-stu-id="3035a-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="3035a-125">Högerklicka på elementet **Steg 1** och välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="3035a-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="3035a-126">I fönstret **Egenskaper**, välj **Villkor** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3035a-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="3035a-127">Välj **Kör bara det här steget när följande villkor uppfylls**.</span><span class="sxs-lookup"><span data-stu-id="3035a-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="3035a-128">Välj **Lägg till villkor**.</span><span class="sxs-lookup"><span data-stu-id="3035a-128">Select **Add condition**.</span></span> <span data-ttu-id="3035a-129">Efter **Var**, välj **Anställdas självbetjäningsförmåga** och välj sedan **Anställdas självbetjäningsförmåga.Person**.</span><span class="sxs-lookup"><span data-stu-id="3035a-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="3035a-130">Efter **är**, välj **fält** och välj **Förhållande mellan användare och person.Person**.</span><span class="sxs-lookup"><span data-stu-id="3035a-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="3035a-131">[![Ange villkor](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="3035a-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="3035a-132">Välj **Tilldelning** i det vänstra stapeln.</span><span class="sxs-lookup"><span data-stu-id="3035a-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="3035a-133">På fliken **Tilldelningstyp**, välj **Hierarki**.</span><span class="sxs-lookup"><span data-stu-id="3035a-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="3035a-134">På fliken **Hierarkival** i fältet **Hierarkityp:**, välj **Chefshierarki**.</span><span class="sxs-lookup"><span data-stu-id="3035a-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="3035a-135">[![Ange en chefshierarki](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="3035a-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="3035a-136">Välj **Stäng**, välj **Arbetsflöde** i arbetsflödet och välj sedan **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="3035a-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="3035a-137">För mer information om att skapa arbetsflöden, se [arbetsflödessystem, översikt](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="3035a-137">For more information about creating workflows, see [Workflow system overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="3035a-138">Ange färdigheter för en arbetare</span><span class="sxs-lookup"><span data-stu-id="3035a-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="3035a-139">Välj en arbetare.</span><span class="sxs-lookup"><span data-stu-id="3035a-139">Select a worker.</span></span>

2. <span data-ttu-id="3035a-140">I åtgärdsfältet på sidan **Arbetare**, välj **Person** och välj sedan **Färdigheter**.</span><span class="sxs-lookup"><span data-stu-id="3035a-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="3035a-141">På sidan **Färdigheter** slutför följande fält för varje färdighet:</span><span class="sxs-lookup"><span data-stu-id="3035a-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="3035a-142">**Färdighet**: välj en färdighet.</span><span class="sxs-lookup"><span data-stu-id="3035a-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="3035a-143">**Nivåtyp**: Välj **Faktiskt** för en färdighet som a arbetaren redan har eller välj **Mål** för en färdighet som arbetar mot.</span><span class="sxs-lookup"><span data-stu-id="3035a-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="3035a-144">**Nivå**: Välj en nivå för arbetarens färdighet.</span><span class="sxs-lookup"><span data-stu-id="3035a-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="3035a-145">**Nivådatum**: Välj ett datum i kalenderverktyget.</span><span class="sxs-lookup"><span data-stu-id="3035a-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="3035a-146">**Granskare**: vid behov kan du välja en användare från listan.</span><span class="sxs-lookup"><span data-stu-id="3035a-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="3035a-147">Du kan filtrera sökningen.</span><span class="sxs-lookup"><span data-stu-id="3035a-147">You can filter your search.</span></span>
   - <span data-ttu-id="3035a-148">**Års erfarenhet**: Ange år av erfarenhet.</span><span class="sxs-lookup"><span data-stu-id="3035a-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="3035a-149">**Verifierat**: Om färdigheten har verifierats ska du markera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="3035a-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="3035a-150">**Verifierat av**: Ange namnet på kontrollören.</span><span class="sxs-lookup"><span data-stu-id="3035a-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="3035a-151">När du har angett färdigheterna väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3035a-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3035a-152">Se även</span><span class="sxs-lookup"><span data-stu-id="3035a-152">See also</span></span>

[<span data-ttu-id="3035a-153">Konfigurera färdigheter</span><span class="sxs-lookup"><span data-stu-id="3035a-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="3035a-154">Mappa kompetenser</span><span class="sxs-lookup"><span data-stu-id="3035a-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]