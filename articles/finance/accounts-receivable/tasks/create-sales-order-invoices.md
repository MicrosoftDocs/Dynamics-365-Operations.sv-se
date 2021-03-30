---
title: Skapa fakturor för försäljningsorder
description: Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d2e1dd552f529d09756c1ddeec39fc54a1f073a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241596"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="7f45a-103">Skapa fakturor för försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="7f45a-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f45a-104">Den här uppgiftsguiden beskriver fakturering av en försäljningsorder, inklusive att sammanslå fakturor och batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="7f45a-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="7f45a-105">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="7f45a-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="7f45a-106">Skapa en faktura från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="7f45a-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="7f45a-107">Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Levererade men inte fakturerade försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="7f45a-108">Välj en försäljningsorder i listan.</span><span class="sxs-lookup"><span data-stu-id="7f45a-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="7f45a-109">I **åtgärdsrutan**, klicka på **Faktura > Generera > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="7f45a-110">Observera att den här försäljningsordern har flera följesedlar som associeras med den.</span><span class="sxs-lookup"><span data-stu-id="7f45a-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="7f45a-111">Här visas bara ordet <multiple> i stället för följesedelsnumret.</span><span class="sxs-lookup"><span data-stu-id="7f45a-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="7f45a-112">Expandera avsnittet **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="7f45a-113">Bokföring måste ställas in på Ja när du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="7f45a-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="7f45a-114">Du kan även stänga av bokföring och bara skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="7f45a-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="7f45a-115">Men du kan få samma resultat genom att skapa en proformafaktura i stället för en faktura.</span><span class="sxs-lookup"><span data-stu-id="7f45a-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="7f45a-116">Detta alternativ används för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="7f45a-116">This option is used for batch jobs.</span></span> <span data-ttu-id="7f45a-117">Frågan körs när batchjobbet körs.</span><span class="sxs-lookup"><span data-stu-id="7f45a-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="7f45a-118">Välj "Efter" i fältet **Skriv ut**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="7f45a-119">Välj **Ja** för **Skriv ut faktura**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="7f45a-120">Med Utskriftshantering kan du skriva ut flera kopior av fakturan och också skicka fakturan med e-post som en PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="7f45a-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="7f45a-121">I fältet **Skriv ut avgifter** väljer du "Summera".</span><span class="sxs-lookup"><span data-stu-id="7f45a-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="7f45a-122">I fältet **checkkreditgräns** väljer du ”Saldo”.</span><span class="sxs-lookup"><span data-stu-id="7f45a-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="7f45a-123">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="7f45a-124">Kombinera order till en enda faktura</span><span class="sxs-lookup"><span data-stu-id="7f45a-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="7f45a-125">Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="7f45a-126">Leta upp en kund som har flera öppna fakturor.</span><span class="sxs-lookup"><span data-stu-id="7f45a-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="7f45a-127">Välj flera öppna försäljningsorder från samma kund.</span><span class="sxs-lookup"><span data-stu-id="7f45a-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="7f45a-128">I **åtgärdsrutan**, klicka på **Faktura > Generera > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="7f45a-129">Expandera avsnittet **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="7f45a-130">I fältet **Kvantitet**, välj 'Alla'.</span><span class="sxs-lookup"><span data-stu-id="7f45a-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="7f45a-131">Observera att det finns två fakturor som anges i översiktsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="7f45a-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="7f45a-132">Låt oss nu sammanslå dem till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="7f45a-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="7f45a-133">Välj "Fakturakonto" i fältet **Samlingsuppdatering för**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="7f45a-134">Klicka på **ordna** så slår du ihop dessa försäljningsorder till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="7f45a-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="7f45a-135">Dessa två försäljningsorder sammanslås nu till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="7f45a-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="7f45a-136">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="7f45a-137">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="7f45a-138">Bokför fakturor i en batch</span><span class="sxs-lookup"><span data-stu-id="7f45a-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="7f45a-139">Gå till **Navigeringsfönster > Moduler > Kundreskontra > Fakturor > Batchfakturering > Faktura**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="7f45a-140">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-140">Click **Select**.</span></span>
3. <span data-ttu-id="7f45a-141">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-141">Click **OK**.</span></span>
4. <span data-ttu-id="7f45a-142">Klicka på **batch**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-142">Click **Batch**.</span></span>
5. <span data-ttu-id="7f45a-143">Välj **Ja** i **batchbearbetning**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="7f45a-144">Klicka på **Upprepning.**</span><span class="sxs-lookup"><span data-stu-id="7f45a-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="7f45a-145">Välj **Dagar**</span><span class="sxs-lookup"><span data-stu-id="7f45a-145">Select **Days**.</span></span>
8. <span data-ttu-id="7f45a-146">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-146">Click **OK**.</span></span>
9. <span data-ttu-id="7f45a-147">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-147">Click **OK**.</span></span>
10. <span data-ttu-id="7f45a-148">Klicka på **Avbryt**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="7f45a-149">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7f45a-149">Click **Yes**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]