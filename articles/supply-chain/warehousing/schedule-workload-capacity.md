---
title: "Tidsplanera kapacitet för lagerställe"
description: "Det här avsnittet beskrivs hur du ställer in och schemalägger den arbetsbelastningskapacitet för arbetare i ett lagerställe eller en hel lagerställe."
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2814753f4fece38274f216a881c608cc40c49185
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="schedule-workload-capacity"></a><span data-ttu-id="87cbb-103">Tidsplanera kapacitet för lagerställe</span><span class="sxs-lookup"><span data-stu-id="87cbb-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="87cbb-104">Du kan tidsplanera arbetsbördakapacitet för lagerställen och även förutse de aktuella och framtida arbetsbördorna för arbetarna i enskilda lagerställen.</span><span class="sxs-lookup"><span data-stu-id="87cbb-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="87cbb-105">Du kan förutse arbetsbelastningen för hela lagerstället, eller så kan du förutse arbetsbelastningen separat för inkommande och utgående arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="87cbb-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="87cbb-106">Om du förutser arbetsbelastningen som tillverkats för valda huvudplaneringdata, måste lagerställen vara tillgängliga för de valda lagerställen.</span><span class="sxs-lookup"><span data-stu-id="87cbb-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="87cbb-107">För mer information se [Huvudplaner](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="87cbb-107">For more information, see [Master plans](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="87cbb-108">Tidsplanera och visa arbetsbördor för ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="87cbb-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="87cbb-109">Om du vill Tidsplaneringen för arbetsbördakapacitet för ett lagerställe, skapar du en arbetsbelastning som har ställts in för en eller flera lagerställen, och kopplar sedan den arbetsbelastningen med en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="87cbb-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="87cbb-110">I arbetsbördakapacitetinställningar kan du definiera gränser för vikt och volym för inkommande och utgående transaktioner.</span><span class="sxs-lookup"><span data-stu-id="87cbb-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="87cbb-111">Du kan också skapa fler än en inställning för varje lagerställe, och sedan koppla enskilda inställningen med huvudplaner.</span><span class="sxs-lookup"><span data-stu-id="87cbb-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="87cbb-112">Du kan till exempel göra detta för att rätta säsongsbetonade ändringar i Personal.</span><span class="sxs-lookup"><span data-stu-id="87cbb-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="87cbb-113">Om arbetarna för ett lagerställe arbetar med transaktioner för både inkommande och utgående arbetsbelastningar, kan du konfigurera lagerställekapacitetinställningar till att förutse arbetsbelastningen i en kombinerad vyn.</span><span class="sxs-lookup"><span data-stu-id="87cbb-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="87cbb-114">Du planering och visa arbetsbelastningar för lagerställen måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="87cbb-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="87cbb-115">Skapa en arbetsbördakapacitetinställning och definiera arbetsbördakapacitetgränser för ett eller flera lagerställen.</span><span class="sxs-lookup"><span data-stu-id="87cbb-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="87cbb-116">Koppla arbetsbördakapacitetinställningar med en huvudplan för att skapa arbetsbördaprojektioner och för att ange hur länge projektionerna ska gälla.</span><span class="sxs-lookup"><span data-stu-id="87cbb-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="87cbb-117">Skapa en arbetsbördakapacitetinställning för ett lagerställe</span><span class="sxs-lookup"><span data-stu-id="87cbb-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="87cbb-118">Välj **lagerhantering**\>**inställningar**\>**Övervakning av lagerställe**\>**Arbetsbelastningskapacitet**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="87cbb-119">I åtgärdsfönstret, välj **Ny** för att skapa en inställning för arbetsbelastningskapacitet.</span><span class="sxs-lookup"><span data-stu-id="87cbb-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="87cbb-120">På snabbfliken **Lagerställen** väljer du **Ny** och anger sedan värden på raden som ska associeras med arbetsbördakapacitetinställningar ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="87cbb-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="87cbb-121">Välj kryssrutan **Kombinerade arbetsbelastningen för inkommande och utgående** om rapporten **arbetsbelastningskapacitet** visa den totala arbetsbelastningen för inkommande och utgående transaktioner i en enda vy.</span><span class="sxs-lookup"><span data-stu-id="87cbb-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="87cbb-122">Välj inkommande och utgående arbetsbördagränserna för de transaktionstyper som ska användas för, på snabbfliken **Transaktionstyper**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87cbb-123">Du måste välja minst en transaktionstyp för både inkommande och utgående arbetsbördorna.</span><span class="sxs-lookup"><span data-stu-id="87cbb-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="87cbb-124">Definiera gränser för volym eller vikt</span><span class="sxs-lookup"><span data-stu-id="87cbb-124">Define limits for volume or weight</span></span>

<span data-ttu-id="87cbb-125">Du kan ställa in gränser för vikt och volym, beroende på begränsningar som är relevant för lagerställepersonalen.</span><span class="sxs-lookup"><span data-stu-id="87cbb-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="87cbb-126">Gränserna som du anger, inkluderas i arbetsbördakapacitetprojektionen som du kan visa i rapporten **arbetsbördakapacitet**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="87cbb-127">Till projektinformation om volym och vikt för artiklar, måste standardvolym för en artikel i lager och vikt för en lagerartikel, anges för alla produkter.</span><span class="sxs-lookup"><span data-stu-id="87cbb-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="87cbb-128">Obligatoriska fält är tillgängliga i följande fältgrupper på snabbfliken **hantera lager** på sidan **Information om frisläppt produkt**:</span><span class="sxs-lookup"><span data-stu-id="87cbb-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="87cbb-129">Hantering</span><span class="sxs-lookup"><span data-stu-id="87cbb-129">Handling</span></span>
- <span data-ttu-id="87cbb-130">Fysiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="87cbb-130">Physical dimensions</span></span>
- <span data-ttu-id="87cbb-131">Viktmått</span><span class="sxs-lookup"><span data-stu-id="87cbb-131">Weight measurements</span></span>

<span data-ttu-id="87cbb-132">Om den här informationen inte anges korrekt, visas ett meddelande när du genererar rapporten **Arbetsbelastningskapacitet**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="87cbb-133">Från rapporten kan du gå ner för att identifiera den information som saknas till förutse den framtida arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="87cbb-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="87cbb-134">Koppla en in arbetsbördakapacitetinställning med en huvudplan</span><span class="sxs-lookup"><span data-stu-id="87cbb-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="87cbb-135">Välj **Lagerhantering** \> **Periodiska uppgifter** \> **Tidsplanera arbetsbelastning**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="87cbb-136">Välj den huvudplan som ska användas för arbetsbördaprojektioner, i fältet **huvudplan**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="87cbb-137">Ange det antal dagar som täcker arbetsbördaprojektionen, i fältet **Antal dagar**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="87cbb-138">Välj arbetsbördainställningar som ska associeras med huvudplanen i fältet **arbetsbörda**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="87cbb-139">Visa arbetsbelastningskapacitet</span><span class="sxs-lookup"><span data-stu-id="87cbb-139">View workload capacity</span></span>

1. <span data-ttu-id="87cbb-140">Välj **lagerhantering**\>**förfrågningar och rapporter**\>**Rapporter om fysiskt lager**\>**Arbetsbelastningskapacitet**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="87cbb-141">Ange det antal kolumner som ska visas på rapporten, i fältet **Antal kolumner**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="87cbb-142">På fältet **Ordertyp** välj **planerat och bekräftat**, **planerat**, eller **bekräftat** för att bestämma vilken typ av order till projekt i rapporten.</span><span class="sxs-lookup"><span data-stu-id="87cbb-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="87cbb-143">Välj en beläggningtyp om du vill visa att arbetsbördakapaciteten ska förutses för volym eller vikt, i fältet **Beläggningstyp**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="87cbb-144">Välj en inställning för arbetsbelastningskapacitet i fältet **Arbetsbelastningskapacitet**.</span><span class="sxs-lookup"><span data-stu-id="87cbb-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>

