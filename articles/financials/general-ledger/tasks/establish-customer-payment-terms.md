---
title: Upprätta villkor för kundbetalning
description: I den här proceduren definieras kassarabatt- och förfallodatuminställningar.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49f4047ab4bff6bdfbe8326a6680f9d8f9762c95
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "312495"
---
# <a name="establish-customer-payment-terms"></a><span data-ttu-id="b3520-103">Upprätta villkor för kundbetalning</span><span class="sxs-lookup"><span data-stu-id="b3520-103">Establish customer payment terms</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b3520-104">I den här proceduren definieras kassarabatt- och förfallodatuminställningar.</span><span class="sxs-lookup"><span data-stu-id="b3520-104">This procedure defines a cash discount and due date setup.</span></span> <span data-ttu-id="b3520-105">I den här uppgiftsguiden används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b3520-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="b3520-106">Gå till Kundreskontra > Betalningsinställning > Betalningsdagar.</span><span class="sxs-lookup"><span data-stu-id="b3520-106">Go to Accounts receivable > Payments setup > Payment days.</span></span>
    * <span data-ttu-id="b3520-107">Inställningar för betalningsvillkoren delas för kundreskontra och leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="b3520-107">The setup for the Terms of payment is shared for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="b3520-108">Om du definierar den i modulen, kommer den att vara tillgängliga i den andra modulen också.</span><span class="sxs-lookup"><span data-stu-id="b3520-108">If you define it in module, it will be available in the other module also.</span></span> <span data-ttu-id="b3520-109">För den här uppgifthandbok ställer in I alla betalningsvillkor under kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="b3520-109">For this task guide, I set up all the terms of payment under Accounts receivable.</span></span>  
2. <span data-ttu-id="b3520-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b3520-110">Click New.</span></span>
    * <span data-ttu-id="b3520-111">Skapa en betalningsdag, om betalningsvillkoret kräver en specifik dag i veckan (måndag, tisdag, etc.) eller ett visst datum i månaden (5:e, 10:e etc.).</span><span class="sxs-lookup"><span data-stu-id="b3520-111">Create a payment day if your terms of payment require a specific day of the week (Monday, Tuesday, etc) or a specific date of the month (5th, 10th, etc).</span></span>  
3. <span data-ttu-id="b3520-112">Ange ett ID för betalningsdagen i betalningsdagfältet i betalningsdagfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-112">In the Payment day field, enter an ID for the Payment day in the payment day field.</span></span>
4. <span data-ttu-id="b3520-113">Ange en beskrivning av betalningsdagen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b3520-113">In the Description field, enter a description of the payment day.</span></span>
5. <span data-ttu-id="b3520-114">Välj antingen veckan eller månaden i vecka-/månadfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-114">In the Week/Month field, select either Week or Month.</span></span>
    * <span data-ttu-id="b3520-115">Om du vill ange en dag i veckan, till exempel måndag, markera veckan.</span><span class="sxs-lookup"><span data-stu-id="b3520-115">If you want to enter a day of the week, such as Monday, select Week.</span></span> <span data-ttu-id="b3520-116">Om du vill ange ett datum i månaden, till exempel 10:e, välj månad.</span><span class="sxs-lookup"><span data-stu-id="b3520-116">If you want to enter a date in the month, such as the 10th, select Month.</span></span> <span data-ttu-id="b3520-117">I det här exemplet väljer du Månad.</span><span class="sxs-lookup"><span data-stu-id="b3520-117">Select Month for this example.</span></span>  
6. <span data-ttu-id="b3520-118">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="b3520-118">In the Day of month field, enter a date.</span></span>
    * <span data-ttu-id="b3520-119">Datumet då anges som ett tal, till exempel ”10”, och inte som ”10:e”.</span><span class="sxs-lookup"><span data-stu-id="b3520-119">The date should be entered as a number, such as '10', and not as '10th'.</span></span>  
7. <span data-ttu-id="b3520-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b3520-120">Click Save.</span></span>
8. <span data-ttu-id="b3520-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b3520-121">Close the page.</span></span>
9. <span data-ttu-id="b3520-122">Gå till Kundreskontra > Betalningsinställning > Betalningsvillkor.</span><span class="sxs-lookup"><span data-stu-id="b3520-122">Go to Accounts receivable > Payments setup > Terms of payment.</span></span>
10. <span data-ttu-id="b3520-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b3520-123">Click New.</span></span>
    * <span data-ttu-id="b3520-124">Betalningsvillkoren används för att definiera hur förfallodatumen ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="b3520-124">Terms of payment is used to define how the due dates will be calculated.</span></span> <span data-ttu-id="b3520-125">Kassarabattdatuminställningar definieras i en separat sida.</span><span class="sxs-lookup"><span data-stu-id="b3520-125">The cash discount date setup is defined in a separate page.</span></span>  
11. <span data-ttu-id="b3520-126">I betalningsvillkoret infogas ett ID i betalningsvillkorfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-126">In the Terms of payment field, enter an ID in the Terms of payment field.</span></span>
12. <span data-ttu-id="b3520-127">Ange en beskrivning i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-127">In the Description field, enter a description.</span></span>
13. <span data-ttu-id="b3520-128">Välj en betalningsmetod, till exempel postförskott, netto, aktuell månad, etc.</span><span class="sxs-lookup"><span data-stu-id="b3520-128">Select a Payment method such as COD, Net, Current month, etc.</span></span>
    * <span data-ttu-id="b3520-129">Betalningsvillkoren används för att definiera hur förfallodatumen börjar beräknas.</span><span class="sxs-lookup"><span data-stu-id="b3520-129">The Payment method is used to define the start of how the due will be calculated.</span></span>  <span data-ttu-id="b3520-130">Till exempel, netto används om förfallodatumet är alltid ett visst antal månader eller dagar efter fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="b3520-130">For example, Net is used if the due date is always a set number of months or days after the invoice date.</span></span> <span data-ttu-id="b3520-131">Postförskott kan användas för att, när betalning krävs vid faktura, så ett förfallodatum beräknas inte.</span><span class="sxs-lookup"><span data-stu-id="b3520-131">COD can be used to when payment is required upon invoice, so a due date wouldn't be calculated.</span></span> <span data-ttu-id="b3520-132">Välj aktuell månad för den här uppgifthandbok.</span><span class="sxs-lookup"><span data-stu-id="b3520-132">Select Current month for this task guide.</span></span>  
14. <span data-ttu-id="b3520-133">Välj en betalningsdag, om en specifik dag i veckan eller datum tas med i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="b3520-133">Select a Payment day if a specific day of the  week or date are included in the calculation.</span></span>
    * <span data-ttu-id="b3520-134">Beroende på betalningsvillkoret kan du ange en kvantitet i månader eller dagar.</span><span class="sxs-lookup"><span data-stu-id="b3520-134">Depending on your terms of payment, you may enter a quantity in Months or Days.</span></span> <span data-ttu-id="b3520-135">Du kan använda betalningsplanen, eller betalningsdagen ”till” lägger till slutet av betalningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="b3520-135">Or you can use the Payment schedule or Payment day to 'add' to the end of the Payment method.</span></span> <span data-ttu-id="b3520-136">Om förfallodatumet är alltid 10:e i nästa månad, välj betalningsdag den 10:e.</span><span class="sxs-lookup"><span data-stu-id="b3520-136">If the due date will always be the 10th of the next month, select a Payment day of the 10th.</span></span>  
15. <span data-ttu-id="b3520-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b3520-137">Click Save.</span></span>
16. <span data-ttu-id="b3520-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b3520-138">Close the page.</span></span>
17. <span data-ttu-id="b3520-139">Gå till Kundreskontra > Betalningsinställning > Kassarabatter.</span><span class="sxs-lookup"><span data-stu-id="b3520-139">Go to Accounts receivable > Payments setup > Cash discounts.</span></span>
18. <span data-ttu-id="b3520-140">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b3520-140">Click New.</span></span>
    * <span data-ttu-id="b3520-141">På den här sidan används för att definiera hur kassarabattdatum beräknas.</span><span class="sxs-lookup"><span data-stu-id="b3520-141">This page is used to define how the cash discount date will be calculated.</span></span>  
19. <span data-ttu-id="b3520-142">Ange ett ID i kassarabattfältet i kassarabattfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-142">In the Cash discount field, enter an ID in the Cash discount field.</span></span>
20. <span data-ttu-id="b3520-143">Ange en beskrivning i beskrivningsfältet.</span><span class="sxs-lookup"><span data-stu-id="b3520-143">In the Description field, enter a description.</span></span>
21. <span data-ttu-id="b3520-144">Om en tiered kassarabatt är tillgänglig, väljer nästa rabattkoden som gäller efter det nya kassarabatt.</span><span class="sxs-lookup"><span data-stu-id="b3520-144">If a tiered cash discount is available, select the Next discount code that is relevant after this new cash discount.</span></span>
22. <span data-ttu-id="b3520-145">Ange det antal dagar som används för att beräkna kassarabattdatumet.</span><span class="sxs-lookup"><span data-stu-id="b3520-145">Enter the number of days used to calculate the cash dicount date.</span></span>
    * <span data-ttu-id="b3520-146">Om Nettoprincipen markeras, antal dagar ska läggas till fakturadatumet för att beräkna kassarabattdatumet.</span><span class="sxs-lookup"><span data-stu-id="b3520-146">If Net principle is selected, the number of days will be added to the invoice date to calculate the cash discount date.</span></span>  
23. <span data-ttu-id="b3520-147">Ange procentbeloppet för kassarabatten.</span><span class="sxs-lookup"><span data-stu-id="b3520-147">Enter the percentage of the cash discount.</span></span>
24. <span data-ttu-id="b3520-148">Ange huvudkontot som kassarabatten ska bokföras på för kundfakturor.</span><span class="sxs-lookup"><span data-stu-id="b3520-148">Enter the main account to which the cash discount will post for customer invoices.</span></span>
25. <span data-ttu-id="b3520-149">Välj alternativ på samma sätt som i fältet Rabattmotkonton.</span><span class="sxs-lookup"><span data-stu-id="b3520-149">In the Discount offset accounts field, select an option.</span></span>
    * <span data-ttu-id="b3520-150">Om du väljer ”konton på fakturaraderna, ska bokföra kassarabatten till samma tillgångs/utgifthuvudkontot på raderna för leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="b3520-150">If you select 'Accounts on the invoice lines', the cash discount will post to the same asset/expense main account on the lines of the vendor invoice.</span></span> <span data-ttu-id="b3520-151">Om du väljer Använd huvudkonto för leverantörsfakturor, kassarabatten ska bokföras i huvudkontot som du definierar i Använd huvudkonto för leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b3520-151">If you select 'Use main account for vendor invoices', the cash discount will post to the main account you define in the 'Main account for vendor invoices'.</span></span> <span data-ttu-id="b3520-152">För det här exemplet väljs Använd huvudkonto för leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b3520-152">For this example, select 'Use main account for vendor invoices.'</span></span>  
26. <span data-ttu-id="b3520-153">Ange huvudkontot som kassarabatten ska bokföras på för leverantörsfakturor.</span><span class="sxs-lookup"><span data-stu-id="b3520-153">Enter the main account to which the cash discount will post for vendor invoices.</span></span>
27. <span data-ttu-id="b3520-154">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b3520-154">Click Save.</span></span>

