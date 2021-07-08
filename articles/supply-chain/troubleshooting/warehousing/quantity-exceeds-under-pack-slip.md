---
title: Kvantiteten underskrider procentsatsen för överleverans under genereringen av följesedeln
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som underskrider överleveransprocenten.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249170"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="b3af2-103">Kvantiteten underskrider procentsatsen för överleverans under genereringen av följesedeln</span><span class="sxs-lookup"><span data-stu-id="b3af2-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="b3af2-104">Felkod: SYS24921</span><span class="sxs-lookup"><span data-stu-id="b3af2-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="b3af2-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="b3af2-105">Symptoms</span></span>

<span data-ttu-id="b3af2-106">När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som underskrider överleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="b3af2-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="b3af2-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="b3af2-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="b3af2-108">Underleverans av raden är %1 procent men tillåten underleverans är bara %2 procent.</span><span class="sxs-lookup"><span data-stu-id="b3af2-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="b3af2-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="b3af2-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="b3af2-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="b3af2-110">Cause</span></span>

<span data-ttu-id="b3af2-111">Den plockade kvantiteten för beläggningen eller leveransen är mindre än den beställda kvantiteten och ligger inte inom intervallet för underleveransprocenten.</span><span class="sxs-lookup"><span data-stu-id="b3af2-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="b3af2-112">Lösning</span><span class="sxs-lookup"><span data-stu-id="b3af2-112">Resolution</span></span>

<span data-ttu-id="b3af2-113">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="b3af2-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="b3af2-114">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="b3af2-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="b3af2-115">Justera procentsats för underleverans.</span><span class="sxs-lookup"><span data-stu-id="b3af2-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="b3af2-116">Återför och gör justeringar.</span><span class="sxs-lookup"><span data-stu-id="b3af2-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="b3af2-117">Justera procentsats för underleverans</span><span class="sxs-lookup"><span data-stu-id="b3af2-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="b3af2-118">Använd följande procedur för att justera procentsats för underleverans.</span><span class="sxs-lookup"><span data-stu-id="b3af2-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="b3af2-119">Gå till **Kundreskontra \> Order \> Alla order**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="b3af2-120">Välj den försäljningsorder som du inte kan bokföra en följesedel för.</span><span class="sxs-lookup"><span data-stu-id="b3af2-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="b3af2-121">På fliken  **Försäljningsorderrader** markerar du försäljningsorderraden för den artikel som överskrider underleveransens procentsats.</span><span class="sxs-lookup"><span data-stu-id="b3af2-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="b3af2-122">På fliken  **Radinformation** väljer du **Leverans**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="b3af2-123">I fältet **Underleverans** anger du värdet som en större procentsats som rymmer den kvantitet som har plockats mot generering av följesedel kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="b3af2-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="b3af2-124">Återför och gör justeringar</span><span class="sxs-lookup"><span data-stu-id="b3af2-124">Reverse and make adjustments</span></span>

<span data-ttu-id="b3af2-125">Återför allt som har bokförts för lasten (till exempel följesedel, leveransbekräftelse och arbete), gör försäljningsorder justeringar, frisläpp ordern till lagerstället och slutför försändelseproceduren.</span><span class="sxs-lookup"><span data-stu-id="b3af2-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="b3af2-126">Använd följande procedur när du annullerar en följesedel.</span><span class="sxs-lookup"><span data-stu-id="b3af2-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="b3af2-127">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b3af2-128">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Annullera följesedel**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="b3af2-129">Använd följande procedur när du återför en försändelsebekräftelse.</span><span class="sxs-lookup"><span data-stu-id="b3af2-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="b3af2-130">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b3af2-131">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="b3af2-132">Gör på följande sätt för att återföra arbete.</span><span class="sxs-lookup"><span data-stu-id="b3af2-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="b3af2-133">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b3af2-134">I åtgärdsfönstret, på fliken  **Laster**, i gruppen  **Arbete**, väljer du  **återför arbete**.</span><span class="sxs-lookup"><span data-stu-id="b3af2-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
