---
title: Huvudfakturadata i AP-system med hjälp av leverantörsfakturan
description: Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569642"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="27032-103">Huvudfakturadata i AP-system med hjälp av leverantörsfakturan</span><span class="sxs-lookup"><span data-stu-id="27032-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27032-104">Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).</span><span class="sxs-lookup"><span data-stu-id="27032-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="27032-105">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="27032-105">Create a purchase order</span></span>
1. <span data-ttu-id="27032-106">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="27032-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="27032-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="27032-107">Click New.</span></span>
3. <span data-ttu-id="27032-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="27032-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="27032-109">Sök efter en leverantör att välja.</span><span class="sxs-lookup"><span data-stu-id="27032-109">Find a vendor to select.</span></span> <span data-ttu-id="27032-110">Rulla nedåt till US-104, till exempel.</span><span class="sxs-lookup"><span data-stu-id="27032-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="27032-111">Välj leverantör US-104.</span><span class="sxs-lookup"><span data-stu-id="27032-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="27032-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="27032-112">Click OK.</span></span>
7. <span data-ttu-id="27032-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="27032-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="27032-114">Välj en lagerartikel.</span><span class="sxs-lookup"><span data-stu-id="27032-114">Select an inventory item.</span></span> <span data-ttu-id="27032-115">I det här exemplet väljer du artikelnummer 1000.</span><span class="sxs-lookup"><span data-stu-id="27032-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="27032-116">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="27032-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="27032-117">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="27032-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="27032-118">Du kan åsidosätta matchningspolicyn om du vill använda ingen matchning, tvåvägsmatchning eller trevägsmatchning.</span><span class="sxs-lookup"><span data-stu-id="27032-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="27032-119">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="27032-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="27032-120">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="27032-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="27032-121">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="27032-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="27032-122">Ta emot produkterna</span><span class="sxs-lookup"><span data-stu-id="27032-122">Receive the products</span></span>
1. <span data-ttu-id="27032-123">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="27032-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="27032-124">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="27032-124">Click Product receipt.</span></span>
3. <span data-ttu-id="27032-125">Ange produktinleveransnumret i fältet Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="27032-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="27032-126">Ange exempelvis PR123.</span><span class="sxs-lookup"><span data-stu-id="27032-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="27032-127">Klicka på OK när du vill bokföra produktinleveransen.</span><span class="sxs-lookup"><span data-stu-id="27032-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="27032-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="27032-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="27032-129">Skapa en leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="27032-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="27032-130">Gå till Leverantörsreskontra > Inköpsorder > Inköpsorder som tagits emot men inte fakturerats.</span><span class="sxs-lookup"><span data-stu-id="27032-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="27032-131">Välj inköpsordern som du skapat.</span><span class="sxs-lookup"><span data-stu-id="27032-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="27032-132">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="27032-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="27032-133">Klicka på faktura.</span><span class="sxs-lookup"><span data-stu-id="27032-133">Click Invoice.</span></span>
5. <span data-ttu-id="27032-134">Ange fakturanumret i fältet Nummer.</span><span class="sxs-lookup"><span data-stu-id="27032-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="27032-135">Ange ett värde i fältet Fakturabeskrivning.</span><span class="sxs-lookup"><span data-stu-id="27032-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="27032-136">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="27032-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="27032-137">Ange 1200 i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="27032-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="27032-138">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="27032-138">Click Add line.</span></span>
10. <span data-ttu-id="27032-139">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="27032-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="27032-140">Sök efter artikelnumret med installationavgiften i listan.</span><span class="sxs-lookup"><span data-stu-id="27032-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="27032-141">Till exempel S0001</span><span class="sxs-lookup"><span data-stu-id="27032-141">For example, S0001</span></span>
12. <span data-ttu-id="27032-142">Välj artikelnumret med installationavgiften.</span><span class="sxs-lookup"><span data-stu-id="27032-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="27032-143">Notera att matchning inte har utförts sedan du utförde ändringarna.</span><span class="sxs-lookup"><span data-stu-id="27032-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="27032-144">Klicka på Uppdatera matchningsstatus.</span><span class="sxs-lookup"><span data-stu-id="27032-144">Click Update match status.</span></span>
14. <span data-ttu-id="27032-145">Klicka på Granska i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="27032-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="27032-146">Klicka på Matcha detaljer.</span><span class="sxs-lookup"><span data-stu-id="27032-146">Click Matching details.</span></span>
    * <span data-ttu-id="27032-147">Den nya raden med tjänster behöver inte matchas, så statusen är fortfarande ”Inte utförd”.</span><span class="sxs-lookup"><span data-stu-id="27032-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="27032-148">Välj produktinleveransen för lagerartikeln som du har fått.</span><span class="sxs-lookup"><span data-stu-id="27032-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="27032-149">Raden med produktinleveransen matchades, men det fanns en felmatchning av kvantiteten eller priset, så den misslyckades.</span><span class="sxs-lookup"><span data-stu-id="27032-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="27032-150">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="27032-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="27032-151">När nu priset per enhet matchar, uppdateras statusvärdet till Godkänt.</span><span class="sxs-lookup"><span data-stu-id="27032-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="27032-152">Om din policy tillåter avvikelser, eller om matchningen bara är en varning, kan du fortfarande bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="27032-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="27032-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="27032-153">Close the page.</span></span>
19. <span data-ttu-id="27032-154">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="27032-154">Click Post.</span></span>
20. <span data-ttu-id="27032-155">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="27032-155">Close the form.</span></span>
    * <span data-ttu-id="27032-156">Observera att inköpsordern inte längre registreras som mottagen men inte fakturerad.</span><span class="sxs-lookup"><span data-stu-id="27032-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

