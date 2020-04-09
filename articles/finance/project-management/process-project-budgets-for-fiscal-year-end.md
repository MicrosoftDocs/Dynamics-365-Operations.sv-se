---
title: Överför projektbudgetar vid räkenskapsårets slut
description: Den här artikeln innehåller inoformation om hur du överför resterande budgetbelopp till framtida år och skapar budgetregisterdetaljer.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172340"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a><span data-ttu-id="749c5-103">Överför projektbudgetar vid räkenskapsårets slut</span><span class="sxs-lookup"><span data-stu-id="749c5-103">Transfer project budgets at fiscal year end</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="749c5-104">När du arbetar med ett projekt med flera år kanske du har resterande budget vid slutet av räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="749c5-104">When working on a multi-year project, you might have remaining budget at the end of the fiscal year.</span></span> <span data-ttu-id="749c5-105">Du kan överföra de återstående budgetbeloppen för framtida år och skapa budgetregisterdetaljer för beloppen i associerad redovisning.</span><span class="sxs-lookup"><span data-stu-id="749c5-105">You can transfer the remaining budget amounts to a future year, and create budget register details for the amounts in the associated general ledger accounts.</span></span> <span data-ttu-id="749c5-106">Innan du överför de återstående beloppen bör du granska och analysera de resterande budgetbeloppen.</span><span class="sxs-lookup"><span data-stu-id="749c5-106">Before you carry forward the remaining amounts, review and analyze the remaining budget amounts.</span></span>

## <a name="review-and-analyze-remaining-budget-amounts"></a><span data-ttu-id="749c5-107">Granska och analysera återstående budgetbelopp</span><span class="sxs-lookup"><span data-stu-id="749c5-107">Review and analyze remaining budget amounts</span></span>

<span data-ttu-id="749c5-108">Gör på följande sätt om du vill granska årsslutsbudgetbeloppen för projekt, men du är inte klar att föra beloppen framåt.</span><span class="sxs-lookup"><span data-stu-id="749c5-108">Complete the following steps to review the year-end budget amounts for projects, but not carry the amounts forward.</span></span>

1. <span data-ttu-id="749c5-109">Gå till **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-109">Go to **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**.</span></span> 
2. <span data-ttu-id="749c5-110">På sidan **Överföringsprocess för projektbudget** på fliken **Årsslutsalternativ**, kontrollera att **Överför återstående projektbudgetbelopp** inte är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="749c5-110">On the **Project budget carry-forward process** page, on the **Year-end options** tab, verify that **Carry forward remaining project budget amounts** is not enabled.</span></span>
3. <span data-ttu-id="749c5-111">På fliken **Parametrar** i fältet **projektbudgetår**, välj det räkenskapsår som du vill visa det återstående budgetbeloppet för.</span><span class="sxs-lookup"><span data-stu-id="749c5-111">On the **Parameters** tab, in the **Project budget year** field, select the fiscal year for which you want to view the remaining budget amount.</span></span> 
4. <span data-ttu-id="749c5-112">Välj fältet **Ingående räkenskapsår** väljer du det räkenskapsår du vill visa det återstående budgetbeloppet för.</span><span class="sxs-lookup"><span data-stu-id="749c5-112">In the **Opening fiscal year** field, select the fiscal year for which you want to view the remaining budget amount.</span></span> 
5. <span data-ttu-id="749c5-113">I fältet **från prognosmodell** väljer du **resterande budget**.</span><span class="sxs-lookup"><span data-stu-id="749c5-113">In the **From forecast model** field, select **Remaining budget**.</span></span> 
6. <span data-ttu-id="749c5-114">Om du vill inkludera projekt som uppfyller dina valda kriterier och inte har någon resterande budget, väljer du **Visa noll återstående**.</span><span class="sxs-lookup"><span data-stu-id="749c5-114">To include projects that meet your selected criteria and have no remaining budget, select **Show zero remaining**.</span></span>  
7. <span data-ttu-id="749c5-115">På fliken **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier och väljer **process**.</span><span class="sxs-lookup"><span data-stu-id="749c5-115">On the **Select Budgets** tab, select **Retrieve all budgets** to load all budgets that match your selected criteria, and then select **Process**.</span></span> 
8. <span data-ttu-id="749c5-116">För att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-116">To design a database query that loads a specific set of budgets into the pane, select **Retrieve selected budgets**.</span></span>

<span data-ttu-id="749c5-117">Mer information om en viss rad i fönstret får du om du markerar raden och sedan väljer **Visa budgetdetaljer** eller **visa konton**.</span><span class="sxs-lookup"><span data-stu-id="749c5-117">For more information about a specific line in the pane, select the line, and then select **View budget details** or **View accounts**.</span></span>

## <a name="carry-forward-remaining-budget-amounts"></a><span data-ttu-id="749c5-118">Överför återstående budgetbelopp</span><span class="sxs-lookup"><span data-stu-id="749c5-118">Carry forward remaining budget amounts</span></span> 

<span data-ttu-id="749c5-119">När du bearbetar återstående budgetbelopp, kan du skapa transaktioner i redovisningen för beloppen som du överför.</span><span class="sxs-lookup"><span data-stu-id="749c5-119">When you process remaining budget amounts, you can create transactions in the general ledger for the amounts that you are carrying forward.</span></span> <span data-ttu-id="749c5-120">Du skapar redovisningstransaktioner genom att följa stegen i avsnittet, [Överför budgetbelopp och skapa redovisningstransaktioner](#carry-forward).</span><span class="sxs-lookup"><span data-stu-id="749c5-120">To create general ledger transactions, complete the steps in the section, [Carry forward budget amounts and create general ledger transactions](#carry-forward).</span></span> 

> [!NOTE]
> <span data-ttu-id="749c5-121">Budgetbelopp som överförs, överförs till den prognosmodell som är markerad på sidan **Prognosmodeller** som överföringsprognosmodell.</span><span class="sxs-lookup"><span data-stu-id="749c5-121">Budget amounts that are carried forward are transferred to the forecast model that is selected in the **Forecast models** page as the carry-forward forecast model.</span></span>  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a><span data-ttu-id="749c5-122">Överför budgetbelopp och skapa redovisningstransaktioner</span><span class="sxs-lookup"><span data-stu-id="749c5-122">Carry forward budget amounts and create general ledger transactions</span></span>

1.  <span data-ttu-id="749c5-123">Välj **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-123">Select **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**.</span></span> 
2. <span data-ttu-id="749c5-124">På sidan **Överföringsprocess för projektbudget** välj **Årsslut** och aktivera sedan **Överför återstående projektbudgetbelopp** och **Skapa budgetregisterposter i redovisningen**.</span><span class="sxs-lookup"><span data-stu-id="749c5-124">On the **Project budget carry-forward process** page, select **Year-end**, and then enable **Carry forward remaining project budget amounts** and **Create budget register entries in general ledger**.</span></span> 
3. <span data-ttu-id="749c5-125">På fliken **Parametrar** i fältgruppen **Projektparametrar** välj följande:</span><span class="sxs-lookup"><span data-stu-id="749c5-125">On the **Parameters** tab, in the **Project parameters** field group, select the following:</span></span>

   - <span data-ttu-id="749c5-126">**Projektbudgetår**: Välj början på det räkenskapsår som du vill visa de återstående budgetbeloppen för.</span><span class="sxs-lookup"><span data-stu-id="749c5-126">**Project budget year**: Select the beginning of the fiscal year for which you want to view the remaining budget amounts.</span></span> 
   - <span data-ttu-id="749c5-127">**Vinst och förlust**: Skapa resultaträkningstransaktioner i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="749c5-127">**Profit and loss**: Create profit and loss transactions in the general ledger.</span></span> 
   -  <span data-ttu-id="749c5-128">**PIA**: skapa PIA-transaktioner (pågående arbete) i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="749c5-128">**WIP**: Create Work in Progress (WIP) transactions in the general ledger.</span></span>
   -  <span data-ttu-id="749c5-129">**Lön**: Skapa löneallokeringstransaktioner i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="749c5-129">**Payroll**: Create payroll allocation transactions in the general ledger.</span></span> 

5. <span data-ttu-id="749c5-130">I fältgruppen **redovisning** ange följande information:</span><span class="sxs-lookup"><span data-stu-id="749c5-130">In the **General ledger** field group, provide the following information:</span></span> 

   - <span data-ttu-id="749c5-131">I fältet **Ingående räkenskapsår** välj det räkenskapsår som du vill överföra återstående budgetbelopp för projekten.</span><span class="sxs-lookup"><span data-stu-id="749c5-131">In the **Opening fiscal year** field, select the fiscal year that you want to transfer remaining budget amounts to for the projects.</span></span> <span data-ttu-id="749c5-132">Standardvärdet är ett år efter värdet för fältet **Projektbudgetår**.</span><span class="sxs-lookup"><span data-stu-id="749c5-132">The default value is one year after the value in the **Project budget year** field.</span></span>
   -  <span data-ttu-id="749c5-133">I fältet **Överföringsperiod** väljer du den period du vill skapa information om budgetregistret för i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="749c5-133">In the **Carry-forward period** field, select the period that you want to create the budget register details for in the general ledger.</span></span> <span data-ttu-id="749c5-134">Detta är normalt den första perioden i den öppnande räkenskapsåret.</span><span class="sxs-lookup"><span data-stu-id="749c5-134">This is typically the first period in the opening fiscal year.</span></span>

6. <span data-ttu-id="749c5-135">I fältgruppen **Kopiera från/till** ange följande information:</span><span class="sxs-lookup"><span data-stu-id="749c5-135">In the **Copy from/to** field group, provide the following information:</span></span>

   - <span data-ttu-id="749c5-136">I fältet **från prognosmodell** välj den projektprognosmodellen som associeras med de återstående budgetbeloppen du vill överföra för projekten.</span><span class="sxs-lookup"><span data-stu-id="749c5-136">In the **From forecast model** field, select the project budget forecast model associated with the remaining budget amounts you want to transfer for the projects.</span></span> 
   - <span data-ttu-id="749c5-137">Välj den redovisningsbudgetprognosmodell som associeras med budgetbeloppen som du vill överföra till redovisningen i fältet **Till redovisningsbudgetmodell**.</span><span class="sxs-lookup"><span data-stu-id="749c5-137">In the **To ledger budget model** field, select the ledger budget model associated with the budget amounts you want to transfer to the general ledger.</span></span> 
   -  <span data-ttu-id="749c5-138">Markera **Överför försäljningsvaluta** om du vill använda projektets försäljningsvaluta för redovisningstransaktioner som skapas när du överför budgetbeloppen för projekt.</span><span class="sxs-lookup"><span data-stu-id="749c5-138">Select **Transfer sales currency** to use the project's sales currency for the general ledger transactions that are created when you transfer the budget amounts for the projects.</span></span> <span data-ttu-id="749c5-139">Om alternativet inte är valt använder transaktionerna redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="749c5-139">When the option is not selected, the transactions use the accounting currency.</span></span> 
   -  <span data-ttu-id="749c5-140">Välj **Visa noll återstående** för att inkludera projekt som inte har några återstående budgetbelopp, men som uppfyller de andra kriterierna som du väljer i de projekt som visas i den nedre rutan.</span><span class="sxs-lookup"><span data-stu-id="749c5-140">Select **Show zero remaining** to include projects that have no remaining budget amounts, but meet the other criteria that you select in the projects displayed in the bottom pane.</span></span>

7. <span data-ttu-id="749c5-141">På fliken **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier.</span><span class="sxs-lookup"><span data-stu-id="749c5-141">On the **Select Budgets** tab, select **Retrieve all budgets** to load all budgets that match the criteria you selected.</span></span> <span data-ttu-id="749c5-142">Om du föredrar att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-142">If you prefer to design a database query that loads a specific set of project budgets into the pane, select **Retrieve selected budgets**.</span></span>
8. <span data-ttu-id="749c5-143">Markera alternativet i början av raden för projektet För varje projekt, som du vill bearbeta.</span><span class="sxs-lookup"><span data-stu-id="749c5-143">For each project that you want to process, select the option at the beginning of the line for the project.</span></span>

    > [!TIP]
    > <span data-ttu-id="749c5-144">Markera alla eller de flesta av projekten genom att markera kryssrutan högst upp till vänster i det övre vänstra hörnet.</span><span class="sxs-lookup"><span data-stu-id="749c5-144">To select all or most of the projects, select the check mark in the top upper-left corner.</span></span> <span data-ttu-id="749c5-145">Avmarkera kryssrutan för projektet om du vill undanta bearbetning av ett projekt.</span><span class="sxs-lookup"><span data-stu-id="749c5-145">To exclude processing any project, clear the check mark for that project.</span></span>

9. <span data-ttu-id="749c5-146">Om du vill överföra de återstående budgetbeloppen för valda projekt till valt räkenskapsår och skapa budgetregisterdetaljer i redovisningen väljer du **Process**</span><span class="sxs-lookup"><span data-stu-id="749c5-146">To transfer the remaining budget amounts for the selected projects to the selected fiscal year and create budget register details in the general ledger, select **Process**.</span></span>

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a><span data-ttu-id="749c5-147">Överför budgetbelopp utan att skapa redovisningstransaktioner</span><span class="sxs-lookup"><span data-stu-id="749c5-147">Carry forward budget amounts without creating general ledger transactions</span></span>

1. <span data-ttu-id="749c5-148">Gå till **projekthantering och redovisning** > **periodisk** > **budgetar** > **överföra budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-148">Go to **Project management and accounting** > **Periodic** > **Budgets** > **Carry forward budgets**.</span></span>
2. <span data-ttu-id="749c5-149">På sidan **Överföringsprocess för projektbudget** i fältet **Årsslutsalternativ**, välj **Överför återstående projektbudgetbelopp**.</span><span class="sxs-lookup"><span data-stu-id="749c5-149">On the **Project budget carry-forward process** page, in the **Year-end options** field, select **Carry forward remaining project budget amounts**.</span></span>
3. <span data-ttu-id="749c5-150">I gruppen **Parametrar** i fältet **projektbudgetår**, välj det räkenskapsår som du vill visa det återstående budgetbeloppen.</span><span class="sxs-lookup"><span data-stu-id="749c5-150">In the **Parameters** group, in the **Project budget year** field, select the fiscal year for which you want to view the remaining budget amounts.</span></span>
4. <span data-ttu-id="749c5-151">I gruppen **Kopiera från/till** ange följande information:</span><span class="sxs-lookup"><span data-stu-id="749c5-151">In the **Copy from/to** group, provide the following information:</span></span>

   - <span data-ttu-id="749c5-152">I fältet **från prognosmodell** välj den projektprognosmodellen som associeras med de återstående budgetbeloppen du vill överföra för projekten.</span><span class="sxs-lookup"><span data-stu-id="749c5-152">In the **From forecast model** field, select the project budget forecast model that is associated with the remaining budget amounts that you want to transfer for the projects.</span></span> 
   - <span data-ttu-id="749c5-153">Välj **Visa noll återstående** om du vill inkludera projekt som inte har några återstående budgetbelopp, men som uppfyller de andra kriterierna du valt.</span><span class="sxs-lookup"><span data-stu-id="749c5-153">Select **Show zero remaining** to include projects that have no remaining budget amounts, but that meet the other criteria you selected.</span></span>
   - <span data-ttu-id="749c5-154">I gruppen **Välj budget** väljer du **Hämta alla budgetar** för att läsa in alla budgetar som matchar dina valda kriterier.</span><span class="sxs-lookup"><span data-stu-id="749c5-154">In the **Select Budgets** group, select **Retrieve all budgets** to load all budgets that match the criteria that you selected.</span></span> <span data-ttu-id="749c5-155">För att utforma en databasfråga som läser in en viss uppsättning projektbudgetar till fönstret, välj **Hämta valda budgetar**.</span><span class="sxs-lookup"><span data-stu-id="749c5-155">To design a database query that loads a specific set of project budgets into the pane, select **Retrieve selected budgets**.</span></span>

5. <span data-ttu-id="749c5-156">Markera alternativet i början av raden för projektet För varje projekt, som du vill bearbeta.</span><span class="sxs-lookup"><span data-stu-id="749c5-156">For each project that you want to process, select the option at the beginning of the line for the project.</span></span> 
6. <span data-ttu-id="749c5-157">Välj **Process** om du vill överföra återstående budgetbeloppen för valda projekten till valt räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="749c5-157">Select **Process** to transfer the remaining budget amounts for the selected projects to the selected fiscal year.</span></span>

