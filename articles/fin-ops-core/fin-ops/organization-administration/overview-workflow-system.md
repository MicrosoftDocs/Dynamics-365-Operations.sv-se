---
title: Arbetsflödessystem – översikt
description: Det här ämnet beskriver arbetsflödessystemet.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eef77a5d81d12ec92eea86b1dd9902d9e3d80b33
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812373"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="2f48c-103">Arbetsflödessystem – översikt</span><span class="sxs-lookup"><span data-stu-id="2f48c-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f48c-104">Det här ämnet beskriver arbetsflödessystemet.</span><span class="sxs-lookup"><span data-stu-id="2f48c-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="2f48c-105">Vad är ett arbetsflöde?</span><span class="sxs-lookup"><span data-stu-id="2f48c-105">What is workflow?</span></span>

<span data-ttu-id="2f48c-106">Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="2f48c-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="2f48c-107">Arbetsflödet som ett system</span><span class="sxs-lookup"><span data-stu-id="2f48c-107">Workflow is a system</span></span>

<span data-ttu-id="2f48c-108">Arbetsflöde är ett system som körs på programobjektservern (AOS).</span><span class="sxs-lookup"><span data-stu-id="2f48c-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="2f48c-109">Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="2f48c-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="2f48c-110">Arbetsflödet som en affärsprocess</span><span class="sxs-lookup"><span data-stu-id="2f48c-110">Workflow is a business process</span></span>

<span data-ttu-id="2f48c-111">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="2f48c-111">A workflow represents a business process.</span></span> <span data-ttu-id="2f48c-112">Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="2f48c-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="2f48c-113">Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="2f48c-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Arbetsflöde med element som tilldelas till användare](./media/workflow_user.gif)

<span data-ttu-id="2f48c-115">För att du ska få en bättre förståelse för det här arbetsflödet, anta att Sam skickar in en utgiftsrapport på 7 000 USD.</span><span class="sxs-lookup"><span data-stu-id="2f48c-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="2f48c-116">I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom.</span><span class="sxs-lookup"><span data-stu-id="2f48c-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="2f48c-117">Sedan måste Frank och Sue godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="2f48c-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="2f48c-118">Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor.</span><span class="sxs-lookup"><span data-stu-id="2f48c-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="2f48c-119">I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="2f48c-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="2f48c-120"> Fördelar med att använda arbetsflödessystemet</span><span class="sxs-lookup"><span data-stu-id="2f48c-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="2f48c-121">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="2f48c-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="2f48c-122">**Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas.</span><span class="sxs-lookup"><span data-stu-id="2f48c-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="2f48c-123">Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="2f48c-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="2f48c-124">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="2f48c-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="2f48c-125">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="2f48c-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="2f48c-126">**Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="2f48c-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="2f48c-127">Arbetsflödesinnehåll</span><span class="sxs-lookup"><span data-stu-id="2f48c-127">Workflow content</span></span>

+ [<span data-ttu-id="2f48c-128">Arbetsflödessystemets arkitektur</span><span class="sxs-lookup"><span data-stu-id="2f48c-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="2f48c-129">Arbetsflödeselement</span><span class="sxs-lookup"><span data-stu-id="2f48c-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="2f48c-130">Åtgärder i godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="2f48c-131">Skapa arbetsflöden – översikt</span><span class="sxs-lookup"><span data-stu-id="2f48c-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="2f48c-132">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="2f48c-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="2f48c-133">Konfigurera manuella uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="2f48c-134">Konfigurera automatiska uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="2f48c-135">Konfigurera godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="2f48c-136">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="2f48c-137">Konfigurera manuella beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="2f48c-138">Konfigurera villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="2f48c-139">Konfigurera parallella aktiviteter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="2f48c-140">Konfigurera parallella grenar i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="2f48c-141">Konfigurera arbetsflöden för radartiklar</span><span class="sxs-lookup"><span data-stu-id="2f48c-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="2f48c-142">Vanliga frågor om arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="2f48c-142">Workflow FAQ</span></span>](workflow-FAQ.md)
