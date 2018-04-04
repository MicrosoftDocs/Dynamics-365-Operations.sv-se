---
title: "Dataallokering för budgetplanering"
description: "Det här avsnittet beskriver de olika allokeringsmetoder som är tillgängliga i Microsoft Dynamics 365 for Finance and Operations och hur de kan användas."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: b5f262318b4defb941f1216d0bfe06961f62bad4
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="budget-planning-data-allocation"></a><span data-ttu-id="1100a-103">Dataallokering för budgetplanering</span><span class="sxs-lookup"><span data-stu-id="1100a-103">Budget planning data allocation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1100a-104">Det här avsnittet beskriver de olika allokeringsmetoder som är tillgängliga i Microsoft Dynamics 365 for Finance and Operations och hur de kan användas.</span><span class="sxs-lookup"><span data-stu-id="1100a-104">This article describes the various allocation methods that are available in Microsoft Dynamics 365 for Finance and Operations and how they can be used.</span></span>  

<span data-ttu-id="1100a-105">Du kan fördela data i en budgetplan på många sätt för att exakt att beskriva de projekterade beloppen.</span><span class="sxs-lookup"><span data-stu-id="1100a-105">You can distribute the data in a budget plan in a number of ways to accurately portray the projected amounts.</span></span>

## <a name="allocation-methods"></a><span data-ttu-id="1100a-106">Allokeringsmetoder</span><span class="sxs-lookup"><span data-stu-id="1100a-106">Allocation methods</span></span>
<span data-ttu-id="1100a-107">Tre allokeringsmetoder (Allokera över perioder, Allokera över dimensioner Använd allokeringsregler för redovisning kan skapa budgetplanrader som baseras på rader i samma budgetplan.</span><span class="sxs-lookup"><span data-stu-id="1100a-107">Three allocation methods (Allocate across periods, Allocate to dimensions, and Use ledger allocation rules) can create budget plan lines that are based on lines in the same budget plan.</span></span> <span data-ttu-id="1100a-108">Tre andra metoder (Aggregera, Distribuera och Kopiera från budgetplan) kan skapa budgetplanrader i andra budgetplaner.</span><span class="sxs-lookup"><span data-stu-id="1100a-108">Three other methods (Aggregate, Distribute, and Copy from budget plan) can create budget plan lines in other budget plans.</span></span> <span data-ttu-id="1100a-109">För alla sex allokeringmetoder anger du målscenariot.</span><span class="sxs-lookup"><span data-stu-id="1100a-109">For all six allocation methods, you specify the destination scenario.</span></span> <span data-ttu-id="1100a-110">Målscenariot kan antingen vara samma som källscenariot eller skilja sig från källscenariot.</span><span class="sxs-lookup"><span data-stu-id="1100a-110">The destination scenario can be either the same as the source scenario or different from the source scenario.</span></span> <span data-ttu-id="1100a-111">Dessutom kan du ange om nya rader bifogas till budgetplanen eller om de aktuella raderna i budgetplanen ska ersättas.</span><span class="sxs-lookup"><span data-stu-id="1100a-111">Additionally, you can specify whether new lines are appended to the budget plan or replace the current lines in the budget plan.</span></span>

<span data-ttu-id="1100a-112">[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allokera över flera perioder** – En kategori för periodallokering används för att allokera budgetplanraderna från källbudgetplanscenariot över perioder i målscenariot.</span><span class="sxs-lookup"><span data-stu-id="1100a-112">[![AllocateAcrossPeriods](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allocate across periods** – A period allocation category is used to allocate the budget plan lines from the source budget plan scenario across periods in the destination scenario.</span></span> <span data-ttu-id="1100a-113">Källbeloppet tilldelas flera rader i målscenariot baserat på den procentsats och det datum som har anges i kategorin för periodallokering.</span><span class="sxs-lookup"><span data-stu-id="1100a-113">The source amount is assigned to multiple lines in the destination scenario, based on the percentage and date that are defined in the period allocation category.</span></span>         

<span data-ttu-id="1100a-114">[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allokera över dimensioner** – budgetplanraderna allokeras från källbudgetplaneringsscenariot till en eller flera rader i målscenariot baserat på de procentsatser och ekonomiska dimensioner som har definierats i ett valt budgetallokeringsvillkor.</span><span class="sxs-lookup"><span data-stu-id="1100a-114">[![AllocateToDimensions](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allocate to dimensions** – The budget plan lines are allocated from the source budget planning scenario to one or more lines in the destination scenario, based on the percentages and financial dimensions that are defined in a selected budget allocation term.</span></span>           

<span data-ttu-id="1100a-115">![AggregateChart](./media/aggregatechart-300x230.png)
**Aggregera** – budgetplansraderna aggregeras från källbudgetplansscenariot i den associerade (underordnade) budgetplanen till målscenariot i den överordnade budgetplanen.</span><span class="sxs-lookup"><span data-stu-id="1100a-115">![AggregateChart](./media/aggregatechart-300x230.png)
**Aggregate** – The budget plan lines are aggregated from the source budget plan scenario in the associated (child) budget plans to the destination scenario in the parent budget plan.</span></span> <span data-ttu-id="1100a-116">Den här metoden aktiverar budgetbelopp som förbereds på lägre nivå i organisationen att konsolideras på en högre nivå.</span><span class="sxs-lookup"><span data-stu-id="1100a-116">This method enables budget amounts that are prepared at a lower level in the organization to be consolidated at a higher level.</span></span>          

<span data-ttu-id="1100a-117">[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Fördela** - Budgetplanraderna fördelas från källbudgetplaneringsscenariot i den överordnade i budgetplanen till målscenariot i de associerade (underordnade) budgetplanerna baserat på organisationsenheternas ekonomiska dimensioner av de associerade planerna.</span><span class="sxs-lookup"><span data-stu-id="1100a-117">[![DistributeChart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribute** – The budget plan lines are distributed from the source budget planning scenario in the parent budget plan to the destination scenario in the associated (child) budget plans, based on the financial dimensions of the organization units of the associated plans.</span></span> <span data-ttu-id="1100a-118">Den här metoden aktiverar budgetbelopp som förbereds på högre nivå i organisationen att fördelas ut för mer lokaliserad granskning.</span><span class="sxs-lookup"><span data-stu-id="1100a-118">This method enables budget amounts that are prepared at a higher level in the organization to be spread out for more localized review.</span></span>           

<span data-ttu-id="1100a-119">[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Använd allokeringsregler för redovisning** – Budgetplanraderna distribueras från källbudgetplaneringsscenariot till målscenariot baserat på vald allokeringsregel för redovisning.</span><span class="sxs-lookup"><span data-stu-id="1100a-119">[![LedgerAllocationRules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Use ledger allocation rules** – The budget plan lines are distributed from the source budget planning scenario to the destination scenario, based on the ledger allocation rule that is selected.</span></span> 

<span data-ttu-id="1100a-120">[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Kopiera från budgetplan** – På samma sätt som med metoden Fördela allokering skapas budgetplanrader i målet baserat på rader i en relaterad budgetplan.</span><span class="sxs-lookup"><span data-stu-id="1100a-120">[![CopyFromBudgetPlan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copy from budget plan** – As in the Distribute allocation method, budget plan lines are created in the destination, based on lines in a related budget plan.</span></span> <span data-ttu-id="1100a-121">Men för den här metoden behöver inte källbudgetplanen vara den överordnade utan kan vara på en högre nivå i budgetplanshierarkin.</span><span class="sxs-lookup"><span data-stu-id="1100a-121">However, for this method, the source budget plan doesn't have to be the parent but can be at any higher level in the budget plan hierarchy.</span></span> <span data-ttu-id="1100a-122">Denna allokeringsmetod är användbar om konsoliderade belopp ursprungligen budgeteras på en mycket högre nivå och måste överföras till en lägre nivå i organisationen för detaljerad granskning och justering, innan de kan få överordnat godkännande.</span><span class="sxs-lookup"><span data-stu-id="1100a-122">This allocation method is useful if consolidated amounts are originally budgeted at a much higher level, and must be transferred to a lower level of the organization for detailed review and adjustment before they can receive upper-level approval.</span></span>          

## <a name="using-allocation-methods-in-a-budget-plan"></a><span data-ttu-id="1100a-123">Använda allokeringsmetoder i en budgetplan</span><span class="sxs-lookup"><span data-stu-id="1100a-123">Using allocation methods in a budget plan</span></span>
<span data-ttu-id="1100a-124">För att utföra allokeringar på sidan Budgetplan, välj raderna som ska allokeras och klicka sedan på **Allokera budget**</span><span class="sxs-lookup"><span data-stu-id="1100a-124">To perform allocations on the budget plan page, select the lines to allocate, and then click **Allocate budget**.</span></span>

<span data-ttu-id="1100a-125">[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span><span class="sxs-lookup"><span data-stu-id="1100a-125">[![AllocateBudgetButton](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span></span> 

<span data-ttu-id="1100a-126">Sedan väljer du en allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="1100a-126">Next, select an allocation method.</span></span> <span data-ttu-id="1100a-127">De återstående fälten ställs sedan in, baserat på den metod som du har valt.</span><span class="sxs-lookup"><span data-stu-id="1100a-127">The remaining fields are then set, based on the method that you selected.</span></span> <span data-ttu-id="1100a-128">Fälten inkluderar källa och mål för budgetplanen och ett alternativ som låter dig multiplicera källan för en angiven faktor när målbeloppen skapas, om du vill förenkla bulkjustering.</span><span class="sxs-lookup"><span data-stu-id="1100a-128">These fields include the source and destination of the budget plan data, and an option that lets you multiply the source by a specified factor when the destination amounts are created, to simplify bulk adjustment.</span></span> <span data-ttu-id="1100a-129">Du kan även ange alternativet **Bifoga till plan**.</span><span class="sxs-lookup"><span data-stu-id="1100a-129">You can also set the **Append to plan** option.</span></span> <span data-ttu-id="1100a-130">Välj **Nej** om du vill ersätta befintliga budgetplanrader eller välj **Ja** för att behålla de befintliga budgetplanraderna och för att lägga till nya rader för de allokerade beloppen.</span><span class="sxs-lookup"><span data-stu-id="1100a-130">Select **No** to replace the existing budget plan lines, or select **Yes** to retain the existing budget plan lines and add new lines for the allocated amounts.</span></span>

## <a name="automating-allocations-during-a-workflow"></a><span data-ttu-id="1100a-131">Automatisera allokering under ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="1100a-131">Automating allocations during a workflow</span></span>
<span data-ttu-id="1100a-132">En kraftfull funktion låter allokeringar utföras automatiskt som en del av en budgetplaneringsarbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="1100a-132">One powerful feature enables allocations to be performed automatically as part of a budget planning workflow.</span></span> <span data-ttu-id="1100a-133">Som en budgetplan flyttas genom sin arbetsflödet, kan automatiska uppgifter aktivera en allokering vid en specifik budgetplaneringsfas.</span><span class="sxs-lookup"><span data-stu-id="1100a-133">As a budget plan moves through its workflow, automated tasks can invoke an allocation at a specified budget planning stage.</span></span> 

<span data-ttu-id="1100a-134">Om du vill ställa in automatiserad allokering måste du först skapa ett allokeringsschema på sidan **Budgetplaneringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1100a-134">To set up automated allocation, you must first create an allocation schedule on the **Budget planning configuration** page.</span></span> <span data-ttu-id="1100a-135">Allokeringsschemat definierar den allokeringsmetod som ska användas när den automatiserade allokeringen körs och värdena i de olika allokeringsalternativen (se det tidigare avsnittet för beskrivningar).</span><span class="sxs-lookup"><span data-stu-id="1100a-135">The allocation schedule defines the allocation method that will be used when the automated allocation is run, and the values of the various allocation options (see the previous section for descriptions).</span></span> 

<span data-ttu-id="1100a-136">Därefter skapar du en fasallokering på sidan **Budgetplaneringskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1100a-136">Next, you create a stage allocation on the **Budget planning configuration** page.</span></span> <span data-ttu-id="1100a-137">Fasallokeringen tilldelar ett allokeringsschema till budgetplaneringsarbetsflödet och -fasen.</span><span class="sxs-lookup"><span data-stu-id="1100a-137">The stage allocation assigns an allocation schedule to the budget planning workflow and stage.</span></span> 

<span data-ttu-id="1100a-138">Lägg slutligen till en automatisk uppgift för allokeringsfas för budgetplanering på önskad arbetsflödefas.</span><span class="sxs-lookup"><span data-stu-id="1100a-138">Finally, add an automated task for budget planning stage allocation at the desired workflow stage.</span></span> <span data-ttu-id="1100a-139">I följande exempel har två fasallokeringar för budgetplanering (anges i rött) infogats i arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="1100a-139">In the following example, two budget planning stage allocations (outlined in red) have been inserted into the workflow.</span></span>

<span data-ttu-id="1100a-140">[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span><span class="sxs-lookup"><span data-stu-id="1100a-140">[![BudgetPlanningStageAllocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span></span>




