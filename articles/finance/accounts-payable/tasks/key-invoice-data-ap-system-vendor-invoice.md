---
title: Huvudfakturadata i AP med hjälp av leverantörsfakturan
description: Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f80c88b7fb3542f624d233f670cd7cd6ccd48b94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447845"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="05f4e-103">Huvudfakturadata i AP med hjälp av leverantörsfakturan</span><span class="sxs-lookup"><span data-stu-id="05f4e-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="05f4e-104">Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).</span><span class="sxs-lookup"><span data-stu-id="05f4e-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="05f4e-105">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="05f4e-105">Create a purchase order</span></span>
1. <span data-ttu-id="05f4e-106">I navigeringsfönstret går du till **moduler > leverantörsreskontra > inköpsorder > alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="05f4e-107">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-107">Click **New**.</span></span>
3. <span data-ttu-id="05f4e-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="05f4e-109">Sök efter en leverantör att välja.</span><span class="sxs-lookup"><span data-stu-id="05f4e-109">Find a vendor to select.</span></span> <span data-ttu-id="05f4e-110">Rulla nedåt till US-104, till exempel.</span><span class="sxs-lookup"><span data-stu-id="05f4e-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="05f4e-111">Välj leverantör US-104.</span><span class="sxs-lookup"><span data-stu-id="05f4e-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="05f4e-112">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-112">Click **OK**.</span></span>
7. <span data-ttu-id="05f4e-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="05f4e-114">Välj en lagerartikel.</span><span class="sxs-lookup"><span data-stu-id="05f4e-114">Select an inventory item.</span></span> <span data-ttu-id="05f4e-115">I det här exemplet väljer du artikelnummer 1000.</span><span class="sxs-lookup"><span data-stu-id="05f4e-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="05f4e-116">Visa snabbfliken **Radinformation**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="05f4e-117">Klicka på fliken **Inställningar** Du kan åsidosätta matchningspolicyn om du vill använda ingen matchning, tvåvägsmatchning eller trevägsmatchning.</span><span class="sxs-lookup"><span data-stu-id="05f4e-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="05f4e-118">I åtgärdsrutan, klicka på **Köp**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="05f4e-119">Klicka på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="05f4e-120">Ta emot produkterna</span><span class="sxs-lookup"><span data-stu-id="05f4e-120">Receive the products</span></span>
1. <span data-ttu-id="05f4e-121">I åtgärdsrutan, klicka på **Ta emot**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="05f4e-122">Klicka på **Produktinleverans**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="05f4e-123">Ange produktinleveransnumret i fältet **Produktinleverans**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="05f4e-124">Ange exempelvis PR123.</span><span class="sxs-lookup"><span data-stu-id="05f4e-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="05f4e-125">Klicka på **OK** när du vill bokföra produktinleveransen.</span><span class="sxs-lookup"><span data-stu-id="05f4e-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="05f4e-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05f4e-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="05f4e-127">Skapa en leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="05f4e-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="05f4e-128">I navigeringsfönstret går du till **moduler > leverantörsreskontra > inköpsorder > inköpsorder har inlevererats men inte fakturerats**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="05f4e-129">Välj inköpsordern som du skapat.</span><span class="sxs-lookup"><span data-stu-id="05f4e-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="05f4e-130">I åtgärdsrutan, klicka på **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="05f4e-131">Klicka på **faktura**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="05f4e-132">Ange fakturanumret i fältet **Nummer**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="05f4e-133">Ange ett värde i fältet **Fakturabeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="05f4e-134">Ange ett datum i fältet **Fakturadatum**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="05f4e-135">Ange 1200 i fältet **Enhetspris**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="05f4e-136">Klicka på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-136">Click **Add line**.</span></span>
10. <span data-ttu-id="05f4e-137">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="05f4e-138">Sök efter artikelnumret med installationavgiften i listan.</span><span class="sxs-lookup"><span data-stu-id="05f4e-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="05f4e-139">Till exempel S0001</span><span class="sxs-lookup"><span data-stu-id="05f4e-139">For example, S0001</span></span>
12. <span data-ttu-id="05f4e-140">Välj artikelnumret med installationavgiften.</span><span class="sxs-lookup"><span data-stu-id="05f4e-140">Select the installation charge item number.</span></span> <span data-ttu-id="05f4e-141">Notera att matchning inte har utförts sedan du utförde ändringarna.</span><span class="sxs-lookup"><span data-stu-id="05f4e-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="05f4e-142">Klicka på **Uppdatera matchningsstatus**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="05f4e-143">Klicka på **Granska** i åtgärdsrutan.</span><span class="sxs-lookup"><span data-stu-id="05f4e-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="05f4e-144">Klicka på **Matcha detaljer**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-144">Click **Matching details**.</span></span> <span data-ttu-id="05f4e-145">Den nya raden med tjänster behöver inte matchas, så statusen är fortfarande ”Inte utförd”.</span><span class="sxs-lookup"><span data-stu-id="05f4e-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="05f4e-146">Välj produktinleveransen för lagerartikeln som du har fått.</span><span class="sxs-lookup"><span data-stu-id="05f4e-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="05f4e-147">Raden med produktinleveransen matchades, men det fanns en felmatchning av kvantiteten eller priset, så den misslyckades.</span><span class="sxs-lookup"><span data-stu-id="05f4e-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="05f4e-148">Ange ett tal i fältet **Enhetspris**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="05f4e-149">När nu priset per enhet matchar, uppdateras statusvärdet till Godkänt.</span><span class="sxs-lookup"><span data-stu-id="05f4e-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="05f4e-150">Om din policy tillåter avvikelser, eller om matchningen bara är en varning, kan du fortfarande bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="05f4e-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="05f4e-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="05f4e-151">Close the page.</span></span>
19. <span data-ttu-id="05f4e-152">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="05f4e-152">Click **Post**.</span></span>
20. <span data-ttu-id="05f4e-153">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="05f4e-153">Close the form.</span></span> <span data-ttu-id="05f4e-154">Observera att inköpsordern inte längre registreras som mottagen men inte fakturerad.</span><span class="sxs-lookup"><span data-stu-id="05f4e-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

