---
title: Kvantiteten som du försöker uppdatera överstiger den mottagna/levererade kvantiteten.
description: När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider arbetskvantiteten som plockades och reserverades för försäljningsordern.
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
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249175"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="78b1f-103">Kvantiteten som du försöker uppdatera överstiger den mottagna/levererade kvantiteten</span><span class="sxs-lookup"><span data-stu-id="78b1f-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="78b1f-104">Felkod: SYS7676</span><span class="sxs-lookup"><span data-stu-id="78b1f-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="78b1f-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="78b1f-105">Symptoms</span></span>

<span data-ttu-id="78b1f-106">När du genererar en följesedel innehåller den utgående inläsningen en kvantitet som överskrider arbetskvantiteten som plockades och reserverades för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="78b1f-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="78b1f-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="78b1f-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="78b1f-108">Kvantiteten som du försöker uppdatera överskrider den kvantitet som inlevererats/levererats.</span><span class="sxs-lookup"><span data-stu-id="78b1f-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="78b1f-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="78b1f-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="78b1f-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="78b1f-110">Cause</span></span>

<span data-ttu-id="78b1f-111">Den plockade arbetskvantiteten matchar inte den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="78b1f-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="78b1f-112">Det här problemet kan till exempel inträffa om beläggningsradkvantiteten, arbetskvantiteten eller den plockade kvantiteten inte stämmer.</span><span class="sxs-lookup"><span data-stu-id="78b1f-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="78b1f-113">Lösning</span><span class="sxs-lookup"><span data-stu-id="78b1f-113">Resolution</span></span>

<span data-ttu-id="78b1f-114">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="78b1f-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="78b1f-115">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="78b1f-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="78b1f-116">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="78b1f-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="78b1f-117">Justera kvantiteten för beläggningsrad.</span><span class="sxs-lookup"><span data-stu-id="78b1f-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="78b1f-118">Återför alla plockregistreringar och gör om plockningen.</span><span class="sxs-lookup"><span data-stu-id="78b1f-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="78b1f-119">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="78b1f-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="78b1f-120">Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="78b1f-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="78b1f-121">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="78b1f-122">Välj den beläggning som leveransen inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="78b1f-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="78b1f-123">På snabbfliken **Beläggningsrader** väljer du beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="78b1f-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="78b1f-124">Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="78b1f-125">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="78b1f-126">Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="78b1f-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="78b1f-127">Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="78b1f-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="78b1f-128">Justera kvantiteten för beläggningsrad</span><span class="sxs-lookup"><span data-stu-id="78b1f-128">Adjust the load line quantity</span></span>

<span data-ttu-id="78b1f-129">Använd följande procedur för att justera lastradkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78b1f-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="78b1f-130">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="78b1f-131">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="78b1f-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="78b1f-132">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="78b1f-133">På fliken  **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.</span><span class="sxs-lookup"><span data-stu-id="78b1f-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="78b1f-134">Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78b1f-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="78b1f-135">Ställ in fältet **Minska lastrad** om du vill återspegla justeringar på lastraden.</span><span class="sxs-lookup"><span data-stu-id="78b1f-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="78b1f-136">Återför alla plockregistreringar och gör om plockningen</span><span class="sxs-lookup"><span data-stu-id="78b1f-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="78b1f-137">Om någon har använt plockregistrering för att stänga en lastrad utan arbete kan det uppstå en avvikelse mellan kvantiteten på lastraden och den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="78b1f-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="78b1f-138">I det här fallet måste manuell plockregistrering återföras, och plockningen måste sedan slutföras med hjälp av den mobila appen Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="78b1f-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="78b1f-139">Använd följande procedur när du återför plockregistreringen.</span><span class="sxs-lookup"><span data-stu-id="78b1f-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="78b1f-140">Gå till **Kundreskontra \> Order \> Alla order**.</span><span class="sxs-lookup"><span data-stu-id="78b1f-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="78b1f-141">Välj den försäljningsorder som du inte kan bokföra en följesedel för.</span><span class="sxs-lookup"><span data-stu-id="78b1f-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="78b1f-142">På fliken  **Försäljningsorderrader** väljer du den försäljningsorderrad för vilken plockningsregistreringen har gjorts.</span><span class="sxs-lookup"><span data-stu-id="78b1f-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="78b1f-143">Välj **Uppdatera rad \> Plockning** om du vill häva plockningen av artiklarna.</span><span class="sxs-lookup"><span data-stu-id="78b1f-143">Select **Update line \> Pick** to unpick the items.</span></span>
