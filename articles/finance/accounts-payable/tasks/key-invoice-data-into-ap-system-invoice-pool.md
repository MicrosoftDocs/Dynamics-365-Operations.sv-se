---
title: Mata in fakturadata i LR-systemet genom att använda fakturapool
description: I det här avsnittet beskrivs hur du använder fakturaregister för att skapa fakturor.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd6de42dda650d42d703e905f8d48f73b9e4afd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447955"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="f55e5-103">Mata in fakturadata i LR-systemet genom att använda fakturapool</span><span class="sxs-lookup"><span data-stu-id="f55e5-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f55e5-104">I det här avsnittet beskrivs hur du använder fakturaregister för att skapa fakturor.</span><span class="sxs-lookup"><span data-stu-id="f55e5-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="f55e5-105">Använd sedan fakturapoolen för att matcha fakturan till en inköpsorder och för att slutföra utgiften i leverantörsfakturasidan.</span><span class="sxs-lookup"><span data-stu-id="f55e5-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="f55e5-106">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="f55e5-106">Create a purchase order</span></span>
1. <span data-ttu-id="f55e5-107">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Inköpsorder > Inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="f55e5-108">Skapa en inköpsorder genom att välja **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="f55e5-109">I fältet **Leverantörskonto** väljer du en levernatör i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="f55e5-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="f55e5-110">Välj till exempel leverantör **1001**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="f55e5-111">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-111">Select **OK**.</span></span>
5. <span data-ttu-id="f55e5-112">I fält **Artikelnummer** klicka på tjänstartikeln i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="f55e5-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="f55e5-113">Välj till exempel **S0001**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-113">For example, select **S0001**.</span></span> <span data-ttu-id="f55e5-114">Nettobeloppet är 75.00.</span><span class="sxs-lookup"><span data-stu-id="f55e5-114">The net amount is 75.00.</span></span>  <span data-ttu-id="f55e5-115">Det är det belopp som ska förvänta vi på fakturan.</span><span class="sxs-lookup"><span data-stu-id="f55e5-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="f55e5-116">I åtgärdsfönstret, välj **Inköp**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="f55e5-117">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="f55e5-118">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="f55e5-118">Create and post and invoice</span></span>
1. <span data-ttu-id="f55e5-119">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturaregister**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="f55e5-120">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-120">Select **New**.</span></span>
3. <span data-ttu-id="f55e5-121">Öppna sökningen för att välja namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f55e5-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="f55e5-122">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f55e5-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="f55e5-123">Välj **Rader** om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="f55e5-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="f55e5-124">Välj en leverantör i sökningen.</span><span class="sxs-lookup"><span data-stu-id="f55e5-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="f55e5-125">Välj till exempel leverantör **1001**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="f55e5-126">Ange fakturanumret i fältet **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="f55e5-127">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="f55e5-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="f55e5-128">I fältet **Kredit** väljer du ett tal.</span><span class="sxs-lookup"><span data-stu-id="f55e5-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="f55e5-129">I fältet **Inköpsorder** öppnar du den nedrullningsbara listan för att välja den inköpsorder som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="f55e5-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="f55e5-130">Markera en godkännare i den nedrullningsbara listan i fältet **Godkänd av** och klicka på **Välj** för att välja godkännare.</span><span class="sxs-lookup"><span data-stu-id="f55e5-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="f55e5-131">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="f55e5-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="f55e5-132">Öppna en faktura från poolen och matcha den till en inköpsorder för att slutföra fakturaprocessen</span><span class="sxs-lookup"><span data-stu-id="f55e5-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="f55e5-133">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturapool**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="f55e5-134">Välj **Inköpsorder** om du vill skapa en leverantörsfaktura från fakturan i poolen.</span><span class="sxs-lookup"><span data-stu-id="f55e5-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="f55e5-135">Välj fakturan som du vill granska.</span><span class="sxs-lookup"><span data-stu-id="f55e5-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="f55e5-136">Välj **Uppdatera matchningsstatus** så utförs matchningen.</span><span class="sxs-lookup"><span data-stu-id="f55e5-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="f55e5-137">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f55e5-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="f55e5-138">Välj **Byt visning**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-138">Select **Change view**.</span></span>
7. <span data-ttu-id="f55e5-139">Välj **Rutnätsvy**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="f55e5-140">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="f55e5-140">Select **Post**.</span></span>
9. <span data-ttu-id="f55e5-141">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="f55e5-141">Close the form.</span></span>
10. <span data-ttu-id="f55e5-142">I navigeringsfönstret, gå till **Moduler > Leverantörsreskontra > Leverantörer > Leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="f55e5-143">Välj leverantören på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="f55e5-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="f55e5-144">Välj till exempel leverantör **1001**.</span><span class="sxs-lookup"><span data-stu-id="f55e5-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="f55e5-145">Klicka på **Leverantör** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f55e5-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="f55e5-146">Markera **transaktioner**</span><span class="sxs-lookup"><span data-stu-id="f55e5-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="f55e5-147">Välj den faktura som du själv har skapat.</span><span class="sxs-lookup"><span data-stu-id="f55e5-147">Select the invoice that you created.</span></span> <span data-ttu-id="f55e5-148">Ankomstregistreringaccrualen återfördes och bokförts i lämplig utgiftskonto.</span><span class="sxs-lookup"><span data-stu-id="f55e5-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

