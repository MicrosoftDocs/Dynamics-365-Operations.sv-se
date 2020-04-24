---
title: Underhållsarbetare och arbetargrupper
description: I det här avsnittet beskrivs hur du ställer in underhållsarbetare och arbetargrupper i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cf7e8e796032b348cff5a77c10b376dbbeef974
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214792"
---
# <a name="maintenance-workers-and-worker-groups"></a><span data-ttu-id="b7fde-103">Underhållsarbetare och arbetargrupper</span><span class="sxs-lookup"><span data-stu-id="b7fde-103">Maintenance workers and worker groups</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="b7fde-104">I det här avsnittet beskrivs hur du ställer in underhållsarbetare och arbetargrupper i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="b7fde-104">This topic explains maintenance workers and worker groups in Asset Management.</span></span> <span data-ttu-id="b7fde-105">I tillgångshantering kan du ansluta underhållsarbetare till funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="b7fde-105">In Asset Management, you can connect maintenance workers to functional locations.</span></span> <span data-ttu-id="b7fde-106">(Mer information om funktionsplatser finns i [skapa funktionsplatser](../functional-locations/create-functional-locations.md).) Den här funktionen kan vara användbar om du till exempel schemalägger ett underhållsjobb på en dator som finns i funktionsplats 01 och du vill allokera underhållsarbetare från samma plats för att utföra jobbet.</span><span class="sxs-lookup"><span data-stu-id="b7fde-106">(For more information about functional locations, see [Create functional locations](../functional-locations/create-functional-locations.md).) This functionality might be useful if, for example, you're scheduling a maintenance job on a machine that is located in functional location 01, and you want to allocate maintenance workers from the same location to perform the job.</span></span>

<span data-ttu-id="b7fde-107">Du kan också skapa underhållsarbetargrupper och associera underhållsarbetare med dem.</span><span class="sxs-lookup"><span data-stu-id="b7fde-107">You can also create maintenance worker groups and associate maintenance workers with them.</span></span> <span data-ttu-id="b7fde-108">Den här funktionen är användbar när du gör enkla arbetsorderplaneringar och du vill planera en grupp av underhållsarbetare på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b7fde-108">This functionality is useful when you do simple work order scheduling, and you want to schedule a group of maintenance workers on a work order.</span></span> <span data-ttu-id="b7fde-109">Du kan använda underhållsarbetare och underhållsarbetsgrupper för att ställa in önskade underhållsarbetare och ansvariga underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="b7fde-109">You can use maintenance workers and maintenance worker groups to set up preferred maintenance workers and responsible maintenance workers.</span></span> 


## <a name="create-workers"></a><span data-ttu-id="b7fde-110">Skapa arbetare</span><span class="sxs-lookup"><span data-stu-id="b7fde-110">Create workers</span></span>

1. <span data-ttu-id="b7fde-111">Välj **tillgångshantering** \> **inställning** \> **arbetare** \> **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-111">Select **Asset management** \> **Setup** \> **Workers** \> **Workers**.</span></span>
2. <span data-ttu-id="b7fde-112">Välj **Ny** om du vill lägga till en arbetare till listan.</span><span class="sxs-lookup"><span data-stu-id="b7fde-112">Select **New** to add a worker to the list.</span></span>
3. <span data-ttu-id="b7fde-113">I fältet **arbetare** väljer du arbetaren.</span><span class="sxs-lookup"><span data-stu-id="b7fde-113">In the **Worker** field, select the worker.</span></span>
4. <span data-ttu-id="b7fde-114">Ange alternativet **aktiva** till **ja** för att schemalägga arbetaren på arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b7fde-114">Set the **Active** option to **Yes** to schedule the worker on work orders.</span></span>

    <span data-ttu-id="b7fde-115">På snabbfliken **allmänt** fylls fälten **resurs** och **beskrivning** i automatiskt om en resurs har valts för medarbetaren.</span><span class="sxs-lookup"><span data-stu-id="b7fde-115">On the **General** FastTab, the **Resource** and **Description** fields are automatically filled in if a resource has been selected for the worker.</span></span> <span data-ttu-id="b7fde-116">Fältet **kalender** fylls också i automatiskt, förutsatt att du har ställt in arbetaren som en resurs och tilldelat en kalender till den resursen på sidan **resurser** (**Organisationsadministration** \> **Resurser** \> **Resurser**).</span><span class="sxs-lookup"><span data-stu-id="b7fde-116">The **Calendar** field is also automatically filled in, provided that you've set up the worker as a resource and allocated a calendar to that resource on the **Resources** page (**Organization administration** \> **Resources** \> **Resources**).</span></span>

5. <span data-ttu-id="b7fde-117">På snabbfliken **grupper** väljer du **Lägg till** och väljer sedan en underhållsarbetsgrupp för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="b7fde-117">On the **Groups** FastTab, select **Add**, and then select a maintenance worker group for the worker.</span></span> <span data-ttu-id="b7fde-118">En arbetare kan vara kopplad till fler än en grupp.</span><span class="sxs-lookup"><span data-stu-id="b7fde-118">A worker can be affiliated with more than one group.</span></span>
6. <span data-ttu-id="b7fde-119">I standardkonfigurationen gäller en arbetares tillhörighet till en grupp från det datum då du lägger till gruppen och den upphör aldrig att gälla.</span><span class="sxs-lookup"><span data-stu-id="b7fde-119">In the standard setup, a worker's affiliation with a group is effective from the date when you add the group, and it never expires.</span></span> <span data-ttu-id="b7fde-120">Detta datum visas i fältet **gällande**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-120">This date is shown in the **Effective** field.</span></span> <span data-ttu-id="b7fde-121">För att visa fältet **Giltighet** väljer du **Visa** \> **Alla**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-121">To see the **Effective** field, select **View** \> **All**.</span></span> <span data-ttu-id="b7fde-122">Om medarbetarens tillhörighet till en grupp ska begränsas till en viss period använder du fälten **Giltighet** och **Utgång** för att definiera perioden.</span><span class="sxs-lookup"><span data-stu-id="b7fde-122">If the worker's affiliation with a group should be limited to a specific period, use the **Effective** and **Expiration** fields to define the period.</span></span>
7. <span data-ttu-id="b7fde-123">På snabbfliken **funktionsplatser** väljer du **Lägg till** och väljer sedan en funktionsplatser för underhållsarbetaren.</span><span class="sxs-lookup"><span data-stu-id="b7fde-123">On the **Functional locations** FastTab, select **Add**, and then select a functional location for the maintenance worker.</span></span> <span data-ttu-id="b7fde-124">Ange även vilken plats som är den primära funktionsplatsen för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="b7fde-124">Also specify which location is the primary functional location for the worker.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7fde-125">När du lägger till funktionsplatser till en arbetare, visas alla aktiva tillgångar som är relaterade till dessa funktionsplatser på olika menyalternativ, till exempel **mina aktiva tillgångar** och **mina aktiva funktionsplatser**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-125">When you add functional locations to a worker, all active assets that are related to those functional locations appear on various menu items, such as **My active assets** and **My active functional locations**.</span></span> <span data-ttu-id="b7fde-126">De visas också i tillgångsuppslag som visas när du skapar en ny tillgång, underhållsbegäran eller arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b7fde-126">They also appear in the asset lookups that are shown when you create a new asset, maintenance request, or work order.</span></span>

    <span data-ttu-id="b7fde-127">Fälten på snabbfliken **Detaljer** visar antalet underhålls arbetsgrupper och funktionsplatser som den valda underhållsarbetaren är relaterad till.</span><span class="sxs-lookup"><span data-stu-id="b7fde-127">The fields on the **Details** FastTab show the number of maintenance worker groups and functional locations that the selected maintenance worker is related to.</span></span>

## <a name="create-worker-groups"></a><span data-ttu-id="b7fde-128">Skapa arbetargrupper</span><span class="sxs-lookup"><span data-stu-id="b7fde-128">Create worker groups</span></span>

1. <span data-ttu-id="b7fde-129">Välj **tillgångshantering** \> **inställning** \> **arbetare** \> **underhållsarbetargrupper**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-129">Select **Asset management** \> **Setup** \> **Workers** \> **Maintenance worker groups**.</span></span>
2. <span data-ttu-id="b7fde-130">Välj **Ny** om du vill lägga till en arbetargrupp till listan.</span><span class="sxs-lookup"><span data-stu-id="b7fde-130">Select **New** to add a worker group to the list.</span></span>
3. <span data-ttu-id="b7fde-131">I fältet **underhållsarbetargrupp** anger du ett grupp-ID.</span><span class="sxs-lookup"><span data-stu-id="b7fde-131">In the **Maintenance worker group** field, enter a group ID.</span></span>
4. <span data-ttu-id="b7fde-132">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-132">In the **Name** field, enter a name.</span></span>
5. <span data-ttu-id="b7fde-133">På snabbfliken **arbetare** väljer du **Lägg till** och väljer sedan en underhållsarbetsgrupp för arbetargruppen.</span><span class="sxs-lookup"><span data-stu-id="b7fde-133">On the **Workers** FastTab, select **Add**, and then select a maintenance worker for the worker group.</span></span> <span data-ttu-id="b7fde-134">Information om fälten **giltighet** och **utgång** finns i steg 6 i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="b7fde-134">For information about the **Effective** and **Expiration** fields, see step 6 in the previous procedure.</span></span>
6. <span data-ttu-id="b7fde-135">Om en resursgrupp ska relateras till den valda gruppen för underhållsarbetare väljer du **kopiera från resursgrupp**.</span><span class="sxs-lookup"><span data-stu-id="b7fde-135">If a resource group should be related to the selected maintenance worker group, select **Copy from resource group**.</span></span> <span data-ttu-id="b7fde-136">i fältet **grupp** väljer du den resursgrupp som du vill kopiera kalenderinställningar från.</span><span class="sxs-lookup"><span data-stu-id="b7fde-136">In the **Group** field, select the resource group to copy calendar settings from.</span></span> <span data-ttu-id="b7fde-137">Välj sedan i fältet **arbetargrupp** den arbetargrupp som du vill kopiera resursgruppens kalenderinställningar till.</span><span class="sxs-lookup"><span data-stu-id="b7fde-137">Then, in the **Worker group** field, select the worker group to copy the resource group's calendar settings to.</span></span> <span data-ttu-id="b7fde-138">Det här steget är endast relevant om du vill att underhållsarbetare ska använda kalendern som är relaterad till en resurs (produktionsgruppen) vid schemaläggning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="b7fde-138">This step is relevant only if you want maintenance workers to use the calendar that is related to a resource (work center) during work order scheduling.</span></span>

    <span data-ttu-id="b7fde-139">Fältet på snabbfliken **Detaljer** visar antalet underhållsarbetare som har ställt in den valda underhållsarbetargruppen.</span><span class="sxs-lookup"><span data-stu-id="b7fde-139">The field on the **Details** FastTab shows the number of maintenance workers that have been set up on the selected maintenance worker group.</span></span>
