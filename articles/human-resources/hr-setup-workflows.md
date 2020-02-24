---
title: Använd arbetsflöden för att hantera medarbetarinformation
description: Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b637186e8ab43378e9d7f0fd3b8e7d7415c21cc2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010625"
---
# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="fb1c0-104">Använd arbetsflöden för att hantera medarbetarinformation</span><span class="sxs-lookup"><span data-stu-id="fb1c0-104">Use workflows to manage employee information</span></span>

<span data-ttu-id="fb1c0-105">Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-105">This article explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="fb1c0-106">Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="fb1c0-107">Arbetsflödeskapaciteten för personal innehåller flera arbetsflöden för hantering av personalaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="fb1c0-108">Dessutom finns många alternativ så att du kan ändra särskilda arbetsflöden och koppla dem till en rapporthierarki.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="fb1c0-109">Arbetsflöden är tillgängliga för att hantera ändringar i flera olika standardtyper av medarbetarinformation.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="fb1c0-110">Du kan associera ett arbetsflöde med en befattning.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="fb1c0-111">Om sedan medarbetare ändrar sin medarbetarpost startas ett arbetsflöde som måste godkännas innan den nya informationen sparas.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="fb1c0-112">Arbetsflöden är fördefinierade för följande typer av information som kan hjälpa dig att effektivt hantera ändringar och behålla medarbetarnas data korrekt:</span><span class="sxs-lookup"><span data-stu-id="fb1c0-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="fb1c0-113">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="fb1c0-113">Identification numbers</span></span>
-   <span data-ttu-id="fb1c0-114">Kurser</span><span class="sxs-lookup"><span data-stu-id="fb1c0-114">Courses</span></span>
-   <span data-ttu-id="fb1c0-115">Utbildning</span><span class="sxs-lookup"><span data-stu-id="fb1c0-115">Education</span></span>
-   <span data-ttu-id="fb1c0-116">Bild</span><span class="sxs-lookup"><span data-stu-id="fb1c0-116">Image</span></span>
-   <span data-ttu-id="fb1c0-117">Lånade objekt</span><span class="sxs-lookup"><span data-stu-id="fb1c0-117">Loaned items</span></span>
-   <span data-ttu-id="fb1c0-118">Yrkeserfarenhet</span><span class="sxs-lookup"><span data-stu-id="fb1c0-118">Professional experience</span></span>
-   <span data-ttu-id="fb1c0-119">Projekterfarenhet</span><span class="sxs-lookup"><span data-stu-id="fb1c0-119">Project experience</span></span>
-   <span data-ttu-id="fb1c0-120">Kompetenser</span><span class="sxs-lookup"><span data-stu-id="fb1c0-120">Skills</span></span>
-   <span data-ttu-id="fb1c0-121">Förtroendeuppdrag</span><span class="sxs-lookup"><span data-stu-id="fb1c0-121">Positions of trust</span></span>
-   <span data-ttu-id="fb1c0-122">Personalåtgärder</span><span class="sxs-lookup"><span data-stu-id="fb1c0-122">Human resources actions</span></span>
-   <span data-ttu-id="fb1c0-123">Kursregistrering</span><span class="sxs-lookup"><span data-stu-id="fb1c0-123">Course registration</span></span>

<span data-ttu-id="fb1c0-124">När medarbetare anställs, överförs eller sägs upp kan arbetsflödet innehålla en granskningsprocess.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="fb1c0-125">På så sätt kan ett dokument ändras eller villkoren för en åtgärd kan definieras som en del av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="fb1c0-126">När granskningen är klar slutförs dokumentet eller åtgärden och arbetsflödet fortsätter till ett slutligt godkännandesteg.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="fb1c0-127">Associera ett arbetsflöde med en befattningshierarki</span><span class="sxs-lookup"><span data-stu-id="fb1c0-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="fb1c0-128">Du kan associera ett arbetsflöde till vilken hierarki som helst som du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="fb1c0-129">Om en befattning som är kopplad till en matrisrapporteringshierarki kan du konfigurera ett arbetsflöde som vidarebefordrar utgifter för ett specifikt projekt till projektledning i stället för chefen för den medarbetare som är kopplad till den befattningen.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="fb1c0-130">Om du vill skapa ett nytt arbetsflöde eller ändra ett befintligt arbetsflöde på sidan **Personalarbetsflöde** klickar du på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="fb1c0-131">Markera ett arbetsflöde i listan för att starta arbetsflödesdesignern.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="fb1c0-132">Du kan använda designern för att skapa ett nytt arbetsflöde eller för att ändra stegen i ett befintligt arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="fb1c0-133">När du ändrar ett befintligt arbetsflöde, sparas dina ändringar som en ny version.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="fb1c0-134">Därför kan kan du alltid gå tillbaka till en tidigare version om du behöver.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="fb1c0-135">Konfigurera personalåtgärdsarbetsflöden</span><span class="sxs-lookup"><span data-stu-id="fb1c0-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="fb1c0-136">Om du vill konfigurera ett grundläggande arbetsflöde som startas när anställda begär ändringar i sin personliga kod följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="fb1c0-137">Klicka på **Ny** på sidan **Personalarbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="fb1c0-138">I listan över tillgängliga arbetsflöden väljer du **ID-nummer**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="fb1c0-139">Klicka på **Kör** för att starta arbetsflödesdesignern och ange ditt användarnamn och lösenord när du uppmanas.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="fb1c0-140">Dra elementet **Godkänna identifieringsnummer** från listan med arbetsflödeselement till designerarbetsytan.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="fb1c0-141">Anslut godkännandeelement för **Starta** och **Slutföra**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="fb1c0-142">Dubbelklicka på **Godkänn elementt** och högerklicka sedan och välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="fb1c0-143">Så här lägger du till arbetsuppgiftsinstruktioner:</span><span class="sxs-lookup"><span data-stu-id="fb1c0-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="fb1c0-144">Välj **Tilldelning** och välj sedan **Hierarki** under tilldelningstypen.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="fb1c0-145">Under **Hierarki** väljer du **Konfigurerbar hierarki**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="fb1c0-146">Lägg till ett stoppvillkor och stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="fb1c0-147">Slutför eventuella ytterligare instruktioner (inga fler varningar bör finnas).</span><span class="sxs-lookup"><span data-stu-id="fb1c0-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="fb1c0-148">Klicka på **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-148">Click **Save and close**.</span></span> <span data-ttu-id="fb1c0-149">Aktivera det nya arbetsflödet när dialogrutan öppnas och välj **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="fb1c0-150">Gå till **Personal** &gt; **Befattningar** &gt; **Befattningshierarkityper**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="fb1c0-151">Välj **Matris**.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="fb1c0-152">Lägg till arbetsflödet **Medarbetares ID-nummer** i listan.</span><span class="sxs-lookup"><span data-stu-id="fb1c0-152">Add the **Worker identification number** workflow to the list.</span></span>




