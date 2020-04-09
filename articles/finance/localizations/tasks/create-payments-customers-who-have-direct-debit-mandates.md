---
title: Skapa betalningar för en kund som har autogiromedgivanden
description: Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a4714f1f1b24554684219fc1d766b4b87cff7bb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141613"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="4de73-103">Skapa betalningar för en kund som har autogiromedgivanden</span><span class="sxs-lookup"><span data-stu-id="4de73-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4de73-104">Denna uppgift visar hur du skapar en ISO20022-betalningsfil för autogiro för en kund som har autogiro konfigurerat och en faktura som ska betalas.</span><span class="sxs-lookup"><span data-stu-id="4de73-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="4de73-105">Att skapa och bokföra en faktura är valfritt.</span><span class="sxs-lookup"><span data-stu-id="4de73-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="4de73-106">Istället för att ha en faktura som ska betalas kan du välja en fullmakt i en journal innan du genererar en betalningsfil, detta för att stödja ett scenario för kundförskottsbetalning.</span><span class="sxs-lookup"><span data-stu-id="4de73-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="4de73-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="4de73-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="4de73-108">Detta är den femte av fem procedurer av fem som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="4de73-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="4de73-109">Innan du kan slutföra uppgiften, måste du genomföra de föregående uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="4de73-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="4de73-110">Du måste först importera konfigurationer för elektronisk rapportering om kundbetalning, konfigurera betalningsmetoder och konfigurerar ditt företag och dina kunduppgifter.</span><span class="sxs-lookup"><span data-stu-id="4de73-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="4de73-111">Bokför en fritextfaktura med information om direktdebitering</span><span class="sxs-lookup"><span data-stu-id="4de73-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="4de73-112">Gå till Kundreskontra > Fakturor > Alla fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="4de73-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="4de73-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4de73-113">Click New.</span></span>
3. <span data-ttu-id="4de73-114">I fältet Kundkonto, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="4de73-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="4de73-115">Välj till exempel DE-010.</span><span class="sxs-lookup"><span data-stu-id="4de73-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="4de73-116">Ange eller välj ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="4de73-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="4de73-117">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="4de73-117">For example.</span></span> <span data-ttu-id="4de73-118">välj "Electronic".</span><span class="sxs-lookup"><span data-stu-id="4de73-118">select Electronic.</span></span>  
5. <span data-ttu-id="4de73-119">Ange eller välj ett värde i fältet Autogiromedgivande-ID.</span><span class="sxs-lookup"><span data-stu-id="4de73-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="4de73-120">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="4de73-120">Click Add line.</span></span>
7. <span data-ttu-id="4de73-121">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4de73-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="4de73-122">Ange önskade värden i fältet Huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="4de73-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="4de73-123">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="4de73-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="4de73-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="4de73-124">Click Post.</span></span>
11. <span data-ttu-id="4de73-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4de73-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="4de73-126">Skapa en betalning</span><span class="sxs-lookup"><span data-stu-id="4de73-126">Create a payment</span></span>
1. <span data-ttu-id="4de73-127">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="4de73-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="4de73-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4de73-128">Click New.</span></span>
3. <span data-ttu-id="4de73-129">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4de73-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="4de73-130">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="4de73-130">Click Lines.</span></span>
5. <span data-ttu-id="4de73-131">Klicka på Betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="4de73-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="4de73-132">Klicka på Skapa betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="4de73-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="4de73-133">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="4de73-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="4de73-134">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="4de73-134">Click Filter.</span></span>
9. <span data-ttu-id="4de73-135">Markera raden för kundtransaktionregistret och fältet Betalningsmetod i listan.</span><span class="sxs-lookup"><span data-stu-id="4de73-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="4de73-136">Du kan använda valfria villkor för att välja kundtransaktioner för betalning.</span><span class="sxs-lookup"><span data-stu-id="4de73-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="4de73-137">Använd "Electronic" som en betalningsmetod för att filtrera transaktioner i det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="4de73-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="4de73-138">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="4de73-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="4de73-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4de73-139">Click OK.</span></span>
12. <span data-ttu-id="4de73-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4de73-140">Click OK.</span></span>
13. <span data-ttu-id="4de73-141">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="4de73-141">Click Create payments.</span></span>
