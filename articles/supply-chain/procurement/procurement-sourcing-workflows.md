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
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cc995b474e86272b49629f97e1b4d4b4fb597b9d
ms.openlocfilehash: d25ca64fb6a3fa7d7898ec68568703f3de7b1595
ms.contentlocale: sv-se
ms.lasthandoff: 11/13/2018

---

# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="b16a6-104">Anskaffnings- och källarbetsflöden</span><span class="sxs-lookup"><span data-stu-id="b16a6-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b16a6-105">Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b16a6-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="b16a6-106">Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="b16a6-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="b16a6-107">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="b16a6-107">A workflow represents a business process.</span></span> <span data-ttu-id="b16a6-108">Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="b16a6-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="b16a6-109">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="b16a6-109">There are several benefits of using the workflow system in your organization:</span></span>
-   <span data-ttu-id="b16a6-110">**Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="b16a6-110">**Consistent processes**— You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="b16a6-111">Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="b16a6-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
-   <span data-ttu-id="b16a6-112">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="b16a6-112">**Process visibility**— You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="b16a6-113">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="b16a6-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
-   <span data-ttu-id="b16a6-114">**Centraliserad arbetslista** – Användarna kan visa en centraliserad arbetslista för att visa arbetsflödesuppgifterna och godkännanden som har tilldelats dem för alla arbetsflöden som de deltar i.</span><span class="sxs-lookup"><span data-stu-id="b16a6-114">**Centralized work list**— Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="b16a6-115">Detta är tillgängligt på sidan Arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b16a6-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="b16a6-116"> De typer av arbetsflöden som du kan skapa</span><span class="sxs-lookup"><span data-stu-id="b16a6-116">The types of workflows that you can create</span></span>
<span data-ttu-id="b16a6-117">Följande arbetsflödestyper är tillgängliga för Anskaffning och källa.</span><span class="sxs-lookup"><span data-stu-id="b16a6-117">The following workflow types are available for Procurement and sourcing.</span></span>

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| <span data-ttu-id="b16a6-118">**Typ**</span><span class="sxs-lookup"><span data-stu-id="b16a6-118">**Type**</span></span>                         | <span data-ttu-id="b16a6-119">**Använd den här typen för att**</span><span class="sxs-lookup"><span data-stu-id="b16a6-119">**Use this type to**</span></span>                                          |
| <span data-ttu-id="b16a6-120">Granskning av inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="b16a6-120">Purchase requisition review</span></span>      | <span data-ttu-id="b16a6-121">Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="b16a6-121">Create review and approval workflows for purchase requisitions.</span></span>            |
| <span data-ttu-id="b16a6-122">Granskning av inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="b16a6-122">Purchase requisition line review</span></span> | <span data-ttu-id="b16a6-123">Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitionsrader.</span><span class="sxs-lookup"><span data-stu-id="b16a6-123">Create review and approval workflows for purchase requisition lines.</span></span>       |
| <span data-ttu-id="b16a6-124">Arbetsflöde för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="b16a6-124">Purchase order workflow</span></span>          | <span data-ttu-id="b16a6-125">Skapa granskning- och godkännandearbetsflöden för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="b16a6-125">Create review and approval workflows for purchase orders.</span></span>     |
| <span data-ttu-id="b16a6-126">Arbetsflöde för inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="b16a6-126">Purchase order line workflow</span></span>     | <span data-ttu-id="b16a6-127">Skapa granskning- och godkännandearbetsflöden för orderrader.</span><span class="sxs-lookup"><span data-stu-id="b16a6-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="b16a6-128">Ansökningsarbetsflöde för leverantörstillägg</span><span class="sxs-lookup"><span data-stu-id="b16a6-128">Vendor add application workflow</span></span>  | <span data-ttu-id="b16a6-129">Att granska och godkänna arbetsflöden för att lägga till nya leverantörer via leverantörsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="b16a6-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

## <a name="creating-a-workflow"></a><span data-ttu-id="b16a6-130">Skapa ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b16a6-130">Creating a workflow</span></span>

<span data-ttu-id="b16a6-131">Om du vill skapa ett arbetsflöde, gå till Anskaffning och källa &gt; Inställningar &gt; Anskaffnings- och källarbetsflöden och skapa ett nytt arbetsflöde genom att välja vilken typ av arbetsflöden som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="b16a6-131">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span>  

<span data-ttu-id="b16a6-132">I arbetsflödets arbetsyta kan du dra arbetsflödeselement till designern och länka elementen till ett flöde.</span><span class="sxs-lookup"><span data-stu-id="b16a6-132">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="b16a6-133">Arbetsflödeselementen bör konfigureras.</span><span class="sxs-lookup"><span data-stu-id="b16a6-133">The workflow elements should be configured.</span></span> <span data-ttu-id="b16a6-134">För arbetsflödeselement för godkännande och uppgift kan du konfigurera vilken deltagare som ska vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b16a6-134">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="b16a6-135">Typer av deltagare</span><span class="sxs-lookup"><span data-stu-id="b16a6-135">Types of participants</span></span>

<span data-ttu-id="b16a6-136">Du kan tilldela ett godkännandesteg till följande grupper för deltagare.</span><span class="sxs-lookup"><span data-stu-id="b16a6-136">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="b16a6-137">Användargrupp</span><span class="sxs-lookup"><span data-stu-id="b16a6-137">User group</span></span>    | <span data-ttu-id="b16a6-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b16a6-138">Description</span></span>                                                               |
|---------------|---------------------------------------------------------------------------|
| <span data-ttu-id="b16a6-139">Deltagare</span><span class="sxs-lookup"><span data-stu-id="b16a6-139">Participant</span></span>   | <span data-ttu-id="b16a6-140">Tilldela godkännandesteget till medlemmar i en grupp eller en roll.</span><span class="sxs-lookup"><span data-stu-id="b16a6-140">Assign the approval step to members of a group or role.</span></span>                   |
| <span data-ttu-id="b16a6-141">Hierarki</span><span class="sxs-lookup"><span data-stu-id="b16a6-141">Hierarchy</span></span>     | <span data-ttu-id="b16a6-142">Tilldela godkännandesteget till användare i en viss organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="b16a6-142">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="b16a6-143">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="b16a6-143">Workflow user</span></span> | <span data-ttu-id="b16a6-144">Tilldela godkännandesteget till användare i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="b16a6-144">Assign the approval step to users of this workflow.</span></span>                       |
| <span data-ttu-id="b16a6-145">Kö</span><span class="sxs-lookup"><span data-stu-id="b16a6-145">Queue</span></span>         | <span data-ttu-id="b16a6-146">Tilldela godkännandesteget till en arbetsuppgiftskö.</span><span class="sxs-lookup"><span data-stu-id="b16a6-146">Assign the approval step to a work item queue.</span></span>                            |
| <span data-ttu-id="b16a6-147">Användare</span><span class="sxs-lookup"><span data-stu-id="b16a6-147">User</span></span>          | <span data-ttu-id="b16a6-148">Tilldela godkännandesteget till specifika användare.</span><span class="sxs-lookup"><span data-stu-id="b16a6-148">Assign the approval step to specific users.</span></span>                               |



## <a name="additional-resources"></a><span data-ttu-id="b16a6-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b16a6-149">Additional resources</span></span>

- [<span data-ttu-id="b16a6-150">Definiera affärsprocessarbetsflöden för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="b16a6-150">Defining business process workflows for purchase requisitions</span></span>](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

- [<span data-ttu-id="b16a6-151">Arbetsflöde för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="b16a6-151">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)

- [<span data-ttu-id="b16a6-152">Integration av leverantörer</span><span class="sxs-lookup"><span data-stu-id="b16a6-152">Onboarding vendors</span></span>](vendor-onboarding.md)


