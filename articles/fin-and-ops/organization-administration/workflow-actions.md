---
title: "Åtgärder i godkännandeprocesser i ett arbetsflöde"
description: "Det här avsnittet innehåller en beskrivning av åtgärder som alla deltagare i en arbetsflödesgodkännandeprocess kan utföra."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3ee5334c87b2b0acae2afa6882feca63e3b9cc8e
ms.openlocfilehash: 829ee16b8fd72a0808a657419524487d9c1b3123
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2018

---

# <a name="actions-in-workflow-approval-processes"></a><span data-ttu-id="21084-103">Åtgärder i godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="21084-103">Actions in workflow approval processes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21084-104">Det här avsnittet innehåller en beskrivning av åtgärder som alla deltagare i en arbetsflödesgodkännandeprocess kan utföra.</span><span class="sxs-lookup"><span data-stu-id="21084-104">This article explains the actions that each participant in a workflow approval process can take.</span></span>

<span data-ttu-id="21084-105">Ett arbetsflöde kan omfatta flera grupper med personer: upphovsmannen, de som tilldelats uppgifter, beslutsfattare och godkännare.</span><span class="sxs-lookup"><span data-stu-id="21084-105">A workflow can involve several groups of people: the originator, task assignees, decision makers, and approvers.</span></span> <span data-ttu-id="21084-106">I följande arbetsflöde för utgiftsrapporter är Sam upphovsmannen, medlemmarna i kön har tilldelats uppgifter, John är beslutsfattare och Frank, Sue och Ann är godkännare.</span><span class="sxs-lookup"><span data-stu-id="21084-106">For example, in the following expense report workflow, Sam is the originator, the members of the queue are task assignees, John is a decision maker, and Frank, Sue, and Ann are approvers.</span></span>

<span data-ttu-id="21084-107">[![Arbetsflöde\_MedManuelltBeslut](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)</span><span class="sxs-lookup"><span data-stu-id="21084-107">[![Workflow\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)</span></span>

<span data-ttu-id="21084-108">Följande avsnitt förklarar de arbetsflödesåtgärder som respektive grupp kan utföra.</span><span class="sxs-lookup"><span data-stu-id="21084-108">The following sections explain the workflow actions that each group can perform.</span></span>

## <a name="actions-that-an-originator-can-perform"></a><span data-ttu-id="21084-109">Åtgärder som en upphovsman kan utföra</span><span class="sxs-lookup"><span data-stu-id="21084-109">Actions that an originator can perform</span></span>

<span data-ttu-id="21084-110">Upphovsmannen startar en arbetsflödesinstans genom att skicka ett dokument för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="21084-110">The originator starts a workflow instance by submitting a document for processing.</span></span> <span data-ttu-id="21084-111">Till exempel måste Sam klicka på **Skicka** på sidan **Utgiftsrapport** för att skicka in sin utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="21084-111">For example, Sam must click the **Submit** button on the **Expense report** page to submit his expense report.</span></span>

## <a name="actions-that-a-task-assignee-can-perform"></a><span data-ttu-id="21084-112">Åtgärder som någon som tilldelats en uppgift kan utföra</span><span class="sxs-lookup"><span data-stu-id="21084-112">Actions that a task assignee can perform</span></span>

<span data-ttu-id="21084-113">En uppgift kan tilldelas flera kontakter eller en arbetsuppgiftskö som övervakas av flera personer.</span><span class="sxs-lookup"><span data-stu-id="21084-113">A task can be assigned to multiple people or to a work item queue that is monitored by several people.</span></span> <span data-ttu-id="21084-114">Det är dock endast en person som kan genomföra en uppgift.</span><span class="sxs-lookup"><span data-stu-id="21084-114">However, only one person can complete a task.</span></span> <span data-ttu-id="21084-115">Till exempel har Sam skickat en utgiftsrapport och lämnat sina kvitton till organisationens utgiftsrapportavdelning för granskning.</span><span class="sxs-lookup"><span data-stu-id="21084-115">For example, Sam has submitted an expense report and has routed his receipts to his organization's Expense Reports department for review.</span></span>

<span data-ttu-id="21084-116">Medlemmarna i utgiftsrapportavdelningen på Adventure Works övervakar kön.</span><span class="sxs-lookup"><span data-stu-id="21084-116">The members of the Adventure Works Expense Reports department monitor the queue.</span></span> <span data-ttu-id="21084-117">Julie, en medlem på avdelningen, har accepterat uppgiften för granskning av Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-117">Julie, a member of that department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-118">Hon kan nu utföra någon av följande åtgärder: slutföra, avvisa, delegera, begära ändring, omtilldela eller frisläppa.</span><span class="sxs-lookup"><span data-stu-id="21084-118">She can now perform one of the following actions: complete, reject, delegate, request change, reassign, or release.</span></span>

> [!NOTE]
> <span data-ttu-id="21084-119">Vilka åtgärder som står till buds varierar beroende på hur uppgiften har utformats av programutvecklaren.</span><span class="sxs-lookup"><span data-stu-id="21084-119">The actions that are available vary, depending on how the software developer designed the task.</span></span>

### <a name="complete"></a><span data-ttu-id="21084-120">Slutföra</span><span class="sxs-lookup"><span data-stu-id="21084-120">Complete</span></span>

<span data-ttu-id="21084-121">När en användare slutför en uppgift tilldelas dokumentet som skickades för bearbetning till nästa användare i arbetsflödet om det finns en nästa användare.</span><span class="sxs-lookup"><span data-stu-id="21084-121">When a user completes a task, the document that was submitted for processing is assigned to the next user in the workflow, if there is a next user.</span></span> <span data-ttu-id="21084-122">Om ingen ytterligare bearbetning krävs avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-122">If no additional processing is required, the workflow process ends.</span></span>

<span data-ttu-id="21084-123">Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-123">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-124">När Julie slutför sin granskning tilldelas dokumentet till John.</span><span class="sxs-lookup"><span data-stu-id="21084-124">After Julie completes her review, the document is assigned to John.</span></span>

### <a name="reject"></a><span data-ttu-id="21084-125">Avvisa</span><span class="sxs-lookup"><span data-stu-id="21084-125">Reject</span></span>

<span data-ttu-id="21084-126">När en användare avvisar ett dokument avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-126">When a user rejects a document, the workflow process ends.</span></span>

<span data-ttu-id="21084-127">Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-127">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-128">Om Julie avvisar utgiftsrapporten avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-128">If Julie rejects the expense report, the workflow process ends.</span></span>

<span data-ttu-id="21084-129">Sedan kan Sam skicka utgiftsrapporten på nytt.</span><span class="sxs-lookup"><span data-stu-id="21084-129">Sam can then resubmit the expense report.</span></span> <span data-ttu-id="21084-130">Han kan göra ändringar först eller skicka om den ursprungliga versionen.</span><span class="sxs-lookup"><span data-stu-id="21084-130">He can make changes first, or he can resubmit the original version.</span></span> <span data-ttu-id="21084-131">Om Sam skickar om utgiftsrapporen startar arbetsflödesprocessen vid uppgiften för manuell granskning.</span><span class="sxs-lookup"><span data-stu-id="21084-131">If Sam resubmits the expense report, the workflow process starts at the manual review task.</span></span>

### <a name="delegate"></a><span data-ttu-id="21084-132">Delegera</span><span class="sxs-lookup"><span data-stu-id="21084-132">Delegate</span></span>

<span data-ttu-id="21084-133">När en användare delegerar en uppgift tilldelas den en annan användare.</span><span class="sxs-lookup"><span data-stu-id="21084-133">When a user delegates a task, the task is assigned to another user.</span></span>

<span data-ttu-id="21084-134">Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-134">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-135">Julie delegerar den här uppgiften till Tim, som är hennes medhjälpare.</span><span class="sxs-lookup"><span data-stu-id="21084-135">Julie delegates this task to Tim, who is her assistant.</span></span>

<span data-ttu-id="21084-136">Tim agerar sedan på uppdrag av Julie.</span><span class="sxs-lookup"><span data-stu-id="21084-136">Tim then acts on behalf of Julie.</span></span> <span data-ttu-id="21084-137">Därför, när Tim slutar sin granskning, tilldelas utgiftsrapporten till John, som om Julie hade slutfört uppgiften.</span><span class="sxs-lookup"><span data-stu-id="21084-137">Therefore, when Tim completes his review, the expense report is assigned to John, just as if Julie had completed the task.</span></span>

### <a name="request-change"></a><span data-ttu-id="21084-138">Begär ändring</span><span class="sxs-lookup"><span data-stu-id="21084-138">Request change</span></span>

<span data-ttu-id="21084-139">När en användare begär en ändring av ett dokument som har skickats, skickas dokumentet tillbaka till upphovsmannen.</span><span class="sxs-lookup"><span data-stu-id="21084-139">When a user requests a change to a document that was submitted, the document is sent back to the originator.</span></span>

<span data-ttu-id="21084-140">Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-140">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-141">Julie upptäcker några fel i utgiftsrapporten och begär ändringar.</span><span class="sxs-lookup"><span data-stu-id="21084-141">Julie notices some errors on the expense report and requests changes.</span></span> <span data-ttu-id="21084-142">Utgiftsrapporten skickas tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="21084-142">The expense report is sent back to Sam.</span></span>

<span data-ttu-id="21084-143">Sam kan skicka utgiftsrapporten på nytt.</span><span class="sxs-lookup"><span data-stu-id="21084-143">Sam can resubmit the expense report.</span></span> <span data-ttu-id="21084-144">Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen.</span><span class="sxs-lookup"><span data-stu-id="21084-144">He can make the requested changes first, or he can resubmit the original version.</span></span> <span data-ttu-id="21084-145">Om Sam skickar om utgiftsrapporten måste en medlem i arbetsuppgiftskön granska utgiftsrapporten och kvittona igen.</span><span class="sxs-lookup"><span data-stu-id="21084-145">If Sam resubmits the expense report, a member of the work item queue must review the expense report and the receipts again.</span></span>

### <a name="reassign"></a><span data-ttu-id="21084-146">Tilldela om</span><span class="sxs-lookup"><span data-stu-id="21084-146">Reassign</span></span>

<span data-ttu-id="21084-147">Medlemmarna i en arbetsuppgiftskö kan tilldela om dokument som finns i kön till en annan kö.</span><span class="sxs-lookup"><span data-stu-id="21084-147">The members of a work item queue can reassign documents that are in that queue to another queue.</span></span>

<span data-ttu-id="21084-148">Exempelvis övervakar Julie, som arbetar på utgiftsrapportsavdelningen på Adventure Works, kön.</span><span class="sxs-lookup"><span data-stu-id="21084-148">For example, Julie, a member of the Adventure Works Expense Reports department, is monitoring the queue.</span></span> <span data-ttu-id="21084-149">För att balansera arbetsbelastningen kan hon tilldela om utgiftsrapporten och de kvitton som ingår i den till en annan kö.</span><span class="sxs-lookup"><span data-stu-id="21084-149">To help balance the workload, she can reassign the expense report, and the receipts that are included with it, to another queue.</span></span>

### <a name="release"></a><span data-ttu-id="21084-150">Frisläpp</span><span class="sxs-lookup"><span data-stu-id="21084-150">Release</span></span>

<span data-ttu-id="21084-151">Ibland kan en medlem av en arbetsuppgiftskö acceptera en uppgift, men sedan bestämma sig för att inte genomföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="21084-151">Occasionally, a member of a work item queue might accept a task, but then decide that he or she can't complete the task.</span></span> <span data-ttu-id="21084-152">I det här fallet kan personen som accepterade uppgiften frisläppa dokumentet tillbaka till arbetsuppgiftskön.</span><span class="sxs-lookup"><span data-stu-id="21084-152">In this case, the person who accepted the task can release the document back to the work item queue.</span></span>

<span data-ttu-id="21084-153">Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton.</span><span class="sxs-lookup"><span data-stu-id="21084-153">For example, Julie, a member of the Adventure Works Expense Reports department, has accepted the task of reviewing Sam's expense report and receipts.</span></span> <span data-ttu-id="21084-154">Om Julie väljer att hon inte kan genomföra uppgiften, kan hon frisläppa dokumentet.</span><span class="sxs-lookup"><span data-stu-id="21084-154">If Julie decides that she can't complete the task, she can release the document.</span></span> <span data-ttu-id="21084-155">Utgiftsrapporten returneras till kön, så att andra medlemmar på utgiftsrapportsavdelningen på Adventure Works kan slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="21084-155">The expense report is returned to the queue, so that other members of the Adventure Works Expense Reports department can complete the task.</span></span>

## <a name="actions-that-a-decision-maker-can-perform"></a><span data-ttu-id="21084-156">Åtgärder som en beslutsfattare kan utföra</span><span class="sxs-lookup"><span data-stu-id="21084-156">Actions that a decision maker can perform</span></span>

<span data-ttu-id="21084-157">Vanligtvis tilldelas ett dokument till en beslutsfattare eftersom det finns en fråga som beslutsfattaren måste besvara.</span><span class="sxs-lookup"><span data-stu-id="21084-157">Typically, a document is assigned to a decision maker, because there is a question that the decision maker must answer.</span></span> <span data-ttu-id="21084-158">Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="21084-158">The answer to the question is typically **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="21084-159">Om beslutsfattaren inte väljer något av dessa alternativ kan han eller hon delegera beslutet.</span><span class="sxs-lookup"><span data-stu-id="21084-159">If the decision maker doesn't select one of those choices, he or she can delegate the decision.</span></span>

### <a name="choice-1-or-choice-2"></a><span data-ttu-id="21084-160">\[Alternativ 1\] eller \[Alternativ 2\]</span><span class="sxs-lookup"><span data-stu-id="21084-160">\[Choice 1\] or \[Choice 2\]</span></span>

<span data-ttu-id="21084-161">En beslutsfattare måste besvara en fråga som är relaterad till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="21084-161">A decision maker must answer a question that is related to the document.</span></span> <span data-ttu-id="21084-162">Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**.</span><span class="sxs-lookup"><span data-stu-id="21084-162">The answer to the question is typically **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="21084-163">Svaret som beslutsfattaren väljer avgör arbetsflödesförgreningen som används för att bearbeta dokumentet.</span><span class="sxs-lookup"><span data-stu-id="21084-163">The answer that the decision maker selects determines the workflow branch that is used to process the document.</span></span>

<span data-ttu-id="21084-164">Till exempel tilldelas Sams utgiftsrapport till John.</span><span class="sxs-lookup"><span data-stu-id="21084-164">For example, Sam's expense report is assigned to John.</span></span> <span data-ttu-id="21084-165">John måste bestämma om informationen i dokumentet kräver ett samtal till Sams chef.</span><span class="sxs-lookup"><span data-stu-id="21084-165">John must decide whether the information in the document requires a call to Sam's manager.</span></span> <span data-ttu-id="21084-166">Om John beslutar att ett samtal krävs tilldelas utgiftsrapporten till Aretha, som sedan måste ringa Sams chef.</span><span class="sxs-lookup"><span data-stu-id="21084-166">If John decides that a call is required, the expense report is assigned to Aretha, who must then call Sam's manager.</span></span> <span data-ttu-id="21084-167">Om John anser att ett samtal inte krävs tilldelas utgiftsrapporten till Frank för godkännande.</span><span class="sxs-lookup"><span data-stu-id="21084-167">If John decides that a call isn't required, the expense report is assigned to Frank for approval.</span></span>

### <a name="delegate"></a><span data-ttu-id="21084-168">Delegera</span><span class="sxs-lookup"><span data-stu-id="21084-168">Delegate</span></span>

<span data-ttu-id="21084-169">När en beslutsfattare delegerar ett beslut tilldelas dokumentet till en annan användare som måste fatta beslutet.</span><span class="sxs-lookup"><span data-stu-id="21084-169">When a decision maker delegates a decision, the document is assigned to another user who must make the decision.</span></span>

<span data-ttu-id="21084-170">Till exempel tilldelas Sams utgiftsrapport till John.</span><span class="sxs-lookup"><span data-stu-id="21084-170">For example, Sam's expense report is assigned to John.</span></span> <span data-ttu-id="21084-171">John delegerar beslutet till Maria, som är hans assistent.</span><span class="sxs-lookup"><span data-stu-id="21084-171">John delegates the decision to Maria, who is his assistant.</span></span>

<span data-ttu-id="21084-172">Maria agerar sedan på uppdrag av John.</span><span class="sxs-lookup"><span data-stu-id="21084-172">Maria then acts on behalf of John.</span></span> <span data-ttu-id="21084-173">Om Maria beslutar att ett samtal till Sams chef krävs tilldelas utgiftsrapporten till Aretha, som måste ringa Sams chef.</span><span class="sxs-lookup"><span data-stu-id="21084-173">If Maria decides that a call to Sam's manager is required, the expense report is assigned to Aretha, who must then call Sam's manager.</span></span> <span data-ttu-id="21084-174">Om Maria anser att ett samtal inte krävs tilldelas utgiftsrapporten till Frank för godkännande.</span><span class="sxs-lookup"><span data-stu-id="21084-174">If Maria decides that a call isn't required, the expense report is assigned to Frank for approval.</span></span>

## <a name="actions-that-an-approver-can-perform"></a><span data-ttu-id="21084-175">Åtgärder som en godkännare kan utföra</span><span class="sxs-lookup"><span data-stu-id="21084-175">Actions that an approver can perform</span></span>

<span data-ttu-id="21084-176">När ett dokument tilldelas en godkännare, kan denne vidta någon av följande åtgärder: godkänna, avvisa, delegera eller begära ändringar.</span><span class="sxs-lookup"><span data-stu-id="21084-176">When a document is assigned to an approver, the approver can perform one of the following actions: approve, reject, delegate, or request change.</span></span>

### <a name="approve"></a><span data-ttu-id="21084-177">Godkänna</span><span class="sxs-lookup"><span data-stu-id="21084-177">Approve</span></span>

<span data-ttu-id="21084-178">När en godkännare godkänner ett dokument, tilldelas det nästa användare i arbetsflödet, om det finns en nästa användare.</span><span class="sxs-lookup"><span data-stu-id="21084-178">When an approver approves a document, the document is assigned to the next user in the workflow, if there is a next user.</span></span> <span data-ttu-id="21084-179">Om ingen ytterligare bearbetning krävs avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-179">If no additional processing is required, the workflow process ends.</span></span>

<span data-ttu-id="21084-180">Till exempel har Sam skickat en utgiftsrapport på 6 000 USD och detta dokument har tilldelats till Frank.</span><span class="sxs-lookup"><span data-stu-id="21084-180">For example, Sam has submitted an expense report for USD 6,000, and this document is assigned to Frank.</span></span> <span data-ttu-id="21084-181">Om Frank godkänner dokumentet skickas det vidare till Sue för godkännande.</span><span class="sxs-lookup"><span data-stu-id="21084-181">When Frank approves the document, it's assigned to Sue for approval.</span></span> <span data-ttu-id="21084-182">När Sue har godkänt utgiftsrapporten avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-182">When Sue approves the expense report, the workflow process ends.</span></span>

### <a name="reject"></a><span data-ttu-id="21084-183">Avvisa</span><span class="sxs-lookup"><span data-stu-id="21084-183">Reject</span></span>

<span data-ttu-id="21084-184">När en godkännare avvisar ett dokument, avslutas bearbetningen av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="21084-184">When an approver rejects a document, the workflow process ends.</span></span>

<span data-ttu-id="21084-185">Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Sue.</span><span class="sxs-lookup"><span data-stu-id="21084-185">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Sue.</span></span> <span data-ttu-id="21084-186">Om Sue avslår utgiftsrapporten avslutas arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-186">If Sue rejects the expense report, the workflow process ends.</span></span>

<span data-ttu-id="21084-187">Sam kan skicka utgiftsrapporten på nytt.</span><span class="sxs-lookup"><span data-stu-id="21084-187">Sam can resubmit the expense report.</span></span> <span data-ttu-id="21084-188">Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen av utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="21084-188">He can make changes first, or he can resubmit the original version of the expense report.</span></span> <span data-ttu-id="21084-189">Om Sam skickar om utgiftsrapporten startar arbetsflödesprocessen vid godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-189">If Sam resubmits the expense report, the workflow process starts at the approval process.</span></span>

### <a name="delegate"></a><span data-ttu-id="21084-190">Delegera</span><span class="sxs-lookup"><span data-stu-id="21084-190">Delegate</span></span>

<span data-ttu-id="21084-191">När en godkännare delegerar ett dokument, tilldelas dokumentet en annan användare för godkännande.</span><span class="sxs-lookup"><span data-stu-id="21084-191">When an approver delegates a document, the document is assigned to another user for approval.</span></span>

<span data-ttu-id="21084-192">Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Frank.</span><span class="sxs-lookup"><span data-stu-id="21084-192">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Frank.</span></span> <span data-ttu-id="21084-193">Frank delegerar utgiftsrapporten till Ann.</span><span class="sxs-lookup"><span data-stu-id="21084-193">Frank delegates the expense report to Ann.</span></span>

<span data-ttu-id="21084-194">Ann agerar då i Franks ställe.</span><span class="sxs-lookup"><span data-stu-id="21084-194">Ann then acts on behalf of Frank.</span></span> <span data-ttu-id="21084-195">Om Ann godkänner dokumentet tilldelas det till Sue för godkännande, precis som om Frank hade godkänt det.</span><span class="sxs-lookup"><span data-stu-id="21084-195">Therefore, when Ann approves the document, it's assigned to Sue for approval, just as if Frank had approved it.</span></span> <span data-ttu-id="21084-196">Så snart Sue har godkänt dokumentet skickas det vidare till Ann för godkännande.</span><span class="sxs-lookup"><span data-stu-id="21084-196">After Sue approves the document, it's sent to Ann for approval.</span></span>

### <a name="request-change"></a><span data-ttu-id="21084-197">Begär ändring</span><span class="sxs-lookup"><span data-stu-id="21084-197">Request change</span></span>

<span data-ttu-id="21084-198">När en godkännare begär en ändring av ett dokument, skickas det tillbaka till upphovsmannen.</span><span class="sxs-lookup"><span data-stu-id="21084-198">When an approver requests a change to a document, the document is sent back to the originator.</span></span>

<span data-ttu-id="21084-199">Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Sue.</span><span class="sxs-lookup"><span data-stu-id="21084-199">For example, Sam has submitted an expense report for USD 12,000, and this document is assigned to Sue.</span></span> <span data-ttu-id="21084-200">Om Sue begär ändringar skickas utgiftsrapporten tillbaka till Sam.</span><span class="sxs-lookup"><span data-stu-id="21084-200">If Sue requests a change, the expense report is sent back to Sam.</span></span>

<span data-ttu-id="21084-201">Sam kan skicka utgiftsrapporten på nytt.</span><span class="sxs-lookup"><span data-stu-id="21084-201">Sam can resubmit the expense report.</span></span> <span data-ttu-id="21084-202">Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen av utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="21084-202">He can make the requested changes first, or he can resubmit the original version of the expense report.</span></span> <span data-ttu-id="21084-203">Om Sam skickar om utgiftsrapporten skickas den till Frank för godkännande eftersom Frank är den första godkännaren i godkännandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="21084-203">If Sam resubmits the expense report, it's sent to Frank for approval, because Frank is the first approver in the approval process.</span></span>

