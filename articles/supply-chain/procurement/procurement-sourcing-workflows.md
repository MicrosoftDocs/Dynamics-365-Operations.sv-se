---
title: "Anskaffnings- och källarbetsflöden"
description: "Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 80853a06e599786e2dcaf049ac733c47dfe4d9a5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="e9a09-104">Anskaffnings- och källarbetsflöden</span><span class="sxs-lookup"><span data-stu-id="e9a09-104">Procurement and sourcing workflows</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e9a09-105">Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen.</span><span class="sxs-lookup"><span data-stu-id="e9a09-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="e9a09-106">Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="e9a09-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="e9a09-107">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="e9a09-107">A workflow represents a business process.</span></span> <span data-ttu-id="e9a09-108">Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="e9a09-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="e9a09-109">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="e9a09-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="e9a09-110">**Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="e9a09-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="e9a09-111">Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="e9a09-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="e9a09-112">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="e9a09-112">**Process visibility**— You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="e9a09-113">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="e9a09-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="e9a09-114">**Centraliserad arbetslista** – Användarna kan visa en centraliserad arbetslista för att visa arbetsflödesuppgifterna och godkännanden som har tilldelats dem för alla arbetsflöden som de deltar i.</span><span class="sxs-lookup"><span data-stu-id="e9a09-114">**Centralized work list**— Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="e9a09-115">Detta är tillgängligt på sidan Arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="e9a09-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="e9a09-116"> De typer av arbetsflöden som du kan skapa</span><span class="sxs-lookup"><span data-stu-id="e9a09-116">The types of workflows that you can create</span></span>
<span data-ttu-id="e9a09-117">Följande arbetsflödestyper är tillgängliga för Anskaffning och källa.</span><span class="sxs-lookup"><span data-stu-id="e9a09-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="e9a09-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="e9a09-118">**Type**</span></span>                         | <span data-ttu-id="e9a09-119">**Använd den här typen för att**</span><span class="sxs-lookup"><span data-stu-id="e9a09-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="e9a09-120">Granskning av inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="e9a09-120">Purchase requisition review</span></span>      | <span data-ttu-id="e9a09-121">Skapa granskningsarbetsflöden för inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="e9a09-121">Create review workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="e9a09-122">Granskning av inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="e9a09-122">Purchase requisition line review</span></span> | <span data-ttu-id="e9a09-123">Skapa granskningsarbetsflöden för inköpsrekvisitionsrader.</span><span class="sxs-lookup"><span data-stu-id="e9a09-123">Create review workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="e9a09-124">Arbetsflöde för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="e9a09-124">Purchase order workflow</span></span>          | <span data-ttu-id="e9a09-125">Skapa granskning- och godkännandearbetsflöden för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="e9a09-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="e9a09-126">Arbetsflöde för inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="e9a09-126">Purchase order line workflow</span></span>     | <span data-ttu-id="e9a09-127">Skapa granskning- och godkännandearbetsflöden för orderrader.</span><span class="sxs-lookup"><span data-stu-id="e9a09-127">Create review and approve workflows for purchase order lines.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="e9a09-128">Skapa ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="e9a09-128">Creating a workflow</span></span>
<span data-ttu-id="e9a09-129">Om du vill skapa ett arbetsflöde, gå till Anskaffning och källa &gt; Inställningar &gt; Anskaffnings- och källarbetsflöden och skapa ett nytt arbetsflöde genom att välja vilken typ av arbetsflöden som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="e9a09-129">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="e9a09-130">I arbetsflödets arbetsyta kan du dra arbetsflödeselement till designern och länka elementen till ett flöde.</span><span class="sxs-lookup"><span data-stu-id="e9a09-130">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="e9a09-131">Arbetsflödeselementen bör konfigureras.</span><span class="sxs-lookup"><span data-stu-id="e9a09-131">The workflow elements should be configured.</span></span> <span data-ttu-id="e9a09-132">För arbetsflödeselement för godkännande och uppgift kan du konfigurera vilken deltagare som ska vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e9a09-132">For approval and task workflow elements you can configure which participant should take action.</span></span>
<span data-ttu-id="e9a09-133">Typer av deltagare</span><span class="sxs-lookup"><span data-stu-id="e9a09-133">Types of participants</span></span>
----------------------

<span data-ttu-id="e9a09-134">Du kan tilldela ett godkännandesteg till följande grupper för deltagare.</span><span class="sxs-lookup"><span data-stu-id="e9a09-134">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="e9a09-135">Användargrupp</span><span class="sxs-lookup"><span data-stu-id="e9a09-135">User group</span></span>    | <span data-ttu-id="e9a09-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e9a09-136">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="e9a09-137">Deltagare</span><span class="sxs-lookup"><span data-stu-id="e9a09-137">Participant</span></span>   | <span data-ttu-id="e9a09-138">Tilldela godkännandesteget till medlemmar i en grupp eller en roll.</span><span class="sxs-lookup"><span data-stu-id="e9a09-138">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="e9a09-139">Hierarki</span><span class="sxs-lookup"><span data-stu-id="e9a09-139">Hierarchy</span></span>     | <span data-ttu-id="e9a09-140">Tilldela godkännandesteget till användare i en viss organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="e9a09-140">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="e9a09-141">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="e9a09-141">Workflow user</span></span> | <span data-ttu-id="e9a09-142">Tilldela godkännandesteget till användare i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="e9a09-142">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="e9a09-143">Kö</span><span class="sxs-lookup"><span data-stu-id="e9a09-143">Queue</span></span>         | <span data-ttu-id="e9a09-144">Tilldela godkännandesteget till en arbetsuppgiftskö.</span><span class="sxs-lookup"><span data-stu-id="e9a09-144">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="e9a09-145">Användare</span><span class="sxs-lookup"><span data-stu-id="e9a09-145">User</span></span>          | <span data-ttu-id="e9a09-146">Tilldela godkännandesteget till specifika användare.</span><span class="sxs-lookup"><span data-stu-id="e9a09-146">Assign the approval step to specific users.</span></span>                               |



<a name="see-also"></a><span data-ttu-id="e9a09-147">Se även</span><span class="sxs-lookup"><span data-stu-id="e9a09-147">See also</span></span>
--------

[<span data-ttu-id="e9a09-148">Definiera affärsprocessarbetsflöden för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="e9a09-148">Defining business process workflows for purchase requisitions</span></span>](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[<span data-ttu-id="e9a09-149">Arbetsflöde för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="e9a09-149">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)




