---
title: Skapa en journalpost med en mall
description: Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6a3ec1d04515106d7e391834ec646f957cbc03b0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837043"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="fde42-103">Skapa en journalpost med en mall</span><span class="sxs-lookup"><span data-stu-id="fde42-103">Create a journal entry using template</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fde42-104">Bokförda journalverifikationer kan sparas som verifikationsmallar och tillämpas vid en ny bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="fde42-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="fde42-105">I den här proceduren används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fde42-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="fde42-106">Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalposter > Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="fde42-106">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
2. <span data-ttu-id="fde42-107">Klicka på **Nytt** i **Åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="fde42-107">On the **Action pane**, click **New**.</span></span> <span data-ttu-id="fde42-108">I den här proceduren börjar vi med att skapa och bokföra en journal verifikation, men alla tidigare bokförd bokföringsorder kan sparas som en mall.</span><span class="sxs-lookup"><span data-stu-id="fde42-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
3. <span data-ttu-id="fde42-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fde42-109">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fde42-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fde42-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fde42-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fde42-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fde42-112">Klicka på **Rader**.</span><span class="sxs-lookup"><span data-stu-id="fde42-112">Click **Lines**.</span></span>
7. <span data-ttu-id="fde42-113">I fältet **Kontotyp**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="fde42-113">In the **Account type** field, type a value.</span></span>
8. <span data-ttu-id="fde42-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="fde42-114">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="fde42-115">Ange ett värde i fältet **Debet**.</span><span class="sxs-lookup"><span data-stu-id="fde42-115">In the **Debit** field, type a value.</span></span>
10. <span data-ttu-id="fde42-116">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fde42-116">Click **New**.</span></span>
11. <span data-ttu-id="fde42-117">I fältet **Kontotyp**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="fde42-117">In the **Account type** field, type a value.</span></span>
12. <span data-ttu-id="fde42-118">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="fde42-118">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="fde42-119">Ange ett värde i fältet **Debet**.</span><span class="sxs-lookup"><span data-stu-id="fde42-119">In the **Debit** field, type a value.</span></span>
14. <span data-ttu-id="fde42-120">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fde42-120">Click **New**.</span></span>
14. <span data-ttu-id="fde42-121">Ange önskade värden i fältet **Konto**.</span><span class="sxs-lookup"><span data-stu-id="fde42-121">In the **Account** field, specify the desired values.</span></span>
15. <span data-ttu-id="fde42-122">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="fde42-122">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="fde42-123">Ange ett värde för att balansera verifikationen i fältet **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="fde42-123">In the **Credit** field, type a value to balance the voucher.</span></span>
17. <span data-ttu-id="fde42-124">Klicka på **Bokför** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="fde42-124">On the **Action pane**, click **Post**.</span></span>
18. <span data-ttu-id="fde42-125">Klicka på **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="fde42-125">Click **Functions**.</span></span>
19. <span data-ttu-id="fde42-126">Klicka på mallen **Spara verifikation**.</span><span class="sxs-lookup"><span data-stu-id="fde42-126">Click **Save voucher** template.</span></span>
20. <span data-ttu-id="fde42-127">I den här proceduren förutsätts typen **Procentmall**.</span><span class="sxs-lookup"><span data-stu-id="fde42-127">This procedure assumes a **Percent Template** type.</span></span> <span data-ttu-id="fde42-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fde42-128">Click OK.</span></span>
    - <span data-ttu-id="fde42-129">Procent: Beloppen i verifikationen konverteras till procentsatsfaktorer, vilket innebär att alla belopp som kan användas när verifikationsmallen har valts.</span><span class="sxs-lookup"><span data-stu-id="fde42-129">Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>
    - <span data-ttu-id="fde42-130">Belopp: De möjligt att beloppen lagras och kommer att användas.</span><span class="sxs-lookup"><span data-stu-id="fde42-130">Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="fde42-131">Klicka på **Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="fde42-131">Click **General journals**.</span></span>
22. <span data-ttu-id="fde42-132">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="fde42-132">Click **New**.</span></span>
23. <span data-ttu-id="fde42-133">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="fde42-133">In the **Name** field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="fde42-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fde42-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="fde42-135">Klicka på **Rader**.</span><span class="sxs-lookup"><span data-stu-id="fde42-135">Click **Lines**.</span></span>
26. <span data-ttu-id="fde42-136">Klicka på **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="fde42-136">Click **Functions**.</span></span>
27. <span data-ttu-id="fde42-137">Klicka på **Välj verifikationsmall**.</span><span class="sxs-lookup"><span data-stu-id="fde42-137">Click **Select voucher template**.</span></span>
28. <span data-ttu-id="fde42-138">Sök efter mallen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="fde42-138">Find the template that you created earlier.</span></span> <span data-ttu-id="fde42-139">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="fde42-139">Click **OK**.</span></span> <span data-ttu-id="fde42-140">Du kan behöva klicka på  **Föregående steg** och sedan välja korrekt mallen, om annan mallar finns.</span><span class="sxs-lookup"><span data-stu-id="fde42-140">You may need to click **Previous step** and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="fde42-141">Ange det belopp som ska användas för verifikationen i fältet **Belopp**.</span><span class="sxs-lookup"><span data-stu-id="fde42-141">In the **Amount** field, enter the amount to be applied to the voucher.</span></span> <span data-ttu-id="fde42-142">Fältet **Belopp** visas bara om verifikationsmallen är av typen Procent.</span><span class="sxs-lookup"><span data-stu-id="fde42-142">The **Amount** field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="fde42-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="fde42-143">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]