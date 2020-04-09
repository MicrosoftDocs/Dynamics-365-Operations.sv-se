---
title: Bekräfta försäljningsorder
description: I den här proceduren visas hur du bekräftar försäljningsorder.
author: omulvad
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6383576302789d268d64edcbbe05305b03e956d0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148724"
---
# <a name="confirm-sales-orders"></a><span data-ttu-id="2b906-103">Bekräfta försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="2b906-103">Confirm sales orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2b906-104">I den här proceduren visas hur du bekräftar försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="2b906-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="2b906-105">Du får reda på hur du bekräftar en enstaka order och hur du bekräftar flera order på en gång.</span><span class="sxs-lookup"><span data-stu-id="2b906-105">You'll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="2b906-106">Dessa uppgifter utförs vanligtvis via en försäljningsorderbehandlare.</span><span class="sxs-lookup"><span data-stu-id="2b906-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="2b906-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="2b906-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="2b906-108">Kontrollera att det finns flera öppna försäljningsorder för samma kund innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="2b906-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="2b906-109">Om du använder USMF kan du använda kunden US-027.</span><span class="sxs-lookup"><span data-stu-id="2b906-109">If you're using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="2b906-110">Bekräfta en enskild försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="2b906-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="2b906-111">Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b906-111">Go to **Navigation pane > Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="2b906-112">Hitta och markera den order du vill bekräfta i listan.</span><span class="sxs-lookup"><span data-stu-id="2b906-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="2b906-113">Klicka på länken för försäljningsordernumret för att öppna den valda ordern.</span><span class="sxs-lookup"><span data-stu-id="2b906-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="2b906-114">Klicka på **Sälj** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="2b906-114">On the **Action Pane**, click **Sell**.</span></span>
5. <span data-ttu-id="2b906-115">Klicka på **Bekräfta försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b906-115">Click **Confirm sales order**.</span></span>
6. <span data-ttu-id="2b906-116">Expandera avsnittet **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="2b906-116">Expand the **Parameters** section.</span></span> <span data-ttu-id="2b906-117">Kontrollera att alternativet **Bokför** har värdet Ja.</span><span class="sxs-lookup"><span data-stu-id="2b906-117">Make sure that the **Posting** option is set to 'Yes'.</span></span>  
7. <span data-ttu-id="2b906-118">Ställ in alternativet **Skriv ut bekräftelse** på Ja.</span><span class="sxs-lookup"><span data-stu-id="2b906-118">Set the **Print confirmation option** to 'Yes'.</span></span> <span data-ttu-id="2b906-119">Fältet **Checkkreditgräns** anger vilken metod som ska användas för att beräkna en kunds återstående kredit.</span><span class="sxs-lookup"><span data-stu-id="2b906-119">The **Check credit limit** field specifies the method that's used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="2b906-120">Som standard kopieras den från sidan Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="2b906-120">By default, it's copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="2b906-121">Om du vill hoppa över kreditgränskontrollen när du bekräftar en specifik försäljningsorder anger du **checkkreditgränsen** till Ingen.</span><span class="sxs-lookup"><span data-stu-id="2b906-121">If you want to skip the credit limit check when confirming a specific sales order, set the **Check credit limit** to 'None'.</span></span> <span data-ttu-id="2b906-122">Du bör dock vara medveten om att även om det här fältet är inställt på Ingen, så kommer kreditgränskontrollen fortfarande att utföras om alternativet **Obligatorisk kreditgräns** har valts i kundhuvuddata.</span><span class="sxs-lookup"><span data-stu-id="2b906-122">However, you should be aware that even with if this field is set to 'None', the credit limit check will still be performed if the **Mandatory credit limit** option is selected on the customer master data.</span></span> 
8. <span data-ttu-id="2b906-123">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b906-123">Click **OK**.</span></span>
9. <span data-ttu-id="2b906-124">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2b906-124">Click **Yes**.</span></span>
10. <span data-ttu-id="2b906-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b906-125">Close the page.</span></span>
11. <span data-ttu-id="2b906-126">I **åtgärdsrutan** klickar du på **Alternativ**.</span><span class="sxs-lookup"><span data-stu-id="2b906-126">On the **Action Pane**, click **Options**.</span></span>
12. <span data-ttu-id="2b906-127">Klicka på **ändra uppfattning**.</span><span class="sxs-lookup"><span data-stu-id="2b906-127">Click **Change view**.</span></span>
13. <span data-ttu-id="2b906-128">Klicka på **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="2b906-128">Click **Header view**.</span></span> <span data-ttu-id="2b906-129">När en order har bekräftats anges **dokumentstatusen** till Bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="2b906-129">When an order is confirmed, the **Document status** is set to 'Confirmation'.</span></span> 
14. <span data-ttu-id="2b906-130">Klicka på **Sälj** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="2b906-130">On the **Action Pane**, click **Sell**.</span></span>
15. <span data-ttu-id="2b906-131">Klicka på **Försäljningsorderbekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="2b906-131">Click **Sales order confirmation**.</span></span>
16. <span data-ttu-id="2b906-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="2b906-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="2b906-133">Bekräfta flera försäljningsorder samtidigt</span><span class="sxs-lookup"><span data-stu-id="2b906-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="2b906-134">Gå till **Försäljning och marknadsföring > Försäljningsorder > Orderbekräftelse > Bekräfta försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b906-134">Go to **Sales and marketing > Sales orders > Order confirmation > Confirm sales order**.</span></span>
2. <span data-ttu-id="2b906-135">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="2b906-135">Click **Select**.</span></span>
3. <span data-ttu-id="2b906-136">Välj den post som refererar till fältet **Kundkonto** i listan på fliken **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="2b906-136">In the list on the **Range** tab, find and select the record that references the **Customer account** field.</span></span>
4. <span data-ttu-id="2b906-137">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kriterier**.</span><span class="sxs-lookup"><span data-stu-id="2b906-137">In the **Criteria** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2b906-138">Hitta och välj kundkontot som har flera order som du vill massbekräfta.</span><span class="sxs-lookup"><span data-stu-id="2b906-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span> <span data-ttu-id="2b906-139">Om du använder USMF kan du välja kontot US-027.</span><span class="sxs-lookup"><span data-stu-id="2b906-139">If you're using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="2b906-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b906-140">Click **OK**.</span></span>
    - <span data-ttu-id="2b906-141">På fliken **Översikt** visas en lista över order som matchar frågekriterierna.</span><span class="sxs-lookup"><span data-stu-id="2b906-141">The **Overview** tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="2b906-142">Dessa inkluderas i bekräftelsen.</span><span class="sxs-lookup"><span data-stu-id="2b906-142">These will be included in the confirmation.</span></span>  
    - <span data-ttu-id="2b906-143">I fältet **Samlingsuppdatering** för anges avsnitt **parameter** som ska användas för att summera flera order till ett bekräftelsedokument.</span><span class="sxs-lookup"><span data-stu-id="2b906-143">The **Summary update for** field in the **Parameters** section specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="2b906-144">Som standard kopieras alternativet från inställningen **Standardvärden för samlingsuppdatering** på sidan **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="2b906-144">By default, the option is copied from the D**efault values for summary update setting** on the **Accounts receivable parameters** page.</span></span>  
7. <span data-ttu-id="2b906-145">Välj "Order" i **Samlingsuppdatering** för fält.</span><span class="sxs-lookup"><span data-stu-id="2b906-145">In the **Summary update for** field, select 'Order'.</span></span> <span data-ttu-id="2b906-146">Minimiparametrarna som krävs för att skapa samlingsuppdateringar är **Fakturakonto** och **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="2b906-146">The minimum parameters that are required to create summary updates are **Invoice account** and **Currency**.</span></span> <span data-ttu-id="2b906-147">Det innebär att samlingsuppdateringar som har olika fakturakonton och olika valutor inte är tillåtna.</span><span class="sxs-lookup"><span data-stu-id="2b906-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="2b906-148">Ytterligare parametrar kan ställas in på sidan **Samlingsuppdateringsparametrar** som är tillgänglig från sidan **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="2b906-148">Additional parameters can be set up in the **Summary update parameters** page which is accessible from the **Accounts receivable parameters** page.</span></span> 
8. <span data-ttu-id="2b906-149">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="2b906-149">In the **Sales order** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="2b906-150">Markera det ordernummer som du vill ska vara samlingsorder i listan.</span><span class="sxs-lookup"><span data-stu-id="2b906-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="2b906-151">Klicka på **Ordna**.</span><span class="sxs-lookup"><span data-stu-id="2b906-151">Click **Arrange**.</span></span>
11. <span data-ttu-id="2b906-152">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b906-152">Click **OK**.</span></span>
12. <span data-ttu-id="2b906-153">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b906-153">Click **OK**.</span></span>

