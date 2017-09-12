--- 
title: "Bekräfta försäljningsorder"
description: "I den här proceduren visas hur du bekräftar försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7cab69222c5004e6a62c632a9e85085403434ffd
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="confirm-sales-orders"></a><span data-ttu-id="ae446-103">Bekräfta försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="ae446-103">Confirm sales orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ae446-104">I den här proceduren visas hur du bekräftar försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ae446-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="ae446-105">Du får reda på hur du bekräftar en enstaka order och hur du bekräftar flera order på en gång.</span><span class="sxs-lookup"><span data-stu-id="ae446-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="ae446-106">Dessa uppgifter utförs vanligtvis via en försäljningsorderbehandlare.</span><span class="sxs-lookup"><span data-stu-id="ae446-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="ae446-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="ae446-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="ae446-108">Kontrollera att det finns flera öppna försäljningsorder för samma kund innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="ae446-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="ae446-109">Om du använder USMF kan du använda kunden US-027.</span><span class="sxs-lookup"><span data-stu-id="ae446-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="ae446-110">Bekräfta en enskild försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="ae446-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="ae446-111">Gå till försäljning och marknadsföring > beställningar > Alla beställningar.</span><span class="sxs-lookup"><span data-stu-id="ae446-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="ae446-112">Hitta och markera den order du vill bekräfta i listan.</span><span class="sxs-lookup"><span data-stu-id="ae446-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="ae446-113">Klicka på länken för försäljningsordernumret för att öppna den valda ordern.</span><span class="sxs-lookup"><span data-stu-id="ae446-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="ae446-114">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ae446-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="ae446-115">Klicka på Bekräfta försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ae446-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="ae446-116">Utöka eller komprimera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="ae446-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="ae446-117">Kontrollera att fältet Bokföring ja är aktivt.</span><span class="sxs-lookup"><span data-stu-id="ae446-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="ae446-118">Ställ in alternativet Skriv ut bekräftelse på Ja.</span><span class="sxs-lookup"><span data-stu-id="ae446-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="ae446-119">Fältet Checkkreditgräns anger vilken metod som ska användas för att beräkna en kunds återstående kredit.</span><span class="sxs-lookup"><span data-stu-id="ae446-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="ae446-120">Som standard kopieras den från sidan Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="ae446-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="ae446-121">Om du vill hoppa över kreditgränskontrollen när du bekräftar en specifik försäljningsorder anger du checkkreditgränsen till Ingen.</span><span class="sxs-lookup"><span data-stu-id="ae446-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="ae446-122">Du bör dock vara medveten om att även om det här fältet är inställt på Ingen, så kommer kreditgränskontrollen fortfarande att utföras om alternativet Obligatorisk kreditgräns har valts i kundhuvuddata.</span><span class="sxs-lookup"><span data-stu-id="ae446-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="ae446-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ae446-123">Click OK.</span></span>
9. <span data-ttu-id="ae446-124">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="ae446-124">Click Yes.</span></span>
10. <span data-ttu-id="ae446-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ae446-125">Close the page.</span></span>
11. <span data-ttu-id="ae446-126">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ae446-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="ae446-127">Klicka på Ändra vy.</span><span class="sxs-lookup"><span data-stu-id="ae446-127">Click Change view.</span></span>
13. <span data-ttu-id="ae446-128">Klicka på Huvudvy.</span><span class="sxs-lookup"><span data-stu-id="ae446-128">Click Header view.</span></span>
    * <span data-ttu-id="ae446-129">När en order har bekräftats anges dokumentstatusen till Bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="ae446-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="ae446-130">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ae446-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="ae446-131">Klicka på Försäljningsorderbekräftelse.</span><span class="sxs-lookup"><span data-stu-id="ae446-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="ae446-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ae446-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="ae446-133">Bekräfta flera försäljningsorder samtidigt</span><span class="sxs-lookup"><span data-stu-id="ae446-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="ae446-134">Gå till Försäljning och marknadsföring > Försäljningsorder > Orderbekräftelse > Bekräfta försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ae446-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="ae446-135">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="ae446-135">Click Select.</span></span>
3. <span data-ttu-id="ae446-136">Välj den post som refererar till fältet Kundkonto i listan på fliken Intervall.</span><span class="sxs-lookup"><span data-stu-id="ae446-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="ae446-137">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="ae446-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ae446-138">Hitta och välj kundkontot som har flera order som du vill massbekräfta.</span><span class="sxs-lookup"><span data-stu-id="ae446-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="ae446-139">Om du använder USMF kan du välja kontot US-027.</span><span class="sxs-lookup"><span data-stu-id="ae446-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="ae446-140">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ae446-140">Click OK.</span></span>
    * <span data-ttu-id="ae446-141">På fliken Översikt visas en lista över order som matchar frågekriterierna.</span><span class="sxs-lookup"><span data-stu-id="ae446-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="ae446-142">Dessa inkluderas i bekräftelsen.</span><span class="sxs-lookup"><span data-stu-id="ae446-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="ae446-143">I fältet Samlingsuppdatering för anges den parameter som ska användas för att summera flera order till ett bekräftelsedokument.</span><span class="sxs-lookup"><span data-stu-id="ae446-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="ae446-144">Som standard kopieras alternativet från inställningen Standardvärden för samlingsuppdatering på sidan Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="ae446-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="ae446-145">Välj "Order" i Samlingsuppdatering för fält.</span><span class="sxs-lookup"><span data-stu-id="ae446-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="ae446-146">Minimiparametrarna som krävs för att skapa samlingsuppdateringar är Fakturakonto och Valuta.</span><span class="sxs-lookup"><span data-stu-id="ae446-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="ae446-147">Det innebär att samlingsuppdateringar som har olika fakturakonton och olika valutor inte är tillåtna.</span><span class="sxs-lookup"><span data-stu-id="ae446-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="ae446-148">Ytterligare parametrar kan ställas in på sidan Samlingsuppdateringsparametrar som är tillgänglig från sidan Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="ae446-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="ae446-149">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="ae446-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="ae446-150">Markera det ordernummer som du vill ska vara samlingsorder i listan.</span><span class="sxs-lookup"><span data-stu-id="ae446-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="ae446-151">Klicka på Ordna.</span><span class="sxs-lookup"><span data-stu-id="ae446-151">Click Arrange.</span></span>
11. <span data-ttu-id="ae446-152">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ae446-152">Click OK.</span></span>
12. <span data-ttu-id="ae446-153">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ae446-153">Click OK.</span></span>


