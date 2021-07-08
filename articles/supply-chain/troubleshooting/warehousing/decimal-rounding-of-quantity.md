---
title: Decimalavrundning för den fysiska uppdateringskvantiteten blir fel
description: När du genererar en följesedel innehåller den utgående beläggningen en kvantitet som inte matchar det antal decimaler som definierats i enheten.
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
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248805"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="3b462-103">Decimalavrundning för den fysiska uppdateringskvantiteten blir fel</span><span class="sxs-lookup"><span data-stu-id="3b462-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="3b462-104">Felkod: SYS19589</span><span class="sxs-lookup"><span data-stu-id="3b462-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="3b462-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="3b462-105">Symptoms</span></span>

<span data-ttu-id="3b462-106">När du genererar en följesedel innehåller den utgående beläggningen en kvantitet som inte matchar det antal decimaler som definierats i enheten.</span><span class="sxs-lookup"><span data-stu-id="3b462-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="3b462-107">När du försöker generera en följesedel visas följande felmeddelande i systemet:</span><span class="sxs-lookup"><span data-stu-id="3b462-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="3b462-108">Decimalavrundningen av den fysiskt uppdaterade kvantiteten i enheten %1 är felaktig.</span><span class="sxs-lookup"><span data-stu-id="3b462-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="3b462-109">Du kan därför inte generera följesedel för beläggningen.</span><span class="sxs-lookup"><span data-stu-id="3b462-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="3b462-110">Orsak</span><span class="sxs-lookup"><span data-stu-id="3b462-110">Cause</span></span>

<span data-ttu-id="3b462-111">Systemet utvärderar om decimalavrundningen för leveranskvantiteten motsvarar det decimalvärde som har definierats för leveransenheten.</span><span class="sxs-lookup"><span data-stu-id="3b462-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="3b462-112">När systemet avrundar leveranskvantiteten till angivet antal decimaler och det visar sig att den avrundade skeppningskvantiteten inte matchar den faktiska leveranskvantiteten kan du inte generera följesedeln.</span><span class="sxs-lookup"><span data-stu-id="3b462-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="3b462-113">Det här problemet kan till exempel inträffa om försäljningskvantiteten är 1,75 kilo (kg), men antalet decimaler är satt till *1*.</span><span class="sxs-lookup"><span data-stu-id="3b462-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="3b462-114">Lösning</span><span class="sxs-lookup"><span data-stu-id="3b462-114">Resolution</span></span>

<span data-ttu-id="3b462-115">Beläggningen eller leveransen befinner sig för närvarande i ett skick där generering av följesedel misslyckas.</span><span class="sxs-lookup"><span data-stu-id="3b462-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="3b462-116">Utför en eller flera av följande uppgifter för att åtgärda detta problem:</span><span class="sxs-lookup"><span data-stu-id="3b462-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="3b462-117">Granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem.</span><span class="sxs-lookup"><span data-stu-id="3b462-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="3b462-118">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="3b462-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="3b462-119">Granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem</span><span class="sxs-lookup"><span data-stu-id="3b462-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="3b462-120">Använd följande procedurer för att granska dina lastrader och gör justeringar för att säkerställa att kvantiteten kan omvandlas rent utan decimaltal och andra avrundningsproblem.</span><span class="sxs-lookup"><span data-stu-id="3b462-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="3b462-121">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="3b462-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="3b462-122">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="3b462-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="3b462-123">I åtgärdsfönstret, på fliken **Leverera och ta emot** i gruppen **Återför** välj **Återför leveransbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="3b462-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="3b462-124">På fliken  **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.</span><span class="sxs-lookup"><span data-stu-id="3b462-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="3b462-125">Välj **Minska plockad kvantitet** om du vill justera den plockade kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="3b462-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="3b462-126">På fliken  **Radinformation** väljer du **Order**.</span><span class="sxs-lookup"><span data-stu-id="3b462-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="3b462-127">I fältet **Kvantitet** anger du värdet för den plockade kvantiteten (det vill säga värdet för **Arbetsskapad kvantitet**), så att generering av följesedel kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="3b462-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="3b462-128">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="3b462-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="3b462-129">Granska beläggningsraderna och gör justeringar för att se till att enheten och kvantiteten stämmer överens med antalet decimaler för enheten.</span><span class="sxs-lookup"><span data-stu-id="3b462-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="3b462-130">Gå till **Warehouse management \> Laster \> Alla laster**.</span><span class="sxs-lookup"><span data-stu-id="3b462-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="3b462-131">Välj den beläggning som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="3b462-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="3b462-132">På snabbfliken **Lastrader** väljer du lastraden för den artikel som orsakar ett problem.</span><span class="sxs-lookup"><span data-stu-id="3b462-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="3b462-133">Lägg märke till värdet i fältet **kvantitet** och **enhet**.</span><span class="sxs-lookup"><span data-stu-id="3b462-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="3b462-134">Gå till **Organisationsadministration \> Enheter \> Enheter**.</span><span class="sxs-lookup"><span data-stu-id="3b462-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="3b462-135">Välj den enhet som följesedel inte kan genereras för.</span><span class="sxs-lookup"><span data-stu-id="3b462-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="3b462-136">Justera värdet i fältet **Decimalprecision** efter behov.</span><span class="sxs-lookup"><span data-stu-id="3b462-136">Adjust the value of the **Decimal precision** field as required.</span></span>
