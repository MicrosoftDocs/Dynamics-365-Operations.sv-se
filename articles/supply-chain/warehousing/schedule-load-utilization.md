---
title: Tidsplanera beläggningsutnyttjande
description: Det här avsnittet beskriver hur du ställer in och schemalägger beläggningen för ett lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88dc44b036f6d5535f7e83693a387149f94f37d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239264"
---
# <a name="schedule-load-utilization"></a><span data-ttu-id="4496c-103">Tidsplanera beläggningsutnyttjande</span><span class="sxs-lookup"><span data-stu-id="4496c-103">Schedule load utilization</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4496c-104">Du kan tidsplanera beläggningsutnyttjande för valda platstyper och även planera nuvarande och framtida beläggningsutnyttjande.</span><span class="sxs-lookup"><span data-stu-id="4496c-104">You can schedule load utilization for selected location types, and you can also project the current and future load utilization.</span></span> <span data-ttu-id="4496c-105">Du kan planera belastningen för en eller flera platser för beläggningenheterna i lagerstället eller zonen, eller för en kombination av zonen och lagerstället.</span><span class="sxs-lookup"><span data-stu-id="4496c-105">You can project the load for one or more sites, for the load units (zone or warehouse), or for a combination of a zone and a warehouse.</span></span>

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a><span data-ttu-id="4496c-106">Tidsplanera och visa beläggningen för ett lagerställe eller en plats</span><span class="sxs-lookup"><span data-stu-id="4496c-106">Schedule and view the load for a warehouse or site</span></span>

<span data-ttu-id="4496c-107">Om du vill tidsplanera beläggningen för platser, lagerställen och zoner skapar du en inställning för utrymmesutnyttjande och kopplar den till en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="4496c-107">To schedule the load for sites, warehouses, or zones, you create a space utilization setup and associate it with a master plan.</span></span>

<span data-ttu-id="4496c-108">I utrymmesutnyttjandeinställningen använder du platstyper, t.ex. **Bulkplats** och **Plockplats**, för att ange hur utrymmesutnyttjande bör planeras.</span><span class="sxs-lookup"><span data-stu-id="4496c-108">In the space utilization setup, you use location types, such as **Bulk location** and **Picking location**, to specify how space utilization should be projected.</span></span> <span data-ttu-id="4496c-109">Du kan även ange ett lagerbeläggningläge, till exempel **Zon**.</span><span class="sxs-lookup"><span data-stu-id="4496c-109">You also specify a storage load mode, such as **Zone**.</span></span>

<span data-ttu-id="4496c-110">Planeringen av framtida utrymmesutnyttjande baseras på information som beräknas från den associerade huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="4496c-110">The projection of future space utilization is based on information that is calculated on the associated master plan.</span></span> <span data-ttu-id="4496c-111">Huvudplanerna resursplanerar inför inkommande och utgående order för produktion och operationer.</span><span class="sxs-lookup"><span data-stu-id="4496c-111">Master plans forecast the resource planning for incoming and outgoing orders for production and operations.</span></span> <span data-ttu-id="4496c-112">Planeringen av tillgängligt för utrymme baseras på relationen mellan det inställda utrymmesutnyttjandet och den valda huvudplanen.</span><span class="sxs-lookup"><span data-stu-id="4496c-112">The projection of available space is based on the relation between the space utilization setup and the selected master plan.</span></span>

<span data-ttu-id="4496c-113">Genom att använda lagerbeläggningsläget, som du väljer i utrymmesutnyttjandesinställningen, anger du om beläggningen ska planeras för respektive lagerställe eller zon, eller om planeringen ska innehålla information om både lagerställe och zon.</span><span class="sxs-lookup"><span data-stu-id="4496c-113">By using the storage load mode that you selected in the space utilization setup, you can specify whether the load should be projected for each warehouse or zone, or whether the projections should include information about both warehouses and zones.</span></span> <span data-ttu-id="4496c-114">Du kan också ange om spärrade platser ska utelämnas från beräkningen av beläggningsutnyttjandet.</span><span class="sxs-lookup"><span data-stu-id="4496c-114">You also specify whether blocked locations should be excluded from the calculation of load utilization.</span></span>

<span data-ttu-id="4496c-115">Du kan planera ut utrymmesutnyttjande genom att generera rapporten **beläggningsutnyttjande för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="4496c-115">You can project the space utilization by generating the **Warehouse load utilization** report.</span></span> <span data-ttu-id="4496c-116">När du genererar rapporten kan du ange om beläggningsutnyttjandet ska planeras för varje plats eller mellan platser, eller för den valda beläggningsenheten, till exempel zon eller lagerställen.</span><span class="sxs-lookup"><span data-stu-id="4496c-116">When you generate this report, you can specify whether the load utilization should be projected for each site, across sites, or for the selected load unit, such as zone or warehouse.</span></span>

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a><span data-ttu-id="4496c-117">Skapa ett utrymmesutnyttjande som har ställts in för ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="4496c-117">Create a space utilization setup for a warehouse</span></span>

1. <span data-ttu-id="4496c-118">Välj **lagerhantering**\>**inställningar**\>**Övervakning av lagerställe**\>**Utrymmesutnyttjande**.</span><span class="sxs-lookup"><span data-stu-id="4496c-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Space utilization**.</span></span>
2. <span data-ttu-id="4496c-119">Klicka på **Ny** om du vill skapa en ny utrymmesutnyttjandeinställning.</span><span class="sxs-lookup"><span data-stu-id="4496c-119">Select **New** to create a space utilization setup.</span></span> <span data-ttu-id="4496c-120">Ange ett ID och ett namn för den nya inställningen.</span><span class="sxs-lookup"><span data-stu-id="4496c-120">Specify an ID and a name for the new setup.</span></span>
3. <span data-ttu-id="4496c-121">Välj om översikten över utrymmesutnyttjandet ska vara efter lagerställe, zon eller lagerställe och zon i fältet **Lagringsbeläggningsläge**.</span><span class="sxs-lookup"><span data-stu-id="4496c-121">In the **Storage load mode** field, select whether the overview of space utilization should show information by warehouse, zone, or warehouse and zone.</span></span>
4. <span data-ttu-id="4496c-122">Ange alternativet **exkludera spärrade platser** till **Ja** för att exkludera spärrade lagerplatser från beräkningen av tillgängligt utrymme.</span><span class="sxs-lookup"><span data-stu-id="4496c-122">Set the **Exclude blocked locations** option to **Yes** to exclude blocked inventory locations from the calculation of available space.</span></span> <span data-ttu-id="4496c-123">Du kan spärra en lagerplats för in- och utleverans genom att ange spärrorsaker för platsen på fälten **Inleverans spärrad** eller **Utleverans spärrad** på snabbfliken **Andra** på sidan **Lagerplatser**.</span><span class="sxs-lookup"><span data-stu-id="4496c-123">You can block an inventory location for input and output by specifying a blocking cause for the location in the **Input blocked** or **Output blocked** field on the **Other** FastTab on the **Inventory locations** page.</span></span>
5. <span data-ttu-id="4496c-124">Välj platstyper som ska inkluderas i utrymmesutnyttjandeberäkningen på snabbfliken **Lagertyp**.</span><span class="sxs-lookup"><span data-stu-id="4496c-124">On the **Location type** FastTab, select the location types to include in the space utilization calculation.</span></span> <span data-ttu-id="4496c-125">Du måste minst välja en platstyp för planeringen.</span><span class="sxs-lookup"><span data-stu-id="4496c-125">You must select at least one location type for the projection.</span></span>

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a><span data-ttu-id="4496c-126">Koppla en utrymmesutnyttjandeinställning till en huvudplan</span><span class="sxs-lookup"><span data-stu-id="4496c-126">Associate a space utilization setup with a master plan</span></span>

1. <span data-ttu-id="4496c-127">Välj **Lagerhantering** \> **Periodiska uppgifter** \> **Tidsplanera beläggningsutnyttjande**.</span><span class="sxs-lookup"><span data-stu-id="4496c-127">Select **Inventory management** \> **Periodic tasks** \> **Schedule load utilization**.</span></span>
2. <span data-ttu-id="4496c-128">Välj en huvudplan i fältet **huvudplan**.</span><span class="sxs-lookup"><span data-stu-id="4496c-128">In the **Master plan** field, select a master plan.</span></span>
3. <span data-ttu-id="4496c-129">I fältet **Antal dagar** ange antalet dagar du vill inkludera i planen för aktuella och framtida arbetsbeläggningar.</span><span class="sxs-lookup"><span data-stu-id="4496c-129">In the **Number of days** field, specify the number of days to include in the projection of current and future workloads.</span></span>
4. <span data-ttu-id="4496c-130">Välj utrymmesutnyttjandeinställning som ska användas för planeringen av aktuella och framtida arbetsbeläggningar i fältet **utrymmesutnyttjande**.</span><span class="sxs-lookup"><span data-stu-id="4496c-130">In the **Space utilization** field, select the space utilization setup to use for the projection of current and future workloads.</span></span>

### <a name="specify-the-load-utilization-projection-and-view-information"></a><span data-ttu-id="4496c-131">Ange och visa information om beläggningsutnyttjandeplanen</span><span class="sxs-lookup"><span data-stu-id="4496c-131">Specify the load utilization projection and view information</span></span>

1. <span data-ttu-id="4496c-132">Välj **lagerhantering**\>**förfrågningar och rapporter**\>**Rapporter om fysiskt lager**\>**beläggningsutnyttjande för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="4496c-132">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Warehouse load utilization**.</span></span>
2. <span data-ttu-id="4496c-133">I fältet **Visa efter** välj planeringen av utrymmesutnyttjandenivån:</span><span class="sxs-lookup"><span data-stu-id="4496c-133">In the **Show by** field, select the level of the space utilization projection:</span></span>

    - <span data-ttu-id="4496c-134">**Plats** – Planera utrymmesutnyttjandet för varje plats.</span><span class="sxs-lookup"><span data-stu-id="4496c-134">**Site** – Project the space utilization for each site.</span></span> <span data-ttu-id="4496c-135">Den här planeringen är praktisk om du till exempel vill visa alla lagerställen för en plats, så att du kan stämma av utrymmesutnyttjandet mellan lagerställen.</span><span class="sxs-lookup"><span data-stu-id="4496c-135">This projection is useful if, for example, you want to view all the warehouses for a site so that you can balance the space utilization between the warehouses.</span></span>
    - <span data-ttu-id="4496c-136">**Beläggningsenhet** – planera utrymmesutnyttjande för zoner eller lagerställen.</span><span class="sxs-lookup"><span data-stu-id="4496c-136">**Load unit** – Project the space utilization for zones or warehouses.</span></span> <span data-ttu-id="4496c-137">Sedan beräknas det tillgängliga utrymmet enligt det värde som du valde i fältet **Lagringsbeläggningsläge** på sidan **Utrymmesutnyttjande** när du har skapat utrymmesutnyttjandeinställningen.</span><span class="sxs-lookup"><span data-stu-id="4496c-137">The available space is then projected according to the value that you selected in the **Storage load mode** field on the **Space utilization** page when you created the space utilization setup.</span></span>

3. <span data-ttu-id="4496c-138">Gör något av följande, beroende på vilket värde du valde i föregående steg:</span><span class="sxs-lookup"><span data-stu-id="4496c-138">Follow one of these steps, depending on the value that you selected in the previous step:</span></span>

    - <span data-ttu-id="4496c-139">Om du valde **Plats** i fältet **Visa efter** är fältet **Plats** tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4496c-139">If you selected **Site** in the **Show by** field, the **Site** field is available.</span></span> <span data-ttu-id="4496c-140">Markera en eller flera platser som ska inkluderas i planeringen i fältet .</span><span class="sxs-lookup"><span data-stu-id="4496c-140">Select one or more sites to include in the projection.</span></span>
    - <span data-ttu-id="4496c-141">Om du valde **Beläggningsenhet** i fältet **Visa efter** är fältet **Beläggningsenhet** tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4496c-141">If you selected **Load unit** in the **Show by** field, the **Load unit** field is available.</span></span> <span data-ttu-id="4496c-142">Välj beläggningsenhet</span><span class="sxs-lookup"><span data-stu-id="4496c-142">Select the load unit.</span></span>

4. <span data-ttu-id="4496c-143">I fältet **Beläggningstyp**, välj **Volym** eller **Vikt** när du vill ange lagerställesdriftenhet för planering av utrymme.</span><span class="sxs-lookup"><span data-stu-id="4496c-143">In the **Load type** field, select **Volume** or **Weight** to specify the warehouse operating unit to project space for.</span></span>
5. <span data-ttu-id="4496c-144">I fältet **inställningar av utrymmesutnyttjandet**, välj de inställningar av utrymmesutnyttjandet som planeringen ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="4496c-144">In the **Space utilization setup** field, select the space utilization setup that the projection should be based on.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]