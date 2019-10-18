---
title: Skapa arbetsflöden – översikt
description: Det här ämnet förklarar hur du skapar ett arbetsflöde.
author: sericks007
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
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 2168b33c8495eab61ec0c8262b042cd16420031c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190107"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="8a0ad-103">Skapa arbetsflöden – översikt</span><span class="sxs-lookup"><span data-stu-id="8a0ad-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a0ad-104">Det här ämnet förklarar hur du skapar ett arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="8a0ad-105">Öppna arbetsflödesredigeraren</span><span class="sxs-lookup"><span data-stu-id="8a0ad-105">Open the workflow editor</span></span>

<span data-ttu-id="8a0ad-106">Den modul som du arbetar i bestämmer vilka typer av arbetsflöden som du kan skapa.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="8a0ad-107">Gör på följande sätt för att välja vilken typ av arbetsflöden du vill skapa, och öppna arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="8a0ad-108">Öppna den modul som du vill skapa ett nytt arbetsflöde för.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="8a0ad-109">Om du till exempel vill skapa ett arbetsflöde för inköpsrekvisitioner, klicka då på **Anskaffning och källa**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="8a0ad-110">Klicka på **Inställningar** &gt; **\[Modulnamn\] arbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="8a0ad-111">Klicka på **Nytt** i åtgärdsfönstret på den listsida som visas.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="8a0ad-112">På sidan **Skapa arbetsflöde** väljer du den typ av arbetsflöde som du vill skapa, och klickar sedan på **Skapa arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="8a0ad-113">Arbetsflödesredigeraren visas.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-113">The workflow editor appears.</span></span> <span data-ttu-id="8a0ad-114">Du kan nu använda följande procedurer när du skapar arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="8a0ad-115">Dra arbetsflödeselementen till arbetsytan</span><span class="sxs-lookup"><span data-stu-id="8a0ad-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="8a0ad-116">Området **Arbetsflödeselement** i arbetsflödesredigeraren innehåller de element som du kan lägga till i ditt arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="8a0ad-117">Dra element till arbetsflödet om du vill lägga till dem i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="8a0ad-118">Anslut elementen</span><span class="sxs-lookup"><span data-stu-id="8a0ad-118">Connect the elements</span></span>

<span data-ttu-id="8a0ad-119">Om du vill koppla ett arbetsflödeselement till ett annat håller du pekaren över elementet tills kopplingspekaren visas.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="8a0ad-120">Klicka på en kopplingspunkt och dra den till det andra elementet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="8a0ad-121">Kontrollera att du ansluter alla element.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="8a0ad-122">Konfigurera egenskaperna för arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="8a0ad-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="8a0ad-123">Använd följande steg när du vill konfigurera egenskaperna för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="8a0ad-124">Klicka på arbetsytan för att försäkra dig om att inget arbetsflödeselement är markerat.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="8a0ad-125">Klicka på **Properties** för att öppna sidan **Properties** för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="8a0ad-126">Följ procedurerna i ämnet [Konfigurera egenskaper för ett arbetsflöde](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8a0ad-126">Follow the procedures in the [Configure the properties of a workflow](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="8a0ad-127">Konfigurera elementen i arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="8a0ad-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="8a0ad-128">Konfigurera varje element som du har dragit till arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="8a0ad-129">För information om hur du konfigurerar respektive arbetsflödeselement, se följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="8a0ad-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="8a0ad-130">Konfigurera en manuell uppgift</span><span class="sxs-lookup"><span data-stu-id="8a0ad-130">Configure a manual task</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="8a0ad-131">Konfigurera en automatisk uppgift</span><span class="sxs-lookup"><span data-stu-id="8a0ad-131">Configure an automated task</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="8a0ad-132">Konfigurera en godkännandeprocess</span><span class="sxs-lookup"><span data-stu-id="8a0ad-132">Configure an approval process</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="8a0ad-133">Konfigurera ett godkännandesteg</span><span class="sxs-lookup"><span data-stu-id="8a0ad-133">Configure an approval step</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="8a0ad-134">Konfigurera ett manuellt beslut</span><span class="sxs-lookup"><span data-stu-id="8a0ad-134">Configure a manual decision</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="8a0ad-135">Konfigurera ett villkorligt beslut</span><span class="sxs-lookup"><span data-stu-id="8a0ad-135">Configure a conditional decision</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="8a0ad-136">Konfigurera en parallell aktivitet</span><span class="sxs-lookup"><span data-stu-id="8a0ad-136">Configure a parallel activity</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="8a0ad-137">Konfigurera en parallell gren</span><span class="sxs-lookup"><span data-stu-id="8a0ad-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="8a0ad-138">Konfigurera ett arbetsflöde för radartiklar</span><span class="sxs-lookup"><span data-stu-id="8a0ad-138">Configure a line-item workflow</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="8a0ad-139">Lösa eventuella fel eller varningar</span><span class="sxs-lookup"><span data-stu-id="8a0ad-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="8a0ad-140">Fönstret **Errors and warning** i nedre delen av arbetsflödesredigeraren visar meddelanden som har skapats för arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="8a0ad-141">Dubbelklicka på felet eller varningsmeddelandet för att hitta det element där en varning eller ett fel har inträffat.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="8a0ad-142">Du måste åtgärda alla fel och varningar innan du kan aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="8a0ad-143">Spara och aktivera arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="8a0ad-143">Save and activate the workflow</span></span>

<span data-ttu-id="8a0ad-144">Följ dessa steg när du är redo att spara och aktivera arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="8a0ad-145">Klicka på **Spara och stäng** för att stänga redigeraren för arbetsflöde och öppna sidan **Spara arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="8a0ad-146">Ange kommentarer om de ändringar som du har genomfört på arbetsflödet, och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="8a0ad-147">Om alla fel och varningar har lösts, visas sidan **Aktivera arbetsflöde**.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="8a0ad-148">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="8a0ad-148">Select one of the following options:</span></span>

    - <span data-ttu-id="8a0ad-149">Klicka på **Aktivera den nya versionen** för att aktivera denna version av arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="8a0ad-150">När ett arbetsflöde är aktivt kan användare skicka dokument till det för bearbetning.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="8a0ad-151">Klicka på **Aktivera inte den nya versionen** om du inte vill aktivera denna version.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="8a0ad-152">Du kan aktivera arbetsflödet senare.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-152">You can activate the workflow later.</span></span>
