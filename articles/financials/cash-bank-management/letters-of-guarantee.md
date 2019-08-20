---
title: Garanti
description: Det här avsnittet innehåller information om garanti. I en garanti förbinder sig en bank att betala ett visst belopp till en person om en av bankens kunder inte betalar fakturan eller skulden till den personen.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e7ab2e66c378388d002d2f2090f89bf6c96dac2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842339"
---
# <a name="letters-of-guarantee"></a><span data-ttu-id="f274c-104">Garanti</span><span class="sxs-lookup"><span data-stu-id="f274c-104">Letters of guarantee</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f274c-105">Det här avsnittet innehåller information om garanti.</span><span class="sxs-lookup"><span data-stu-id="f274c-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="f274c-106">I en garanti förbinder sig en bank att betala ett visst belopp till en person om en av bankens kunder inte betalar fakturan eller skulden till den personen.</span><span class="sxs-lookup"><span data-stu-id="f274c-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="f274c-107">En bankgaranti är ett avtal med en bank (garanten) om att betala ett belopp som till en person (mottagare) om en bankkund (gäldenär) inte gör en betalning eller uppfyller en skyldighet gentemot mottagaren.</span><span class="sxs-lookup"><span data-stu-id="f274c-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="f274c-108">Garantier är inte överlåtbara.</span><span class="sxs-lookup"><span data-stu-id="f274c-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="f274c-109">De gäller endast mottagaren som anges i avtalet.</span><span class="sxs-lookup"><span data-stu-id="f274c-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="f274c-110">Gäldenären kan begära en ökning eller minskning en värdet på en garanti, i enlighet med villkoren för avtalet.</span><span class="sxs-lookup"><span data-stu-id="f274c-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="f274c-111">Om du vill likvidera en garanti måste mottagaren skicka den ursprungliga garantin och informera banken om att gäldenären inte har betalat före utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="f274c-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="f274c-112">Banken betalar sedan det utestående beloppet till mottagarens konto, enligt villkoren i garantin.</span><span class="sxs-lookup"><span data-stu-id="f274c-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="f274c-113">Banken tar en procentandel av betalningen som marginal.</span><span class="sxs-lookup"><span data-stu-id="f274c-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="f274c-114">Procentandelen överenskoms och anges i villkoren för avtalet.</span><span class="sxs-lookup"><span data-stu-id="f274c-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="f274c-115">Du kan skapa en kod för att följa syftet med en garanti.</span><span class="sxs-lookup"><span data-stu-id="f274c-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="f274c-116">Du kan även ange de orsaker som kan kopplas till en garanti när garantin annulleras.</span><span class="sxs-lookup"><span data-stu-id="f274c-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="f274c-117">Du kan visa syftekoderna och bankorsakerna på sidorna **Syfteskoder för betalning** och **Bankorsaker** .</span><span class="sxs-lookup"><span data-stu-id="f274c-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="f274c-118">Du kan använda sidan **Garanti** för att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="f274c-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="f274c-119">Skapa korrekta redovisningsposter och eliminera manuell registrering.</span><span class="sxs-lookup"><span data-stu-id="f274c-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="f274c-120">Registrera alla monetära och icke-monetära transaktioner följa upp saldon för garantier.</span><span class="sxs-lookup"><span data-stu-id="f274c-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="f274c-121">Registrera och följa upp status och förfallotidpunkten för garantier.</span><span class="sxs-lookup"><span data-stu-id="f274c-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="f274c-122">Generera en rapport som visar banker som har garantier.</span><span class="sxs-lookup"><span data-stu-id="f274c-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="f274c-123">I tabellen nedan beskrivs vilka åtgärder du kan utföra i samband med en garanti.</span><span class="sxs-lookup"><span data-stu-id="f274c-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="f274c-124">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="f274c-124">Action</span></span>              | <span data-ttu-id="f274c-125">Syfte</span><span class="sxs-lookup"><span data-stu-id="f274c-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f274c-126">Skicka till bank</span><span class="sxs-lookup"><span data-stu-id="f274c-126">Submit to bank</span></span>      | <span data-ttu-id="f274c-127">Skicka en begäran till banken att utfärda en garanti.</span><span class="sxs-lookup"><span data-stu-id="f274c-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="f274c-128">Ta emot från bank</span><span class="sxs-lookup"><span data-stu-id="f274c-128">Receive from bank</span></span>   | <span data-ttu-id="f274c-129">När banken har gått med på att begäran, får du garantin från banken.</span><span class="sxs-lookup"><span data-stu-id="f274c-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="f274c-130">Ge till mottagare</span><span class="sxs-lookup"><span data-stu-id="f274c-130">Give to beneficiary</span></span> | <span data-ttu-id="f274c-131">När du har fått garantin från banken ger du den till mottagaren.</span><span class="sxs-lookup"><span data-stu-id="f274c-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="f274c-132">Öka värde</span><span class="sxs-lookup"><span data-stu-id="f274c-132">Increase value</span></span>      | <span data-ttu-id="f274c-133">Om mottagaren och gäldenären är överens kan det monetära värdet ökas.</span><span class="sxs-lookup"><span data-stu-id="f274c-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="f274c-134">Minska värde</span><span class="sxs-lookup"><span data-stu-id="f274c-134">Decrease value</span></span>      | <span data-ttu-id="f274c-135">Om mottagaren och gäldenären är överens kan det monetära värdet minskas.</span><span class="sxs-lookup"><span data-stu-id="f274c-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="f274c-136">Utöka</span><span class="sxs-lookup"><span data-stu-id="f274c-136">Extend</span></span>              | <span data-ttu-id="f274c-137">När du har gett garantin till mottagaren går det att förlänga giltighetstiden om det är nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="f274c-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="f274c-138">Avbryt</span><span class="sxs-lookup"><span data-stu-id="f274c-138">Cancel</span></span>              | <span data-ttu-id="f274c-139">När syftet med garantin inte längre finns kan du avsluta avtalet.</span><span class="sxs-lookup"><span data-stu-id="f274c-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="f274c-140">Likvidera</span><span class="sxs-lookup"><span data-stu-id="f274c-140">Liquidate</span></span>           | <span data-ttu-id="f274c-141">När mottagaren presenterar garantin för banken betalas garantin.</span><span class="sxs-lookup"><span data-stu-id="f274c-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="f274c-142">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f274c-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="f274c-143">Garantitransaktion</span><span class="sxs-lookup"><span data-stu-id="f274c-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="f274c-144">Ställ in bankkreditlimiter och bokföringsprofiler för garanti</span><span class="sxs-lookup"><span data-stu-id="f274c-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)


