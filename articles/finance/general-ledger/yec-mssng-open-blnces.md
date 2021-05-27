---
title: Ingående balanser saknas i årsbokslut
description: Det här ämnet förklarar varför ingående balanser kan saknas vid årsbokslut och hur du återskapar dem om de saknas.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028587"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="4d92f-103">Ingående balanser saknas i årsbokslut</span><span class="sxs-lookup"><span data-stu-id="4d92f-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d92f-104">Det här ämnet förklarar varför ingående balanser kan saknas vid årsbokslut och hur du återskapar dem om de saknas.</span><span class="sxs-lookup"><span data-stu-id="4d92f-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="4d92f-105">Symptom</span><span class="sxs-lookup"><span data-stu-id="4d92f-105">Symptom</span></span>

<span data-ttu-id="4d92f-106">Varför finns det inga ingående balanser efter körning av redovisningens årsbokslut?</span><span class="sxs-lookup"><span data-stu-id="4d92f-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="4d92f-107">Lösning</span><span class="sxs-lookup"><span data-stu-id="4d92f-107">Resolution</span></span>

<span data-ttu-id="4d92f-108">Saker att kontrollera vid ett årsbokslut i redovisningen och när du har genererat en råbalans som inte visar ingående balanser för nästa räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="4d92f-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="4d92f-109">Om fältet **Ångra föregående slut** är inställt på **Ja** återförs föregående årsbokslut för samma räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="4d92f-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="4d92f-110">När du kör en process för att återföra årsboksluten tas alla utgående och ingående balansposter bort, som om årsbokslutet aldrig hade körts.</span><span class="sxs-lookup"><span data-stu-id="4d92f-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="4d92f-111">Verifikationerna tas också bort.</span><span class="sxs-lookup"><span data-stu-id="4d92f-111">The vouchers are also deleted.</span></span> <span data-ttu-id="4d92f-112">Årsbokslutet körs inte automatiskt igen.</span><span class="sxs-lookup"><span data-stu-id="4d92f-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="4d92f-113">Du måste starta processen på nytt och nu uppdatera alternativet **Ångra föregående slut** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="4d92f-114">Det här scenariot beskrivs i ämnet vanliga frågor och svar om årsbokslut.</span><span class="sxs-lookup"><span data-stu-id="4d92f-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="4d92f-115">Mer information finns i [Vanliga frågor och svar om aktiviteter för årsavslut](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="4d92f-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="4d92f-116">Symptom</span><span class="sxs-lookup"><span data-stu-id="4d92f-116">Symptom</span></span>

<span data-ttu-id="4d92f-117">Jag körde årsbokslut med alternativet **Ångra föregående stängning** inställt på **Nej** och jag har fortfarande inga ingående balanser för räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="4d92f-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="4d92f-118">Lösning</span><span class="sxs-lookup"><span data-stu-id="4d92f-118">Resolution</span></span>

<span data-ttu-id="4d92f-119">Kontrollera för batchjobbets status.</span><span class="sxs-lookup"><span data-stu-id="4d92f-119">First check the status of the batch job.</span></span> <span data-ttu-id="4d92f-120">Årsbokslut innehåller ett antal separata uppgifter, men det viktigaste steget är batchaktiviteten med aktivitetsbeskrivningen **Steg 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="4d92f-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="4d92f-121">Bokföring av IB-transaktioner och eventuellt UB-transaktionerna i redovisningen sker under det här steget.</span><span class="sxs-lookup"><span data-stu-id="4d92f-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="4d92f-122">[![Lista med batchhistorik](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="4d92f-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="4d92f-123">Om det här steget har slutförts, men du ser inga ingående balanser på sidan **Förfrågan om råbalans** (**Redovisning > Förfrågningar och rapporter > Råbalans**) måste du granska resultatet av årsbokslutets batchjobb för att kontrollera om steget Återskapa saldon har slutförts.</span><span class="sxs-lookup"><span data-stu-id="4d92f-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="4d92f-124">[![Resultat av årsbokslutets batchjobb](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="4d92f-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="4d92f-125">Om det här steget av någon anledning inte slutfördes, bokfördes troligen IB-transaktionerna (och valfria UB).</span><span class="sxs-lookup"><span data-stu-id="4d92f-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="4d92f-126">Du kan kontrollera att redovisningstransaktionerna bokfördes på sidan **Förfrågan om verifikationstransaktioner** genom att ange verifikationsnumret och datumet som angavs i dialogrutan Årsbokslut för året som du stängde (**Redovisning > Förfrågningar och rapporter > Verifikationstransaktioner**).</span><span class="sxs-lookup"><span data-stu-id="4d92f-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="4d92f-127">[![Förfrågan om verifikationstransaktioner](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="4d92f-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="4d92f-128">Om det finns ingående verifikationer (och eventuellt utgående verifikationer) behöver du inte köra årsbokslutet igen.</span><span class="sxs-lookup"><span data-stu-id="4d92f-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="4d92f-129">Se i stället nästa avsnitt för information om att gå vidare.</span><span class="sxs-lookup"><span data-stu-id="4d92f-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="4d92f-130">Symptom</span><span class="sxs-lookup"><span data-stu-id="4d92f-130">Symptom</span></span>

<span data-ttu-id="4d92f-131">Måste jag köra om hela årsbokslutsprocessen om steget Återskapa saldon i årsbokslutet inte slutfördes?</span><span class="sxs-lookup"><span data-stu-id="4d92f-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="4d92f-132">Lösning</span><span class="sxs-lookup"><span data-stu-id="4d92f-132">Resolution</span></span>

<span data-ttu-id="4d92f-133">Steget Återskapa saldon uppdaterar redovisningssaldona som används när förfrågan Råbalans genereras.</span><span class="sxs-lookup"><span data-stu-id="4d92f-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="4d92f-134">Det är det sista steget i årsbokslutsprocessen.</span><span class="sxs-lookup"><span data-stu-id="4d92f-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="4d92f-135">Om det här steget är det enda som inte slutfördes har redovisningstransaktionerna bokförts.</span><span class="sxs-lookup"><span data-stu-id="4d92f-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="4d92f-136">Du behöver inte köra årsbokslutet på nytt.</span><span class="sxs-lookup"><span data-stu-id="4d92f-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="4d92f-137">Det går att köra processen som återskapar saldona manuellt på sidan **Ekonomiska dimensionsuppsättningar** (**Redovisning > Kontoplan > Dimensioner > Ekonomiska dimensionsuppsättningar**).</span><span class="sxs-lookup"><span data-stu-id="4d92f-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="4d92f-138">[![Knappen Återskapa saldon på sidan Ekonomiska dimensionsuppsättningar](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="4d92f-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="4d92f-139">Om det här steget tar lång tid att bearbeta rekommenderar vi att du granskar metodtipsen för ekonomiska dimensionsuppsättningar enligt beskrivningen i [Metodtips för uppdatering av ekonomiska dimensionsuppsättningar](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="4d92f-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

