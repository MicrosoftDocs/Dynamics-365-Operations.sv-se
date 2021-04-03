---
title: Manuellt skapade arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder manuellt i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b704699c5e04f38c3b79691f935287f8f9c24fba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263720"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="2e5b5-103">Manuellt skapade arbetsorder</span><span class="sxs-lookup"><span data-stu-id="2e5b5-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="2e5b5-104">Du kan skapa arbetsorder manuellt på två sätt:</span><span class="sxs-lookup"><span data-stu-id="2e5b5-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="2e5b5-105">På sidan **Alla arbetsorder** eller **Aktiva arbetsorder**</span><span class="sxs-lookup"><span data-stu-id="2e5b5-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="2e5b5-106">PÅ sidan **Alla underhållsbegäranden**, **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="2e5b5-107">Skapa arbetsorder</span><span class="sxs-lookup"><span data-stu-id="2e5b5-107">Create work order</span></span>

1. <span data-ttu-id="2e5b5-108">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2e5b5-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-109">Select **New**.</span></span>

3. <span data-ttu-id="2e5b5-110">I dialogrutan **Skapa arbetsorder** väljer du en arbetsordertyp i fältet **arbetsordertyp**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="2e5b5-111">Ange en **beskrivning** om det krävs.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="2e5b5-112">Välj tillgången i fältet **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="2e5b5-113">När du väljer en tillgång kan det hända att tre flikar är tillgängliga i listrutan **tillgång**:</span><span class="sxs-lookup"><span data-stu-id="2e5b5-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="2e5b5-114">**Aktiva tillgångar** - Den här fliken innehåller en lista över alla tillgångar som har livscykelstatus "aktiv".</span><span class="sxs-lookup"><span data-stu-id="2e5b5-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="2e5b5-115">**Tillgångsvisning** - Den här fliken visar en trädvy över funktionsplatser och tillgångar som är installerade på dem.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="2e5b5-116">**Mina tillgångar** – Den här fliken innehåller tillgångar som är relaterade till de funktionella platser som du (som är inloggade på systemet) kan fördelas på.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="2e5b5-117">(Mer information om inställningarna finns i [underhållsarbetare och arbetsgrupper](../setup-for-objects/workers-and-worker-groups.md).) Om inga funktionella platser har ställts in för en arbetare [underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md) är fliken **mina tillgångar** inte tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="2e5b5-118">I fältet **typ av underhållsjobb**, välj en typ av underhållsjobb för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="2e5b5-119">Välj vid behov **Variant av underhållsjobbtyp** och **Yrkesgren**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="2e5b5-120">Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="2e5b5-121">Välj datum för **Förväntad start** och **Förväntad slut** i de relaterade fälten.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="2e5b5-122">Klicka på **OK** för att skapa arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="2e5b5-123">På listsidan **Alla arbetsorder** kan du redigera arbetsordern som du behöver.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="2e5b5-124">Observera följande:</span><span class="sxs-lookup"><span data-stu-id="2e5b5-124">Note the following points:</span></span>

- <span data-ttu-id="2e5b5-125">I informationsvyn på listsidan **Alla arbetsorder** kan du lägga till flera tillgångar i en arbetsorder genom att lägga till rader på snabbfliken **Underhållsjobb för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="2e5b5-126">För en tillgång kan du bara välja de typer av underhållsjobb som är definierade för den tillgångstyp som valts för tillgången.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="2e5b5-127">Om du ändrar en tillgångs tjänstenivån eller allvarlighetsgrad är den här tillgången på arbetsorder, tjänstenivå eller allvarlighetsgrad på allvarlighetsgraden på arbetsordern i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="2e5b5-128">Mer information om tjänstenivåer och allvarlighetsgrad finns i [Tillgångs tjänstenivå](../setup-for-objects/object-priorities.md) och [Allvarlighetsgradtyper för tillgång](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="2e5b5-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="2e5b5-129">Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderjobb läggs till eller tas bort från arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="2e5b5-130">I informationsvyn **Alla arbetsorder** > fliken **Sidhuvud** > snabbfliken **Tidsplanera** i **Ansvarig grupp** eller **Ansvarig** kan du välja en ansvarig underhållsgrupp för arbetare eller en ansvarig underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="2e5b5-131">Dessa inställningar kan ändras när arbetsordern är aktiv.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="2e5b5-132">De kan till exempel ändras när arbetsorderns livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="2e5b5-133">Det automatiskt val som görs när arbetsordern skapas baseras på inställningarna på sidan **Ansvariga underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="2e5b5-134">Om du lägger till eller tar bort arbetsorderjobb efter att du har skapat en arbetsorder och fältet **Ansvarig grupp** och fältet **Ansvarig** är tomt när du uppdaterar arbetsordern, söker Tillgångshantering efter en möjlig matchning i inställningsformuläret för en ansvarig underhållsarbetargrupp eller ansvarig underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="2e5b5-135">Om **Ansvarig grupp** eller **Ansvarig** redan är ifyllt när du uppdaterar arbetsordern, görs inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="2e5b5-136">För mer information om ansvariga underhållsarbetare och arbetargrupper, se [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="2e5b5-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="2e5b5-137">Från sidan [Underhållsstatus](../controlling-and-reporting/maintenance-status.md) kan du göra en beräkning för att få en översikt över belastningen på inkommande och slutförda arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="2e5b5-138">I detaljvyn på sidan **Alla arbetsorder** på snabbfliken **Raddetaljer** kan du använda fälten **Latitud** och **Longitud** för att lägga till geografiska koordinater för den anläggnings tillgång som valts för arbetsorderjobbet.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="2e5b5-139">Skapa relaterad arbetsorder</span><span class="sxs-lookup"><span data-stu-id="2e5b5-139">Create related work order</span></span>

<span data-ttu-id="2e5b5-140">Du kan skapa en arbetsorder som är relaterad till en befintlig arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="2e5b5-141">Den här funktionen är användbar om du till exempel vill arbeta med primära och sekundära arbetsordrar.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="2e5b5-142">En ny arbetsorder baseras på ett arbetsorderjobb från en befintlig arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="2e5b5-143">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2e5b5-144">Välj arbetsorder för att skapa en relaterad arbetsordning för.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="2e5b5-145">I åtgärdsfönstret, på fliken **Arbetsorder**, i gruppen **New**, väljer du **Relaterad arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="2e5b5-146">I listrutan **Skapa relaterad arbetsorder** i fältet **arbetsorderjobb** välj arbetsordern att skapa en relaterad arbetsorder för.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="2e5b5-147">Välj underhållsjobbtyp i fältet **Underhållsjobbtyp**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="2e5b5-148">I fälten **Variant av underhållsjobbtyp** och **Yrkesgren** väljer varianten av underhållsjobbtypen och en yrkesgren för underhållsjobbtypen.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="2e5b5-149">Gör så här om denna arbetsorder är den första relaterade arbetsorder som har skapats för den valda arbetsordern:</span><span class="sxs-lookup"><span data-stu-id="2e5b5-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="2e5b5-150">Välj alternativet **ny arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="2e5b5-151">I fältet **arbetsordertyp** väljer du en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="2e5b5-152">Ange en beskrivning i **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="2e5b5-153">Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="2e5b5-154">I fälten **Förväntad start** and **Förväntad slut** välj förväntade start- och slutdatum.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="2e5b5-155">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-155">Select **OK**.</span></span> <span data-ttu-id="2e5b5-156">Den nya relaterade arbetsordern visas på listsidan **Alla arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="2e5b5-157">Om arbetsordern som du skapar den relaterade arbetsordern för redan har relaterade arbetsorder, följer du dessa steg för att lägga till ett nytt arbetsorderjobb i en befintlig relaterad arbetsorder:</span><span class="sxs-lookup"><span data-stu-id="2e5b5-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="2e5b5-158">Välj alternativet **Lägg till i relaterade arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="2e5b5-159">I fältet **arbetsorder** väljer du den relaterade arbetsorder som du vill lägga till ett nytt arbetsorderjobb till.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="2e5b5-160">Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="2e5b5-161">I fälten **Förväntad start** and **Förväntad slut** ändra förväntade start- och slutdatum efter behov.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="2e5b5-162">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-162">Select **OK**.</span></span> <span data-ttu-id="2e5b5-163">Arbetsorderjobbet läggs till i befintlig relaterad arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="2e5b5-164">I bilden nedan visas ett exempel på sidan dialogrutan **Skapa relaterad arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Figur 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="2e5b5-166">Om du har angett en relaterad arbetsordermask i **Parametrar för tillgångshantering** fliken  > **Arbetsorder** > fältet **Relaterad arbetsordermask** skapas arbetsorder-ID enligt inställningen för masken.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="2e5b5-167">Om ingen relaterad arbetsordermask ställs in används nästa tillgängliga arbetsorder-ID för relaterade arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="2e5b5-168">Kopiera arbetsorder</span><span class="sxs-lookup"><span data-stu-id="2e5b5-168">Copy a work order</span></span>

<span data-ttu-id="2e5b5-169">Det är möjligt att snabbt skapa en ny arbetsorder utifrån en befintlig arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="2e5b5-170">Det här sättet att arbeta med arbetsorder skiljer sig från att skapa arbetsorder utifrån [underhållsplaner](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2e5b5-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="2e5b5-171">Det är användbart om du till exempel har en arbetsorder som innehåller många arbetsorderjobb med olika jobb för olika till gångar som ska slutföras med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="2e5b5-172">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="2e5b5-173">Välj den arbetsorder från vilken du vill kopiera innehållet.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="2e5b5-174">I åtgärdsfönstret, på fliken > **Arbetsorder**, i gruppen **New**, väljer du **Kopiera arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="2e5b5-175">Inställningarna för arbetsorder från den valda arbetsordern visas.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="2e5b5-176">Om det behövs kan du redigera vissa av fälten.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="2e5b5-177">Klicka på **OK** för att skapa den nya arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="2e5b5-178">På listsidan **Alla arbetsorder** kan du redigera arbetsordern som du behöver.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="2e5b5-179">När den nya arbetsordern skapas kopieras viss information direkt från den befintliga arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="2e5b5-180">Information om prognoser, verktyg, underhållschecklistor, funktionella platser, adresser och tidsplanering kopieras inte.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="2e5b5-181">I stället initieras den från de aktuella inställningarna i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="2e5b5-182">Om informationen ändras mellan den tidpunkt då den första arbetsordern skapades och den tidpunkt då du gjorde en kopia av arbetsordern, inkluderas därför ändringarna i den nya arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="2e5b5-183">Exempel är ändringar i prognoser eller uppdaterade underhållschecklistor.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="2e5b5-184">Illustrationen nedan visar ett exempel på dialogrutan **Kopiera arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Figur 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="2e5b5-186">Skapa en arbetsorder baserad på en underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="2e5b5-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="2e5b5-187">Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsbegäranden** > **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="2e5b5-188">Välj den underhållsbegäran som du vill skapa en arbetsorder för och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="2e5b5-189">I åtgärdsfönstret, på fliken > **Underhållsbegäran**, i gruppen **New**, väljer du **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="2e5b5-190">Ställ in fälten i dialogrutan **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="2e5b5-191">Om en underhållsjobbtyp har valts i underhållsbegäran kan du välja en annan underhållsjobbtyp om det behövs, när du skapar arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="2e5b5-192">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-192">Select **OK**.</span></span> <span data-ttu-id="2e5b5-193">Meddelandet informerar dig om att en arbetsorder har skapats.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="2e5b5-194">Om du vill se vilka arbetsorder som är kopplade till en underhållsbegäran väljer du **Alla underhållsbegäran** i listan **Aktiva underhållsbegäran** och underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="2e5b5-195">Sedan i åtgärdsfönstret på fliken **Underhållsbegäran** i gruppen **Vy** väljer du **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="2e5b5-196">Illustrationen nedan visar ett exempel på dialogrutan **Skapa arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Figur 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="2e5b5-198">Om du vill att arbetsordrar ska skapas automatiskt kan du schemalägga underhållsplanjobb eller så kan du ställa in "Skapa automatiskt" [underhållsplaner](../preventive-and-reactive-maintenance/maintenance-plans.md) eller [underhållsrundor](../preventive-and-reactive-maintenance/maintenance-rounds.md) på en tillgång.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="2e5b5-199">Arbetsorder som skapas från underhållsbegäranden på listsidan **All underhållsschema** har samma underhållsjobbtyper som väljs i underhållsbegärandena.</span><span class="sxs-lookup"><span data-stu-id="2e5b5-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]