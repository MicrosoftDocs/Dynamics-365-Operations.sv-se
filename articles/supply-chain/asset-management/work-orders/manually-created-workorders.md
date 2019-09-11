---
title: Manuellt skapade arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder manuellt i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875902"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="ea349-103">Manuellt skapade arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ea349-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="ea349-104">Du kan skapa arbetsorder manuellt på två sätt:</span><span class="sxs-lookup"><span data-stu-id="ea349-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="ea349-105">i **Alla arbetsorder** eller **Aktiva arbetsorder**</span><span class="sxs-lookup"><span data-stu-id="ea349-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="ea349-106">i **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden** eller **Mina underhållsbegäranden för funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="ea349-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="ea349-107">Skapa arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ea349-107">Create work order</span></span>

1. <span data-ttu-id="ea349-108">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ea349-109">Klicka på knappen **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="ea349-109">Click the **New** button.</span></span>

3. <span data-ttu-id="ea349-110">I listrutan **Skapa arbetsorder** väljer du en arbetsordertyp.</span><span class="sxs-lookup"><span data-stu-id="ea349-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="ea349-111">Ange en beskrivning om det krävs.</span><span class="sxs-lookup"><span data-stu-id="ea349-111">If required, select a description.</span></span>

5. <span data-ttu-id="ea349-112">Välj till gången för arbetsordern samt en underhållsjobbtyp.</span><span class="sxs-lookup"><span data-stu-id="ea349-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="ea349-113">När du väljer en tillgång är tre flikar tillgängliga: fliken **Mina tillgångar** innehåller tillgångar som är relaterade till de funktionsplatser som du (arbetaren som är inloggad på systemet) kan allokeras till (ställs in i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="ea349-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="ea349-114">Om inga funktionsplatser ställs in för en underhållsarbetare i formuläret [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md) kommer fliken **Mina tillgångar** inte att visas.</span><span class="sxs-lookup"><span data-stu-id="ea349-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="ea349-115">Fliken **aktiva tillgångar** innehåller en lista över alla tillgångar med livscykelstatus "aktiv".</span><span class="sxs-lookup"><span data-stu-id="ea349-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="ea349-116">Fliken **tillgångsvisning** visar en trädvy över funktionsplatser och tillgångar som är installerade på dessa platser.</span><span class="sxs-lookup"><span data-stu-id="ea349-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="ea349-117">Välj vid behov **Variant av underhållsjobbtyp** och **Yrkesgren**.</span><span class="sxs-lookup"><span data-stu-id="ea349-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="ea349-118">Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="ea349-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="ea349-119">Välj förväntade start- och slutdatum i de relaterade fälten.</span><span class="sxs-lookup"><span data-stu-id="ea349-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="ea349-120">Klicka på **OK** för att skapa en ny arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="ea349-121">Redigera arbetsordern i **Alla arbetsorder** om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ea349-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="ea349-122">I **Alla arbetsorder** kan du lägga till flera tillgångar i en arbetsorder i informationsvyn genom att lägga till rader på snabbfliken **Underhållsjobb för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="ea349-123">För en tillgång kan du bara välja de typer av underhållsjobb som är definierade för den tillgångstyp som valts för tillgången.</span><span class="sxs-lookup"><span data-stu-id="ea349-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="ea349-124">Om du har ändrat en tillgångs servicenivå eller en tillgångs allvarlighetsgrad efter att du har använt dem på en arbetsorder (se [Tillgångs tjänstenivå](../setup-for-objects/object-priorities.md) och [Allvarlighetsgrad för tillgång](../setup-for-objects/object-criticalities.md)) är servicenivån eller den allvarlighetsgraden för arbetsordern inte uppdaterad därefter.</span><span class="sxs-lookup"><span data-stu-id="ea349-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="ea349-125">Allvarlighetsgraden på en arbetsorder beräknas om varje gång en arbetsorderrad läggs till eller tas bort från arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="ea349-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="ea349-126">I informationsvyn **Alla arbetsorder** > vyn **Sidhuvud** > snabbfliken **Tidsplanera** kan du välja en ansvarig underhållsgrupp för arbetare eller en ansvarig underhållsarbetare i fälten **Ansvarig grupp** eller **Ansvarig**.</span><span class="sxs-lookup"><span data-stu-id="ea349-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="ea349-127">Dessa inställningar kan ändras så länge arbetsordern är aktiv, t.ex. när arbetsorderns livscykeltillstånd ändras.</span><span class="sxs-lookup"><span data-stu-id="ea349-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="ea349-128">Det automatiskt val som görs när arbetsordern skapas baseras på inställningarna i **Ansvariga underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="ea349-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="ea349-129">Om du lägger till eller tar bort arbetsorderjobb efter att du har skapat en arbetsorder och fältet **Ansvarig grupp** och fältet **Ansvarig** är tomt när du uppdaterar arbetsordern, söker Tillgångshantering efter en möjlig matchning i inställningsformuläret för en ansvarig underhållsarbetargrupp eller ansvarig underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="ea349-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="ea349-130">Om fältet **Ansvarig grupp** eller fältet **Ansvarig** redan är ifyllt när du uppdaterar arbetsordern, görs inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="ea349-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="ea349-131">I **Underhållsstatus** kan du göra en beräkning för att få en översikt över belastningen på inkommande och slutförda arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="ea349-132">På snabbfliken **Radinformation** kan du använda fälten **Latitud** och **Longitud** för att lägga till geografiska koordinater för den tillgång som valts i arbetsorderjobbet.</span><span class="sxs-lookup"><span data-stu-id="ea349-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="ea349-133">Skapa relaterad arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ea349-133">Create related work order</span></span>

<span data-ttu-id="ea349-134">Du kan skapa en relaterad arbetsorder till en befintlig arbetsorder om du t.ex. vill arbeta med primära och sekundära arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="ea349-135">En ny arbetsorder baseras på ett arbetsorderjobb från en befintlig arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="ea349-136">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ea349-137">Välj den arbetsorder för vilken du vill skapa en relaterad arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="ea349-138">Klicka på **Relaterad arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="ea349-139">I listrutan **Skapa relaterad arbetsorder** väljer du arbetsorderjobbet som du vill skapa en relaterad arbetsorder för i fältet **Arbetsorderjobb**.</span><span class="sxs-lookup"><span data-stu-id="ea349-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="ea349-140">Välj en underhållsjobbtyp i fältet **Underhållsjobbtyp** och om det behövs en relaterad variant av underhållsjobbtyp och yrkesgren i **Variant av underhållsjobbtyp** och fältet **Yrkesgren**.</span><span class="sxs-lookup"><span data-stu-id="ea349-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="ea349-141">Om detta är den första relaterade arbetsorder som du gör, klickar du på alternativknappen **Ny arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="ea349-142">Välj en **Arbetsordertyp** och en **Beskrivning** i de relaterade fälten.</span><span class="sxs-lookup"><span data-stu-id="ea349-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="ea349-143">Vid behov kan du ändra servicenivån för arbetsorder i fältet **Servicenivå**.</span><span class="sxs-lookup"><span data-stu-id="ea349-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="ea349-144">Ange förväntade start- och slutdatum i de relaterade fälten.</span><span class="sxs-lookup"><span data-stu-id="ea349-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="ea349-145">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea349-145">Click **OK**.</span></span> <span data-ttu-id="ea349-146">Den nya relaterade arbetsordern visas i listan **Alla arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="ea349-147">Om du skapar en relaterad arbetsorder för en arbetsorder som redan har relaterade arbetsorder, kan du lägga till arbetsorderjobbet till en redan relaterad arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="ea349-148">Detta gör du genom att klicka på alternativknappen **Lägg till i relaterad arbetsorder** i steg 6.</span><span class="sxs-lookup"><span data-stu-id="ea349-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="ea349-149">Sedan väljer du den relaterade arbetsorder som du vill lägga till ett nytt arbetsorderjobb i.</span><span class="sxs-lookup"><span data-stu-id="ea349-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="ea349-150">Redigera fälten **Servicenivå**, **Förväntad start** och **Förväntat slut** och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea349-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="ea349-151">Arbetsorderjobbet läggs till i befintlig relaterad arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-151">The work order job is added to the existing related work order.</span></span>


![Figur 1](media/03-work-orders.png)

<span data-ttu-id="ea349-153">**Obs!** Om du har angett en relaterad arbetsordermask i **Parametrar för tillgångshantering** >  länken **Arbetsorder** > fältet **Relaterad arbetsordermask** skapas arbetsorder-ID enligt inställningen för masken.</span><span class="sxs-lookup"><span data-stu-id="ea349-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="ea349-154">Om ingen relaterad arbetsordermask ställs in används nästa tillgängliga arbetsorder-ID för relaterade arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="ea349-155">Kopiera arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ea349-155">Copy work order</span></span>

<span data-ttu-id="ea349-156">Det är möjligt att snabbt skapa en ny arbetsorder utifrån en befintlig arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ea349-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="ea349-157">Det här sättet att arbeta med arbetsorder skiljer sig från att skapa arbetsorder utifrån underhållsplaner.</span><span class="sxs-lookup"><span data-stu-id="ea349-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="ea349-158">Det är användbart om du till exempel har en arbetsorder som innehåller många arbetsorderjobb med olika jobb för olika till gångar som ska slutföras med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="ea349-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="ea349-159">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ea349-160">Välj den arbetsorder från vilken du vill kopiera innehållet.</span><span class="sxs-lookup"><span data-stu-id="ea349-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="ea349-161">Klicka på **Kopiera arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-161">Click **Copy work order**.</span></span> <span data-ttu-id="ea349-162">Inställningarna för arbetsorder från den valda arbetsordern visas.</span><span class="sxs-lookup"><span data-stu-id="ea349-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="ea349-163">Om det behövs kan du redigera vissa av fälten.</span><span class="sxs-lookup"><span data-stu-id="ea349-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="ea349-164">Klicka på **OK** för att skapa den nya arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="ea349-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="ea349-165">Redigera arbetsordern i **Alla arbetsorder** om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ea349-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="ea349-166">När den nya arbetsordern skapas kopieras viss information direkt från den befintliga arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="ea349-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="ea349-167">Information om prognoser, verktyg, underhållschecklistor, funktionsplatser, adresser och tidsplanering kopieras inte, utan initieras från de aktuella inställningarna i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="ea349-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="ea349-168">Det innebär att om ändringar har gjorts i dessa data från tidpunkten för skapandet av den första arbetsordern tills du gjorde en kopia av arbetsordern, inkluderas dessa ändringar i den nya arbetsordern som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="ea349-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="ea349-169">Exempel är ändringar i prognoser eller uppdaterade underhållschecklistor.</span><span class="sxs-lookup"><span data-stu-id="ea349-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Figur 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="ea349-171">Skapa en arbetsorder baserad på en underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="ea349-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="ea349-172">Klicka på **Tillgångshantering** > **Allmänt** > **Underhållsbegäranden** > **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden**.</span><span class="sxs-lookup"><span data-stu-id="ea349-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="ea349-173">Välj den underhållsbegäran som du vill skapa en arbetsorder för och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="ea349-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="ea349-174">I **Alla begäranden**, klicka på **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="ea349-175">Fyll i listrutan **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="ea349-176">Om en underhållsjobbtyp har valts i underhållsbegäran kan du välja en annan underhållsjobbtyp om det behövs, när du skapar arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="ea349-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="ea349-177">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea349-177">Click **OK**.</span></span> <span data-ttu-id="ea349-178">Ett meddelande visas som informerar dig om att arbetsordern har skapats.</span><span class="sxs-lookup"><span data-stu-id="ea349-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="ea349-179">Om du vill se vilka arbetsorder som är kopplade till en underhållsbegäran väljer du underhållsbegäran i listan **Alla underhållsbegäranden** eller **Aktiva underhållsbegäranden** och klickar på knappen **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ea349-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Figur 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="ea349-181">Arbetsorder kan också skapas automatiskt genom planering av underhållsplanjobb, eller genom att ställa in underhållsplaner eller underhållsomgångar för Autoskapa på en tillgång.</span><span class="sxs-lookup"><span data-stu-id="ea349-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="ea349-182">Arbetsorder som skapas från underhållsbegäranden i **Underhållsschema** skapas med de underhållsjobbtyper som väljs i underhållsbegärandena.</span><span class="sxs-lookup"><span data-stu-id="ea349-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

