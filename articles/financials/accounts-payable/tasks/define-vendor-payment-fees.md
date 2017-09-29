--- 
title: "Definiera leverantörsbetalningsavgifter"
description: "Ställ in avgifter för leverantörsbetalningar."
author: abruer
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
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f62d07ffa1ee4a525f0f266922bc88e5ac8d5ada
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="86a4f-103">Definiera leverantörsbetalningsavgifter</span><span class="sxs-lookup"><span data-stu-id="86a4f-103">Define vendor payment fees</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86a4f-104">Ställ in avgifter för leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="86a4f-104">Set up vendor payment fees.</span></span> <span data-ttu-id="86a4f-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="86a4f-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="86a4f-106">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsavgift.</span><span class="sxs-lookup"><span data-stu-id="86a4f-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="86a4f-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="86a4f-107">Click New.</span></span>
3. <span data-ttu-id="86a4f-108">Skriv ett värde i fältet Avgifts-ID.</span><span class="sxs-lookup"><span data-stu-id="86a4f-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="86a4f-109">Avgifts-ID bör beskriva när avgiften ska användas, till exempel ”EFT_Fee”.</span><span class="sxs-lookup"><span data-stu-id="86a4f-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="86a4f-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="86a4f-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="86a4f-111">I fältet Avgiftsbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="86a4f-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="86a4f-112">Lägg till en beskrivning med mer detaljer om när avgiften åläggs.</span><span class="sxs-lookup"><span data-stu-id="86a4f-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="86a4f-113">Välj antingen leverantör eller redovisning i avgiftsfältet.</span><span class="sxs-lookup"><span data-stu-id="86a4f-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="86a4f-114">Huvudboken används när avgift ska åläggas din organisation.</span><span class="sxs-lookup"><span data-stu-id="86a4f-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="86a4f-115">Leverantören används när avgift ska åläggas leverantören.</span><span class="sxs-lookup"><span data-stu-id="86a4f-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="86a4f-116">Ange ett huvudkonto där avgiften ska konteras.</span><span class="sxs-lookup"><span data-stu-id="86a4f-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="86a4f-117">Det här alternativet kan bara användas när Huvudbok har valts som Tillägg.</span><span class="sxs-lookup"><span data-stu-id="86a4f-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="86a4f-118">Välj den journal som avgiften kan användas för.</span><span class="sxs-lookup"><span data-stu-id="86a4f-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="86a4f-119">För en leverantörsbetalningsavgift ska du välja journalen Leverantörsutbetalning.</span><span class="sxs-lookup"><span data-stu-id="86a4f-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="86a4f-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86a4f-120">Click Save.</span></span>
10. <span data-ttu-id="86a4f-121">Klicka på Betalningsavgiftsinställning.</span><span class="sxs-lookup"><span data-stu-id="86a4f-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="86a4f-122">Fortsätt till betalningsavgiftinställningar för att definiera när kostnaden ska användas som standard till journalen du valt.</span><span class="sxs-lookup"><span data-stu-id="86a4f-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="86a4f-123">Välj Register eller Grupp eller Alla.</span><span class="sxs-lookup"><span data-stu-id="86a4f-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="86a4f-124">Registret används för att väljer ett enskilt bankkonto, är gruppen för att väljer en bankgrupp, och alla är att använda den här ställer in avgift för alla bankkonton</span><span class="sxs-lookup"><span data-stu-id="86a4f-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="86a4f-125">Välj antingen en bankgrupp eller ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="86a4f-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="86a4f-126">Sökningen ska visa bankgruppen, om du markerade gruppen, och visar bankkonton, om du har valt registret.</span><span class="sxs-lookup"><span data-stu-id="86a4f-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="86a4f-127">Välj en betalningsmetod som ska användas för åläggandet av den aktuella betalningsavgiften.</span><span class="sxs-lookup"><span data-stu-id="86a4f-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="86a4f-128">Välj betalningsspecifikation för aktuell betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="86a4f-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="86a4f-129">Betalningsspecifikationen används med överföringsbetalningsmetoder av elektronisk fond.</span><span class="sxs-lookup"><span data-stu-id="86a4f-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="86a4f-130">Välj om tillägget ska vara procent, ett belopp eller ett intervall.</span><span class="sxs-lookup"><span data-stu-id="86a4f-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="86a4f-131">Ange procent eller belopp för avgiften.</span><span class="sxs-lookup"><span data-stu-id="86a4f-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="86a4f-132">Om tillägget är en procentsats, ange procentsatsen.</span><span class="sxs-lookup"><span data-stu-id="86a4f-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="86a4f-133">Om tillägget är ett belopp, ange beloppet för avgiften.</span><span class="sxs-lookup"><span data-stu-id="86a4f-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="86a4f-134">Om tillägget är ett intervall, ska du använda intervallfliken de definierade tiered avgifterna.</span><span class="sxs-lookup"><span data-stu-id="86a4f-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="86a4f-135">Välj den valuta som avgiften ska åläggas med i avgiftvalutafältet.</span><span class="sxs-lookup"><span data-stu-id="86a4f-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="86a4f-136">Valutan avser avgiften.</span><span class="sxs-lookup"><span data-stu-id="86a4f-136">This currency is for the fee.</span></span> <span data-ttu-id="86a4f-137">Betalningvalutan används för att ange när avgiftregeln ska vara bedömt baserat på betalningens valuta.</span><span class="sxs-lookup"><span data-stu-id="86a4f-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="86a4f-138">Anta att din bank läsa in en avgift, när en betalning görs i euro, men alla andra betalningar bedömas inte en avgift.</span><span class="sxs-lookup"><span data-stu-id="86a4f-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="86a4f-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="86a4f-139">Click Save.</span></span>


