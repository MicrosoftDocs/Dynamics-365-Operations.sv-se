---
title: Plockad kvantitet räcker inte under genereringen av följesedeln
description: När du genererar ett paket innehåller den utgående lasten en plockad kvantitet som inte matchar den skapade arbetskvantiteten på lastraden.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249174"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="6e443-103">Plockad kvantitet räcker inte under genereringen av följesedeln</span><span class="sxs-lookup"><span data-stu-id="6e443-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="6e443-104">Felkod: SYS54073</span><span class="sxs-lookup"><span data-stu-id="6e443-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="6e443-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="6e443-105">Symptoms</span></span>

<span data-ttu-id="6e443-106">När du genererar ett paket innehåller den utgående lasten en plockad kvantitet som inte matchar den skapade arbetskvantiteten på lastraden.</span><span class="sxs-lookup"><span data-stu-id="6e443-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="6e443-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="6e443-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="6e443-108">Eftersom %1 har plockats är det inte tillräckligt att uppdatera %2 när resten måste vara %3.</span><span class="sxs-lookup"><span data-stu-id="6e443-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="6e443-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="6e443-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="6e443-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="6e443-110">Cause</span></span>

<span data-ttu-id="6e443-111">Paketet kan inte genereras kan inte bekräftas i sitt aktuella tillstånd eftersom något av följande villkor kan finnas:</span><span class="sxs-lookup"><span data-stu-id="6e443-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="6e443-112">Det relaterade arbetet har ännu inte plockats och flyttats till den slutliga leveransplatsen.</span><span class="sxs-lookup"><span data-stu-id="6e443-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="6e443-113">Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="6e443-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="6e443-114">Lastraden kvantitet, arbetskapad kvantitet och plockad kvantitet matchar inte.</span><span class="sxs-lookup"><span data-stu-id="6e443-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="6e443-115">Lösning</span><span class="sxs-lookup"><span data-stu-id="6e443-115">Resolution</span></span>

<span data-ttu-id="6e443-116">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="6e443-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="6e443-117">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="6e443-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="6e443-118">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="6e443-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="6e443-119">Justera kvantiteten för beläggningsrad.</span><span class="sxs-lookup"><span data-stu-id="6e443-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="6e443-120">Återför alla plockregistreringar och gör om plockningen.</span><span class="sxs-lookup"><span data-stu-id="6e443-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="6e443-121">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="6e443-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="6e443-122">Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="6e443-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="6e443-123">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="6e443-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="6e443-124">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="6e443-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="6e443-125">På snabbfliken **Beläggningsrader** väljer du beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="6e443-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="6e443-126">Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="6e443-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="6e443-127">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="6e443-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="6e443-128">Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="6e443-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="6e443-129">Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="6e443-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="6e443-130">Justera kvantiteten för beläggningsrad</span><span class="sxs-lookup"><span data-stu-id="6e443-130">Adjust the load line quantity</span></span>

<span data-ttu-id="6e443-131">Använd följande procedur för att justera lastradkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6e443-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="6e443-132">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="6e443-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="6e443-133">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="6e443-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="6e443-134">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="6e443-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="6e443-135">På fliken  **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.</span><span class="sxs-lookup"><span data-stu-id="6e443-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="6e443-136">Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6e443-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="6e443-137">Ställ in fältet **Minska lastrad** om du vill återspegla justeringar på lastraden.</span><span class="sxs-lookup"><span data-stu-id="6e443-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="6e443-138">Återför alla plockregistreringar och gör om plockningen</span><span class="sxs-lookup"><span data-stu-id="6e443-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="6e443-139">Problemet kan inträffa eftersom någon har använt plockregistrering för att stänga en beläggningsrad utan arbete.</span><span class="sxs-lookup"><span data-stu-id="6e443-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="6e443-140">I det här fallet måste manuell plockregistrering återföras, och plockningen måste sedan slutföras med hjälp av den mobila appen Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="6e443-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="6e443-141">Använd följande procedur när du återför plockregistreringen.</span><span class="sxs-lookup"><span data-stu-id="6e443-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="6e443-142">Gå till **Kundreskontra \> Order \> Alla order**.</span><span class="sxs-lookup"><span data-stu-id="6e443-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="6e443-143">Välj den försäljningsorder som du inte kan bokföra en följesedel för.</span><span class="sxs-lookup"><span data-stu-id="6e443-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="6e443-144">På fliken  **Försäljningsorderrader** väljer du den försäljningsorderrad för vilken plockningsregistreringen har gjorts.</span><span class="sxs-lookup"><span data-stu-id="6e443-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="6e443-145">Välj **Uppdatera rad \> Plockning** om du vill häva plockningen av artiklarna.</span><span class="sxs-lookup"><span data-stu-id="6e443-145">Select **Update line \> Pick** to unpick the items.</span></span>
