---
title: Skapa arbetsflöden – översikt
description: Det här ämnet förklarar hur du skapar ett arbetsflöde.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: a64329780b96ca1e1675ced103c86c7cf0bc3754
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567400"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="d8842-103">Skapa arbetsflöden – översikt</span><span class="sxs-lookup"><span data-stu-id="d8842-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8842-104">Det här ämnet förklarar hur du skapar ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="d8842-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="d8842-105">Öppna arbetsflödesredigeraren</span><span class="sxs-lookup"><span data-stu-id="d8842-105">Open the workflow editor</span></span>

<span data-ttu-id="d8842-106">Den modul som du arbetar i bestämmer vilka typer av arbetsflöden som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="d8842-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="d8842-107">Gör på följande sätt för att välja vilken typ av arbetsflöden du vill skapa, och öppna arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="d8842-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="d8842-108">Öppna den modul som du vill skapa ett nytt arbetsflöde för.</span><span class="sxs-lookup"><span data-stu-id="d8842-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="d8842-109">Om du till exempel vill skapa ett arbetsflöde för inköpsrekvisitioner, klicka då på **Anskaffning och källa**.</span><span class="sxs-lookup"><span data-stu-id="d8842-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="d8842-110">Klicka på **Inställningar** &gt; **\[Modulnamn\] arbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="d8842-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="d8842-111">Klicka på **Nytt** i åtgärdsfönstret på den listsida som visas.</span><span class="sxs-lookup"><span data-stu-id="d8842-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="d8842-112">På sidan **Skapa arbetsflöde** väljer du den typ av arbetsflöde som du vill skapa, och klickar sedan på **Skapa arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="d8842-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="d8842-113">Arbetsflödesredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="d8842-113">The workflow editor appears.</span></span> <span data-ttu-id="d8842-114">Du kan nu använda följande procedurer när du skapar arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="d8842-115">Dra arbetsflödeselementen till arbetsytan</span><span class="sxs-lookup"><span data-stu-id="d8842-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="d8842-116">Området **Arbetsflödeselement** i arbetsflödesredigeraren innehåller de element som du kan lägga till i ditt arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="d8842-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="d8842-117">Dra element till arbetsflödet om du vill lägga till dem i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="d8842-118">Anslut elementen</span><span class="sxs-lookup"><span data-stu-id="d8842-118">Connect the elements</span></span>

<span data-ttu-id="d8842-119">Om du vill koppla ett arbetsflödeselement till ett annat håller du pekaren över elementet tills kopplingspekaren visas.</span><span class="sxs-lookup"><span data-stu-id="d8842-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="d8842-120">Klicka på en kopplingspunkt och dra den till det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="d8842-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="d8842-121">Kontrollera att du ansluter alla element.</span><span class="sxs-lookup"><span data-stu-id="d8842-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="d8842-122">Konfigurera egenskaperna för arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d8842-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="d8842-123">Använd följande steg när du vill konfigurera egenskaperna för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="d8842-124">Klicka på arbetsytan för att försäkra dig om att inget arbetsflödeselement är markerat.</span><span class="sxs-lookup"><span data-stu-id="d8842-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="d8842-125">Klicka på **Properties** för att öppna sidan **Properties** för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="d8842-126">Följ procedurerna i ämnet [Konfigurera egenskaper för arbetsflöde](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d8842-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="d8842-127">Konfigurera elementen i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d8842-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="d8842-128">Konfigurera varje element som du har dragit till arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="d8842-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="d8842-129">För information om hur du konfigurerar respektive arbetsflödeselement, se följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="d8842-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="d8842-130">Konfigurera manuella uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="d8842-131">Konfigurera automatiska uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="d8842-132">Konfigurera godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="d8842-133">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="d8842-134">Konfigurera manuella beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="d8842-135">Konfigurera villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="d8842-136">Konfigurera parallella grenar i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="d8842-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="d8842-137">Konfigurera en parallell gren</span><span class="sxs-lookup"><span data-stu-id="d8842-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="d8842-138">Konfigurera arbetsflöden för radartiklar</span><span class="sxs-lookup"><span data-stu-id="d8842-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="d8842-139">Lösa eventuella fel eller varningar</span><span class="sxs-lookup"><span data-stu-id="d8842-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="d8842-140">Fönstret **Errors and warning** i nedre delen av arbetsflödesredigeraren visar meddelanden som har skapats för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="d8842-141">Dubbelklicka på felet eller varningsmeddelandet för att hitta det element där en varning eller ett fel har inträffat.</span><span class="sxs-lookup"><span data-stu-id="d8842-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="d8842-142">Du måste åtgärda alla fel och varningar innan du kan aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="d8842-143">Spara och aktivera arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="d8842-143">Save and activate the workflow</span></span>

<span data-ttu-id="d8842-144">Följ dessa steg när du är redo att spara och aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="d8842-145">Klicka på **Spara och stäng** för att stänga redigeraren för arbetsflöde och öppna sidan **Spara arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="d8842-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="d8842-146">Ange kommentarer om de ändringar som du har genomfört på arbetsflödet, och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8842-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="d8842-147">Om alla fel och varningar har lösts, visas sidan **Aktivera arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="d8842-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="d8842-148">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d8842-148">Select one of the following options:</span></span>

    - <span data-ttu-id="d8842-149">Klicka på **Aktivera den nya versionen** för att aktivera denna version av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="d8842-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="d8842-150">När ett arbetsflöde är aktivt kan användare skicka dokument till det för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="d8842-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="d8842-151">Klicka på **Aktivera inte den nya versionen** om du inte vill aktivera denna version.</span><span class="sxs-lookup"><span data-stu-id="d8842-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="d8842-152">Du kan aktivera arbetsflödet senare.</span><span class="sxs-lookup"><span data-stu-id="d8842-152">You can activate the workflow later.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]