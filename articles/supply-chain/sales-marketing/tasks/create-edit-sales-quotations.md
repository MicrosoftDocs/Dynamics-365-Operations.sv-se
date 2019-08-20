---
title: Skapa och redigera försäljningsofferter
description: I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f66ec29cc0afd6e1ba5a65b241e3aac42a3c59b5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835653"
---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="e0b48-103">Skapa och redigera försäljningsofferter</span><span class="sxs-lookup"><span data-stu-id="e0b48-103">Create and edit sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0b48-104">I den här proceduren visas hur du kan skapa och uppdatera en försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="e0b48-105">Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e0b48-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="e0b48-106">Skapa en försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-106">Create a sales quotation</span></span>
1. <span data-ttu-id="e0b48-107">Gå till försäljning och marknadsföring > offerter > Alla offerter.</span><span class="sxs-lookup"><span data-stu-id="e0b48-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="e0b48-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e0b48-108">Click New.</span></span>
3. <span data-ttu-id="e0b48-109">Välj Potentiell kund i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="e0b48-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="e0b48-110">Ange eller välj ett värde i fältet Potentiell kund.</span><span class="sxs-lookup"><span data-stu-id="e0b48-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="e0b48-111">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="e0b48-111">Expand the General section.</span></span>
    * <span data-ttu-id="e0b48-112">Eftersom du valde att skapa en offert från området Försäljning och marknadsföring ställs typen automatiskt in på Försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="e0b48-113">Om du vill skapa en offert för ett projekt måste du öppna det från modulen Projekthantering och redovisning.</span><span class="sxs-lookup"><span data-stu-id="e0b48-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="e0b48-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0b48-114">Click OK.</span></span>
    * <span data-ttu-id="e0b48-115">Fälten och åtgärder på offertraderna liknar de på försäljningsorderraderna.</span><span class="sxs-lookup"><span data-stu-id="e0b48-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="e0b48-116">På samma sätt som med försäljningsorder kan offerter skapas för en specifik artikel eller, när artikelnumret är okänt eller inte finns när offerten skapas, också kan offerter skapas för en försäljningskategori.</span><span class="sxs-lookup"><span data-stu-id="e0b48-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="e0b48-117">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="e0b48-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="e0b48-118">Ange ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="e0b48-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="e0b48-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-119">Close the page.</span></span>
10. <span data-ttu-id="e0b48-120">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="e0b48-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e0b48-121">Om det finns giltiga handelsavtal för den markerade artikeln på raden, kommer tillhörande pris och rabatter automatiskt kopieras till offertraden.</span><span class="sxs-lookup"><span data-stu-id="e0b48-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="e0b48-122">Kontrollera att enhetsprisfältet innehåller ett värde och du kan även ange rabattvärden, om du vill.</span><span class="sxs-lookup"><span data-stu-id="e0b48-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="e0b48-123">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e0b48-123">Click Save.</span></span>
12. <span data-ttu-id="e0b48-124">Klicka på Försäljningsoffert i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0b48-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="e0b48-125">Klicka på Summor.</span><span class="sxs-lookup"><span data-stu-id="e0b48-125">Click Totals.</span></span>
14. <span data-ttu-id="e0b48-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0b48-126">Click OK.</span></span>
15. <span data-ttu-id="e0b48-127">Klicka på Försäljningsoffertrad.</span><span class="sxs-lookup"><span data-stu-id="e0b48-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="e0b48-128">Klicka på Priser.</span><span class="sxs-lookup"><span data-stu-id="e0b48-128">Click Prices.</span></span>
    * <span data-ttu-id="e0b48-129">I Kör pris simulering kan du experimentera med att justera det förväntade inkomster eller lönsamheten för din offert utifrån önskat pris per enhet, rabattbelopp, rabatt i procent, totalt belopp, marginal, eller bidrag.</span><span class="sxs-lookup"><span data-stu-id="e0b48-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="e0b48-130">När du är nöjd med mål att tillämpa förslaget till offertraden och dess pris-relaterade fält uppdateras.</span><span class="sxs-lookup"><span data-stu-id="e0b48-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="e0b48-131">Du kan skapa så många prissimuleringar som du vill ha.</span><span class="sxs-lookup"><span data-stu-id="e0b48-131">Y ou can create as many price simulations as you wish.</span></span> <span data-ttu-id="e0b48-132">När du klickar på Nytt, kopieras prisvillkoren från den aktuella offertraden till sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="e0b48-133">Du kan sedan ändra värdena i någon av de prisrelaterade fälten till målfältet.</span><span class="sxs-lookup"><span data-stu-id="e0b48-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="e0b48-134">En ändring i ett av fälten leder till omräkning av alla övriga fält.</span><span class="sxs-lookup"><span data-stu-id="e0b48-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="e0b48-135">För att systemet ska kunna beräkna försäljningsmarginalen och täckningsgraden, måste produktens enhetskostnad vara känd.</span><span class="sxs-lookup"><span data-stu-id="e0b48-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="e0b48-136">Använd fliken Simulerade priser för en detaljerad vy över de ursprungliga priserna, föreslagna ändringarna och deras inverkan på offertsummorna.</span><span class="sxs-lookup"><span data-stu-id="e0b48-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="e0b48-137">Som en allmän regel räknar systemet om och anger ett nytt värde i fältet Enhetspris när en simulering som anger ett nytt belopp används på offertraden.</span><span class="sxs-lookup"><span data-stu-id="e0b48-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="e0b48-138">Om simuleringen baseras på en ny marginal eller ny täckningsgrad, uppdateras bara nettobeloppsfältet, medan enhetspriset är tomt.</span><span class="sxs-lookup"><span data-stu-id="e0b48-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="e0b48-139">I båda fallen raderas eventuella rabatter som användes på offertraden före simuleringen.</span><span class="sxs-lookup"><span data-stu-id="e0b48-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="e0b48-140">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-140">Close the page.</span></span>
18. <span data-ttu-id="e0b48-141">Klicka på Offert i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0b48-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="e0b48-142">Klicka på Skicka offert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-142">Click Send quotation.</span></span>
20. <span data-ttu-id="e0b48-143">Välj Ja i fältet Skriv ut offert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="e0b48-144">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0b48-144">Click OK.</span></span>
    * <span data-ttu-id="e0b48-145">Rapporten kan ta någon minut att skapa.</span><span class="sxs-lookup"><span data-stu-id="e0b48-145">The report may take a minute to generate.</span></span> <span data-ttu-id="e0b48-146">Stäng inte sidan förrän den har skapats.</span><span class="sxs-lookup"><span data-stu-id="e0b48-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="e0b48-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="e0b48-148">Uppdatera en försäljningsoffert.</span><span class="sxs-lookup"><span data-stu-id="e0b48-148">Update a sales quotation</span></span>
1. <span data-ttu-id="e0b48-149">Klicka på Uppföljning i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0b48-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="e0b48-150">Klicka på Konvertera till kund.</span><span class="sxs-lookup"><span data-stu-id="e0b48-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="e0b48-151">Ange ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="e0b48-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="e0b48-152">Klicka på Kontrollera.</span><span class="sxs-lookup"><span data-stu-id="e0b48-152">Click Check.</span></span>
    * <span data-ttu-id="e0b48-153">Se till att det visas ett meddelande om att kontonumret du har angett är ledigt.</span><span class="sxs-lookup"><span data-stu-id="e0b48-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="e0b48-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0b48-154">Click OK.</span></span>
    * <span data-ttu-id="e0b48-155">Systemet har nu skapat ett nytt kundkonto för den potentiella kunden i offerten.</span><span class="sxs-lookup"><span data-stu-id="e0b48-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="e0b48-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-156">Close the page.</span></span>
7. <span data-ttu-id="e0b48-157">Klicka på Uppföljning i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0b48-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="e0b48-158">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="e0b48-158">Click Confirm.</span></span>
9. <span data-ttu-id="e0b48-159">Ange eller välj ett värde i fältet Orsak.</span><span class="sxs-lookup"><span data-stu-id="e0b48-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="e0b48-160">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e0b48-160">Click OK.</span></span>
11. <span data-ttu-id="e0b48-161">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e0b48-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="e0b48-162">Klicka på Försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="e0b48-162">Click Sales orders.</span></span>
13. <span data-ttu-id="e0b48-163">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e0b48-163">Close the page.</span></span>

