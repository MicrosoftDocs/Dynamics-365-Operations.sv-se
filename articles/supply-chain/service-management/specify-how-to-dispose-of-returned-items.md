---
title: Ange hur returnerade artiklar ska avyttras
description: Ange hur returnerade artiklar ska avyttras
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0049e47d5e0e5f8a2a6d7cc5feb29593c764d323
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991550"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="0aadd-103">Ange hur returnerade artiklar ska avyttras</span><span class="sxs-lookup"><span data-stu-id="0aadd-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0aadd-104">När du hanterar en returorder måste du ange en orsakskod som visar varför produkten returneras identifiera.</span><span class="sxs-lookup"><span data-stu-id="0aadd-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="0aadd-105">Du måste även ange en dispositionskod och dispositionsåtgärden om vad som ska göras med den returnerade produkten.</span><span class="sxs-lookup"><span data-stu-id="0aadd-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="0aadd-106">En dispositionskod kan anges när du skapar returordern, registrerar eller följesedelsuppdaterar artikelinförseln och avslutar en karantänorder.</span><span class="sxs-lookup"><span data-stu-id="0aadd-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="0aadd-107">Du kan definiera alla de dispostionskoder du behöver som stöd för affärsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="0aadd-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="0aadd-108">Följande register innehåller ett antal vanliga koder som tilldelas returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="0aadd-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0aadd-109">Dispositionstyp</span><span class="sxs-lookup"><span data-stu-id="0aadd-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="0aadd-110">Vanlig kod</span><span class="sxs-lookup"><span data-stu-id="0aadd-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="0aadd-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0aadd-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-112">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="0aadd-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0aadd-113">SC</span><span class="sxs-lookup"><span data-stu-id="0aadd-113">SC</span></span></p></td>
<td><p><span data-ttu-id="0aadd-114">Skrota/förstör</span><span class="sxs-lookup"><span data-stu-id="0aadd-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-115">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="0aadd-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0aadd-116">DC</span><span class="sxs-lookup"><span data-stu-id="0aadd-116">DC</span></span></p></td>
<td><p><span data-ttu-id="0aadd-117">Donera till välgörande ändamål</span><span class="sxs-lookup"><span data-stu-id="0aadd-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-118">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="0aadd-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0aadd-119">TD</span><span class="sxs-lookup"><span data-stu-id="0aadd-119">TD</span></span></p></td>
<td><p><span data-ttu-id="0aadd-120">Avyttrande till tredje part</span><span class="sxs-lookup"><span data-stu-id="0aadd-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-121">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="0aadd-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0aadd-122">SL</span><span class="sxs-lookup"><span data-stu-id="0aadd-122">SL</span></span></p></td>
<td><p><span data-ttu-id="0aadd-123">Återvinn</span><span class="sxs-lookup"><span data-stu-id="0aadd-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-124">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="0aadd-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="0aadd-125">TS</span><span class="sxs-lookup"><span data-stu-id="0aadd-125">TS</span></span></p></td>
<td><p><span data-ttu-id="0aadd-126">Försäljning till tredje part (sekundära marknader)</span><span class="sxs-lookup"><span data-stu-id="0aadd-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-127">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0aadd-128">RW</span><span class="sxs-lookup"><span data-stu-id="0aadd-128">RW</span></span></p></td>
<td><p><span data-ttu-id="0aadd-129">Omarbeta</span><span class="sxs-lookup"><span data-stu-id="0aadd-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-130">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0aadd-131">RF</span><span class="sxs-lookup"><span data-stu-id="0aadd-131">RF</span></span></p></td>
<td><p><span data-ttu-id="0aadd-132">Omtillverka/renovera</span><span class="sxs-lookup"><span data-stu-id="0aadd-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-133">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0aadd-134">MD</span><span class="sxs-lookup"><span data-stu-id="0aadd-134">MD</span></span></p></td>
<td><p><span data-ttu-id="0aadd-135">Ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-136">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0aadd-137">RP</span><span class="sxs-lookup"><span data-stu-id="0aadd-137">RP</span></span></p></td>
<td><p><span data-ttu-id="0aadd-138">Reparera</span><span class="sxs-lookup"><span data-stu-id="0aadd-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-139">Reparera/ändra</span><span class="sxs-lookup"><span data-stu-id="0aadd-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="0aadd-140">RV</span><span class="sxs-lookup"><span data-stu-id="0aadd-140">RV</span></span></p></td>
<td><p><span data-ttu-id="0aadd-141">Retur till leverantören</span><span class="sxs-lookup"><span data-stu-id="0aadd-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-142">Övrigt</span><span class="sxs-lookup"><span data-stu-id="0aadd-142">Other</span></span></p></td>
<td><p><span data-ttu-id="0aadd-143">AI</span><span class="sxs-lookup"><span data-stu-id="0aadd-143">AI</span></span></p></td>
<td><p><span data-ttu-id="0aadd-144">Använd i befintligt skick</span><span class="sxs-lookup"><span data-stu-id="0aadd-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-145">Övrigt</span><span class="sxs-lookup"><span data-stu-id="0aadd-145">Other</span></span></p></td>
<td><p><span data-ttu-id="0aadd-146">RS</span><span class="sxs-lookup"><span data-stu-id="0aadd-146">RS</span></span></p></td>
<td><p><span data-ttu-id="0aadd-147">Återförsäljning</span><span class="sxs-lookup"><span data-stu-id="0aadd-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-148">Övrigt</span><span class="sxs-lookup"><span data-stu-id="0aadd-148">Other</span></span></p></td>
<td><p><span data-ttu-id="0aadd-149">EX</span><span class="sxs-lookup"><span data-stu-id="0aadd-149">EX</span></span></p></td>
<td><p><span data-ttu-id="0aadd-150">Växel</span><span class="sxs-lookup"><span data-stu-id="0aadd-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-151">Övrigt</span><span class="sxs-lookup"><span data-stu-id="0aadd-151">Other</span></span></p></td>
<td><p><span data-ttu-id="0aadd-152">MS</span><span class="sxs-lookup"><span data-stu-id="0aadd-152">MS</span></span></p></td>
<td><p><span data-ttu-id="0aadd-153">Diverse</span><span class="sxs-lookup"><span data-stu-id="0aadd-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0aadd-154">För varje dispositionskod, som du definierar, måste du välja dispositionsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="0aadd-155">Dispositionsåtgärden avgör de fysiska och ekonomiska följderna av dispositionskoderna.</span><span class="sxs-lookup"><span data-stu-id="0aadd-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="0aadd-156">Till exempel bestämmer dispositionsåtgärden den fysiska användningen av den returnerade artikeln, ekonomiska effekten av den returnerade artikeln, och om en ersättningsartikel måste skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="0aadd-157">Du kan definiera ett obegränsat antal dispositionskoder enligt dina affärsbehov, men det finns bara sex fördefinierade dispositionsuppgifter som du kan välja från.</span><span class="sxs-lookup"><span data-stu-id="0aadd-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="0aadd-158">I följande register finns dispositionsåtgärderna med definitioner.</span><span class="sxs-lookup"><span data-stu-id="0aadd-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0aadd-159">Dispositionsåtgärd</span><span class="sxs-lookup"><span data-stu-id="0aadd-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="0aadd-160">beskrivning</span><span class="sxs-lookup"><span data-stu-id="0aadd-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-161"><strong>Kredit</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-162">Returnera artikeln till lagret och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-163"><strong>Endast kreditering</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-164">Kreditera kunden, utan att kräva att förvänta att artikeln ska returneras.</span><span class="sxs-lookup"><span data-stu-id="0aadd-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-165"><strong>Kassation</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-166">Kassera artikeln och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-167"><strong>Ersätt och kreditera</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-168">Returnera artikeln till lagret, skapa en ersättningsorder och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0aadd-169"><strong>Ersätt och kassera</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-170">Kassera artikeln, skapa en ersättningsorder och kreditera kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0aadd-171"><strong>Returnera till kund</strong></span><span class="sxs-lookup"><span data-stu-id="0aadd-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="0aadd-172">Avvisa den returnerade artikeln och skicka tillbaka den till kunden.</span><span class="sxs-lookup"><span data-stu-id="0aadd-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="0aadd-173">Välja en dispositionskod för en karantänorder</span><span class="sxs-lookup"><span data-stu-id="0aadd-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="0aadd-174">Klicka på **Lagerhantering** \> **Periodisk** \> **Kvalitetshantering** \> **Karantänorder**.</span><span class="sxs-lookup"><span data-stu-id="0aadd-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="0aadd-175">För en befintlig karantänorder väljer du en åtgärd i fältet **Dispositionskod** på fliken **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="0aadd-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="0aadd-176">Se även</span><span class="sxs-lookup"><span data-stu-id="0aadd-176">See also</span></span>

<span data-ttu-id="0aadd-177">[Karantänorder (formulär)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="0aadd-177">[Quarantine order (form)](https://technet.microsoft.com/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="0aadd-178">[Dispositionskoder (formulär)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="0aadd-178">[Disposition codes (form)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))</span></span>

  


