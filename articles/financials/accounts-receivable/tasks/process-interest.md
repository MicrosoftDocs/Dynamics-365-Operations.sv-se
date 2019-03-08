---
title: Beräkna ränta
description: I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5652a38684061914f895d7f8b82999c9840fd63
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "359162"
---
# <a name="process-interest"></a><span data-ttu-id="a08f2-103">Beräkna ränta</span><span class="sxs-lookup"><span data-stu-id="a08f2-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a08f2-104">I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="a08f2-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="a08f2-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a08f2-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="a08f2-106">Ställ in ränta i bokföringsprofilen</span><span class="sxs-lookup"><span data-stu-id="a08f2-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="a08f2-107">Gå till Kredit och inkasso > Inställningar > Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="a08f2-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="a08f2-108">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="a08f2-108">Click Edit.</span></span>
    * <span data-ttu-id="a08f2-109">Välj en räntekod i listrutan.</span><span class="sxs-lookup"><span data-stu-id="a08f2-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="a08f2-110">Om du inte vill skapa beräkna ränta för transaktioner med denna bokföringsprofil, lämna fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="a08f2-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="a08f2-111">Registerbegränsningsfliken gör det möjligt att ändra hur ränta bearbetas.</span><span class="sxs-lookup"><span data-stu-id="a08f2-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="a08f2-112">Om detta fält har satts till Ja, beräknas ränta för denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="a08f2-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="a08f2-113">Beräkna ränta</span><span class="sxs-lookup"><span data-stu-id="a08f2-113">Calculate interest</span></span>
1. <span data-ttu-id="a08f2-114">Gå till Kredit och inkasso > Ränta > Skapa räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="a08f2-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="a08f2-115">Du måste välja transaktionstyperna för att beräkna ränta.</span><span class="sxs-lookup"><span data-stu-id="a08f2-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="a08f2-116">Alla öppna transaktioner för dessa typer inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="a08f2-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="a08f2-117">Om du väljer ränta, ska du beräkna ränta på ränta.</span><span class="sxs-lookup"><span data-stu-id="a08f2-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="a08f2-118">Du kanske du vill kontrollera lagar som styr beräkningen av ränta på ränta som inkluderar för dessa transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a08f2-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="a08f2-119">Ränta beräknas utifrån detta datum i ”till”.</span><span class="sxs-lookup"><span data-stu-id="a08f2-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="a08f2-120">Om du inte bort specifikt ”från-datum”, annulleras alla bokförda räntefakturor och ränta beräknas på nytt från transaktionsdatum.</span><span class="sxs-lookup"><span data-stu-id="a08f2-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="a08f2-121">Ange datum för räntefakturan.</span><span class="sxs-lookup"><span data-stu-id="a08f2-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="a08f2-122">Det finns tre bokföringsprofilalternativ: Konto – använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="a08f2-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="a08f2-123">Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="a08f2-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="a08f2-124">Transaktion – Använd bokföringsprofilen från den transaktioner där ränta beräknas för varje räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="a08f2-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="a08f2-125">Transaktioner som inte har en tilldelad bokföringsprofil kommer använda bokföringsprofilen som angetts i området Redovisning och moms i formuläret Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="a08f2-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="a08f2-126">Välj en bokföringsprofil om du har ändrat Använd bokföringsprofil från till Välj.</span><span class="sxs-lookup"><span data-stu-id="a08f2-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="a08f2-127">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="a08f2-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="a08f2-128">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="a08f2-128">Click Filter.</span></span>
5. <span data-ttu-id="a08f2-129">Ange Kund-ID i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="a08f2-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="a08f2-130">Till exempel US-001.</span><span class="sxs-lookup"><span data-stu-id="a08f2-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="a08f2-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a08f2-131">Click OK.</span></span>
7. <span data-ttu-id="a08f2-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a08f2-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="a08f2-133">Skriv ut räntefakturor</span><span class="sxs-lookup"><span data-stu-id="a08f2-133">Print interest notes</span></span>
1. <span data-ttu-id="a08f2-134">Gå till Kredit och inkasso > Ränta > Granska och beräkna räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="a08f2-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="a08f2-135">Välj Skapad i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="a08f2-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="a08f2-136">Välj Ej utskrivet i fältet Utskriven.</span><span class="sxs-lookup"><span data-stu-id="a08f2-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="a08f2-137">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="a08f2-137">Click Print.</span></span>
5. <span data-ttu-id="a08f2-138">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="a08f2-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="a08f2-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a08f2-139">Click OK.</span></span>
7. <span data-ttu-id="a08f2-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a08f2-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="a08f2-141">Bokför räntefakturan</span><span class="sxs-lookup"><span data-stu-id="a08f2-141">Post the interest note</span></span>
1. <span data-ttu-id="a08f2-142">Välj en räntefakktura som är klar att bokföra (status skapas).</span><span class="sxs-lookup"><span data-stu-id="a08f2-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="a08f2-143">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="a08f2-143">Click Post.</span></span>
3. <span data-ttu-id="a08f2-144">Ange bokföringsdatumet för räntefakturan.</span><span class="sxs-lookup"><span data-stu-id="a08f2-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="a08f2-145">Välj Ja för att skapa en redovisningstransaktion för varje räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="a08f2-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="a08f2-146">Om du inte mväljer Ja ackumuleras räntan på alla räntefakturor till kunden och bokförs i redovisningen i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="a08f2-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="a08f2-147">Utöka eller komprimera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="a08f2-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="a08f2-148">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a08f2-148">Click OK.</span></span>
6. <span data-ttu-id="a08f2-149">Välj Bokförd i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="a08f2-149">In the Status field, select 'Posted'.</span></span>

