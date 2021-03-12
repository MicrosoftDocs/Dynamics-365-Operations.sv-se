---
title: Definiera leverantörsbetalningsavgifter
description: Ställ in avgifter för leverantörsbetalningar.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52321851a1aa588a0bbe238e366a28d503665988
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979348"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="a2719-103">Definiera leverantörsbetalningsavgifter</span><span class="sxs-lookup"><span data-stu-id="a2719-103">Define vendor payment fees</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2719-104">Ställ in avgifter för leverantörsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="a2719-104">Set up vendor payment fees.</span></span> <span data-ttu-id="a2719-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a2719-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a2719-106">Gå till Leverantörsreskontra > Betalningsinställning > Betalningsavgift.</span><span class="sxs-lookup"><span data-stu-id="a2719-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="a2719-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a2719-107">Click New.</span></span>
3. <span data-ttu-id="a2719-108">Skriv ett värde i fältet Avgifts-ID.</span><span class="sxs-lookup"><span data-stu-id="a2719-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="a2719-109">Avgifts-ID bör beskriva när avgiften ska användas, till exempel ”EFT_Fee”.</span><span class="sxs-lookup"><span data-stu-id="a2719-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="a2719-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="a2719-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a2719-111">I fältet Avgiftsbeskrivning, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="a2719-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="a2719-112">Lägg till en beskrivning med mer detaljer om när avgiften åläggs.</span><span class="sxs-lookup"><span data-stu-id="a2719-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="a2719-113">Välj antingen leverantör eller redovisning i avgiftsfältet.</span><span class="sxs-lookup"><span data-stu-id="a2719-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="a2719-114">Huvudboken används när avgift ska åläggas din organisation.</span><span class="sxs-lookup"><span data-stu-id="a2719-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="a2719-115">Leverantören används när avgift ska åläggas leverantören.</span><span class="sxs-lookup"><span data-stu-id="a2719-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="a2719-116">Ange ett huvudkonto där avgiften ska konteras.</span><span class="sxs-lookup"><span data-stu-id="a2719-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="a2719-117">Det här alternativet kan bara användas när Huvudbok har valts som Tillägg.</span><span class="sxs-lookup"><span data-stu-id="a2719-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="a2719-118">Välj den journal som avgiften kan användas för.</span><span class="sxs-lookup"><span data-stu-id="a2719-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="a2719-119">För en leverantörsbetalningsavgift ska du välja journalen Leverantörsutbetalning.</span><span class="sxs-lookup"><span data-stu-id="a2719-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="a2719-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a2719-120">Click Save.</span></span>
10. <span data-ttu-id="a2719-121">Klicka på Betalningsavgiftsinställning.</span><span class="sxs-lookup"><span data-stu-id="a2719-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="a2719-122">Fortsätt till betalningsavgiftinställningar för att definiera när kostnaden ska användas som standard till journalen du valt.</span><span class="sxs-lookup"><span data-stu-id="a2719-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="a2719-123">Välj Register eller Grupp eller Alla.</span><span class="sxs-lookup"><span data-stu-id="a2719-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="a2719-124">Registret används för att väljer ett enskilt bankkonto, är gruppen för att väljer en bankgrupp, och alla är att använda den här ställer in avgift för alla bankkonton</span><span class="sxs-lookup"><span data-stu-id="a2719-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="a2719-125">Välj antingen en bankgrupp eller ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="a2719-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="a2719-126">Sökningen ska visa bankgruppen, om du markerade gruppen, och visar bankkonton, om du har valt registret.</span><span class="sxs-lookup"><span data-stu-id="a2719-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="a2719-127">Välj ett betalsätt som ska användas för åläggandet av den aktuella betalningsavgiften.</span><span class="sxs-lookup"><span data-stu-id="a2719-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="a2719-128">Välj betalningsspecifikation för aktuell betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="a2719-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="a2719-129">Betalningsspecifikationen används med överföringsbetalsätt av elektronisk fond.</span><span class="sxs-lookup"><span data-stu-id="a2719-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="a2719-130">Välj om tillägget ska vara procent, ett belopp eller ett intervall.</span><span class="sxs-lookup"><span data-stu-id="a2719-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="a2719-131">Ange procent eller belopp för avgiften.</span><span class="sxs-lookup"><span data-stu-id="a2719-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="a2719-132">Om tillägget är en procentsats, ange procentsatsen.</span><span class="sxs-lookup"><span data-stu-id="a2719-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="a2719-133">Om tillägget är ett belopp, ange beloppet för avgiften.</span><span class="sxs-lookup"><span data-stu-id="a2719-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="a2719-134">Om tillägget är ett intervall, ska du använda intervallfliken de definierade tiered avgifterna.</span><span class="sxs-lookup"><span data-stu-id="a2719-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="a2719-135">Välj den valuta som avgiften ska åläggas med i avgiftvalutafältet.</span><span class="sxs-lookup"><span data-stu-id="a2719-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="a2719-136">Valutan avser avgiften.</span><span class="sxs-lookup"><span data-stu-id="a2719-136">This currency is for the fee.</span></span> <span data-ttu-id="a2719-137">Betalningvalutan används för att ange när avgiftregeln ska vara bedömt baserat på betalningens valuta.</span><span class="sxs-lookup"><span data-stu-id="a2719-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="a2719-138">Anta att din bank läsa in en avgift, när en betalning görs i euro, men alla andra betalningar bedömas inte en avgift.</span><span class="sxs-lookup"><span data-stu-id="a2719-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="a2719-139">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="a2719-139">Click Save.</span></span>

