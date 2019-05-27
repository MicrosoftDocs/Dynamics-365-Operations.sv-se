---
title: Mata in fakturadata i LR-systemet genom att använda fakturapool
description: Den här uppgifthandbok visas om hur du använder ankomstregistreringen om du vill skapa fakturor.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b4e9a52a383d4acc0bf2adc669fd88c0c0f7402
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550361"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="f677c-103">Mata in fakturadata i LR-systemet genom att använda fakturapool</span><span class="sxs-lookup"><span data-stu-id="f677c-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f677c-104">Den här uppgifthandbok visas om hur du använder ankomstregistreringen om du vill skapa fakturor.</span><span class="sxs-lookup"><span data-stu-id="f677c-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="f677c-105">Använd sedan fakturapoolen för att matcha fakturan till en inköpsorder och för att slutföra utgiften i leverantörsfakturasidan.</span><span class="sxs-lookup"><span data-stu-id="f677c-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="f677c-106">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f677c-106">Create a purchase order</span></span>
1. <span data-ttu-id="f677c-107">Gå till Leverantörsreskontra > Inköpsorder > Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f677c-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="f677c-108">Skapa en inköpsorder genom att klicka på Nytt.</span><span class="sxs-lookup"><span data-stu-id="f677c-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="f677c-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Vendor account.</span><span class="sxs-lookup"><span data-stu-id="f677c-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="f677c-110">Välj leverantören i listan.</span><span class="sxs-lookup"><span data-stu-id="f677c-110">Select the vendor from the list.</span></span> <span data-ttu-id="f677c-111">Till exempel visas leverantör 1001.</span><span class="sxs-lookup"><span data-stu-id="f677c-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="f677c-112">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f677c-112">Click OK.</span></span>
6. <span data-ttu-id="f677c-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Item number.</span><span class="sxs-lookup"><span data-stu-id="f677c-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="f677c-114">Hitta tjänstartikelnumret i listan.</span><span class="sxs-lookup"><span data-stu-id="f677c-114">Find the services item number in the list.</span></span> <span data-ttu-id="f677c-115">Välj till exempel S0001.</span><span class="sxs-lookup"><span data-stu-id="f677c-115">For example, select S0001.</span></span>
8. <span data-ttu-id="f677c-116">Klicka på artikelnumret och välj det.</span><span class="sxs-lookup"><span data-stu-id="f677c-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="f677c-117">Nettobeloppet är 75.00.</span><span class="sxs-lookup"><span data-stu-id="f677c-117">The net amount is 75.00.</span></span>  <span data-ttu-id="f677c-118">Det är det belopp som ska förvänta vi på fakturan.</span><span class="sxs-lookup"><span data-stu-id="f677c-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="f677c-119">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f677c-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="f677c-120">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="f677c-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="f677c-121">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="f677c-121">Create and post and invoice</span></span>
1. <span data-ttu-id="f677c-122">Gå till Leverantörsreskontra > Fakturor > Fakturaregister.</span><span class="sxs-lookup"><span data-stu-id="f677c-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="f677c-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f677c-123">Click New.</span></span>
3. <span data-ttu-id="f677c-124">Öppna sökningen för att välja namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f677c-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="f677c-125">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f677c-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="f677c-126">Klicka på på Rader om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="f677c-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="f677c-127">Välj en leverantör i sökningen.</span><span class="sxs-lookup"><span data-stu-id="f677c-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="f677c-128">Klicka till exempel på leverantör 1001.</span><span class="sxs-lookup"><span data-stu-id="f677c-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="f677c-129">Ange fakturanumret i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="f677c-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="f677c-130">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f677c-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="f677c-131">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="f677c-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="f677c-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Purchase order.</span><span class="sxs-lookup"><span data-stu-id="f677c-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="f677c-133">Välj inköpsordern som du skapat förut.</span><span class="sxs-lookup"><span data-stu-id="f677c-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="f677c-134">Öppna sökningen genom att klicka på den nedrullningsbara knappen Approved by.</span><span class="sxs-lookup"><span data-stu-id="f677c-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="f677c-135">Välj en godkännare och klicka sedan på Välj om du vill välja den godkännaren.</span><span class="sxs-lookup"><span data-stu-id="f677c-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="f677c-136">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="f677c-136">Click Post.</span></span>
15. <span data-ttu-id="f677c-137">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="f677c-137">Close the form.</span></span>
16. <span data-ttu-id="f677c-138">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="f677c-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="f677c-139">Öppna en faktura från poolen och matcha den till en inköpsorder för att slutföra fakturaprocessen</span><span class="sxs-lookup"><span data-stu-id="f677c-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="f677c-140">Gå till Leverantörsreskontra > Fakturor > Fakturapool.</span><span class="sxs-lookup"><span data-stu-id="f677c-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="f677c-141">Klicka på Inköpsorder om du vill skapa en leverantörsfaktura från fakturan i poolen.</span><span class="sxs-lookup"><span data-stu-id="f677c-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="f677c-142">Välj fakturan som du vill granska.</span><span class="sxs-lookup"><span data-stu-id="f677c-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="f677c-143">Klicka på Uppdatera matchningsstatus så utförs matchningen.</span><span class="sxs-lookup"><span data-stu-id="f677c-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="f677c-144">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f677c-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="f677c-145">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="f677c-145">Click Change view.</span></span>
7. <span data-ttu-id="f677c-146">Klicka på Diagramvy.</span><span class="sxs-lookup"><span data-stu-id="f677c-146">Click Grid view.</span></span>
8. <span data-ttu-id="f677c-147">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="f677c-147">Click Post.</span></span>
9. <span data-ttu-id="f677c-148">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="f677c-148">Close the form.</span></span>
10. <span data-ttu-id="f677c-149">Gå till leverantörsreskontra > Leverantörer > Leverantörer.</span><span class="sxs-lookup"><span data-stu-id="f677c-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="f677c-150">Välj leverantören på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="f677c-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="f677c-151">Välj till exempel leverantör 1001.</span><span class="sxs-lookup"><span data-stu-id="f677c-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="f677c-152">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f677c-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="f677c-153">Klicka på Leverantör i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f677c-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="f677c-154">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="f677c-154">Click Transactions.</span></span>
15. <span data-ttu-id="f677c-155">Välj den faktura som du själv har skapat.</span><span class="sxs-lookup"><span data-stu-id="f677c-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="f677c-156">Ankomstregistreringaccrualen återfördes och bokförts i lämplig utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="f677c-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

