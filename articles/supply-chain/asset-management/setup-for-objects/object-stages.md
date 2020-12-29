---
title: Livscykeltillstånd för tillgångar
description: Det här avsnittet beskriver livscykeltillstånd för tillgångar och livscykelmodeller i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 566036c6361194d910a0fc34bd5d72147585ec4f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437574"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="04ac4-103">Tillgångs livscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="04ac4-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="04ac4-104">Det här avsnittet beskriver livscykeltillstånd för tillgångar och livscykelmodeller i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="04ac4-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="04ac4-105">Tillgångs livscykeltillstånd används för att definiera om tillgången är aktiv eller inaktiv.</span><span class="sxs-lookup"><span data-stu-id="04ac4-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="04ac4-106">Du kan till exempel ställa in tillgångs livscykeltillstånd som **skapad**, **aktiv** och **avslutad**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="04ac4-107">Begär livscykeltillstånd är länkade till livscykeltillstånd för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="04ac4-108">Därför när en begäran ändras till ett nytt livscykeltillstånd ändras tillgången som är kopplad till begäran till ett nytt livscykeltillstånd för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="04ac4-109">Om livscykeltillståndet för en begäran till exempel ändras till **inkommande** ändras livscykeltillståndet för den kopplade tillgången till det livscykeltillstånd som har valts i fältet **inkommande livscykeltillstånd** på snabbfliken **Livscykeltillstånd för tillgångar** på sidan **Livscykelmodeller för tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="04ac4-110">Livscykeltillstånd för tillgångar kan ställas in i livscykelmodeller för tillgångar där du kan definiera de nödvändiga livscykeltillstånden för olika typer av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="04ac4-111">Du ställer först in livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="04ac4-111">You first set up lifecycle states.</span></span> <span data-ttu-id="04ac4-112">Sedan skapar du en livscykelmodell och väljer livscykeltillstånd för den.</span><span class="sxs-lookup"><span data-stu-id="04ac4-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="04ac4-113">Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="04ac4-114">Skapa ett nytt livscykeltillstånd för tillgångar genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="04ac4-115">I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="04ac4-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="04ac4-116">Ange en beskrivning i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="04ac4-117">Fältet **livscykelmodeller** antalet livscykelmodeller för tillgångar som använder det här livscykeltillståndet för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="04ac4-118">Ange alternativet **aktiva** till **ja** om det här livscykeltillståndet ska vara ett aktivt livscykeltillstånd (med andra ord om arbetsorder kan skapas för tillgångar som är i det här livscykeltillståndet).</span><span class="sxs-lookup"><span data-stu-id="04ac4-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="04ac4-119">Ange alternativet **ta bort öppna kalenderrader** till **ja** om öppna tillgångskalenderrader som har livscykeltillståndet för tillgångar **skapad** ska tas bort när de är i det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="04ac4-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="04ac4-120">Den här inställningen är användbar om du vill rensa alla öppna underhållsscheman som inte längre är relevanta för tillgången (till exempel om tillgången inte längre är aktiv).</span><span class="sxs-lookup"><span data-stu-id="04ac4-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="04ac4-121">Livscykeltillstånd för tillgångar, livscykelmodeller för tillgångar och tillgångstyper är relaterade.</span><span class="sxs-lookup"><span data-stu-id="04ac4-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="04ac4-122">De används på samma sätt som livscykeltillstånd för arbetsorder, livscykelmodeller för arbetsorder och arbetsordertyper.</span><span class="sxs-lookup"><span data-stu-id="04ac4-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="04ac4-123">När du har skapat de nödvändiga livscykeltillstånden för tillgångar kan du ställa in livscykeltillstånd i tillgångens livscykelmodeller.</span><span class="sxs-lookup"><span data-stu-id="04ac4-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="04ac4-124">Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **livscykelmodeller**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="04ac4-125">Skapa en ny livscykelmodell för tillgångar genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="04ac4-126">I fältet **livscykelmodell** anger du ett ID för livscykelmodell.</span><span class="sxs-lookup"><span data-stu-id="04ac4-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="04ac4-127">Ange en beskrivning i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="04ac4-128">Fältet **livscykeltillstånd** antalet livscykeltillstånd för tillgångar som väljs i den här livscykelmodellen för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="04ac4-129">Fältet **tillgångstyper** visar antalet tillgångstyper som använder den livscykelmodellen.</span><span class="sxs-lookup"><span data-stu-id="04ac4-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="04ac4-130">På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd för tillgångar som ska inkluderas i livscykelmodellen för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="04ac4-131">Om du vill använda ett livscykeltillstånd för modellen väljer du den i avsnittet **återstående livscykeltillstånd** och markerar sedan högerpilknappen ![högerpil](media/15-setup-for-objects.png) för att flytta den till avsnittet **Valt livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="04ac4-132">Om du vill använda alla tillgängliga livscykeltillstånd förmodellen markerar du knappen **Alla alla tillgängliga livscykeltillstånd** knappen ![Alla alla tillgängliga livscykeltillstånd](media/20-setup-for-objects.png).</span><span class="sxs-lookup"><span data-stu-id="04ac4-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="04ac4-133">Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="04ac4-134">Om du vill ta bort ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **valda livscykeltillstånd** och markerar sedan vänsterpilknappen ![vänsterpil](media/16-setup-for-objects.png) för att flytta den till avsnittet **Återstående livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="04ac4-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="04ac4-135">Välj **uppdateringar av livscykeltillstånd** för att definiera vilka livscykeltillstånd för tillgångar som kan följa ett valt livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="04ac4-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="04ac4-136">Du kan använda snabbfliken **tillgångstillstånd** om du hanterar tillgångar som du tar emot för reparation.</span><span class="sxs-lookup"><span data-stu-id="04ac4-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="04ac4-137">I avsnittet **inkommande/utgående** kan du välja livscykeltillstånd för tillgångar för att indikera arbetsflödet för en tillgång som du tar emot för reparation.</span><span class="sxs-lookup"><span data-stu-id="04ac4-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="04ac4-138">Om du erbjuder lånetillgångar till kunder eller avdelningar kan du i avsnittet **lån** välja livscykeltillstånd för lånetillgångar.</span><span class="sxs-lookup"><span data-stu-id="04ac4-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>
