--- 
title: Bearbeta kravbrev
description: "I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, SysQueryForm, CustCollectionLetterNote
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a1bdf9528b52daa7bb719ea5a751a01e56a8c963
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="process-collection-letters"></a><span data-ttu-id="f191d-103">Bearbeta kravbrev</span><span class="sxs-lookup"><span data-stu-id="f191d-103">Process collection letters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f191d-104">I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev.</span><span class="sxs-lookup"><span data-stu-id="f191d-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="f191d-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f191d-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="f191d-106">Ställ in en kravbrevsserie för bokföringsprofilen</span><span class="sxs-lookup"><span data-stu-id="f191d-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="f191d-107">Gå till Kredit och inkasso > Inställningar > Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="f191d-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="f191d-108">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f191d-108">Click Edit.</span></span>
    * <span data-ttu-id="f191d-109">Välj en kravbrevssekvens i listrutan.</span><span class="sxs-lookup"><span data-stu-id="f191d-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="f191d-110">Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="f191d-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="f191d-111">Registerbegränsningsfliken gör det möjligt att ändra hur kravbrev bearbetas.</span><span class="sxs-lookup"><span data-stu-id="f191d-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="f191d-112">Om detta fält har satts till Ja, kravbrev skapas för denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="f191d-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="f191d-113">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f191d-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="f191d-114">Skapa kravbrev</span><span class="sxs-lookup"><span data-stu-id="f191d-114">Create collection letters</span></span>
1. <span data-ttu-id="f191d-115">Gå till Kredit och inkasso > Kravbrev > Skapa kravbrev.</span><span class="sxs-lookup"><span data-stu-id="f191d-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="f191d-116">Du måste välja transaktionstyperna för kravbrev.</span><span class="sxs-lookup"><span data-stu-id="f191d-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="f191d-117">Alla öppna transaktioner för dessa typer inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="f191d-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="f191d-118">Välj ett alternativ i fältet Collection letter.</span><span class="sxs-lookup"><span data-stu-id="f191d-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="f191d-119">Ange datumet för det aktuella kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="f191d-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="f191d-120">Det finns två bokföringsprofilalternativ: Konto – använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="f191d-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="f191d-121">Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="f191d-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="f191d-122">Välj en bokföringsprofil om du har ändrat Använd bokföringsprofil från till Välj.</span><span class="sxs-lookup"><span data-stu-id="f191d-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="f191d-123">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="f191d-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="f191d-124">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="f191d-124">Click Filter.</span></span>
6. <span data-ttu-id="f191d-125">I fältet Kriterier, ange ett kund ID i kriteriefältet.</span><span class="sxs-lookup"><span data-stu-id="f191d-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="f191d-126">Till exempel US-001.</span><span class="sxs-lookup"><span data-stu-id="f191d-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="f191d-127">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f191d-127">Click OK.</span></span>
8. <span data-ttu-id="f191d-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f191d-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="f191d-129">Skriv ut kravbrev</span><span class="sxs-lookup"><span data-stu-id="f191d-129">Print collection letters</span></span>
1. <span data-ttu-id="f191d-130">Gå till Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev.</span><span class="sxs-lookup"><span data-stu-id="f191d-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="f191d-131">Välj Skapad i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="f191d-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="f191d-132">Välj Ej utskrivet i fältet Utskriven.</span><span class="sxs-lookup"><span data-stu-id="f191d-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="f191d-133">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="f191d-133">Click Print.</span></span>
5. <span data-ttu-id="f191d-134">Klicka på kravbrevsnotering.</span><span class="sxs-lookup"><span data-stu-id="f191d-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="f191d-135">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="f191d-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="f191d-136">Ange slutdatumet för bokföringar</span><span class="sxs-lookup"><span data-stu-id="f191d-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="f191d-137">Klicka på OK för att skriva ut kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="f191d-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="f191d-138">Bokför kravbrevet</span><span class="sxs-lookup"><span data-stu-id="f191d-138">Post the collection letter</span></span>
1. <span data-ttu-id="f191d-139">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="f191d-139">Click Post.</span></span>
2. <span data-ttu-id="f191d-140">Ange bokföringsdatumet för kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="f191d-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="f191d-141">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="f191d-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="f191d-142">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f191d-142">Click OK.</span></span>
5. <span data-ttu-id="f191d-143">Välj Bokförd i fältet Status.</span><span class="sxs-lookup"><span data-stu-id="f191d-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="f191d-144">Välj ett alternativ i fältet Utskriven.</span><span class="sxs-lookup"><span data-stu-id="f191d-144">In the Printed field, select an option.</span></span>


