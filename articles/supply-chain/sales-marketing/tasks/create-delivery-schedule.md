--- 
title: Skapa leveransplaner
description: "Den här proceduren visas hur du kan skapa en leveransplan för en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d99dfae5e045262d34daf3529a6a3f4716b4afe3
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-delivery-schedule"></a><span data-ttu-id="d1f7e-103">Skapa leveransplaner</span><span class="sxs-lookup"><span data-stu-id="d1f7e-103">Create delivery schedule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1f7e-104">Den här proceduren visas hur du kan skapa en leveransplan för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="d1f7e-105">En leveransplan används när en kvantitet på en order eller en offert begärs för att levereras i flera försändelser.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="d1f7e-106">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="d1f7e-107">Skapa leveransplaner</span><span class="sxs-lookup"><span data-stu-id="d1f7e-107">Create delivery schedule</span></span>
1. <span data-ttu-id="d1f7e-108">Gå till Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="d1f7e-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-109">Click New.</span></span>
3. <span data-ttu-id="d1f7e-110">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="d1f7e-111">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-111">Click OK.</span></span>
5. <span data-ttu-id="d1f7e-112">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="d1f7e-113">Ange ett tal som är större än 1 i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="d1f7e-114">Klicka på Försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-114">Click Sales order line.</span></span>
8. <span data-ttu-id="d1f7e-115">Klicka på Leveransplan.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="d1f7e-116">Leveransplansidan är stället där du kan ange antalet leveranser för den totala kvantiteten på orderraden som ska levereras till kunden.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="d1f7e-117">Som standard kopierar systemet den totala kvantiteten och andra leveransdetaljer för de ursprungliga försäljningsraderna till den första leveransplanraden.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="d1f7e-118">I det här exemplet ska du skapa ett schema för två leveranser, med det andra leveransdatumet med förskjutning på en vecka efter den första.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-118">In this example, we’ll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="d1f7e-119">Ange ett tal som är en del av den totala kvantiteten i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="d1f7e-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-120">Click New.</span></span>
11. <span data-ttu-id="d1f7e-121">Ange den återstående kvantiteten i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="d1f7e-122">Ange ett datum som infaller en vecka framåt från datumet för den första leveransraden i fältet Begärt transportdatum.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="d1f7e-123">De två alternativen på avgiftskonverteringssnabbfliken styr hur du vill att avgifterna ska fördelas mellan leveransplanraderna, när de har tilldelats till den ursprungliga orderraden.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they’ve been assigned to the original order line.</span></span> <span data-ttu-id="d1f7e-124">Om du väljer att kopiera bruttobelopp, kopieras samma avgiftsbelopp till varje rad.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="d1f7e-125">Med alternativet Fördela på leveransrader delas avgiften lika mellan leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="d1f7e-126">Endast fasta kostnader kan delas, medan variabla avgifter ska kopieras till raderna.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="d1f7e-127">Flytta markören från den andra leveransraden om du vill uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="d1f7e-128">Du kan spåra den totala kvantiteten som tilldelas till leveransplanraderna genom att visa summan och återstående fält.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-128">You can keep track of the total quantity that’s allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="d1f7e-129">När den resterande kvantiteten är noll, har den fullständiga kvantiteten från den ursprungliga raden allokerats till tidsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="d1f7e-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-130">Click OK.</span></span>
    * <span data-ttu-id="d1f7e-131">Leveransplanen har nu kopierats till orderraderna.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="d1f7e-132">Den ursprungliga orderraden som kallas för en kommersiell rad, har konverterats till en orderrad med flera leveranser.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="d1f7e-133">Den markeras med en särskild ikon och fungerar som rubrik för leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="d1f7e-134">De två nya raderna som kallas för leveransrader utgör en leveransplan.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="d1f7e-135">Ordern ska bearbetas mot dessa rader och inte den ursprungliga raden.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="d1f7e-136">Om dokument som bekräftelser, plocklistor, följesedlar eller fakturor skrivs ut, visas bara leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="d1f7e-137">Leveransraderna kan ha andra leveransdatum, kvantiteter, leveranssätt och lagringsdimensioner, till exempel plats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="d1f7e-138">Men produktdimensionerna måste alltid matcha dem på den kommersiella raden och kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="d1f7e-139">Ange ett tal som är större än det nuvarande i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="d1f7e-140">Markera den kommersiella raden för att se resultatet av kvantitetsomberäkningen.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="d1f7e-141">Klicka på Plocka och packa i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="d1f7e-142">Klicka på Bokför följesedel.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="d1f7e-143">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="d1f7e-144">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="d1f7e-145">Observera att följesedeln ska skapas för de två leveransplanraderna och inte den ursprungliga orderraden.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="d1f7e-146">Välj Ja i fältet Skriv ut följesedel.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="d1f7e-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-147">Click OK.</span></span>
23. <span data-ttu-id="d1f7e-148">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-148">Click Yes.</span></span>
24. <span data-ttu-id="d1f7e-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="d1f7e-149">Close the page.</span></span>


