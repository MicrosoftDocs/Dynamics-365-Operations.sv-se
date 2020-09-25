---
title: Ställ in projektresurser
description: Detta ämne innehåller information om hur du ställer in eller begär projektresurser.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760668"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="a4eb2-103">Ställ in projektresurser</span><span class="sxs-lookup"><span data-stu-id="a4eb2-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4eb2-104">Du måste ställa in en kalender och associera den till en medarbetare eller en arbetare.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="a4eb2-105">Kalendern används för att kunna tidsplanera projektet och arbetstiden för de resurser som har reserverats för projektet.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="a4eb2-106">Under kalenderinställningarna kan projektledare kan utföra resursutjämning som en del av resursoptimeringen.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="a4eb2-107">Baserat på kalendertidsplanen kan begränsningar tillämpas på resurser.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="a4eb2-108">Du kan ställa in en kalender på sidan **Kalendrar**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="a4eb2-109">När du konfigurerar en medarbetare som e projektresurs kan du välja bland medarbetare som arbetar på det företag som du konfigurerar resurser för.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="a4eb2-110">Alternativt kan du välja medarbetare från andra företag inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="a4eb2-111">Dessa medarbetare kallas även företagsinterna resurser.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="a4eb2-112">Följande procedurer förklarar hur du konfigurerar en medarbetare som en projektresurs inom ditt företag samt hur du konfigurerar en företagsintern projektresurs.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="a4eb2-113">Ställ in en arbetare som en projektresurs</span><span class="sxs-lookup"><span data-stu-id="a4eb2-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="a4eb2-114">På sidan **Arbetare**, i listan **Arbetare**, välj den arbetare som du lägger till som en projektresurs och öppna arbetarens post.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="a4eb2-115">I åtgärdsfönstret markerar du **Projekt** &gt; **Inställningar** &gt; **Projektinställning**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="a4eb2-116">Välj en kalender och stäng sedan sidan.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="a4eb2-117">Du kan även ange standardprojekt för en resurs som en typ av förtilldelning.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="a4eb2-118">Förtilldelningar kan användas när resurschefen eller projektledaren vet vilka projekt att resursen ska arbeta med i förväg.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="a4eb2-119">Förtilldelningar kan också baseras på en begäran av en projektsponsor eller kund.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="a4eb2-120">Du förtilldelar ett projekt genom att välja lämpligt projekt på sidan **Tilldela projekt**, på **Projekt** fliken, i listan **Resterande projekt**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="a4eb2-121">Ställa in en koncernintern resurs</span><span class="sxs-lookup"><span data-stu-id="a4eb2-121">Set up an intercompany resource</span></span>

<span data-ttu-id="a4eb2-122">När du ställer in en medarbetare som en företagsintern resurs måste du slutföra inställningarna i både det långivande företaget och det lånande företaget.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="a4eb2-123">I det långivande företaget</span><span class="sxs-lookup"><span data-stu-id="a4eb2-123">In the lending company</span></span>

1. <span data-ttu-id="a4eb2-124">I Finance kontrollerar du att det långivande företaget har valts och slutför sedan proceduren i föregående avsnitt, "Ställ in en medarbetare som en projektresurs".</span><span class="sxs-lookup"><span data-stu-id="a4eb2-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="a4eb2-125">På sidan **Företagsintern redovisning** markerar du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="a4eb2-126">I fältet **ID för juridisk person** markerar du det långivande företaget.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="a4eb2-127">Fyll i återstående fält efter behov och markera sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="a4eb2-128">På sidan **Överföringspris** markerar du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="a4eb2-129">I fältet **Lånande juridisk person** markerar du lämpligt företag.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="a4eb2-130">Om du endast vill låna den resurs som du skapa de i början av detta avsnitt till det lånande företaget, markerar du namnet på den resurs som du skapat i fältet **Resurs**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="a4eb2-131">Om du vill att alla resurser inom företaget som lånar ut ska vara tillgängliga för företaget som lånar, lämnar du fältet **Resurs** tomt.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="a4eb2-132">På sidan **Projekthantering och redovisningsparametrar**, på fliken **Företagsintern**, anger du alternativet **Aktivera företagsintern resursplanering och tidrapporter** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="a4eb2-133">I det lånande företaget</span><span class="sxs-lookup"><span data-stu-id="a4eb2-133">In the borrowing company</span></span>

- <span data-ttu-id="a4eb2-134">I sökfiltret på sidan **Resurslista** anger du namnet på den resurs som du skapade för företaget som lånar ut, detta i syfte att bekräfta att namnet inkluderas i resurslistan för företaget som lånar.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="a4eb2-135">Förfrågningar om projektresurser</span><span class="sxs-lookup"><span data-stu-id="a4eb2-135">Request project resources</span></span>
<span data-ttu-id="a4eb2-136">Schemaläggningsfunktionen för projektresurser låter endast resursansvariga distribuera bemannade resurser för åtaganden eller projekt.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="a4eb2-137">För att aktivera funktionen slutför du följande uppgifter eller bekräftar att de har slutförts:</span><span class="sxs-lookup"><span data-stu-id="a4eb2-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="a4eb2-138">Ställa in nummerserier.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-138">Set up number sequences.</span></span>
- <span data-ttu-id="a4eb2-139">Ställ in projekthanterings- och redovisningsarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="a4eb2-140">Aktivera arbetsflödena för resursbegäran.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-140">Enable resource request workflows.</span></span>

<span data-ttu-id="a4eb2-141">När föregående uppgifter har slutförts kan du slutföra följande uppgifter efter behov:</span><span class="sxs-lookup"><span data-stu-id="a4eb2-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="a4eb2-142">Skapa en resursbegäran från en preliminärbokad bemannad resurs.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="a4eb2-143">Övervaka resursbegäranden.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-143">Monitor resource requests.</span></span>
- <span data-ttu-id="a4eb2-144">Uppfylla resursbegäranden.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="a4eb2-145">Begära en bemannad resurs från en struktur.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="a4eb2-146">Boka resurser till ett projekt utan någon begäran om en bemannad resurs.</span><span class="sxs-lookup"><span data-stu-id="a4eb2-146">Book resources to a project without having a request for a staffed resource.</span></span>
