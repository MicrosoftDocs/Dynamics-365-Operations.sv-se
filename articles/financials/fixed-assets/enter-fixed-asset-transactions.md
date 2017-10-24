---
title: "Alternativ för transaktioner för anläggningstillgång"
description: "Det här avsnittet innehåller en beskrivning av andra tillgängliga metoder för att skapa transaktioner för anläggningstillgångar."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3d16b43eda0157e63a0d30fe806dac9a359d5fa4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="a27d2-103">Alternativ för transaktioner för anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="a27d2-103">Fixed asset transaction options</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a27d2-104">Det här avsnittet innehåller en beskrivning av andra tillgängliga metoder för att skapa transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a27d2-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="a27d2-105">Du kan ställa in Anläggningstillgångar för integrering med Leverantörsreskontra, Kundreskontra, Anskaffning och källa, samt Redovisning.</span><span class="sxs-lookup"><span data-stu-id="a27d2-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="a27d2-106">(Du kan även överföra artiklar i Lager till Anläggningstillgångar för intern användning.</span><span class="sxs-lookup"><span data-stu-id="a27d2-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="a27d2-107">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="a27d2-107">Accounts payable</span></span>
<span data-ttu-id="a27d2-108">Du kan ange transaktioner för anläggningstillgångar på sidan Bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a27d2-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="a27d2-109">Denna sida kan öppnas från sidan Invoice journal.</span><span class="sxs-lookup"><span data-stu-id="a27d2-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="a27d2-110">Du kan också öppna sidan Bokföringsorder på sidan Fakturagodkännandejournal.</span><span class="sxs-lookup"><span data-stu-id="a27d2-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="a27d2-111">Välj Anläggningstillgångar i fältet Motkontotyp.</span><span class="sxs-lookup"><span data-stu-id="a27d2-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="a27d2-112">Välj sedan ett Anläggningstillgångsnummer i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="a27d2-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="a27d2-113">På fliken Anläggningstillgångar anger du värden i fälten Transaction type och Book.</span><span class="sxs-lookup"><span data-stu-id="a27d2-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="a27d2-114">Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="a27d2-114">Accounts receivable</span></span>
<span data-ttu-id="a27d2-115">Du kan ange transaktioner för anläggningstillgångar på sidan Fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="a27d2-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="a27d2-116">Välj en radartikel i rutnätet Fakturarader på sidan Fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="a27d2-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="a27d2-117">Klicka på snabbfältet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="a27d2-117">Click the Line details FastTab.</span></span> <span data-ttu-id="a27d2-118">Ange Anläggningstillgångsnumret och boken för avyttringstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="a27d2-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="a27d2-119">För fritextfakturor är transaktionstypen för anläggningstillgångar alltid Avyttrande försäljning.</span><span class="sxs-lookup"><span data-stu-id="a27d2-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="a27d2-120">Anskaffning och källa</span><span class="sxs-lookup"><span data-stu-id="a27d2-120">Procurement and sourcing</span></span>
<span data-ttu-id="a27d2-121">Du kan ange transaktioner för anläggningstillgångar på sidan Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="a27d2-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="a27d2-122">Ange nödvändig information för att skapa en inköpsorder och klicka sedan på OK.</span><span class="sxs-lookup"><span data-stu-id="a27d2-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="a27d2-123">Klicka på snabbfliken Radinformation på sidan Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="a27d2-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="a27d2-124">Ange sedan information om anläggningstillgången på fliken Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a27d2-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="a27d2-125">Om du vill bokföra en anskaffningstransaktion för en befintlig anläggningstillgång anger du Anläggningstillgångsnumret, boken samt transaktionstypen.</span><span class="sxs-lookup"><span data-stu-id="a27d2-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="a27d2-126">Anläggningstillgången kan inte bokföras om en del av den här informationen saknas.</span><span class="sxs-lookup"><span data-stu-id="a27d2-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="a27d2-127">Om du vill bokföra en anskaffningstransaktion för en ny anläggningstillgång markerar du alternativet Ny anläggningstillgång? och väljer Anläggningstillgångsgruppen som den nya tillgången ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="a27d2-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="a27d2-128">Inget Anläggningstillgångsfält är emellertid tillgängligt för en rad om artikeln finns i en lagermodellgrupp som använder lagermodellen Standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="a27d2-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="a27d2-129">Alternativen som definierats på parametersidan Anläggningstillgångar bestämmer om du kan bokföra anskaffningstransaktioner från inköpsmodulerna.</span><span class="sxs-lookup"><span data-stu-id="a27d2-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="a27d2-130">När inköpsorderjournalen eller journalen för lager till anläggningstillgångar används för anskaffning av anläggningstillgångar påverkas lagervärdet.</span><span class="sxs-lookup"><span data-stu-id="a27d2-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="a27d2-131">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="a27d2-131">General ledger</span></span>
<span data-ttu-id="a27d2-132">Alla transaktionstyper för anläggningstillgångar kan bokföras på sidan Allmän journal.</span><span class="sxs-lookup"><span data-stu-id="a27d2-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="a27d2-133">Du kan också använda journaler i Anläggningstillgångar för att bokföra transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a27d2-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="a27d2-134">Alternativ för att ange transaktionstyper för anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="a27d2-135">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="a27d2-135">Transaction type</span></span>                    | <span data-ttu-id="a27d2-136">Modul</span><span class="sxs-lookup"><span data-stu-id="a27d2-136">Module</span></span>                   | <span data-ttu-id="a27d2-137">Alternativ</span><span class="sxs-lookup"><span data-stu-id="a27d2-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="a27d2-138">Anskaffning, Anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="a27d2-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="a27d2-139">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-139">Fixed assets</span></span>             | <span data-ttu-id="a27d2-140">Anläggningstillgångar, Lager till anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="a27d2-141">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="a27d2-141">General ledger</span></span>           | <span data-ttu-id="a27d2-142">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="a27d2-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="a27d2-143">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="a27d2-143">Accounts payable</span></span>         | <span data-ttu-id="a27d2-144">Fakturajournalen, Fakturagodkännandejournal.</span><span class="sxs-lookup"><span data-stu-id="a27d2-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="a27d2-145">Anskaffning och källa</span><span class="sxs-lookup"><span data-stu-id="a27d2-145">Procurement and sourcing</span></span> | <span data-ttu-id="a27d2-146">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="a27d2-146">Purchase order</span></span>                            |
| <span data-ttu-id="a27d2-147">Avskrivning</span><span class="sxs-lookup"><span data-stu-id="a27d2-147">Depreciation</span></span>                        | <span data-ttu-id="a27d2-148">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-148">Fixed assets</span></span>             | <span data-ttu-id="a27d2-149">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="a27d2-150">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="a27d2-150">General ledger</span></span>           | <span data-ttu-id="a27d2-151">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="a27d2-151">General journal</span></span>                           |
| <span data-ttu-id="a27d2-152">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="a27d2-152">Disposal</span></span>                            | <span data-ttu-id="a27d2-153">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-153">Fixed assets</span></span>             | <span data-ttu-id="a27d2-154">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a27d2-154">Fixed assets</span></span>                              |
| <span data-ttu-id="a27d2-155">** **</span><span class="sxs-lookup"><span data-stu-id="a27d2-155">** **</span></span>                               | <span data-ttu-id="a27d2-156">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="a27d2-156">General ledger</span></span>           | <span data-ttu-id="a27d2-157">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="a27d2-157">General journal</span></span>                           |
| <span data-ttu-id="a27d2-158">** **</span><span class="sxs-lookup"><span data-stu-id="a27d2-158">** **</span></span>                               | <span data-ttu-id="a27d2-159">Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="a27d2-159">Accounts receivable</span></span>      | <span data-ttu-id="a27d2-160">Fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="a27d2-160">Free text invoice</span></span>                         |



<span data-ttu-id="a27d2-161">Mer information finns i [Integrering av anläggningstillgångar](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="a27d2-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




