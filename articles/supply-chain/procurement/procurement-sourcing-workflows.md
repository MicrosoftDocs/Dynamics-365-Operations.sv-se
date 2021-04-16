---
title: Anskaffnings- och källarbetsflöden
description: Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen. Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.
author: kamaybac
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd9ee69e180f2ff605c4f373a95d2346ccc73c0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807954"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="a2830-104">Anskaffnings- och källarbetsflöden</span><span class="sxs-lookup"><span data-stu-id="a2830-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2830-105">Vissa organisationer kräver att inköpsrekvisitioner och inköpsorder godkänns av en annan användare än den som registrerade transaktionen.</span><span class="sxs-lookup"><span data-stu-id="a2830-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="a2830-106">Ställ in en godkännandeprocess genom att skapa ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="a2830-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="a2830-107">Ett arbetsflöde representerar en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="a2830-107">A workflow represents a business process.</span></span> <span data-ttu-id="a2830-108">Det visar ett dokuments väg genom systemet och anger vem som måste genomföra en uppgift eller godkänna ett dokument.</span><span class="sxs-lookup"><span data-stu-id="a2830-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="a2830-109">Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:</span><span class="sxs-lookup"><span data-stu-id="a2830-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="a2830-110">**Konsekventa processer** – Du kan definiera godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="a2830-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="a2830-111">Med arbetsflödessystemet blir det enklare att se till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="a2830-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="a2830-112">**Processerna blir synliga** – Du kan spåra status, historik och prestandamått för specifika arbetsflödesinstanser.</span><span class="sxs-lookup"><span data-stu-id="a2830-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="a2830-113">Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.</span><span class="sxs-lookup"><span data-stu-id="a2830-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="a2830-114">**Centraliserad arbetslista** – Användarna kan visa en centraliserad arbetslista för att visa arbetsflödesuppgifterna och godkännanden som har tilldelats dem för alla arbetsflöden som de deltar i.</span><span class="sxs-lookup"><span data-stu-id="a2830-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="a2830-115">Detta är tillgängligt på sidan Arbetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="a2830-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="a2830-116"> De typer av arbetsflöden som du kan skapa</span><span class="sxs-lookup"><span data-stu-id="a2830-116">The types of workflows that you can create</span></span>

<span data-ttu-id="a2830-117">Följande arbetsflödestyper är tillgängliga för Anskaffning och källa.</span><span class="sxs-lookup"><span data-stu-id="a2830-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="a2830-118">Typ</span><span class="sxs-lookup"><span data-stu-id="a2830-118">Type</span></span> | <span data-ttu-id="a2830-119">Använd den här typen för att</span><span class="sxs-lookup"><span data-stu-id="a2830-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="a2830-120">Granskning av inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="a2830-120">Purchase requisition review</span></span> | <span data-ttu-id="a2830-121">Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="a2830-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="a2830-122">Granskning av inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="a2830-122">Purchase requisition line review</span></span> | <span data-ttu-id="a2830-123">Skapa gransknings- och godkännandearbetsflöden för inköpsrekvisitionsrader.</span><span class="sxs-lookup"><span data-stu-id="a2830-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="a2830-124">Arbetsflöde för inköpsorder</span><span class="sxs-lookup"><span data-stu-id="a2830-124">Purchase order workflow</span></span> | <span data-ttu-id="a2830-125">Skapa granskning- och godkännandearbetsflöden för inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="a2830-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="a2830-126">Arbetsflöde för inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="a2830-126">Purchase order line workflow</span></span> | <span data-ttu-id="a2830-127">Skapa granskning- och godkännandearbetsflöden för orderrader.</span><span class="sxs-lookup"><span data-stu-id="a2830-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="a2830-128">Ansökningsarbetsflöde för leverantörstillägg</span><span class="sxs-lookup"><span data-stu-id="a2830-128">Vendor add application workflow</span></span> | <span data-ttu-id="a2830-129">Att granska och godkänna arbetsflöden för att lägga till nya leverantörer via leverantörsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="a2830-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="a2830-130">När du lägger till ett nytt arbetsflöde kan du också se följande föråldrade arbetsflöden i dialogrutan **Skapa arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="a2830-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="a2830-131">Dessa är relaterade till funktionen *bekräftelse av kvitto* som fanns i [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), men som nu är föråldrade.</span><span class="sxs-lookup"><span data-stu-id="a2830-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="a2830-132">Dessa arbetsflöden stöds för närvarande inte.</span><span class="sxs-lookup"><span data-stu-id="a2830-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="a2830-133">Meddelandearbetsflöde för leveransens förfallodatum</span><span class="sxs-lookup"><span data-stu-id="a2830-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="a2830-134">Meddelandearbetsflöde för mottagen faktura</span><span class="sxs-lookup"><span data-stu-id="a2830-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="a2830-135">Produktinleveransen godkändes inte i meddelandearbetsflödet</span><span class="sxs-lookup"><span data-stu-id="a2830-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="a2830-136">Meddelandearbetsflöde för avvisad obekräftad produktinleverans</span><span class="sxs-lookup"><span data-stu-id="a2830-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="a2830-137">Skapa ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="a2830-137">Creating a workflow</span></span>

<span data-ttu-id="a2830-138">Om du vill skapa ett arbetsflöde, gå till Anskaffning och källa &gt; Inställningar &gt; Anskaffnings- och källarbetsflöden och skapa ett nytt arbetsflöde genom att välja vilken typ av arbetsflöden som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="a2830-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="a2830-139">I arbetsflödets arbetsyta kan du dra arbetsflödeselement till designern och länka elementen till ett flöde.</span><span class="sxs-lookup"><span data-stu-id="a2830-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="a2830-140">Arbetsflödeselementen bör konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a2830-140">The workflow elements should be configured.</span></span> <span data-ttu-id="a2830-141">För arbetsflödeselement för godkännande och uppgift kan du konfigurera vilken deltagare som ska vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a2830-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="a2830-142">Typer av deltagare</span><span class="sxs-lookup"><span data-stu-id="a2830-142">Types of participants</span></span>

<span data-ttu-id="a2830-143">Du kan tilldela ett godkännandesteg till följande grupper för deltagare.</span><span class="sxs-lookup"><span data-stu-id="a2830-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="a2830-144">Användargrupp</span><span class="sxs-lookup"><span data-stu-id="a2830-144">User group</span></span> | <span data-ttu-id="a2830-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a2830-145">Description</span></span> |
|---|---|
| <span data-ttu-id="a2830-146">Deltagare</span><span class="sxs-lookup"><span data-stu-id="a2830-146">Participant</span></span> | <span data-ttu-id="a2830-147">Tilldela godkännandesteget till medlemmar i en grupp eller en roll.</span><span class="sxs-lookup"><span data-stu-id="a2830-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="a2830-148">Hierarki</span><span class="sxs-lookup"><span data-stu-id="a2830-148">Hierarchy</span></span> | <span data-ttu-id="a2830-149">Tilldela godkännandesteget till användare i en viss organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="a2830-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="a2830-150">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="a2830-150">Workflow user</span></span> | <span data-ttu-id="a2830-151">Tilldela godkännandesteget till användare i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="a2830-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="a2830-152">Kö</span><span class="sxs-lookup"><span data-stu-id="a2830-152">Queue</span></span> | <span data-ttu-id="a2830-153">Tilldela godkännandesteget till en arbetsuppgiftskö.</span><span class="sxs-lookup"><span data-stu-id="a2830-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="a2830-154">Användare</span><span class="sxs-lookup"><span data-stu-id="a2830-154">User</span></span> | <span data-ttu-id="a2830-155">Tilldela godkännandesteget till specifika användare.</span><span class="sxs-lookup"><span data-stu-id="a2830-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="a2830-156">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a2830-156">Additional resources</span></span>

- [<span data-ttu-id="a2830-157">Definiera affärsprocessarbetsflöden för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="a2830-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="a2830-158">Arbetsflöde för inköpsrekvisitioner</span><span class="sxs-lookup"><span data-stu-id="a2830-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="a2830-159">Integrera leverantörer</span><span class="sxs-lookup"><span data-stu-id="a2830-159">Onboard vendors</span></span>](vendor-onboarding.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]