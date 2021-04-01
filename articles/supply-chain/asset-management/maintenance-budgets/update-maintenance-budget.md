---
title: Uppdatera underhållsbudgetar
description: I det här avsnittet beskrivs hur du uppdaterar en underhållsbudget i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 21aba6224bba98eb9bbb423847e123616003b5d9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253480"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="8704b-103">Uppdatera underhållsbudgetar</span><span class="sxs-lookup"><span data-stu-id="8704b-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8704b-104">På sidan **Budgetrader för underhåll** visas alla budgetrader som har skapats för den budget som valts på sidan **Underhållsbudgetar**.</span><span class="sxs-lookup"><span data-stu-id="8704b-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="8704b-105">(Mer information finns i [skapa underhållsbudgetar](create-maintenance-budget.md).) Du kan omberäkna och justera underhållsbudgetrader tills underhållsbudgeten har godkänts.</span><span class="sxs-lookup"><span data-stu-id="8704b-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="8704b-106">När budgetperioden har passerat och kostnaderna har bokförts i Tillgångshantering kan du också uppdatera budgetraderna med faktiska kostnader.</span><span class="sxs-lookup"><span data-stu-id="8704b-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="8704b-107">Beräkna om en underhållsbudget</span><span class="sxs-lookup"><span data-stu-id="8704b-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="8704b-108">Du kan beräkna om en underhållsbudget på sidan **Budgetrader för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="8704b-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="8704b-109">När du beräknar om en underhållsbudget raderas befintliga budgetrader och en ny beräkning görs.</span><span class="sxs-lookup"><span data-stu-id="8704b-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="8704b-110">Välj **Beräkna om** på sidan **Budgetrader för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="8704b-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="8704b-111">I dialogrutan **Beräkna om budget** gör du de ändringar som krävs för den nya beräkningen och väljer **OK**.</span><span class="sxs-lookup"><span data-stu-id="8704b-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="8704b-112">Nya budgetrader skapas enligt de värden du anger.</span><span class="sxs-lookup"><span data-stu-id="8704b-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="8704b-113">Justera budgetrader</span><span class="sxs-lookup"><span data-stu-id="8704b-113">Adjust budget lines</span></span>

<span data-ttu-id="8704b-114">I stället för att omberäkna hela underhållsbudgeten kan du justera valda rader är relaterade till budgetkostnader.</span><span class="sxs-lookup"><span data-stu-id="8704b-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="8704b-115">På sidan **Budgetrader för underhåll** väljer du de rader som budgetkostnaden ska uppdateras för.</span><span class="sxs-lookup"><span data-stu-id="8704b-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="8704b-116">Välj **Justera**.</span><span class="sxs-lookup"><span data-stu-id="8704b-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="8704b-117">Om du vill lägga till ett belopp på de markerade raderna markerar du kryssrutan **Lägg till kostnad** och anger sedan värdet i fältet **Lägg till värde**.</span><span class="sxs-lookup"><span data-stu-id="8704b-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="8704b-118">Om du vill multiplicera budgetkostnaden för de valda budgetraderna med en faktor markerar du kryssrutan **Multiplicera kostnad** och anger faktorn i fältet **Multipliceringsvärde**.</span><span class="sxs-lookup"><span data-stu-id="8704b-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="8704b-119">Om du till exempel anger **1,2** i fältet **Multipliceringsvärde**, ökar du budgetkostnaden på de valda raderna med 20 procent.</span><span class="sxs-lookup"><span data-stu-id="8704b-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="8704b-120">Om du anger **0,7** minskar du budgetkostnaden på de valda raderna med 30 procent.</span><span class="sxs-lookup"><span data-stu-id="8704b-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="8704b-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8704b-121">Select **OK**.</span></span>

<span data-ttu-id="8704b-122">De valda budgetraderna uppdateras enligt värdena som du angav i steg 3 eller 4.</span><span class="sxs-lookup"><span data-stu-id="8704b-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="8704b-123">Uppdatera faktiska kostnader</span><span class="sxs-lookup"><span data-stu-id="8704b-123">Update actual costs</span></span>

<span data-ttu-id="8704b-124">När datumen på budgetraderna har passerat och faktiska kostnader har bokförts i Tillgångshantering kan du också uppdatera underhållsbudgeten med faktiska kostnader.</span><span class="sxs-lookup"><span data-stu-id="8704b-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="8704b-125">Välj **Uppdatera kostnad** på sidan **Budgetrader för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="8704b-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="8704b-126">Välj **OK** i dialogrutan **Beräkna faktisk kostnad**.</span><span class="sxs-lookup"><span data-stu-id="8704b-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="8704b-127">Fälten **Faktisk kostnad** på budgetraderna uppdateras om de faktiska kostnaderna har bokförts.</span><span class="sxs-lookup"><span data-stu-id="8704b-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="8704b-128">Nya budgetrader kan skapas om nya tillgångstyper har skapats sedan du skapade budgeten, och om dessa tillgångstyper har använts på tillgångar som arbetsorder har skapats för och relaterade kostnader har bokförts för.</span><span class="sxs-lookup"><span data-stu-id="8704b-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="8704b-129">Nya budgetrader visar bara faktiska kostnader, eftersom inga budgetkostnader har beräknats för dem.</span><span class="sxs-lookup"><span data-stu-id="8704b-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="8704b-130">Om du vill se en översikt över faktiska kostnader uppdelade på förebyggande, korrigerande och investeringskostnader kan du utföra en beräkning för samma period på sidan **Kostnadskontroll för tillgång**.</span><span class="sxs-lookup"><span data-stu-id="8704b-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="8704b-131">Lägga till budgetrader manuellt</span><span class="sxs-lookup"><span data-stu-id="8704b-131">Manually add budget lines</span></span>

<span data-ttu-id="8704b-132">På sidan **Budgetrader för underhåll** kan du manuellt lägga till en ny budgetrad genom att välj **Ny** och sedan göra val på raden.</span><span class="sxs-lookup"><span data-stu-id="8704b-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="8704b-133">Här följer några exempel på situationer där den här metoden kan vara användbar:</span><span class="sxs-lookup"><span data-stu-id="8704b-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="8704b-134">Du vet att reparation av vissa tillgångar för närvarande pågår under planeringsfasen, men relaterade jobb har ännu inte skapats i Tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="8704b-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="8704b-135">Du vill dock att budgetkostnader för dessa jobb ska inkluderas i underhållsbudgeten.</span><span class="sxs-lookup"><span data-stu-id="8704b-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="8704b-136">Nya tillgångar eller tillgångstyper har skapats sedan du gjorde underhållsbudgeten, men underhållsplanerna har inte ställts in för dessa tillgångar eller tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="8704b-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="8704b-137">Du vill dock att budgetkostnader för dessa tillgångstyper ska inkluderas i underhållsbudgeten.</span><span class="sxs-lookup"><span data-stu-id="8704b-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]