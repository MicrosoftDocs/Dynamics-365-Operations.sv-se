---
title: Överföra transaktioner till Intrastat
description: I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategory, UnitOfMeasureLookup, ProcCategoryAddCommodityCode, EcoResProductDetailsExtended, IntrastatCommodityLookup, IntrastatTransactionCode, IntrastatParameters, DeliveryMode, MarkupTable, SalesTableListPage, SalesCreateOrder, SalesTable, MarkupTrans, SalesEditLines,  Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13cc9dc2119ad3dc85d580e92edee7bb9ef2075c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559327"
---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="8bf52-103">Överföra transaktioner till Intrastat</span><span class="sxs-lookup"><span data-stu-id="8bf52-103">Transfer transactions to the Intrastat</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8bf52-104">I den här proceduren går du igenom hur du ställer in Intrastat-parametrar och överför transaktioner till Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8bf52-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="8bf52-105">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="8bf52-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="8bf52-106">Skapa ny och uppdatera befintlig artikelkod</span><span class="sxs-lookup"><span data-stu-id="8bf52-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="8bf52-107">Gå till Produktinformationshantering > Inställningar > Kategorier och attribut > Kategorihierarkier.</span><span class="sxs-lookup"><span data-stu-id="8bf52-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="8bf52-108">I listan markerar du posten "Intrastat-artikelkoder".</span><span class="sxs-lookup"><span data-stu-id="8bf52-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="8bf52-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8bf52-110">Välj en "post" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="8bf52-111">Välj t.ex. ”Intrastat\högtalare”.</span><span class="sxs-lookup"><span data-stu-id="8bf52-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="8bf52-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8bf52-112">Click Edit.</span></span>
6. <span data-ttu-id="8bf52-113">Visa avsnittet Utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="8bf52-114">Ange eller välj ett värde i fältet Ytterligare enheter.</span><span class="sxs-lookup"><span data-stu-id="8bf52-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-115">Välj t.ex. "st".</span><span class="sxs-lookup"><span data-stu-id="8bf52-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="8bf52-116">Välj Ja i fältet Vikten är inte tillämplig.</span><span class="sxs-lookup"><span data-stu-id="8bf52-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="8bf52-117">Välj "Intrastat" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="8bf52-118">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-118">Click New category node.</span></span>
11. <span data-ttu-id="8bf52-119">Ange artikelns namn i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8bf52-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="8bf52-120">Skriv till exempel ”annan artikel”.</span><span class="sxs-lookup"><span data-stu-id="8bf52-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="8bf52-121">Ange artikelkoden i fältet för Kod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="8bf52-122">Skriv till exempel "995 00 00".</span><span class="sxs-lookup"><span data-stu-id="8bf52-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="8bf52-123">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="8bf52-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="8bf52-124">Skriv till exempel "Annat".</span><span class="sxs-lookup"><span data-stu-id="8bf52-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="8bf52-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8bf52-125">Click Save.</span></span>
15. <span data-ttu-id="8bf52-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="8bf52-127">Tilldela artikelkod till produkthierarkin och frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="8bf52-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="8bf52-128">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="8bf52-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8bf52-129">Filtrera till exempel i fältet Namn med värdet "försäljning".</span><span class="sxs-lookup"><span data-stu-id="8bf52-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="8bf52-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="8bf52-131">Expandera "en kategorinod" i trädet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="8bf52-132">Visa t.ex. ”försäljninghierarki\hemmaljud".</span><span class="sxs-lookup"><span data-stu-id="8bf52-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="8bf52-133">Välj kategorin som artikelkoden ska tilldelas i trädet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="8bf52-134">Välj t.ex. ”försäljninghierarki\hemmaljud\högtalare".</span><span class="sxs-lookup"><span data-stu-id="8bf52-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="8bf52-135">Expandera avsnittet Artikelkoder.</span><span class="sxs-lookup"><span data-stu-id="8bf52-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="8bf52-136">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8bf52-136">Click Add.</span></span>
7. <span data-ttu-id="8bf52-137">Välj "Intrastat" i fältet Välj hierarki.</span><span class="sxs-lookup"><span data-stu-id="8bf52-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="8bf52-138">Hitta och markera artikelkod i listan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="8bf52-139">Välj t.ex. ”920 20 34 högtalare”.</span><span class="sxs-lookup"><span data-stu-id="8bf52-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="8bf52-140">Klicka på SelectCodes.</span><span class="sxs-lookup"><span data-stu-id="8bf52-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="8bf52-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-141">Click OK.</span></span>
11. <span data-ttu-id="8bf52-142">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="8bf52-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="8bf52-143">Välj den frisläppta produkten som ska tilldelas artikelkoden i listan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="8bf52-144">Välj t.ex. "D0001".</span><span class="sxs-lookup"><span data-stu-id="8bf52-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="8bf52-145">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8bf52-145">Click Edit.</span></span>
14. <span data-ttu-id="8bf52-146">Visa avsnittet Utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="8bf52-147">Ange artikelkoden i fältet för Artikel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="8bf52-148">Välj t.ex. värdet ”920 20 34 högtalare”.</span><span class="sxs-lookup"><span data-stu-id="8bf52-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="8bf52-149">Välj en siffra i fältet Avgiftsprocent.</span><span class="sxs-lookup"><span data-stu-id="8bf52-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="8bf52-150">Välj t.ex. "3".</span><span class="sxs-lookup"><span data-stu-id="8bf52-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="8bf52-151">Ange eller välj ett land eller region i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="8bf52-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="8bf52-152">Välj till exempel "AUT".</span><span class="sxs-lookup"><span data-stu-id="8bf52-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="8bf52-153">Visa avsnittet Hantera lager.</span><span class="sxs-lookup"><span data-stu-id="8bf52-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="8bf52-154">Ange en vikt i kg i fältet Nettovikt.</span><span class="sxs-lookup"><span data-stu-id="8bf52-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="8bf52-155">Välj t.ex. "2,5".</span><span class="sxs-lookup"><span data-stu-id="8bf52-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="8bf52-156">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8bf52-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="8bf52-157">Ställ in Intrastat-transaktionkoder och utrikeshandelparametrar</span><span class="sxs-lookup"><span data-stu-id="8bf52-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="8bf52-158">Gå till Moms > Inställningar > Utländsk handel > Transaktionskoder</span><span class="sxs-lookup"><span data-stu-id="8bf52-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="8bf52-159">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8bf52-159">Click New.</span></span>
3. <span data-ttu-id="8bf52-160">Skriv ett värde i fältet Transaktionskod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="8bf52-161">Ange t.ex. "21 "för den transaktionskod som används som retur.</span><span class="sxs-lookup"><span data-stu-id="8bf52-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="8bf52-162">Ange namnet på transaktionskoden i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="8bf52-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="8bf52-163">Skriv till exempel "Retur".</span><span class="sxs-lookup"><span data-stu-id="8bf52-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="8bf52-164">Välj ett alternativ i fältet Statistiskt belopp.</span><span class="sxs-lookup"><span data-stu-id="8bf52-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="8bf52-165">Välj t.ex .”Tom” som anger att det statistiska värdet som ska rapporteras för transaktioner med transaktionskoden "21 "är alltid noll.</span><span class="sxs-lookup"><span data-stu-id="8bf52-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="8bf52-166">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="8bf52-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="8bf52-167">Ange eller välj ett värde i fältet Transaktionskod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-168">Välj till exempel "11".</span><span class="sxs-lookup"><span data-stu-id="8bf52-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="8bf52-169">Ange eller välj ett värde i fältet Kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="8bf52-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-170">Det här värdet även identifiera den fysiska returen.</span><span class="sxs-lookup"><span data-stu-id="8bf52-170">This value also identifies the physical return.</span></span> <span data-ttu-id="8bf52-171">Kreditfakturan för fysisk retur ska överföras till Intrastat-journalen med motsatt riktning.</span><span class="sxs-lookup"><span data-stu-id="8bf52-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="8bf52-172">Till exempel överförs införselreturen som utskick.</span><span class="sxs-lookup"><span data-stu-id="8bf52-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="8bf52-173">Annars betraktas kreditfakturan som en korrigering och överförs med samma riktning och motsatt tecken.</span><span class="sxs-lookup"><span data-stu-id="8bf52-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="8bf52-174">Till exempel överförs korrigeringen av införsel som en införsel med negativt belopp, och den aktiva flaggan anges” till ”Korrigering".</span><span class="sxs-lookup"><span data-stu-id="8bf52-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="8bf52-175">Expandera alternativet Överför.</span><span class="sxs-lookup"><span data-stu-id="8bf52-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="8bf52-176">Välj Ja i fältet Artiklar med artikelkod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="8bf52-177">Markera det här alternativet om du endast vill överföra transaktioner med en tilldelad artikelkod.</span><span class="sxs-lookup"><span data-stu-id="8bf52-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="8bf52-178">Transaktioner utan en artikelkod kommer inte att överföras till Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8bf52-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="8bf52-179">Välj ett alternativ i fältet Överför när kriteriet är uppfyllt för.</span><span class="sxs-lookup"><span data-stu-id="8bf52-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="8bf52-180">Välj t.ex. ”Någon av de valda”,</span><span class="sxs-lookup"><span data-stu-id="8bf52-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="8bf52-181">Expandera avsnittet Artikelkodhierarki.</span><span class="sxs-lookup"><span data-stu-id="8bf52-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="8bf52-182">Klicka på fliken Egenskaper för land/region.</span><span class="sxs-lookup"><span data-stu-id="8bf52-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="8bf52-183">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8bf52-183">Click New.</span></span>
15. <span data-ttu-id="8bf52-184">Ange eller välj ett värde i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="8bf52-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-185">Välj till exempel värdet "FRA".</span><span class="sxs-lookup"><span data-stu-id="8bf52-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="8bf52-186">Ange den ISO-koden för landet i Intrastat-kodfältet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="8bf52-187">Skriv till exempel "FR".</span><span class="sxs-lookup"><span data-stu-id="8bf52-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="8bf52-188">Välj EU i fältet Lands-/regiontyp.</span><span class="sxs-lookup"><span data-stu-id="8bf52-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="8bf52-189">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="8bf52-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="8bf52-190">Ställ in leveranssätt och regler för att inkludera avgifter i Intrastat</span><span class="sxs-lookup"><span data-stu-id="8bf52-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="8bf52-191">Gå till Försäljning och marknadsföring > Inställningar > Distribution > Leveransmetod</span><span class="sxs-lookup"><span data-stu-id="8bf52-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="8bf52-192">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8bf52-193">Välj till exempel "20-Air".</span><span class="sxs-lookup"><span data-stu-id="8bf52-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="8bf52-194">Visa avsnittet Utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="8bf52-195">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8bf52-195">Click Edit.</span></span>
5. <span data-ttu-id="8bf52-196">Ange eller välj ett värde i fältet Transport.</span><span class="sxs-lookup"><span data-stu-id="8bf52-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-197">Välj till exempel "02".</span><span class="sxs-lookup"><span data-stu-id="8bf52-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="8bf52-198">Gå till Kundreskontra > Ställa in avgifter > Avgiftskod</span><span class="sxs-lookup"><span data-stu-id="8bf52-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="8bf52-199">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="8bf52-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8bf52-200">Filtrera till exempel i fältet Kod för avgifter med värdet "frakt".</span><span class="sxs-lookup"><span data-stu-id="8bf52-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="8bf52-201">Visa avsnittet Utländsk handel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="8bf52-202">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8bf52-202">Click Edit.</span></span>
10. <span data-ttu-id="8bf52-203">Välj Ja i fältet Intrastat-fakturavärde.</span><span class="sxs-lookup"><span data-stu-id="8bf52-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="8bf52-204">Beloppet kommer att överföras till fältet Fakturaavgifter och kommer att summeras med det överfördabeloppet i fältet Fakturabelopp.</span><span class="sxs-lookup"><span data-stu-id="8bf52-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="8bf52-205">Välj Ja i fältet Intrastat statistiskt värde, om beloppet av ändringar måste överföras till fältet Statistiska avgifter och summerats med Statistiskt belopp.</span><span class="sxs-lookup"><span data-stu-id="8bf52-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="8bf52-206">Sälja produkter för EU-kunder</span><span class="sxs-lookup"><span data-stu-id="8bf52-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="8bf52-207">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="8bf52-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="8bf52-208">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8bf52-208">Click New.</span></span>
3. <span data-ttu-id="8bf52-209">Markera en EU-kund i fältet Kundkonto</span><span class="sxs-lookup"><span data-stu-id="8bf52-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="8bf52-210">Markera till exempel ”DE-012 Litware Butik”.</span><span class="sxs-lookup"><span data-stu-id="8bf52-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="8bf52-211">Expandera avsnittet Leverans.</span><span class="sxs-lookup"><span data-stu-id="8bf52-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="8bf52-212">Ange eller välj ett värde i fältet Leveranssätt.</span><span class="sxs-lookup"><span data-stu-id="8bf52-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-213">Välj till exempel "20-Air".</span><span class="sxs-lookup"><span data-stu-id="8bf52-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="8bf52-214">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-214">Click OK.</span></span>
7. <span data-ttu-id="8bf52-215">Placera markören på den första raden av försäljningsorderrader.</span><span class="sxs-lookup"><span data-stu-id="8bf52-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="8bf52-216">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8bf52-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-217">Välj till exempel "D001".</span><span class="sxs-lookup"><span data-stu-id="8bf52-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="8bf52-218">Expandera avsnittet Radinformation.</span><span class="sxs-lookup"><span data-stu-id="8bf52-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="8bf52-219">Klicka på fliekn Utrikeshandel.</span><span class="sxs-lookup"><span data-stu-id="8bf52-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="8bf52-220">Transporten fylls automatiskt i från det valda leveranssättet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="8bf52-221">Ange eller välj ett värde i fältet Port.</span><span class="sxs-lookup"><span data-stu-id="8bf52-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="8bf52-222">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="8bf52-222">Click Financials.</span></span>
    * <span data-ttu-id="8bf52-223">I enlighet med inställningarna kommer detta belopp att inkluderas i Intrastat-fakturavärdet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="8bf52-224">Klicka på Underhåll avgifter.</span><span class="sxs-lookup"><span data-stu-id="8bf52-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="8bf52-225">Ange eller välj ett värde i fältet Avgifter.</span><span class="sxs-lookup"><span data-stu-id="8bf52-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-226">Välj till exempel "FRAKT".</span><span class="sxs-lookup"><span data-stu-id="8bf52-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="8bf52-227">Markera kryssrutan Behåll.</span><span class="sxs-lookup"><span data-stu-id="8bf52-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="8bf52-228">I fältet Avgiftsvärde, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="8bf52-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="8bf52-229">Ange t.ex. "10".</span><span class="sxs-lookup"><span data-stu-id="8bf52-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="8bf52-230">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8bf52-230">Click Save.</span></span>
18. <span data-ttu-id="8bf52-231">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-231">Close the page.</span></span>
19. <span data-ttu-id="8bf52-232">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8bf52-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="8bf52-233">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="8bf52-233">Click Invoice.</span></span>
21. <span data-ttu-id="8bf52-234">Expandera avsnittet Parametrar.</span><span class="sxs-lookup"><span data-stu-id="8bf52-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="8bf52-235">Välj Alla i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="8bf52-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="8bf52-236">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="8bf52-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="8bf52-237">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="8bf52-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="8bf52-238">Ange till exempel "2015-01-31".</span><span class="sxs-lookup"><span data-stu-id="8bf52-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="8bf52-239">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-239">Click OK.</span></span>
26. <span data-ttu-id="8bf52-240">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-240">Click OK.</span></span>
27. <span data-ttu-id="8bf52-241">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8bf52-241">Close the page.</span></span>
28. <span data-ttu-id="8bf52-242">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8bf52-242">Click New.</span></span>
29. <span data-ttu-id="8bf52-243">Markera en EU-kund i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="8bf52-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="8bf52-244">Välj till exempel "DE-013 Trey Wholesales"</span><span class="sxs-lookup"><span data-stu-id="8bf52-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="8bf52-245">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-245">Click OK.</span></span>
31. <span data-ttu-id="8bf52-246">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8bf52-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="8bf52-247">Välj till exempel "D0001".</span><span class="sxs-lookup"><span data-stu-id="8bf52-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="8bf52-248">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8bf52-248">Click Save.</span></span>
33. <span data-ttu-id="8bf52-249">Klicka på Faktura.</span><span class="sxs-lookup"><span data-stu-id="8bf52-249">Click Invoice.</span></span>
34. <span data-ttu-id="8bf52-250">Ange ett datum i fältet Fakturadatum.</span><span class="sxs-lookup"><span data-stu-id="8bf52-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="8bf52-251">Ange till exempel datumet "2015-01-31".</span><span class="sxs-lookup"><span data-stu-id="8bf52-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="8bf52-252">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-252">Click OK.</span></span>
36. <span data-ttu-id="8bf52-253">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="8bf52-254">Överföra transaktioner till Intrastat</span><span class="sxs-lookup"><span data-stu-id="8bf52-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="8bf52-255">Gå till Moms > Deklarationer > Utländsk handel > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="8bf52-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="8bf52-256">Klicka på Överför.</span><span class="sxs-lookup"><span data-stu-id="8bf52-256">Click Transfer.</span></span>
3. <span data-ttu-id="8bf52-257">Välj Ja i fältet Kundfaktura.</span><span class="sxs-lookup"><span data-stu-id="8bf52-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="8bf52-258">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="8bf52-258">Click Filter.</span></span>
5. <span data-ttu-id="8bf52-259">Markera vald rad med datum.</span><span class="sxs-lookup"><span data-stu-id="8bf52-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="8bf52-260">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="8bf52-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="8bf52-261">Ange filtret för perioden januari 2015 (det exakta värdet beror på ditt datumformat), till exempel: 1/1/2015..1/31/2015</span><span class="sxs-lookup"><span data-stu-id="8bf52-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="8bf52-262">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-262">Click OK.</span></span>
8. <span data-ttu-id="8bf52-263">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8bf52-263">Click OK.</span></span>
9. <span data-ttu-id="8bf52-264">Hitta och markera den överförda posten.</span><span class="sxs-lookup"><span data-stu-id="8bf52-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="8bf52-265">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8bf52-265">Click the General tab.</span></span>
    * <span data-ttu-id="8bf52-266">Granska överförda data, inklusive destinationens/utskickets land/region, ursprungsland, vikt, kvantitet, kvantitet i ytterligare enheter, vara, transaktionskod, fakturabelopp och statistiska belopp.</span><span class="sxs-lookup"><span data-stu-id="8bf52-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="8bf52-267">Du kan ändra data om det behövs.</span><span class="sxs-lookup"><span data-stu-id="8bf52-267">You can modify data if necessary.</span></span>  

