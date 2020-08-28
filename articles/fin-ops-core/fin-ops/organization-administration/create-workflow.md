---
title: Skapa arbetsflöden – översikt
description: Det här ämnet förklarar hur du skapar ett arbetsflöde.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: bcd548bf8e03e0e6df4d413afe8c9ae01c570899
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698028"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="f5476-103">Skapa arbetsflöden – översikt</span><span class="sxs-lookup"><span data-stu-id="f5476-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5476-104">Det här ämnet förklarar hur du skapar ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="f5476-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="f5476-105">Öppna arbetsflödesredigeraren</span><span class="sxs-lookup"><span data-stu-id="f5476-105">Open the workflow editor</span></span>

<span data-ttu-id="f5476-106">Den modul som du arbetar i bestämmer vilka typer av arbetsflöden som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="f5476-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="f5476-107">Gör på följande sätt för att välja vilken typ av arbetsflöden du vill skapa, och öppna arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f5476-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="f5476-108">Öppna den modul som du vill skapa ett nytt arbetsflöde för.</span><span class="sxs-lookup"><span data-stu-id="f5476-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="f5476-109">Om du till exempel vill skapa ett arbetsflöde för inköpsrekvisitioner, klicka då på **Anskaffning och källa**.</span><span class="sxs-lookup"><span data-stu-id="f5476-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="f5476-110">Klicka på **Inställningar** &gt; **\[Modulnamn\] arbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="f5476-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="f5476-111">Klicka på **Nytt** i åtgärdsfönstret på den listsida som visas.</span><span class="sxs-lookup"><span data-stu-id="f5476-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="f5476-112">På sidan **Skapa arbetsflöde** väljer du den typ av arbetsflöde som du vill skapa, och klickar sedan på **Skapa arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="f5476-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="f5476-113">Arbetsflödesredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="f5476-113">The workflow editor appears.</span></span> <span data-ttu-id="f5476-114">Du kan nu använda följande procedurer när du skapar arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="f5476-115">Dra arbetsflödeselementen till arbetsytan</span><span class="sxs-lookup"><span data-stu-id="f5476-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="f5476-116">Området **Arbetsflödeselement** i arbetsflödesredigeraren innehåller de element som du kan lägga till i ditt arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="f5476-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="f5476-117">Dra element till arbetsflödet om du vill lägga till dem i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="f5476-118">Anslut elementen</span><span class="sxs-lookup"><span data-stu-id="f5476-118">Connect the elements</span></span>

<span data-ttu-id="f5476-119">Om du vill koppla ett arbetsflödeselement till ett annat håller du pekaren över elementet tills kopplingspekaren visas.</span><span class="sxs-lookup"><span data-stu-id="f5476-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="f5476-120">Klicka på en kopplingspunkt och dra den till det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="f5476-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="f5476-121">Kontrollera att du ansluter alla element.</span><span class="sxs-lookup"><span data-stu-id="f5476-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="f5476-122">Konfigurera egenskaperna för arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="f5476-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="f5476-123">Använd följande steg när du vill konfigurera egenskaperna för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="f5476-124">Klicka på arbetsytan för att försäkra dig om att inget arbetsflödeselement är markerat.</span><span class="sxs-lookup"><span data-stu-id="f5476-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="f5476-125">Klicka på **Properties** för att öppna sidan **Properties** för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="f5476-126">Följ procedurerna i ämnet [Konfigurera egenskaper för arbetsflöde](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f5476-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="f5476-127">Konfigurera elementen i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="f5476-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="f5476-128">Konfigurera varje element som du har dragit till arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="f5476-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="f5476-129">För information om hur du konfigurerar respektive arbetsflödeselement, se följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="f5476-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="f5476-130">Konfigurera manuella uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="f5476-131">Konfigurera automatiska uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="f5476-132">Konfigurera godkännandeprocesser i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="f5476-133">Konfigurera godkännandesteg i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="f5476-134">Konfigurera manuella beslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="f5476-135">Konfigurera villkorsbeslut i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="f5476-136">Konfigurera parallella grenar i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="f5476-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="f5476-137">Konfigurera en parallell gren</span><span class="sxs-lookup"><span data-stu-id="f5476-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="f5476-138">Konfigurera arbetsflöden för radartiklar</span><span class="sxs-lookup"><span data-stu-id="f5476-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="f5476-139">Lösa eventuella fel eller varningar</span><span class="sxs-lookup"><span data-stu-id="f5476-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="f5476-140">Fönstret **Errors and warning** i nedre delen av arbetsflödesredigeraren visar meddelanden som har skapats för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="f5476-141">Dubbelklicka på felet eller varningsmeddelandet för att hitta det element där en varning eller ett fel har inträffat.</span><span class="sxs-lookup"><span data-stu-id="f5476-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="f5476-142">Du måste åtgärda alla fel och varningar innan du kan aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="f5476-143">Spara och aktivera arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="f5476-143">Save and activate the workflow</span></span>

<span data-ttu-id="f5476-144">Följ dessa steg när du är redo att spara och aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="f5476-145">Klicka på **Spara och stäng** för att stänga redigeraren för arbetsflöde och öppna sidan **Spara arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="f5476-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="f5476-146">Ange kommentarer om de ändringar som du har genomfört på arbetsflödet, och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5476-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="f5476-147">Om alla fel och varningar har lösts, visas sidan **Aktivera arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="f5476-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="f5476-148">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="f5476-148">Select one of the following options:</span></span>

    - <span data-ttu-id="f5476-149">Klicka på **Aktivera den nya versionen** för att aktivera denna version av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f5476-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="f5476-150">När ett arbetsflöde är aktivt kan användare skicka dokument till det för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="f5476-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="f5476-151">Klicka på **Aktivera inte den nya versionen** om du inte vill aktivera denna version.</span><span class="sxs-lookup"><span data-stu-id="f5476-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="f5476-152">Du kan aktivera arbetsflödet senare.</span><span class="sxs-lookup"><span data-stu-id="f5476-152">You can activate the workflow later.</span></span>
