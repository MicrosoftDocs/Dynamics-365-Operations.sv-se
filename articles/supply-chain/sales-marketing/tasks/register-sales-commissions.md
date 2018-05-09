--- 
title: "Registrera försäljningsprovisioner"
description: "I den här proceduren visas hur försäljningsprovisioner beräknas och registreras."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0fad3c62f926e508e09a265a600194b7ea595bf0
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="register-sales-commissions"></a><span data-ttu-id="70b62-103">Registrera försäljningsprovisioner</span><span class="sxs-lookup"><span data-stu-id="70b62-103">Register sales commissions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70b62-104">I den här proceduren visas hur försäljningsprovisioner beräknas och registreras.</span><span class="sxs-lookup"><span data-stu-id="70b62-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="70b62-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="70b62-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="70b62-106">Innan du startar guiden kör du guiden ”Ställ in regler för försäljningsprovision” för att vara säker på att alla nödvändiga inställningar för provisionsberäkningen har gjorts.</span><span class="sxs-lookup"><span data-stu-id="70b62-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="70b62-107">Skriv upp kundnumren och artikelnumret du har valt för provisionsprocessen, och använd dem när du ska skapa en försäljningsorder i den här guiden.</span><span class="sxs-lookup"><span data-stu-id="70b62-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="70b62-108">Fakturera en försäljningsorder som kvalificerar en säljare för provision</span><span class="sxs-lookup"><span data-stu-id="70b62-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="70b62-109">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="70b62-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="70b62-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="70b62-110">Click New.</span></span>
3. <span data-ttu-id="70b62-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="70b62-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="70b62-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="70b62-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="70b62-113">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="70b62-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="70b62-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70b62-114">Click OK.</span></span>
7. <span data-ttu-id="70b62-115">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70b62-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="70b62-116">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="70b62-116">Click Change view.</span></span>
9. <span data-ttu-id="70b62-117">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="70b62-117">Click Header view.</span></span>
10. <span data-ttu-id="70b62-118">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="70b62-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="70b62-119">Värdet i försäljningsgruppfältet representerar en grupp med en eller flera säljare som har kopplats till det.</span><span class="sxs-lookup"><span data-stu-id="70b62-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="70b62-120">Människorna i gruppen är de som ska få provision när ordern är fakturerad enligt fördefinierade frekvenser och distribution.</span><span class="sxs-lookup"><span data-stu-id="70b62-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="70b62-121">Värdet kopieras från kund-kort, men du kan ändra det om du vill.</span><span class="sxs-lookup"><span data-stu-id="70b62-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="70b62-122">Försäljningsgruppen finns också kopieras till kundorderraden.</span><span class="sxs-lookup"><span data-stu-id="70b62-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="70b62-123">Du kan ändra den, så att den kan skilja sig från den i huvudet och/eller mellan raderna.</span><span class="sxs-lookup"><span data-stu-id="70b62-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="70b62-124">Värdet i provisiongruppsfältet representerar en grupp som du har skapat för en eller flera kunder med syftet att spåra provisioner.</span><span class="sxs-lookup"><span data-stu-id="70b62-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="70b62-125">Värdet kopieras från kund-kort, men du kan ändra det om du vill.</span><span class="sxs-lookup"><span data-stu-id="70b62-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="70b62-126">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70b62-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="70b62-127">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="70b62-127">Click Change view.</span></span>
13. <span data-ttu-id="70b62-128">Klicka på Radvy.</span><span class="sxs-lookup"><span data-stu-id="70b62-128">Click Line view.</span></span>
14. <span data-ttu-id="70b62-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="70b62-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="70b62-130">Välj den artikel som du har ställt in för provisioner i listan.</span><span class="sxs-lookup"><span data-stu-id="70b62-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="70b62-131">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70b62-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="70b62-132">Observera radens nettobelopp.</span><span class="sxs-lookup"><span data-stu-id="70b62-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="70b62-133">Det representerar försäljningsintäkten, som i det här exemplet är grunden för provisionsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="70b62-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="70b62-134">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="70b62-134">Click Save.</span></span>
18. <span data-ttu-id="70b62-135">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70b62-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="70b62-136">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="70b62-136">Click Invoice.</span></span>
20. <span data-ttu-id="70b62-137">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="70b62-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="70b62-138">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="70b62-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="70b62-139">Välj Ja i fältet Bokför.</span><span class="sxs-lookup"><span data-stu-id="70b62-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="70b62-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70b62-140">Click OK.</span></span>
24. <span data-ttu-id="70b62-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="70b62-141">Click OK.</span></span>
    * <span data-ttu-id="70b62-142">Den kan ta minut eller så att bokföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="70b62-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="70b62-143">Tillåt processen att slutföras och stäng inte sidan.</span><span class="sxs-lookup"><span data-stu-id="70b62-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="70b62-144">Granska de registrerade försäljningsprovisionerna</span><span class="sxs-lookup"><span data-stu-id="70b62-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="70b62-145">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70b62-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="70b62-146">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="70b62-146">Click Invoice.</span></span>
3. <span data-ttu-id="70b62-147">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="70b62-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="70b62-148">Klicka på Provisionstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="70b62-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="70b62-149">På fliken Översikt visas raderna med provisionsbeloppen som är betalning till säljare som är kopplade till den fakturerade försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="70b62-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="70b62-150">Vi tar en titt på detaljerna.</span><span class="sxs-lookup"><span data-stu-id="70b62-150">Let's review the details.</span></span>     
    * <span data-ttu-id="70b62-151">Om du använde guiden ”Ställ in regler för försäljningsprovision” när du ställde in försäljningsprovisionsgruppen, finns det två säljare som får provision och provisionen fördelas lika mellan dem.</span><span class="sxs-lookup"><span data-stu-id="70b62-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="70b62-152">I det här exemplet beräknas provisionens totala belopp som procent av försäljningsintäkten (nettobeloppet på orderraden).</span><span class="sxs-lookup"><span data-stu-id="70b62-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="70b62-153">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="70b62-153">Close the page.</span></span>
6. <span data-ttu-id="70b62-154">Klicka på Verifikation.</span><span class="sxs-lookup"><span data-stu-id="70b62-154">Click Voucher.</span></span>
    * <span data-ttu-id="70b62-155">Du kan granska de verifikationstransaktionerna för provisionsbeloppen som har bokförts på de fördefinierade kontona för provisionsutgiften och provisionsskulden.</span><span class="sxs-lookup"><span data-stu-id="70b62-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


