---
title: Uppfyll försäljningsavtal
description: I den här proceduren visas hur du uppfyller ett försäljningsavtal genom att koppla försäljningsorder med det.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesTableListPage, SalesTable, AgreementLine, SalesCreateOrder,  SalesEditLines
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f03f05b85b8d242db1c85d0e84667949e241f1f7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563958"
---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="af07d-103">Uppfyll försäljningsavtal</span><span class="sxs-lookup"><span data-stu-id="af07d-103">Fulfill sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="af07d-104">I den här proceduren visas hur du uppfyller ett försäljningsavtal genom att koppla försäljningsorder med det.</span><span class="sxs-lookup"><span data-stu-id="af07d-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="af07d-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="af07d-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="af07d-106">Innan du startar guiden ser du till att du har ett gällande försäljningsavtal av typen Utfästelse för produktvärde.</span><span class="sxs-lookup"><span data-stu-id="af07d-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="af07d-107">Alternativt kan du köra den guiden som heter ”Skapa försäljningsavtal".</span><span class="sxs-lookup"><span data-stu-id="af07d-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="af07d-108">Frisläppa en försäljningsorder som avtalet</span><span class="sxs-lookup"><span data-stu-id="af07d-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="af07d-109">Gå till försäljning och marknadsföring > Försäljning avtal > försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="af07d-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="af07d-110">I listan öppnar du avtalet som du vill släppa ordern mot.</span><span class="sxs-lookup"><span data-stu-id="af07d-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="af07d-111">Klicka på Försäljningsavtal i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="af07d-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="af07d-112">Klicka på Frisläpp order.</span><span class="sxs-lookup"><span data-stu-id="af07d-112">Click Release order.</span></span>
    * <span data-ttu-id="af07d-113">Som texten överst på sidan Skapa frisläppningsorder anger, skiljer sig uppgifterna som behövs på försäljningsorderraderna åt, beroende på om avtalet är baserat på kvantitet eller värde.</span><span class="sxs-lookup"><span data-stu-id="af07d-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="af07d-114">Avtalet i den här guiden är av typen Utfästelse för produktvärde.</span><span class="sxs-lookup"><span data-stu-id="af07d-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="af07d-115">Det är därför radavsnittet på den här sidan är tom.</span><span class="sxs-lookup"><span data-stu-id="af07d-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="af07d-116">Om utfästelsen hade varit baserad på kvantitet, skulle radinformationen ha kopierats från avtalet.</span><span class="sxs-lookup"><span data-stu-id="af07d-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="af07d-117">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="af07d-117">Click Create.</span></span>
    * <span data-ttu-id="af07d-118">Meddelandet informerar dig om att en försäljningsorder har skapats.</span><span class="sxs-lookup"><span data-stu-id="af07d-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="af07d-119">Eftersom ordern inte innehåller några rader, måste du lägga till orderraddetaljer för att slutföra leveransprocessen.</span><span class="sxs-lookup"><span data-stu-id="af07d-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="af07d-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-120">Close the page.</span></span>
7. <span data-ttu-id="af07d-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-121">Close the page.</span></span>
8. <span data-ttu-id="af07d-122">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="af07d-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="af07d-123">I listan letar du reda på ordern som har skapats som resultatet av orderfrisläppandet i föregående uppgift. Öppna ordern.</span><span class="sxs-lookup"><span data-stu-id="af07d-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="af07d-124">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="af07d-124">Click Add line.</span></span>
11. <span data-ttu-id="af07d-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="af07d-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="af07d-126">Ange eller välj artikeln som anges på det associerade försäljningsavtalet i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="af07d-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="af07d-127">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="af07d-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="af07d-128">Se till att du anger en kvantitet som gör att nettovärdet är lägre än värdet i det associerade försäljningsavtalet.</span><span class="sxs-lookup"><span data-stu-id="af07d-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="af07d-129">Observera att eftersom försäljningsordern är länkad till avtalet, gäller den förhandlade rabattprocenten orderraden.</span><span class="sxs-lookup"><span data-stu-id="af07d-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="af07d-130">Klicka på Uppdatera rad.</span><span class="sxs-lookup"><span data-stu-id="af07d-130">Click Update line.</span></span>
15. <span data-ttu-id="af07d-131">Klicka på Kopplat.</span><span class="sxs-lookup"><span data-stu-id="af07d-131">Click Attached.</span></span>
    * <span data-ttu-id="af07d-132">På sidan Bifogat avtal visas id:t och villkoren för avtalet som raden har släppts från.</span><span class="sxs-lookup"><span data-stu-id="af07d-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="af07d-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-133">Close the page.</span></span>
17. <span data-ttu-id="af07d-134">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="af07d-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="af07d-135">Klicka på Bifogat försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="af07d-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="af07d-136">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="af07d-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="af07d-137">Klicka på fliken Uppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="af07d-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="af07d-138">Uppfyllelsefliken visar en sammanfattning av alla försäljningsorderrader som är kopplade till den här åtagandet och dess läge samt beloppet och kvantiteten som ännu inte har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="af07d-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="af07d-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-139">Close the page.</span></span>
22. <span data-ttu-id="af07d-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-140">Close the page.</span></span>
23. <span data-ttu-id="af07d-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="af07d-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="af07d-142">Använda försäljningsavtal i orderprocessen</span><span class="sxs-lookup"><span data-stu-id="af07d-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="af07d-143">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="af07d-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="af07d-144">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="af07d-144">Click New.</span></span>
3. <span data-ttu-id="af07d-145">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="af07d-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="af07d-146">I listan väljer du den kund som anges i försäljningsavtalet.</span><span class="sxs-lookup"><span data-stu-id="af07d-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="af07d-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="af07d-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="af07d-148">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="af07d-148">Expand the General section.</span></span>
7. <span data-ttu-id="af07d-149">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsavtals-ID.</span><span class="sxs-lookup"><span data-stu-id="af07d-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="af07d-150">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="af07d-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="af07d-151">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="af07d-151">Click Yes.</span></span>
10. <span data-ttu-id="af07d-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="af07d-152">Click OK.</span></span>
11. <span data-ttu-id="af07d-153">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="af07d-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="af07d-154">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="af07d-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="af07d-155">Ange eller välj artikeln som anges på det associerade försäljningsavtalet i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="af07d-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="af07d-156">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="af07d-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="af07d-157">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="af07d-157">Click Save.</span></span>
16. <span data-ttu-id="af07d-158">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="af07d-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="af07d-159">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="af07d-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="af07d-160">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="af07d-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="af07d-161">Välj Ja i fältet Bokför.</span><span class="sxs-lookup"><span data-stu-id="af07d-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="af07d-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="af07d-162">Click OK.</span></span>
21. <span data-ttu-id="af07d-163">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="af07d-163">Click OK.</span></span>
22. <span data-ttu-id="af07d-164">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="af07d-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="af07d-165">Klicka på Bifogat försäljningsavtal.</span><span class="sxs-lookup"><span data-stu-id="af07d-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="af07d-166">Klicka på fliken Uppfyllelse.</span><span class="sxs-lookup"><span data-stu-id="af07d-166">Click the Fulfillment tab.</span></span>

