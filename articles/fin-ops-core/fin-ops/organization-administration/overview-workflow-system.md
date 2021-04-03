---
title: Arbetsflödessystem – översikt
description: Det här ämnet beskriver arbetsflödessystemet.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd8fba1376dc5e3dbfea888ca5ff5fdeb608fc9d
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560711"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="b6a5f-103">Arbetsflödessystem – översikt</span><span class="sxs-lookup"><span data-stu-id="b6a5f-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b6a5f-104">Det här ämnet beskriver arbetsflödessystemet.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-104">This topic describes the workflow system.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="b6a5f-105">Vad är ett arbetsflöde?</span><span class="sxs-lookup"><span data-stu-id="b6a5f-105">What is workflow?</span></span>

<span data-ttu-id="b6a5f-106">Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="b6a5f-107">Arbetsflödet som ett system</span><span class="sxs-lookup"><span data-stu-id="b6a5f-107">Workflow is a system</span></span>

<span data-ttu-id="b6a5f-108">Arbetsflöde är ett system som körs på programobjektservern (AOS).</span><span class="sxs-lookup"><span data-stu-id="b6a5f-108">Workflow is a system that runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="b6a5f-109">Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="b6a5f-110">Arbetsflödet som en affärsprocess</span><span class="sxs-lookup"><span data-stu-id="b6a5f-110">Workflow is a business process</span></span>

<span data-ttu-id="b6a5f-111">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-111">A workflow represents a business process.</span></span> <span data-ttu-id="b6a5f-112">Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="b6a5f-113">Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Arbetsflöde med element som tilldelas till användare](./media/workflow_user.gif)

<span data-ttu-id="b6a5f-115">För att du ska få en bättre förståelse för det här arbetsflödet, anta att Sam skickar in en utgiftsrapport på 7 000 USD.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="b6a5f-116">I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="b6a5f-117">Sedan måste Frank och Sue godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="b6a5f-118">Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="b6a5f-119">I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="b6a5f-120"> Fördelar med att använda arbetsflödessystemet</span><span class="sxs-lookup"><span data-stu-id="b6a5f-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="b6a5f-121">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="b6a5f-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="b6a5f-122">**Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="b6a5f-123">Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="b6a5f-124">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="b6a5f-125">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="b6a5f-126">**Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="b6a5f-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="b6a5f-127">Arbetsflödesinnehåll</span><span class="sxs-lookup"><span data-stu-id="b6a5f-127">Workflow content</span></span>

+ [<span data-ttu-id="b6a5f-128">Arbetsflödessystemets arkitektur</span><span class="sxs-lookup"><span data-stu-id="b6a5f-128">Workflow system architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="b6a5f-129">Arbetsflödeselement</span><span class="sxs-lookup"><span data-stu-id="b6a5f-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="b6a5f-130">Åtgärder i godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-130">Actions in workflow approval processes</span></span>](workflow-actions.md)
+ [<span data-ttu-id="b6a5f-131">Skapa arbetsflöden – översikt</span><span class="sxs-lookup"><span data-stu-id="b6a5f-131">Create workflows overview</span></span>](create-workflow.md)
+ [<span data-ttu-id="b6a5f-132">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="b6a5f-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="b6a5f-133">Konfigurera manuella uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-133">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="b6a5f-134">Konfigurera automatiska uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-134">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="b6a5f-135">Konfigurera godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-135">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="b6a5f-136">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-136">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="b6a5f-137">Konfigurera manuella beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-137">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="b6a5f-138">Konfigurera villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-138">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="b6a5f-139">Konfigurera parallella aktiviteter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-139">Configure parallel activities in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="b6a5f-140">Konfigurera parallella grenar i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-140">Configure parallel branches in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="b6a5f-141">Konfigurera arbetsflöden för radartiklar</span><span class="sxs-lookup"><span data-stu-id="b6a5f-141">Configure line-item workflows</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="b6a5f-142">Vanliga frågor om arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b6a5f-142">Workflow FAQ</span></span>](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]