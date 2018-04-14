--- 
title: "Upprätta avgifter för kundbetalning"
description: "Skapa betalningsavgifter för kundbetalningar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d740ea3f9aeef9ae302fbf3f03e9ecebff24aa5d
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="e9e4a-103">Upprätta avgifter för kundbetalning</span><span class="sxs-lookup"><span data-stu-id="e9e4a-103">Establish customer payment fees</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e9e4a-104">Skapa betalningsavgifter för kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="e9e4a-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="e9e4a-106">Gå till Kundreskontra > Betalningsinställning > Betalningsavgift.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="e9e4a-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-107">Click New.</span></span>
3. <span data-ttu-id="e9e4a-108">Ange ID i fältet Avgifts-ID.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="e9e4a-109">Avgifts-ID visas i betalningsjournaler, vilket gör det beskrivande så att du förstår vilken avgiften som åläggs.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="e9e4a-110">Ange namn i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="e9e4a-111">Ange en beskrivning av avgiften i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="e9e4a-112">Välj om tillägget ska debiteras kunden eller ett huvudbokskonto.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="e9e4a-113">Välj Kund om kunden ska debiteras avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="e9e4a-114">Om avgiften ska åläggas din organisation som en utgift, välj redovisning.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="e9e4a-115">Markera kunden för denna uppgift.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="e9e4a-116">Välj typ av journal som kan använda denna betalningsavgift.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="e9e4a-117">Om dessa tillägg används för kundbetalningar, kommer journaltypen troligen vara kundbetalning.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="e9e4a-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-118">Click Save.</span></span>
9. <span data-ttu-id="e9e4a-119">Klicka på Betalningsavgiftsinställning.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="e9e4a-120">Betalningsavgiftinställningar används för att definiera villkoren för betalningsavgiften, när ska bedömas.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="e9e4a-121">Du kan till exempel definiera som avgiften beräknas, om företaget är USMF OPER, och betalningsmetoden är check.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="e9e4a-122">Välj Register, Grupp eller Alla när du vill definiera vilka bankkonton ska bedömas den avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="e9e4a-123">Om du väljer Alla, kan alla bankkonton åläggas avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="e9e4a-124">Om du väljer Register, kan bara det bankkonto som du valt åläggas avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="e9e4a-125">Om du väljer Grupp, kan bara bankkontona i den markerade bankgruppen åläggas avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="e9e4a-126">Välj antingen en bankgrupp eller ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="e9e4a-127">Om du väljer Register, visar sökningen bankkonton.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="e9e4a-128">Om du väljer Grupp, visar sökningen bankgrupper.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="e9e4a-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e9e4a-130">Välj en betalningsmetod som ska användas för åläggandet av den aktuella betalningsavgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="e9e4a-131">Du kan till exempel ålägga en avgift till kunden om de skickar betalningar som en check, snarare än som en elektronisk betalning.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="e9e4a-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="e9e4a-133">Ange en betalningsvaluta, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="e9e4a-134">Betalningvalutan används som villkor för om avgift ska åläggas.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="e9e4a-135">Anta att din bank läsa in en ytterligare avgift för betalningar som tas emot i USD, eftersom de normalt bara arbetar med EUR-valuta.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="e9e4a-136">Välj om tillägget ska vara procent, ett belopp eller ett intervall.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="e9e4a-137">Ange antingen procentandelen eller beloppet av avgiften.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="e9e4a-138">Om procentsatsen/beloppsfält är procentvärde anges värdet som en procentsats.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="e9e4a-139">Om procentsatsen/beloppsfält är belopp, anges värdet som en procentsats.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="e9e4a-140">Om procentsatsen/beloppsfält är intervall, ska du använda intervallfliken för att definiera nivåerna.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="e9e4a-141">Välj valuta för tillägget i avgiftvalutafältet.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="e9e4a-142">Detta är den valuta som avgiften ska skapas i.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="e9e4a-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e9e4a-143">Click Save.</span></span>


