---
title: Livscykeltillstånd för underhållsbegäran
description: I det här avsnittet beskrivs hur du ställer in livscykeltillstånd för underhållsbegäran i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08c45742b064f3a13a0ea2704f8873b9c53aad4e
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275636"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="123c8-103">Underhållsbegärans livscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="123c8-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="123c8-104">Livscykeltillstånd för underhållsbegäran definierar stadier som en begäran kan gå igenom.</span><span class="sxs-lookup"><span data-stu-id="123c8-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="123c8-105">Exempel är **skapad**, **aktiv** och **avslutad**.</span><span class="sxs-lookup"><span data-stu-id="123c8-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="123c8-106">När en underhållsbegäran konverteras till en arbetsorder, bör livscykeltillstånd för underhållsbegäran uppdateras till **avslutad** eller **stängd** för att indikera att underhållsbegäran inte längre är aktiv.</span><span class="sxs-lookup"><span data-stu-id="123c8-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="123c8-107">På listsidan **Alla underhållsbegäran** visas alla underhållsbegäran, oavsett livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="123c8-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="123c8-108">Ställ in livscykeltillstånd för underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="123c8-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="123c8-109">Välj **tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="123c8-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="123c8-110">Välj **ny** för att skapa ett livscykeltillstånd för underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="123c8-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="123c8-111">I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="123c8-112">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="123c8-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="123c8-113">På snabbfliken **Detaljer** visar fältet **livscykelmodeller** antalet livscykelmodeller för underhållsbegäran som använder det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="123c8-114">På snabbfliken **allmänt** anger du alternativet **aktiva** till **ja** om en underhållsbegäran ska vara aktiv medan den är i det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="123c8-115">Ange alternativet **Ange faktiskt slut** till **ja** om ett faktiskt slutdatum och en faktisk tid automatiskt ska anges i en underhållsbegäran i det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-115">Set the **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="123c8-116">Ange alternativet **skapa arbetsorder** till **ja** om en arbetsorder kan skapas från en underhållsbegäran i det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="123c8-117">Ange alternativet **ta bort** till **ja** om en underhållsbegäran kan tas bort när den är i det här livscykeltillståndet.</span><span class="sxs-lookup"><span data-stu-id="123c8-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="123c8-118">På snabbfliken **Uppdatera** är alternativen **inkommande** och **utgående** i avsnittet **tillgång** relevanta om du använder depåreparation.</span><span class="sxs-lookup"><span data-stu-id="123c8-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.</span></span> <span data-ttu-id="123c8-119">Ställ in rätt alternativ på **Ja** om tillgångens livscykeltillstånd för tillgångar som väljs i en begäran om underhåll bör uppdateras automatiskt till **inkommande** eller **utgående** när livscykeltillståndet för underhållsbegäran är inställt på **inkommande** eller **utgående**.</span><span class="sxs-lookup"><span data-stu-id="123c8-119">Set the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="123c8-120">Följande illustration visar ett exempel på sidan **livscykeltillståndet för underhållsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="123c8-120">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Sidan Underhållsbegärans livscykeltillstånd](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="123c8-122">Livscykeltillstånd för underhållsbegäran, livscykeltillståndsgrupper och typer är relaterade till och används på samma sätt som livscykeltillstånd för arbetsorder, livscykeltillståndsgrupper och typer.</span><span class="sxs-lookup"><span data-stu-id="123c8-122">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="123c8-123">Ställ in livscykelmodeller för underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="123c8-123">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="123c8-124">När du har skapat de livscykeltillstånd som krävs för dina underhållsbegäranden kan de delas upp i livscykeltillståndsgrupper eller livscykelmodeller.</span><span class="sxs-lookup"><span data-stu-id="123c8-124">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="123c8-125">Livscykelmodeller för underhållbegäran används för att skapa flödet som kan användas för olika typer av underhållbegäranden.</span><span class="sxs-lookup"><span data-stu-id="123c8-125">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="123c8-126">Som ett minimum ska en standardlivscykelmodell för underhållsbegäran skapas.</span><span class="sxs-lookup"><span data-stu-id="123c8-126">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="123c8-127">Välj **tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykelmodell**.</span><span class="sxs-lookup"><span data-stu-id="123c8-127">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="123c8-128">Välj **ny** för att skapa ett livscykelmodell  för underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="123c8-128">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="123c8-129">I fältet **livscykelmodell** anger du ett ID för livscykelmodell.</span><span class="sxs-lookup"><span data-stu-id="123c8-129">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="123c8-130">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="123c8-130">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="123c8-131">På snabbfliken **Detaljer** visar fältet **livscykeltillstånd** antalet livscykeltillstånd som väljs i den här livscykelmodellen.</span><span class="sxs-lookup"><span data-stu-id="123c8-131">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="123c8-132">Fältet **underhållsbegärantyper** visar antalet underhållsbegärantyper som använder den här livscykelmodellen.</span><span class="sxs-lookup"><span data-stu-id="123c8-132">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="123c8-133">På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd som ska inkluderas i livscykelmodellen.</span><span class="sxs-lookup"><span data-stu-id="123c8-133">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="123c8-134">Om du vill inkludera ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **återstående livscykeltillstånd** och markerar sedan högerpilknappen ![högerpil](media/03-setup-for-requests.png) för att flytta den till avsnittet **Valt livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="123c8-134">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="123c8-135">Om du vill inkludera alla tillgängliga livscykeltillstånd i livscykelmodellen markerar du knappen **Välj alla tillgängliga tillstånd** knappen ![Välj alla tillgängliga tillstånd](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="123c8-135">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="123c8-136">Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="123c8-136">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="123c8-137">Om du vill ta bort ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **valda livscykeltillstånd** och markerar sedan vänsterpilknappen ![vänsterpil](media/05-setup-for-requests.png) för att flytta den till avsnittet **Återstående livscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="123c8-137">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="123c8-138">På snabbfliken **allmänt** är fälten i avsnittet **uppdateringar** relevanta om du använder depåreparation.</span><span class="sxs-lookup"><span data-stu-id="123c8-138">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="123c8-139">I den **livscykeltillstånd för mottagen tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de tas emot för depåreparation.</span><span class="sxs-lookup"><span data-stu-id="123c8-139">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="123c8-140">I fältet **livscykeltillstånd för levererad tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de returneras efter reparation.</span><span class="sxs-lookup"><span data-stu-id="123c8-140">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="123c8-141">Följande illustration visar ett exempel på sidan **livscykelmodeller för underhållsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="123c8-141">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Sidan Livscykelmodeller för underhållsbegäran](media/06-setup-for-requests.png)
