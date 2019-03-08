---
title: Skapa fakturor för försäljningsorder
description: Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a57d204c0dcb44cbce7a0cc4d2f00b75b57e219
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "353320"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="bdca4-103">Skapa fakturor för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="bdca4-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bdca4-104">Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="bdca4-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="bdca4-105">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="bdca4-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="bdca4-106">Skapa en faktura från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="bdca4-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="bdca4-107">Gå till Kundreskontra > Order > Levererade men inte fakturerade försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="bdca4-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="bdca4-108">Välj en försäljningsorder i listan.</span><span class="sxs-lookup"><span data-stu-id="bdca4-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="bdca4-109">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bdca4-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="bdca4-110">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-110">Click Invoice.</span></span>
    * <span data-ttu-id="bdca4-111">Observera att den här försäljningsordern har flera följesedlar som associeras med den.</span><span class="sxs-lookup"><span data-stu-id="bdca4-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="bdca4-112">Här visas bara ordet <multiple> i stället för följesedelsnumret.</span><span class="sxs-lookup"><span data-stu-id="bdca4-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="bdca4-113">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="bdca4-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="bdca4-114">Bokföring måste ställas in på Ja när du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="bdca4-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="bdca4-115">Du kan även stänga av bokföring och bara skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="bdca4-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="bdca4-116">Men du kan få samma resultat genom att skapa en proformafaktura i stället för en faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="bdca4-117">Detta alternativ används för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="bdca4-117">This option is used for batch jobs.</span></span> <span data-ttu-id="bdca4-118">Frågan körs när batchjobbet körs.</span><span class="sxs-lookup"><span data-stu-id="bdca4-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="bdca4-119">Välj "Efter" i fältet Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="bdca4-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="bdca4-120">Välj Ja för Skriv ut faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="bdca4-121">Med Utskriftshantering kan du skriva ut flera kopior av fakturan och också skicka fakturan med e-post som en PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="bdca4-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="bdca4-122">I fältet Skriv ut avgifter väljer du "Summera".</span><span class="sxs-lookup"><span data-stu-id="bdca4-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="bdca4-123">I checkkreditgränsfältet väljer du ”Saldo”.</span><span class="sxs-lookup"><span data-stu-id="bdca4-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="bdca4-124">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="bdca4-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="bdca4-125">Kombinera order till en enda faktura</span><span class="sxs-lookup"><span data-stu-id="bdca4-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="bdca4-126">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="bdca4-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="bdca4-127">Leta upp en kund som har flera öppna fakturor.</span><span class="sxs-lookup"><span data-stu-id="bdca4-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="bdca4-128">Välj en öppen försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="bdca4-128">Select an open sales order.</span></span>
4. <span data-ttu-id="bdca4-129">Visa en annan öppen försäljningsorder för samma kund.</span><span class="sxs-lookup"><span data-stu-id="bdca4-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="bdca4-130">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="bdca4-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="bdca4-131">Klicka på faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-131">Click Invoice.</span></span>
7. <span data-ttu-id="bdca4-132">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="bdca4-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="bdca4-133">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="bdca4-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="bdca4-134">Observera att det finns två fakturor som anges i översiktsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="bdca4-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="bdca4-135">Låt oss nu sammanslå dem till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="bdca4-136">Välj "Fakturakonto" i fältet Samlingsuppdatera.</span><span class="sxs-lookup"><span data-stu-id="bdca4-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="bdca4-137">Klicka på ordna så slår du ihop dessa försäljningsorder till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="bdca4-138">Dessa två försäljningsorder sammanslås nu till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="bdca4-139">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="bdca4-139">Click Cancel.</span></span>
12. <span data-ttu-id="bdca4-140">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="bdca4-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="bdca4-141">Bokför fakturor i en batch</span><span class="sxs-lookup"><span data-stu-id="bdca4-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="bdca4-142">Gå till Kundreskontra > Fakturor > Batchfakturering > Faktura.</span><span class="sxs-lookup"><span data-stu-id="bdca4-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="bdca4-143">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="bdca4-143">Click Select.</span></span>
3. <span data-ttu-id="bdca4-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bdca4-144">Click OK.</span></span>
4. <span data-ttu-id="bdca4-145">Klicka på Batch.</span><span class="sxs-lookup"><span data-stu-id="bdca4-145">Click Batch.</span></span>
5. <span data-ttu-id="bdca4-146">Klicka på Ja om du vill slå på batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="bdca4-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="bdca4-147">Klicka på Upprepning.</span><span class="sxs-lookup"><span data-stu-id="bdca4-147">Click Recurrence.</span></span>
7. <span data-ttu-id="bdca4-148">Välj Dagar</span><span class="sxs-lookup"><span data-stu-id="bdca4-148">Select Days</span></span>
8. <span data-ttu-id="bdca4-149">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bdca4-149">Click OK.</span></span>
9. <span data-ttu-id="bdca4-150">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="bdca4-150">Click OK.</span></span>
10. <span data-ttu-id="bdca4-151">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="bdca4-151">Click Cancel.</span></span>
11. <span data-ttu-id="bdca4-152">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="bdca4-152">Click Yes.</span></span>

