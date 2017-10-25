--- 
title: "Skapa betalningar för en kund som har autogiromedgivanden"
description: "Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas."
author: mrolecki
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: acd6a8076288d8d1d1aa05af33e306c6a29780f7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="03ab8-103">Skapa betalningar för en kund som har autogiromedgivanden</span><span class="sxs-lookup"><span data-stu-id="03ab8-103">Create payments for a customer who have direct debit mandates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="03ab8-104">Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas.</span><span class="sxs-lookup"><span data-stu-id="03ab8-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="03ab8-105">Att skapa och bokföra en faktura är valfritt.</span><span class="sxs-lookup"><span data-stu-id="03ab8-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="03ab8-106">Istället för att ha en faktura som ska betalas kan du välja en fullmakt i en journal innan du genererar en betalningsfil, detta för att stödja ett scenario för kundförskottsbetalning.</span><span class="sxs-lookup"><span data-stu-id="03ab8-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="03ab8-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="03ab8-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="03ab8-108">Detta är den femte av fem procedurer av fem som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="03ab8-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="03ab8-109">Innan du kan slutföra uppgiften, måste du genomföra de föregående uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="03ab8-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="03ab8-110">Du måste först importera konfigurationer för elektronisk rapportering om kundbetalning, konfigurera betalningsmetoder och konfigurerar ditt företag och dina kunduppgifter.</span><span class="sxs-lookup"><span data-stu-id="03ab8-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="03ab8-111">Bokför en fritextfaktura med information om direktdebitering</span><span class="sxs-lookup"><span data-stu-id="03ab8-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="03ab8-112">Gå till Kundreskontra > Fakturor > Alla fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="03ab8-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="03ab8-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="03ab8-113">Click New.</span></span>
3. <span data-ttu-id="03ab8-114">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="03ab8-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="03ab8-115">Välj till exempel DE-010.</span><span class="sxs-lookup"><span data-stu-id="03ab8-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="03ab8-116">Ange eller välj ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="03ab8-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="03ab8-117">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="03ab8-117">For example.</span></span> <span data-ttu-id="03ab8-118">välj "Electronic".</span><span class="sxs-lookup"><span data-stu-id="03ab8-118">select Electronic.</span></span>  
5. <span data-ttu-id="03ab8-119">Ange eller välj ett värde i fältet Autogiromedgivande-ID.</span><span class="sxs-lookup"><span data-stu-id="03ab8-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="03ab8-120">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="03ab8-120">Click Add line.</span></span>
7. <span data-ttu-id="03ab8-121">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="03ab8-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="03ab8-122">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="03ab8-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="03ab8-123">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="03ab8-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="03ab8-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="03ab8-124">Click Post.</span></span>
11. <span data-ttu-id="03ab8-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="03ab8-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="03ab8-126">Skapa en betalning</span><span class="sxs-lookup"><span data-stu-id="03ab8-126">Create a payment</span></span>
1. <span data-ttu-id="03ab8-127">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="03ab8-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="03ab8-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="03ab8-128">Click New.</span></span>
3. <span data-ttu-id="03ab8-129">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="03ab8-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="03ab8-130">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="03ab8-130">Click Lines.</span></span>
5. <span data-ttu-id="03ab8-131">Klicka på Betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="03ab8-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="03ab8-132">Klicka på Skapa betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="03ab8-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="03ab8-133">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="03ab8-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="03ab8-134">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="03ab8-134">Click Filter.</span></span>
9. <span data-ttu-id="03ab8-135">Markera raden för kundtransaktionregistret och fältet Betalningsmetod i listan.</span><span class="sxs-lookup"><span data-stu-id="03ab8-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="03ab8-136">Du kan använda valfria villkor för att välja kundtransaktioner för betalning.</span><span class="sxs-lookup"><span data-stu-id="03ab8-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="03ab8-137">Använd "Electronic" som en betalningsmetod för att filtrera transaktioner i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="03ab8-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="03ab8-138">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="03ab8-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="03ab8-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="03ab8-139">Click OK.</span></span>
12. <span data-ttu-id="03ab8-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="03ab8-140">Click OK.</span></span>
13. <span data-ttu-id="03ab8-141">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="03ab8-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="03ab8-142">Generera en betalningsfil</span><span class="sxs-lookup"><span data-stu-id="03ab8-142">Generate a payment file</span></span>

