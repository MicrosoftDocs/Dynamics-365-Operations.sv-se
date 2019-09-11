---
title: Arbetsflödessystem – översikt
description: Det här ämnet beskriver arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: a2692b9f3595ab001151f8e53a25010474bcd233
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864802"
---
# <a name="workflow-system-overview"></a><span data-ttu-id="c4248-103">Arbetsflödessystem – översikt</span><span class="sxs-lookup"><span data-stu-id="c4248-103">Workflow system overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4248-104">Det här ämnet beskriver arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c4248-104">This topic describes the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="what-is-workflow"></a><span data-ttu-id="c4248-105">Vad är ett arbetsflöde?</span><span class="sxs-lookup"><span data-stu-id="c4248-105">What is workflow?</span></span>

<span data-ttu-id="c4248-106">Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="c4248-106">The term *workflow* can be defined in two ways: as a system and as a business process.</span></span>

### <a name="workflow-is-a-system"></a><span data-ttu-id="c4248-107">Arbetsflödet som ett system</span><span class="sxs-lookup"><span data-stu-id="c4248-107">Workflow is a system</span></span>

<span data-ttu-id="c4248-108">Arbetsflödet är ett system som är installerat i Finance and Operations och som körs på Application Object Server (AOS).</span><span class="sxs-lookup"><span data-stu-id="c4248-108">Workflow is a system that is installed with Finance and Operations and runs on the Application Object Server (AOS).</span></span> <span data-ttu-id="c4248-109">Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="c4248-109">The workflow system provides functionality that you can use to create individual workflows, or business processes.</span></span>

### <a name="workflow-is-a-business-process"></a><span data-ttu-id="c4248-110">Arbetsflödet som en affärsprocess</span><span class="sxs-lookup"><span data-stu-id="c4248-110">Workflow is a business process</span></span>

<span data-ttu-id="c4248-111">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="c4248-111">A workflow represents a business process.</span></span> <span data-ttu-id="c4248-112">Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="c4248-112">It defines how a document flows, or moves, through the system by showing who must complete a task, make a decision, or approve a document.</span></span> <span data-ttu-id="c4248-113">Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="c4248-113">For example, the following illustration shows a workflow for expense reports.</span></span>

![Arbetsflöde med element som tilldelas till användare](./media/workflow_user.gif)

<span data-ttu-id="c4248-115">För att du ska få en bättre förståelse för det här arbetsflödet, anta att Sam skickar in en utgiftsrapport på 7 000 USD.</span><span class="sxs-lookup"><span data-stu-id="c4248-115">To better understand this workflow, suppose that Sam submits an expense report for USD 7,000.</span></span> <span data-ttu-id="c4248-116">I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom.</span><span class="sxs-lookup"><span data-stu-id="c4248-116">In this scenario, Ivan must review the receipts that Sam routes to him.</span></span> <span data-ttu-id="c4248-117">Sedan måste Frank och Sue godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="c4248-117">Then Frank and Sue must approve the expense report.</span></span> <span data-ttu-id="c4248-118">Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor.</span><span class="sxs-lookup"><span data-stu-id="c4248-118">Now suppose that Sam submits an expense report for USD 11,000.</span></span> <span data-ttu-id="c4248-119">I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="c4248-119">In this scenario, Ivan must review the receipts, and Frank, Sue, and Ann must approve the expense report.</span></span>

## <a name="benefits-of-using-the-workflow-system"></a><span data-ttu-id="c4248-120"> Fördelar med att använda arbetsflödessystemet</span><span class="sxs-lookup"><span data-stu-id="c4248-120">Benefits of using the workflow system</span></span>

<span data-ttu-id="c4248-121">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="c4248-121">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="c4248-122">**Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas.</span><span class="sxs-lookup"><span data-stu-id="c4248-122">**Consistent processes** – You can define how specific documents, such as purchase requisitions and expense reports, are processed.</span></span> <span data-ttu-id="c4248-123">Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="c4248-123">By using the workflow system, you ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="c4248-124">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="c4248-124">**Process visibility** – You can track the status, history, and performance metrics of workflow instances.</span></span> <span data-ttu-id="c4248-125">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="c4248-125">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="c4248-126">**Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="c4248-126">**Centralized work list** – Users can view a centralized work list that displays the workflow tasks and approvals that are assigned to them.</span></span>


## <a name="workflow-content"></a><span data-ttu-id="c4248-127">Arbetsflödesinnehåll</span><span class="sxs-lookup"><span data-stu-id="c4248-127">Workflow content</span></span>

+ [<span data-ttu-id="c4248-128">Arbetsflödesarkitektur</span><span class="sxs-lookup"><span data-stu-id="c4248-128">Workflow architecture</span></span>](workflow-system-architecture.md)
+ [<span data-ttu-id="c4248-129">Arbetsflödeselement</span><span class="sxs-lookup"><span data-stu-id="c4248-129">Workflow elements</span></span>](workflow-elements.md)
+ [<span data-ttu-id="c4248-130">Arbetsflödesåtgärder</span><span class="sxs-lookup"><span data-stu-id="c4248-130">Workflow actions</span></span>](workflow-actions.md)
+ [<span data-ttu-id="c4248-131">Skapa ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-131">Create a workflow</span></span>](create-workflow.md)
+ [<span data-ttu-id="c4248-132">Konfigurera arbetsflödesegenskaper</span><span class="sxs-lookup"><span data-stu-id="c4248-132">Configure workflow properties</span></span>](configure-workflow-properties.md)
+ [<span data-ttu-id="c4248-133">Konfigurera en manuell uppgift i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-133">Configure a manual task in a workflow</span></span>](configure-manual-task-workflow.md)
+ [<span data-ttu-id="c4248-134">Konfigurera en automatisk uppgift i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-134">Configure an automated task in a workflow</span></span>](configure-automated-task-workflow.md)
+ [<span data-ttu-id="c4248-135">Konfigurera en godkännandeprocess i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-135">Configure an approval process in a workflow</span></span>](configure-approval-process-workflow.md)
+ [<span data-ttu-id="c4248-136">Konfigurera ett godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-136">Configure an approval step in a workflow</span></span>](configure-approval-step-workflow.md)
+ [<span data-ttu-id="c4248-137">Konfigurera ett manuellt beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-137">Configure a manual decision in a workflow</span></span>](configure-manual-decision-workflow.md)
+ [<span data-ttu-id="c4248-138">Konfigurera ett villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-138">Configure a conditional decision in a workflow</span></span>](configure-conditional-decision-workflow.md)
+ [<span data-ttu-id="c4248-139">Konfigurera en parallell aktivitet i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-139">Configure a parallel activity in a workflow</span></span>](configure-parallel-activity-workflow.md)
+ [<span data-ttu-id="c4248-140">Konfigurera en parallell gren i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-140">Configure a parallel branch in a workflow</span></span>](configure-parallel-branch-workflow.md)
+ [<span data-ttu-id="c4248-141">Konfigurera ett arbetsflöde för radartiklar</span><span class="sxs-lookup"><span data-stu-id="c4248-141">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)
+ [<span data-ttu-id="c4248-142">Vanliga frågor om arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="c4248-142">Workflow FAQ</span></span>](workflow-FAQ.md)
