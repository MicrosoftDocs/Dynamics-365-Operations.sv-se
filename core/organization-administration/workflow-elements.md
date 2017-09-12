---
title: "Arbetsflödeselement"
description: "Den här artikeln beskriver de olika elementen som utgör ett arbetsflöde."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 5620a91ff9f300bed782170307a295ab79fc5b2e
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="workflow-elements"></a><span data-ttu-id="4f7aa-103">Arbetsflödeselement</span><span class="sxs-lookup"><span data-stu-id="4f7aa-103">Workflow elements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4f7aa-104">Den här artikeln beskriver de olika elementen som utgör ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-104">This article describes the various elements that make up a workflow.</span></span>

<span data-ttu-id="4f7aa-105">Ett arbetsflöde består av olika element, t.ex.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-105">A workflow consists of elements.</span></span> <span data-ttu-id="4f7aa-106">De olika avsnitten som följer beskriver varje typ av element.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-106">The sections that follow describe each type of element.</span></span>

## <a name="tasks"></a><span data-ttu-id="4f7aa-107">Uppgifter</span><span class="sxs-lookup"><span data-stu-id="4f7aa-107">Tasks</span></span>
<span data-ttu-id="4f7aa-108">En *uppgift* är en arbetsenhet som måste utföras.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-108">A *task* is a unit of work that must be performed.</span></span> <span data-ttu-id="4f7aa-109">Två typer av uppgifter kan läggas till i ett arbetsflöde: manuella uppgifter och automatiska uppgifter.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-109">Two types of tasks can be added to a workflow: manual tasks and automated tasks.</span></span>

### <a name="manual-task"></a><span data-ttu-id="4f7aa-110">Manuell uppgift</span><span class="sxs-lookup"><span data-stu-id="4f7aa-110">Manual task</span></span>

<span data-ttu-id="4f7aa-111">En *manuell uppgift* är en arbetsenhet som måste utföras av en användare.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-111">A *manual task* is a unit of work that must be performed by a user.</span></span> <span data-ttu-id="4f7aa-112">Till exempel kan en utgiftsrapport arbetsflöde ha manuella uppgifter som kräver att de tilldelade användarna utför följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4f7aa-112">For example, an expense report workflow can have manual tasks that require the assigned users to complete the following actions:</span></span>

-   <span data-ttu-id="4f7aa-113">Granska de inleveranser som skickas in tillsammans med en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-113">Review the receipts that are submitted together with an expense report.</span></span>
-   <span data-ttu-id="4f7aa-114">Kontakta en medarbetares chef.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-114">Call an employee's manager.</span></span>

### <a name="automated-task"></a><span data-ttu-id="4f7aa-115">Automatisk uppgift</span><span class="sxs-lookup"><span data-stu-id="4f7aa-115">Automated task</span></span>

<span data-ttu-id="4f7aa-116">En *automatisk uppgift* är en arbetsenhet som måste utföras av systemet.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-116">An *automated task* is a unit of work that must be performed by the system.</span></span> <span data-ttu-id="4f7aa-117">Ingen mänsklig interaktion krävs.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-117">No human interaction is required.</span></span> <span data-ttu-id="4f7aa-118">Till exempel kan ett arbetsflöde med en försäljningsorder ha automatiska uppgifter som kräver att systemet utför följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4f7aa-118">For example, a sales order workflow can have automated tasks that require the system to complete the following actions:</span></span>

-   <span data-ttu-id="4f7aa-119">Utför en kreditkontroll.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-119">Perform a credit check.</span></span>
-   <span data-ttu-id="4f7aa-120">Skapa en kundpost för kunden, om en post inte redan finns.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-120">Create a customer record for the customer, if a record doesn't already exist.</span></span>

## <a name="approval-processes"></a><span data-ttu-id="4f7aa-121">Godkännandeprocess</span><span class="sxs-lookup"><span data-stu-id="4f7aa-121">Approval processes</span></span>
<span data-ttu-id="4f7aa-122">En *godkännandeprocess* är en process som består av separata steg.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-122">An *approval process* is a process that consists of separate steps.</span></span> <span data-ttu-id="4f7aa-123">I varje godkännandesteg kan användaren utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4f7aa-123">At each approval step, the user can perform the following actions:</span></span>

-   <span data-ttu-id="4f7aa-124">Godkänna dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-124">Approve the document.</span></span>
-   <span data-ttu-id="4f7aa-125">Avvisa dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-125">Reject the document.</span></span>
-   <span data-ttu-id="4f7aa-126">Begära en ändring av dokumentet.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-126">Request a change to the document.</span></span>
-   <span data-ttu-id="4f7aa-127">Tilldela en annan användare dokumentet för godkännande.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-127">Assign the document to another user for approval.</span></span>

## <a name="lineitem-workflow-elements"></a><span data-ttu-id="4f7aa-128">Arbetsflödeselement för radartikel</span><span class="sxs-lookup"><span data-stu-id="4f7aa-128">Lineitem workflow elements</span></span>
<span data-ttu-id="4f7aa-129">Ett arbetsflöde kan skapas för att bearbeta antingen dokument eller radartiklarna på ett dokument.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-129">A workflow can be created to process either documents or the line items on a document.</span></span> <span data-ttu-id="4f7aa-130">Om du till exempel har skapat ett arbetsflöde för godkännande för tidrapporter.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-130">For example, you've created an approval workflow for timesheets.</span></span> <span data-ttu-id="4f7aa-131">(Du refererar till arbetsflödet som *dokumentarbetsflöde*.) Du kan lägga till ett element för *arbetsflöde för radartikel* till det dokumentarbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-131">(We will refer to this workflow as the *document workflow*.) You can add a *line-item workflow* element to that document workflow.</span></span> <span data-ttu-id="4f7aa-132">När elementet för radartikeln körs, skickas varje radartikel på dokumentet in för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-132">When the line-item element is run, each line item on the document is submitted for processing.</span></span> <span data-ttu-id="4f7aa-133">Du kan vilja att alla radartiklar bearbetas av samma radartikelarbetsflöde, eller du kanske vill att varje radartikel kan bearbetas i ett annat arbetsflöde för radartikel.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-133">You might want all the line items to be processed by the same line-item workflow, or you might want each line item to be processed by a different line-item workflow.</span></span> <span data-ttu-id="4f7aa-134">Tänk dig att en medarbetare har skickat in en tidrapport som liknar följande bild.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-134">Imagine that an employee has submitted a timesheet that resembles the following figure.</span></span> <span data-ttu-id="4f7aa-135">![Arbetsflöde med radartiklar](./media/workflow_lineitemworkflow.gif) I detta scenario kanske du vill skapa följande rarbetsflöden för radartiklar:</span><span class="sxs-lookup"><span data-stu-id="4f7aa-135">![Workflow with line items](./media/workflow_lineitemworkflow.gif) In this scenario, you might want to create the following line-item workflows:</span></span>

-   <span data-ttu-id="4f7aa-136">**Arbetsflöde för radartikel 1** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 1111.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-136">**Line-item workflow 1** – This workflow is used to process line items where the project ID is 1111.</span></span>
-   <span data-ttu-id="4f7aa-137">**Arbetsflöde för radartikel 2** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 2222.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-137">**Line-item workflow 2** – This workflow is used to process line items where the project ID is 2222.</span></span>
-   <span data-ttu-id="4f7aa-138">**Arbetsflöde för radartikel 3** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 3333.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-138">**Line-item workflow 3** – This workflow is used to process line items where the project ID is 3333.</span></span>

## <a name="flowcontrol-elements"></a><span data-ttu-id="4f7aa-139">Flödeskontrollelement</span><span class="sxs-lookup"><span data-stu-id="4f7aa-139">Flowcontrol elements</span></span>
<span data-ttu-id="4f7aa-140">Följande element låter dig designa arbetsflöden som har alternativa förgreningar eller förgreningar som körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-140">The following elements let you design workflows that have alternate branches or branches that run at the same time.</span></span>

### <a name="manual-decision"></a><span data-ttu-id="4f7aa-141">Manuellt beslut</span><span class="sxs-lookup"><span data-stu-id="4f7aa-141">Manual decision</span></span>

<span data-ttu-id="4f7aa-142">Ett *manuellt beslut* är en punkt där ett arbetsflöde delas i två förgreningar.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-142">A *manual decision* is a point where a workflow divides into two branches.</span></span> <span data-ttu-id="4f7aa-143">En användare måste ta ett beslut, och detta beslut bestämmer vilken förgrening som används för att bearbeta dokumentet som skickats in.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-143">A user must make a decision, and this decision determines which branch is used to process the document that was submitted.</span></span>

### <a name="conditional-decision"></a><span data-ttu-id="4f7aa-144">Villkorligt beslut</span><span class="sxs-lookup"><span data-stu-id="4f7aa-144">Conditional decision</span></span>

<span data-ttu-id="4f7aa-145">Ett *villkorligt beslut* är också en punkt där ett arbetsflöde delas i två förgreningar.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-145">A *conditional decision* is also a point where a workflow divides into two branches.</span></span> <span data-ttu-id="4f7aa-146">Men systemet bestämmer vilken förgrening som används för att bearbeta dokumentet som skickats in.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-146">However, the system decides which branch is used to process the document that was submitted.</span></span> <span data-ttu-id="4f7aa-147">För att fatta detta beslut utvärderar systemet dokumentet för att avgöra om det uppfyller angivna villkor.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-147">To make this decision, the system evaluates the document to determine whether it meets specified conditions.</span></span>

### <a name="parallel-activity"></a><span data-ttu-id="4f7aa-148">Parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="4f7aa-148">Parallel activity</span></span>

<span data-ttu-id="4f7aa-149">En *parallell aktivitet* är ett arbetsflödeselement som inkluderar två eller flera arbetsflödesgrenar som körs samtidigt.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-149">A *parallel activity* is a workflow element that includes two or more workflow branches that run at the same time.</span></span>

### <a name="subworkflow"></a><span data-ttu-id="4f7aa-150">Delarbetsflöde</span><span class="sxs-lookup"><span data-stu-id="4f7aa-150">Subworkflow</span></span>

<span data-ttu-id="4f7aa-151">Ett *delarbetsflöde* är ett arbetsflöde som körs i ett annat arbetsflödes sammanhang.</span><span class="sxs-lookup"><span data-stu-id="4f7aa-151">A *subworkflow* is a workflow that runs in the context of another workflow.</span></span>




