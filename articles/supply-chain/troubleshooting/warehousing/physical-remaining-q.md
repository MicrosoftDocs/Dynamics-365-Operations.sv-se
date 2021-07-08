---
title: Fysisk resterande kvantitet i enheten får inte vara noll
description: När du genererar en följesedel har data som levereras till den en lagerkvantitet som inte är noll, men ingen försäljningskvantitet.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248804"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="eaf33-103">Fysisk resterande kvantitet i enheten får inte vara noll</span><span class="sxs-lookup"><span data-stu-id="eaf33-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="eaf33-104">Felkod: SYS19591</span><span class="sxs-lookup"><span data-stu-id="eaf33-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="eaf33-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="eaf33-105">Symptoms</span></span>

<span data-ttu-id="eaf33-106">När du genererar en följesedel har data som levereras till den en lagerkvantitet som inte är noll, men ingen försäljningskvantitet.</span><span class="sxs-lookup"><span data-stu-id="eaf33-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="eaf33-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="eaf33-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="eaf33-108">Fysisk rest i enheten %1 måste vara skild från noll.</span><span class="sxs-lookup"><span data-stu-id="eaf33-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="eaf33-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="eaf33-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="eaf33-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="eaf33-110">Cause</span></span>

<span data-ttu-id="eaf33-111">Systemet utvärderar den fysiska återstående kvantiteten i lagerenheten och den fysiska resterande kvantiteten i leveransenheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="eaf33-112">Om systemet hittar att den fysiska resterande kvantiteten i leveransenheten är 0 (noll), men den fysiska resterande kvantiteten i lagerenheten 0, kan du inte generera följesedeln.</span><span class="sxs-lookup"><span data-stu-id="eaf33-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="eaf33-113">Det här problemet kan till exempel uppstå om försäljningsenheten och lagerenheten för artikeln skiljer sig åt och konverteringen mellan enheterna inte stämmer.</span><span class="sxs-lookup"><span data-stu-id="eaf33-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="eaf33-114">Lösning</span><span class="sxs-lookup"><span data-stu-id="eaf33-114">Resolution</span></span>

<span data-ttu-id="eaf33-115">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="eaf33-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="eaf33-116">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="eaf33-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="eaf33-117">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="eaf33-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="eaf33-118">Granska beläggningsraderna och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem.</span><span class="sxs-lookup"><span data-stu-id="eaf33-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="eaf33-119">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="eaf33-120">Kontrollera att lagermåttet är mindre än försäljningsmåttenheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="eaf33-121">Granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="eaf33-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="eaf33-122">Använd följande procedur för att granska dina lastrader och se till att allt relaterat arbete har slutförts vid den slutliga leveransplatsen och att kvantiteterna matchar.</span><span class="sxs-lookup"><span data-stu-id="eaf33-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="eaf33-123">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="eaf33-124">Välj den beläggning som leveransen inte kan bekräftas för.</span><span class="sxs-lookup"><span data-stu-id="eaf33-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="eaf33-125">På snabbfliken **Beläggningsrader** väljer du beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="eaf33-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="eaf33-126">Lägg märke till värdet i fältet **Arbetsskapad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="eaf33-127">I åtgärdsfönstret, på fliken **Geläggningar**, i gruppen **Relaterad information**, väljer du **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="eaf33-128">Kontrollera att arbetet har slutförts vid den slutliga leveransplatsen och att den plockade arbetskvantiteten matchar den skapade arbetskvantiteten på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="eaf33-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="eaf33-129">Upprepa den här proceduren för alla beläggningsrader för att se till att alla kriterier är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="eaf33-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="eaf33-130">Granska beläggningsraderna och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem</span><span class="sxs-lookup"><span data-stu-id="eaf33-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="eaf33-131">Använd följande procedurer för att granska dina lastrader och gör justeringar för att kvantiteten ska kunna konverteras rensas utan avrundningsproblem</span><span class="sxs-lookup"><span data-stu-id="eaf33-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="eaf33-132">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="eaf33-133">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="eaf33-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="eaf33-134">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="eaf33-135">På fliken  **Läs in rader** markerar du inläsningsraden för den artikel som överskrider överleverans.</span><span class="sxs-lookup"><span data-stu-id="eaf33-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="eaf33-136">Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="eaf33-137">På fliken  **Radinformation** väljer du **Order**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="eaf33-138">I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att generering av följesedel kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="eaf33-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="eaf33-139">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="eaf33-140">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="eaf33-141">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="eaf33-142">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="eaf33-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="eaf33-143">På snabbfliken **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.</span><span class="sxs-lookup"><span data-stu-id="eaf33-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="eaf33-144">Lägg märke till värdet i fältet **kvantitet** och **enhet**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="eaf33-145">Gå till **Organisationsadministration \> Enheter \> Enheter**.</span><span class="sxs-lookup"><span data-stu-id="eaf33-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="eaf33-146">Välj den enhet som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="eaf33-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="eaf33-147">Justera värdet i fältet **Decimalprecision** efter behov.</span><span class="sxs-lookup"><span data-stu-id="eaf33-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="eaf33-148">Kontrollera att lagermåttet är mindre än försäljningsmåttenheten</span><span class="sxs-lookup"><span data-stu-id="eaf33-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="eaf33-149">Kontrollera att lagermåttet är mindre än försäljningsmåttenheten.</span><span class="sxs-lookup"><span data-stu-id="eaf33-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="eaf33-150">Överväg att omkonfigurera artikelns måttenhet efter behov.</span><span class="sxs-lookup"><span data-stu-id="eaf33-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
