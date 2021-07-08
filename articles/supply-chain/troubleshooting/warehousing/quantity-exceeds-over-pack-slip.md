---
title: Kvantiteten överskrider procentsatsen för överleverans under genereringen av följesedeln
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider överleveransprocenten.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249172"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="0b527-103">Kvantiteten överskrider procentsatsen för överleverans under genereringen av följesedeln</span><span class="sxs-lookup"><span data-stu-id="0b527-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="0b527-104">Felkod: SYS24920</span><span class="sxs-lookup"><span data-stu-id="0b527-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="0b527-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="0b527-105">Symptoms</span></span>

<span data-ttu-id="0b527-106">När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="0b527-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="0b527-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="0b527-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="0b527-108">Överleverans av raden är %1 procent men tillåten överleverans är bara %2 procent.</span><span class="sxs-lookup"><span data-stu-id="0b527-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="0b527-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="0b527-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="0b527-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="0b527-110">Cause</span></span>

<span data-ttu-id="0b527-111">Den plockade kvantiteten för beläggningen eller leveransen är större än den beställda kvantiteten och ligger inte inom intervallet för överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="0b527-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="0b527-112">Lösning</span><span class="sxs-lookup"><span data-stu-id="0b527-112">Resolution</span></span>

<span data-ttu-id="0b527-113">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="0b527-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="0b527-114">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="0b527-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="0b527-115">Justera kvantiteten för beläggningsrad.</span><span class="sxs-lookup"><span data-stu-id="0b527-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="0b527-116">Justera procentsats för överleverans.</span><span class="sxs-lookup"><span data-stu-id="0b527-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="0b527-117">Återför och gör justeringar.</span><span class="sxs-lookup"><span data-stu-id="0b527-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="0b527-118">Justera kvantiteten för beläggningsrad</span><span class="sxs-lookup"><span data-stu-id="0b527-118">Adjust the load line quantity</span></span>

<span data-ttu-id="0b527-119">Använd följande procedur för att justera lastradkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0b527-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="0b527-120">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="0b527-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0b527-121">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="0b527-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="0b527-122">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="0b527-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="0b527-123">På fliken  **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleveransens procentsats.</span><span class="sxs-lookup"><span data-stu-id="0b527-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="0b527-124">Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="0b527-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="0b527-125">På fliken  **Radinformation** väljer du **Order**.</span><span class="sxs-lookup"><span data-stu-id="0b527-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="0b527-126">I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att generering av följesedel kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="0b527-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="0b527-127">Justera procentsats för överleverans</span><span class="sxs-lookup"><span data-stu-id="0b527-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="0b527-128">Använd följande procedur för att justera procentsats för överleverans.</span><span class="sxs-lookup"><span data-stu-id="0b527-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="0b527-129">Gå till **Kundreskontra \> Order \> Alla order**.</span><span class="sxs-lookup"><span data-stu-id="0b527-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="0b527-130">Välj den försäljningsorder som du inte kan bokföra en följesedel för.</span><span class="sxs-lookup"><span data-stu-id="0b527-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="0b527-131">På fliken  **Försäljningsorderrader** markerar du försäljningsorderraden för den artikel som överskrider överleveransens procentsats.</span><span class="sxs-lookup"><span data-stu-id="0b527-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="0b527-132">På fliken  **Radinformation** väljer du **Leverans**.</span><span class="sxs-lookup"><span data-stu-id="0b527-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="0b527-133">I fältet **Överleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot generering av följesedel kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="0b527-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="0b527-134">Återför och gör justeringar</span><span class="sxs-lookup"><span data-stu-id="0b527-134">Reverse and make adjustments</span></span>

<span data-ttu-id="0b527-135">Återför allt som har bokförts för lasten (till exempel följesedel, leveransbekräftelse och arbete), gör försäljningsorder justeringar, frisläpp ordern till lagerstället och slutför försändelseproceduren.</span><span class="sxs-lookup"><span data-stu-id="0b527-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="0b527-136">Använd följande procedur när du annullerar en följesedel.</span><span class="sxs-lookup"><span data-stu-id="0b527-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="0b527-137">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="0b527-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0b527-138">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Annullera följesedel**.</span><span class="sxs-lookup"><span data-stu-id="0b527-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="0b527-139">Använd följande procedur när du återför en försändelsebekräftelse.</span><span class="sxs-lookup"><span data-stu-id="0b527-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="0b527-140">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="0b527-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0b527-141">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="0b527-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="0b527-142">Gör på följande sätt för att återföra arbete.</span><span class="sxs-lookup"><span data-stu-id="0b527-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="0b527-143">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="0b527-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0b527-144">I åtgärdsfönstret, på fliken  **Laster**, i gruppen  **Arbete**, väljer du  **återför arbete**.</span><span class="sxs-lookup"><span data-stu-id="0b527-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
