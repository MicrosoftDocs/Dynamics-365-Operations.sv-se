---
title: Kvantiteten kan inte reduceras när en försäljningsorder annulleras
description: Kvantiteten kan inte reduceras när en försäljningsorder annulleras.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230846"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="affd5-103">Kvantiteten kan inte reduceras när en försäljningsorder annulleras</span><span class="sxs-lookup"><span data-stu-id="affd5-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="affd5-104">Felkod: SYS138831</span><span class="sxs-lookup"><span data-stu-id="affd5-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="affd5-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="affd5-105">Symptoms</span></span>

<span data-ttu-id="affd5-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="affd5-106">The system shows the following error message:</span></span>

> <span data-ttu-id="affd5-107">Kvantiteten kan inte reduceras.</span><span class="sxs-lookup"><span data-stu-id="affd5-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="affd5-108">Antalet lagertransaktioner för order är för lågt eftersom kvantiteten eller en del av denna refereras till av en utleveransorder eller en tillverkningsorder, eller är markerad mot andra transaktioner.</span><span class="sxs-lookup"><span data-stu-id="affd5-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="affd5-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="affd5-109">Cause</span></span>

<span data-ttu-id="affd5-110">Om arbete associeras med en försäljningsorder kan du inte annullera försäljningsordern förrän arbetet har annullerats och återförts.</span><span class="sxs-lookup"><span data-stu-id="affd5-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="affd5-111">Detta krav gäller även om det arbete som är kopplat till försäljningsordern stängs.</span><span class="sxs-lookup"><span data-stu-id="affd5-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="affd5-112">Lösning</span><span class="sxs-lookup"><span data-stu-id="affd5-112">Resolution</span></span>

<span data-ttu-id="affd5-113">Utför följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="affd5-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="affd5-114">Avbryt det öppna arbetet.</span><span class="sxs-lookup"><span data-stu-id="affd5-114">Cancel open work.</span></span>
1. <span data-ttu-id="affd5-115">Ta bort lasten.</span><span class="sxs-lookup"><span data-stu-id="affd5-115">Delete the load.</span></span>
1. <span data-ttu-id="affd5-116">Minska plockad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="affd5-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="affd5-117">Avbryt det öppna arbetet</span><span class="sxs-lookup"><span data-stu-id="affd5-117">Cancel open work</span></span>

<span data-ttu-id="affd5-118">Om du vill avbryta det öppna arbetet följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="affd5-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="affd5-119">Gå till **Lagerstyrning \> Periodiska uppgifter \> Rensa upp \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="affd5-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="affd5-120">I fältet **Arbets-ID** anger du ID:t för det arbete du vill avbryta och som i nuläget har ett värde för **Arbetsstatus** som är antingen *Öppen*, *Pågår*, *Avbruten*, *Kombinerad* eller *Stängd*.</span><span class="sxs-lookup"><span data-stu-id="affd5-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="affd5-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="affd5-121">Select **OK**.</span></span>
1. <span data-ttu-id="affd5-122">Välj **Ja** för att bekräfta att du vill avbryta arbetet.</span><span class="sxs-lookup"><span data-stu-id="affd5-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="affd5-123">Ta bort beläggningen</span><span class="sxs-lookup"><span data-stu-id="affd5-123">Delete the load</span></span>

<span data-ttu-id="affd5-124">Följ dessa steg om du vill ta bort en beläggning:</span><span class="sxs-lookup"><span data-stu-id="affd5-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="affd5-125">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="affd5-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="affd5-126">Öppna relevant försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="affd5-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="affd5-127">På snabbfliken **Försäljningsorderrader** väljer du **Lagerställe \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="affd5-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="affd5-128">I fönstret **Arbete**, på sidan Åtgärder > fliken **Arbete** > gruppen **Arbete** väljer du **Annullera arbete**.</span><span class="sxs-lookup"><span data-stu-id="affd5-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="affd5-129">Bekräfta att fältet **Arbetsstatus** är inställt *Annulerat*.</span><span class="sxs-lookup"><span data-stu-id="affd5-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="affd5-130">Stäng sidan **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="affd5-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="affd5-131">På sidan för försäljningsorderdetaljer, på snabbfliken **Försäljningsorderrader**, väljer du **Lagerställe \> Beläggningsinformation**.</span><span class="sxs-lookup"><span data-stu-id="affd5-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="affd5-132">Välj sedan **Ta bort** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="affd5-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="affd5-133">Välj **Ja** för att bekräfta att du vill ta bort beläggningen.</span><span class="sxs-lookup"><span data-stu-id="affd5-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="affd5-134">Stäng sidan **Beläggning**.</span><span class="sxs-lookup"><span data-stu-id="affd5-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="affd5-135">Minska plockad kvantitet</span><span class="sxs-lookup"><span data-stu-id="affd5-135">Reduce the picked quantity</span></span>

<span data-ttu-id="affd5-136">När allt arbete har annullerats följer du dessa steg för att minska den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="affd5-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="affd5-137">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="affd5-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="affd5-138">Öppna relevant försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="affd5-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="affd5-139">På snabbfliken **Försäljningsorderrader** väljer du **Uppdatera rad \> Plock** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="affd5-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="affd5-140">På sidan **Plock**, i avsnittet **Transaktioner**, markerar du raden där ut fältet **Ärendestatus** är inställt på *Plockad*.</span><span class="sxs-lookup"><span data-stu-id="affd5-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="affd5-141">I avsnittet **Transaktioner** väljer du **Lägg till plockrad** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="affd5-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="affd5-142">I avsnittet **Plockrader** väljer du **Bekräfta Plocka alla** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="affd5-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="affd5-143">Stäng sidan **Plock**.</span><span class="sxs-lookup"><span data-stu-id="affd5-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="affd5-144">På sidan försäljningsorderdetaljer i åtgärdsfönstret väljer du på fliken **Försäljningsorder** > gruppen **Underhåll** > **Annullera**.</span><span class="sxs-lookup"><span data-stu-id="affd5-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="affd5-145">Välj **Ja** för att bekräfta att du vill annullera försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="affd5-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
