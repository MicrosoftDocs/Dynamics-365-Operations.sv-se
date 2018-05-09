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
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 48364acbaa3fff4be9440256c6b337c0e2d2d9d0
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="3a9c7-103">Alternativ för transaktioner för anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="3a9c7-103">Fixed asset transaction options</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a9c7-104">Det här avsnittet innehåller en beskrivning av andra tillgängliga metoder för att skapa transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="3a9c7-105">Du kan ställa in Anläggningstillgångar för integrering med Leverantörsreskontra, Kundreskontra, Anskaffning och källa, samt Redovisning.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="3a9c7-106">(Du kan även överföra artiklar i Lager till Anläggningstillgångar för intern användning.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="3a9c7-107">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="3a9c7-107">Accounts payable</span></span>
<span data-ttu-id="3a9c7-108">Du kan ange transaktioner för anläggningstillgångar på sidan Bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="3a9c7-109">Denna sida kan öppnas från sidan Invoice journal.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="3a9c7-110">Du kan också öppna sidan Bokföringsorder på sidan Fakturagodkännandejournal.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="3a9c7-111">Välj Anläggningstillgångar i fältet Motkontotyp.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="3a9c7-112">Välj sedan ett Anläggningstillgångsnummer i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="3a9c7-113">På fliken Anläggningstillgångar anger du värden i fälten Transaction type och Book.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="3a9c7-114">Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="3a9c7-114">Accounts receivable</span></span>
<span data-ttu-id="3a9c7-115">Du kan ange transaktioner för anläggningstillgångar på sidan Fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="3a9c7-116">Välj en radartikel i rutnätet Fakturarader på sidan Fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="3a9c7-117">Klicka på snabbfältet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-117">Click the Line details FastTab.</span></span> <span data-ttu-id="3a9c7-118">Ange Anläggningstillgångsnumret och boken för avyttringstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="3a9c7-119">För fritextfakturor är transaktionstypen för anläggningstillgångar alltid Avyttrande försäljning.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="3a9c7-120">Anskaffning och källa</span><span class="sxs-lookup"><span data-stu-id="3a9c7-120">Procurement and sourcing</span></span>
<span data-ttu-id="3a9c7-121">Du kan ange transaktioner för anläggningstillgångar på sidan Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="3a9c7-122">Ange nödvändig information för att skapa en inköpsorder och klicka sedan på OK.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="3a9c7-123">Klicka på snabbfliken Radinformation på sidan Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="3a9c7-124">Ange sedan information om anläggningstillgången på fliken Anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="3a9c7-125">Om du vill bokföra en anskaffningstransaktion för en befintlig anläggningstillgång anger du Anläggningstillgångsnumret, boken samt transaktionstypen.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="3a9c7-126">Anläggningstillgången kan inte bokföras om en del av den här informationen saknas.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="3a9c7-127">Om du vill bokföra en anskaffningstransaktion för en ny anläggningstillgång markerar du alternativet Ny anläggningstillgång? och väljer Anläggningstillgångsgruppen som den nya tillgången ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="3a9c7-128">Inget Anläggningstillgångsfält är emellertid tillgängligt för en rad om artikeln finns i en lagermodellgrupp som använder lagermodellen Standardkostnad.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="3a9c7-129">Alternativen som definierats på parametersidan Anläggningstillgångar bestämmer om du kan bokföra anskaffningstransaktioner från inköpsmodulerna.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="3a9c7-130">När inköpsorderjournalen eller journalen för lager till anläggningstillgångar används för anskaffning av anläggningstillgångar påverkas lagervärdet.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="3a9c7-131">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="3a9c7-131">General ledger</span></span>
<span data-ttu-id="3a9c7-132">Alla transaktionstyper för anläggningstillgångar kan bokföras på sidan Allmän journal.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="3a9c7-133">Du kan också använda journaler i Anläggningstillgångar för att bokföra transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="3a9c7-134">Alternativ för att ange transaktionstyper för anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="3a9c7-135">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="3a9c7-135">Transaction type</span></span>                    | <span data-ttu-id="3a9c7-136">Modul</span><span class="sxs-lookup"><span data-stu-id="3a9c7-136">Module</span></span>                   | <span data-ttu-id="3a9c7-137">Alternativ</span><span class="sxs-lookup"><span data-stu-id="3a9c7-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="3a9c7-138">Anskaffning, Anskaffningsjustering</span><span class="sxs-lookup"><span data-stu-id="3a9c7-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="3a9c7-139">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-139">Fixed assets</span></span>             | <span data-ttu-id="3a9c7-140">Anläggningstillgångar, Lager till anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="3a9c7-141">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="3a9c7-141">General ledger</span></span>           | <span data-ttu-id="3a9c7-142">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="3a9c7-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="3a9c7-143">Leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="3a9c7-143">Accounts payable</span></span>         | <span data-ttu-id="3a9c7-144">Fakturajournalen, Fakturagodkännandejournal.</span><span class="sxs-lookup"><span data-stu-id="3a9c7-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="3a9c7-145">Anskaffning och källa</span><span class="sxs-lookup"><span data-stu-id="3a9c7-145">Procurement and sourcing</span></span> | <span data-ttu-id="3a9c7-146">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="3a9c7-146">Purchase order</span></span>                            |
| <span data-ttu-id="3a9c7-147">Avskrivning</span><span class="sxs-lookup"><span data-stu-id="3a9c7-147">Depreciation</span></span>                        | <span data-ttu-id="3a9c7-148">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-148">Fixed assets</span></span>             | <span data-ttu-id="3a9c7-149">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="3a9c7-150">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="3a9c7-150">General ledger</span></span>           | <span data-ttu-id="3a9c7-151">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="3a9c7-151">General journal</span></span>                           |
| <span data-ttu-id="3a9c7-152">Avyttrande</span><span class="sxs-lookup"><span data-stu-id="3a9c7-152">Disposal</span></span>                            | <span data-ttu-id="3a9c7-153">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-153">Fixed assets</span></span>             | <span data-ttu-id="3a9c7-154">Anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="3a9c7-154">Fixed assets</span></span>                              |
| <span data-ttu-id="3a9c7-155">** **</span><span class="sxs-lookup"><span data-stu-id="3a9c7-155">** **</span></span>                               | <span data-ttu-id="3a9c7-156">Huvudbok</span><span class="sxs-lookup"><span data-stu-id="3a9c7-156">General ledger</span></span>           | <span data-ttu-id="3a9c7-157">Allmän journal</span><span class="sxs-lookup"><span data-stu-id="3a9c7-157">General journal</span></span>                           |
| <span data-ttu-id="3a9c7-158">** **</span><span class="sxs-lookup"><span data-stu-id="3a9c7-158">** **</span></span>                               | <span data-ttu-id="3a9c7-159">Kundreskontra</span><span class="sxs-lookup"><span data-stu-id="3a9c7-159">Accounts receivable</span></span>      | <span data-ttu-id="3a9c7-160">Fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="3a9c7-160">Free text invoice</span></span>                         |



<span data-ttu-id="3a9c7-161">Mer information finns i [Integrering av anläggningstillgångar](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="3a9c7-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




