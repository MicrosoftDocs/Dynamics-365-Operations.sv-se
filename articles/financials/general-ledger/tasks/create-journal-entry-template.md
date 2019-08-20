---
title: Skapa en journalpost med en mall
description: Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a3fb750e04fb134fc9ac38d9a47201803566113
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846641"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="4679a-103">Skapa en journalpost med en mall</span><span class="sxs-lookup"><span data-stu-id="4679a-103">Create a journal entry using template</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4679a-104">Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="4679a-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="4679a-105">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="4679a-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="4679a-106">Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="4679a-106">General ledger > Journal entries > General journals.</span></span> <span data-ttu-id="4679a-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4679a-107">Click New.</span></span>
    * <span data-ttu-id="4679a-108">I den här proceduren börjar vi med att skapa och bokföra en journal verifikation, men alla tidigare bokförd bokföringsorder kan sparas som en mall.</span><span class="sxs-lookup"><span data-stu-id="4679a-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
2. <span data-ttu-id="4679a-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4679a-109">In the Name field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4679a-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4679a-110">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="4679a-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4679a-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="4679a-112">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="4679a-112">Click Lines.</span></span>
6. <span data-ttu-id="4679a-113">Ange ett konto för kontotypen.</span><span class="sxs-lookup"><span data-stu-id="4679a-113">Enter an account for the Account type.</span></span>
7. <span data-ttu-id="4679a-114">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4679a-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="4679a-115">Ange ett belopp i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="4679a-115">Enter an amount in the Debit field.</span></span>
9. <span data-ttu-id="4679a-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4679a-116">Click New.</span></span>
10. <span data-ttu-id="4679a-117">Ange ett annat konto för kontotypen.</span><span class="sxs-lookup"><span data-stu-id="4679a-117">Enter a different account for the Account type.</span></span>
11. <span data-ttu-id="4679a-118">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4679a-118">In the Description field, type a value.</span></span>
12. <span data-ttu-id="4679a-119">Ange ett belopp i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="4679a-119">Enter an amount in the Debit field.</span></span>
13. <span data-ttu-id="4679a-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4679a-120">Click New.</span></span>
14. <span data-ttu-id="4679a-121">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="4679a-121">In the Account field, specify the desired values.</span></span>
15. <span data-ttu-id="4679a-122">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4679a-122">In the Description field, type a value.</span></span>
16. <span data-ttu-id="4679a-123">Ange ett belopp i krediteringsfältet för att balansera verifikationen.</span><span class="sxs-lookup"><span data-stu-id="4679a-123">Enter an amount in the Credit field to balance the voucher.</span></span>
17. <span data-ttu-id="4679a-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="4679a-124">Click Post.</span></span>
18. <span data-ttu-id="4679a-125">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="4679a-125">Click Functions.</span></span>
19. <span data-ttu-id="4679a-126">Klicka på Spara verifikationsmall.</span><span class="sxs-lookup"><span data-stu-id="4679a-126">Click Save voucher template.</span></span>
20. <span data-ttu-id="4679a-127">I den här proceduren förutsätts det en procentmalltyp.</span><span class="sxs-lookup"><span data-stu-id="4679a-127">This procedure assumes a Percent Template type.</span></span> <span data-ttu-id="4679a-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4679a-128">Click OK.</span></span>
    * <span data-ttu-id="4679a-129">• Procent: Beloppen i verifikationen konverteras till procentsatsfaktorer, vilket innebär att alla belopp, används när verifikationsmallen har valts.</span><span class="sxs-lookup"><span data-stu-id="4679a-129">• Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>  <span data-ttu-id="4679a-130">• Belopp: De möjligt att beloppen ska lagras och kommer att användas.</span><span class="sxs-lookup"><span data-stu-id="4679a-130">• Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="4679a-131">Klicka på Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="4679a-131">Click General journals.</span></span>
22. <span data-ttu-id="4679a-132">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4679a-132">Click New.</span></span>
23. <span data-ttu-id="4679a-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="4679a-133">In the Name field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="4679a-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4679a-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="4679a-135">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="4679a-135">Click Lines.</span></span>
26. <span data-ttu-id="4679a-136">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="4679a-136">Click Functions.</span></span>
27. <span data-ttu-id="4679a-137">Klicka på Välj verifikationsmall.</span><span class="sxs-lookup"><span data-stu-id="4679a-137">Click Select voucher template.</span></span>
28. <span data-ttu-id="4679a-138">Sök efter mallen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="4679a-138">Find the template that you created earlier.</span></span> <span data-ttu-id="4679a-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4679a-139">Click OK.</span></span>
    * <span data-ttu-id="4679a-140">Du kan behöva klicka på föregående steget och sedan välja korrekt mallen, om annan mallar finns.</span><span class="sxs-lookup"><span data-stu-id="4679a-140">You may need to click Previous step and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="4679a-141">Ange det belopp som ska användas för verifikationen i beloppsfältet.</span><span class="sxs-lookup"><span data-stu-id="4679a-141">In the Amount field, enter the amount to be applied to the voucher.</span></span>
    * <span data-ttu-id="4679a-142">Beloppsfältet visas bara om verifikationsmallen är av typen Procent.</span><span class="sxs-lookup"><span data-stu-id="4679a-142">The amount field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="4679a-143">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4679a-143">Click OK.</span></span>

