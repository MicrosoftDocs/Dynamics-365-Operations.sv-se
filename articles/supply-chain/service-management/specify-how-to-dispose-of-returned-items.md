---
title: Ange hur returnerade artiklar ska avyttras
description: Ange hur returnerade artiklar ska avyttras
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6991fc04f5015fc3d604306e9327a5e551e728db
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743082"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="06a1d-103">Ange hur returnerade artiklar ska avyttras</span><span class="sxs-lookup"><span data-stu-id="06a1d-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="06a1d-104">När du hanterar en returorder måste du ange en orsakskod som visar varför produkten returneras identifiera.</span><span class="sxs-lookup"><span data-stu-id="06a1d-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="06a1d-105">Du måste även ange en dispositionskod och dispositionsåtgärden om vad som ska göras med den returnerade produkten.</span><span class="sxs-lookup"><span data-stu-id="06a1d-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="06a1d-106">En dispositionskod kan anges när du skapar returordern, registrerar eller följesedelsuppdaterar artikelinförseln och avslutar en karantänorder.</span><span class="sxs-lookup"><span data-stu-id="06a1d-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="06a1d-107">Du kan definiera alla de dispostionskoder du behöver som stöd för affärsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="06a1d-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="06a1d-108">Följande register innehåller ett antal vanliga koder som tilldelas returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="06a1d-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="06a1d-109">Dispositionstyp</span><span class="sxs-lookup"><span data-stu-id="06a1d-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="06a1d-110">Vanlig kod</span><span class="sxs-lookup"><span data-stu-id="06a1d-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="06a1d-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="06a1d-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-112">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="06a1d-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="06a1d-113">SC</span><span class="sxs-lookup"><span data-stu-id="06a1d-113">SC</span></span></p></td>
<td><p><span data-ttu-id="06a1d-114">Skrota/förstör</span><span class="sxs-lookup"><span data-stu-id="06a1d-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-115">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="06a1d-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="06a1d-116">DC</span><span class="sxs-lookup"><span data-stu-id="06a1d-116">DC</span></span></p></td>
<td><p><span data-ttu-id="06a1d-117">Donera till välgörande ändamål</span><span class="sxs-lookup"><span data-stu-id="06a1d-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-118">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="06a1d-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="06a1d-119">TD</span><span class="sxs-lookup"><span data-stu-id="06a1d-119">TD</span></span></p></td>
<td><p><span data-ttu-id="06a1d-120">Avyttrande till tredje part</span><span class="sxs-lookup"><span data-stu-id="06a1d-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-121">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="06a1d-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="06a1d-122">SL</span><span class="sxs-lookup"><span data-stu-id="06a1d-122">SL</span></span></p></td>
<td><p><span data-ttu-id="06a1d-123">Återvinn</span><span class="sxs-lookup"><span data-stu-id="06a1d-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-124">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="06a1d-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="06a1d-125">TS</span><span class="sxs-lookup"><span data-stu-id="06a1d-125">TS</span></span></p></td>
<td><p><span data-ttu-id="06a1d-126">Försäljning till tredje part (sekundära marknader)</span><span class="sxs-lookup"><span data-stu-id="06a1d-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-127">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="06a1d-128">RW</span><span class="sxs-lookup"><span data-stu-id="06a1d-128">RW</span></span></p></td>
<td><p><span data-ttu-id="06a1d-129">Omarbeta</span><span class="sxs-lookup"><span data-stu-id="06a1d-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-130">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="06a1d-131">RF</span><span class="sxs-lookup"><span data-stu-id="06a1d-131">RF</span></span></p></td>
<td><p><span data-ttu-id="06a1d-132">Omtillverka/renovera</span><span class="sxs-lookup"><span data-stu-id="06a1d-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-133">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="06a1d-134">MD</span><span class="sxs-lookup"><span data-stu-id="06a1d-134">MD</span></span></p></td>
<td><p><span data-ttu-id="06a1d-135">Ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-136">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="06a1d-137">RP</span><span class="sxs-lookup"><span data-stu-id="06a1d-137">RP</span></span></p></td>
<td><p><span data-ttu-id="06a1d-138">Reparera</span><span class="sxs-lookup"><span data-stu-id="06a1d-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-139">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="06a1d-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="06a1d-140">RV</span><span class="sxs-lookup"><span data-stu-id="06a1d-140">RV</span></span></p></td>
<td><p><span data-ttu-id="06a1d-141">Retur till leverantören</span><span class="sxs-lookup"><span data-stu-id="06a1d-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-142">Övrigt</span><span class="sxs-lookup"><span data-stu-id="06a1d-142">Other</span></span></p></td>
<td><p><span data-ttu-id="06a1d-143">AI</span><span class="sxs-lookup"><span data-stu-id="06a1d-143">AI</span></span></p></td>
<td><p><span data-ttu-id="06a1d-144">Använd i befintligt skick</span><span class="sxs-lookup"><span data-stu-id="06a1d-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-145">Övrigt</span><span class="sxs-lookup"><span data-stu-id="06a1d-145">Other</span></span></p></td>
<td><p><span data-ttu-id="06a1d-146">RS</span><span class="sxs-lookup"><span data-stu-id="06a1d-146">RS</span></span></p></td>
<td><p><span data-ttu-id="06a1d-147">Återförsäljning</span><span class="sxs-lookup"><span data-stu-id="06a1d-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-148">Övrigt</span><span class="sxs-lookup"><span data-stu-id="06a1d-148">Other</span></span></p></td>
<td><p><span data-ttu-id="06a1d-149">EX</span><span class="sxs-lookup"><span data-stu-id="06a1d-149">EX</span></span></p></td>
<td><p><span data-ttu-id="06a1d-150">Växel</span><span class="sxs-lookup"><span data-stu-id="06a1d-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-151">Övrigt</span><span class="sxs-lookup"><span data-stu-id="06a1d-151">Other</span></span></p></td>
<td><p><span data-ttu-id="06a1d-152">MS</span><span class="sxs-lookup"><span data-stu-id="06a1d-152">MS</span></span></p></td>
<td><p><span data-ttu-id="06a1d-153">Diverse</span><span class="sxs-lookup"><span data-stu-id="06a1d-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="06a1d-154">För varje dispositionskod, som du definierar, måste du välja dispositionsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="06a1d-155">Dispositionsåtgärden avgör de fysiska och ekonomiska följderna av dispositionskoderna.</span><span class="sxs-lookup"><span data-stu-id="06a1d-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="06a1d-156">Till exempel bestämmer dispositionsåtgärden den fysiska användningen av den returnerade artikeln, ekonomiska effekten av den returnerade artikeln, och om en ersättningsartikel måste skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="06a1d-157">Du kan definiera ett obegränsat antal dispositionskoder enligt dina affärsbehov, men det finns bara sex fördefinierade dispositionsuppgifter som du kan välja från.</span><span class="sxs-lookup"><span data-stu-id="06a1d-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="06a1d-158">I följande register finns dispositionsåtgärderna med definitioner.</span><span class="sxs-lookup"><span data-stu-id="06a1d-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="06a1d-159">Dispositionsåtgärd</span><span class="sxs-lookup"><span data-stu-id="06a1d-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="06a1d-160">beskrivning</span><span class="sxs-lookup"><span data-stu-id="06a1d-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-161"><strong>Kredit</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-162">Returnera artikeln till lagret och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-163"><strong>Endast kreditering</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-164">Kreditera kunden, utan att kräva att förvänta att artikeln ska returneras.</span><span class="sxs-lookup"><span data-stu-id="06a1d-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-165"><strong>Kassation</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-166">Kassera artikeln och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-167"><strong>Ersätt och kreditera</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-168">Returnera artikeln till lagret, skapa en ersättningsorder och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06a1d-169"><strong>Ersätt och kassera</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-170">Kassera artikeln, skapa en ersättningsorder och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06a1d-171"><strong>Returnera till kund</strong></span><span class="sxs-lookup"><span data-stu-id="06a1d-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="06a1d-172">Avvisa den returnerade artikeln och skicka tillbaka den till kunden.</span><span class="sxs-lookup"><span data-stu-id="06a1d-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="06a1d-173">Välja en dispositionskod för en karantänorder</span><span class="sxs-lookup"><span data-stu-id="06a1d-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="06a1d-174">Klicka på **Lagerhantering** \> **Periodisk** \> **Kvalitetshantering** \> **Karantänorder**.</span><span class="sxs-lookup"><span data-stu-id="06a1d-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="06a1d-175">För en befintlig karantänorder väljer du en åtgärd i fältet **Dispositionskod** på fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="06a1d-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="06a1d-176">Se även</span><span class="sxs-lookup"><span data-stu-id="06a1d-176">See also</span></span>

<span data-ttu-id="06a1d-177">[Karantänorder (formulär)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="06a1d-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="06a1d-178">[Dispositionskoder (formulär)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="06a1d-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  


