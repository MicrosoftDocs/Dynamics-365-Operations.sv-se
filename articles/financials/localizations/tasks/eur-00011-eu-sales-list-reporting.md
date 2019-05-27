---
title: EUR-00011 Konfigurera rapportering av EU-säljlista
description: Den här uppgiften vägleder dig genom en översikt över förutsättningarna som krävs för rapportering av EU-säljlista.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee87abdc276d80123bbbe44a67c667bb0df9acb6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538386"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a><span data-ttu-id="7562d-103">EUR-00011 Konfigurera rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-103">EUR-00011 Set up EU sales list reporting</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7562d-104">Den här uppgiften vägleder dig genom en översikt över förutsättningarna som krävs för rapportering av EU-säljlista.</span><span class="sxs-lookup"><span data-stu-id="7562d-104">This task walks you through an overview of the prerequisites required for EU sales list reporting.</span></span> <span data-ttu-id="7562d-105">Mer information om rapportering av EU-säljlista, inklusive nödvändiga krav, finns i hjälpen till Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7562d-105">For more information about EU Sales list reporting, including required prerequisites, refer to the Dynamics 365 for Finance and Operations Help.</span></span>

<span data-ttu-id="7562d-106">Den här uppgiften gäller för alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="7562d-106">This task applies to all European countries/regions.</span></span> <span data-ttu-id="7562d-107">Guiden skapades med hjälp av demodataföretaget DEMF och därför används Tyskland som exempelursprungsland.</span><span class="sxs-lookup"><span data-stu-id="7562d-107">The guide was created using the demo data company DEMF and consequently Germany as an exemplar domestic country/region.</span></span> <span data-ttu-id="7562d-108">Guiden använder också Portugal som exempel på ett EU-land.</span><span class="sxs-lookup"><span data-stu-id="7562d-108">The guide also uses Portugal as an exemplar EU country/region.</span></span>

<span data-ttu-id="7562d-109">Dessa uppgifter är avsedda för systemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="7562d-109">These tasks are intended for system administrators.</span></span>


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a><span data-ttu-id="7562d-110">Importera konfigurationer för elektronisk rapportering för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-110">Import electronic reporting configurations for EU sales list reporting</span></span>
1. <span data-ttu-id="7562d-111">Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7562d-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7562d-112">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="7562d-112">Click Set active.</span></span>
3. <span data-ttu-id="7562d-113">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="7562d-113">Click Repositories.</span></span>
4. <span data-ttu-id="7562d-114">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="7562d-114">Click Open.</span></span>
5. <span data-ttu-id="7562d-115">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7562d-115">On the Action Pane, click Options.</span></span>
6. <span data-ttu-id="7562d-116">Klicka på Avancerat filter/sortering.</span><span class="sxs-lookup"><span data-stu-id="7562d-116">Click Advanced Filter/Sort.</span></span>
7. <span data-ttu-id="7562d-117">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7562d-117">Click Add.</span></span>
8. <span data-ttu-id="7562d-118">Välj Konfigurationsnamn i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="7562d-118">In the Field field, select 'Configuration name'.</span></span>
9. <span data-ttu-id="7562d-119">Skriv EU-säljlista (DE) i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="7562d-119">In the Criteria field, type 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="7562d-120">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7562d-120">Click OK.</span></span>
11. <span data-ttu-id="7562d-121">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="7562d-121">Click Import.</span></span>
12. <span data-ttu-id="7562d-122">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="7562d-122">Click Yes.</span></span>
13. <span data-ttu-id="7562d-123">Klicka på Alternativ i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7562d-123">On the Action Pane, click Options.</span></span>
14. <span data-ttu-id="7562d-124">Klicka på Avancerat filter/sortering.</span><span class="sxs-lookup"><span data-stu-id="7562d-124">Click Advanced Filter/Sort.</span></span>
15. <span data-ttu-id="7562d-125">Klicka på Återställ.</span><span class="sxs-lookup"><span data-stu-id="7562d-125">Click Reset.</span></span>
16. <span data-ttu-id="7562d-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7562d-126">Click Add.</span></span>
17. <span data-ttu-id="7562d-127">Välj Konfigurationsnamn i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="7562d-127">In the Field field, select 'Configuration name'.</span></span>
18. <span data-ttu-id="7562d-128">Skriv Rapport över EU-försäljningslista efter rader i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="7562d-128">In the Criteria field, type 'EU Sales list by rows report'.</span></span>
19. <span data-ttu-id="7562d-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7562d-129">Click OK.</span></span>
20. <span data-ttu-id="7562d-130">Klicka på Importera.</span><span class="sxs-lookup"><span data-stu-id="7562d-130">Click Import.</span></span>
21. <span data-ttu-id="7562d-131">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="7562d-131">Click Yes.</span></span>

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a><span data-ttu-id="7562d-132">Ställ in momskoder för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-132">Set up sales tax codes for EU sales list reporting</span></span>
1. <span data-ttu-id="7562d-133">Gå till Skatt > Indirekta skatter > Moms > Momskoder.</span><span class="sxs-lookup"><span data-stu-id="7562d-133">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="7562d-134">Använd snabbfiltret för att filtrera på fältet Moms med värdet VAT19.</span><span class="sxs-lookup"><span data-stu-id="7562d-134">Use the Quick Filter to filter on the Sales tax code field with a value of 'VAT19'.</span></span>
3. <span data-ttu-id="7562d-135">Expandera avsnittet Rapportinställningar.</span><span class="sxs-lookup"><span data-stu-id="7562d-135">Expand the Report setup section.</span></span>
    * <span data-ttu-id="7562d-136">Kontrollera att Exkluderad är inställt på Nej.</span><span class="sxs-lookup"><span data-stu-id="7562d-136">Verify that the Excluded selection is set to No.</span></span>  
    * <span data-ttu-id="7562d-137">Du kan behöva låsa upp uppgiftsguiden för att ändra den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="7562d-137">You may need to unlock the task guide to change this setting.</span></span>  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="7562d-138">Ställ in momsgrupper för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-138">Set up sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="7562d-139">Gå till Skatt > Indirekta skatter > Moms > Momsgrupper.</span><span class="sxs-lookup"><span data-stu-id="7562d-139">Go to Tax > Indirect taxes > Sales tax > Sales tax groups.</span></span>
2. <span data-ttu-id="7562d-140">Använd snabbfiltret för att filtrera på fältet Momsgrupp med värdet AR-DOM.</span><span class="sxs-lookup"><span data-stu-id="7562d-140">Use the Quick Filter to filter on the Sales tax group field with a value of 'AR-DOM'.</span></span>
3. <span data-ttu-id="7562d-141">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="7562d-141">Click Edit.</span></span>
4. <span data-ttu-id="7562d-142">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="7562d-142">Expand the Setup section.</span></span>
5. <span data-ttu-id="7562d-143">Välj den första raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7562d-143">In the list, select the first row.</span></span>
6. <span data-ttu-id="7562d-144">Markera kryssrutan Momsbefrielse.</span><span class="sxs-lookup"><span data-stu-id="7562d-144">Select the Exempt check box.</span></span>
7. <span data-ttu-id="7562d-145">Välj den andra raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7562d-145">In the list, select the second row.</span></span>
8. <span data-ttu-id="7562d-146">Markera kryssrutan Momsbefrielse.</span><span class="sxs-lookup"><span data-stu-id="7562d-146">Select the Exempt check box.</span></span>
9. <span data-ttu-id="7562d-147">Välj den tredje raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7562d-147">In the list, select the third row.</span></span>
10. <span data-ttu-id="7562d-148">Markera kryssrutan Momsbefrielse.</span><span class="sxs-lookup"><span data-stu-id="7562d-148">Select the Exempt check box.</span></span>

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a><span data-ttu-id="7562d-149">Ställ in artikelmomsgrupper för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-149">Set up item sales tax groups for EU sales list reporting</span></span>
1. <span data-ttu-id="7562d-150">Gå till Skatt > Indirekta skatter > Moms > Artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="7562d-150">Go to Tax > Indirect taxes > Sales tax > Item sales tax groups.</span></span>
2. <span data-ttu-id="7562d-151">Använd snabbfiltret för att filtrera på fältet Artikelmomsgrupp med värdet FULL.</span><span class="sxs-lookup"><span data-stu-id="7562d-151">Use the Quick Filter to filter on the Item sales tax group field with a value of 'FULL '.</span></span>
    * <span data-ttu-id="7562d-152">Kontrollera att Rapporteringstyp är inställt på Artikel.</span><span class="sxs-lookup"><span data-stu-id="7562d-152">Verify that the Reporting type selection is set to 'Item'.</span></span>  
    * <span data-ttu-id="7562d-153">Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="7562d-153">You may need to unlock the task guide to change the value in this field.</span></span>  
3. <span data-ttu-id="7562d-154">Använd snabbfiltret för att filtrera på fältet Artikelmomsgrupp med värdet RED.</span><span class="sxs-lookup"><span data-stu-id="7562d-154">Use the Quick Filter to filter on the Item sales tax group field with a value of 'RED '.</span></span>
    * <span data-ttu-id="7562d-155">Kontrollera att Rapporteringstyp är inställt på Tjänst.</span><span class="sxs-lookup"><span data-stu-id="7562d-155">Verify that the Reporting type selection is set to 'Service'.</span></span>  
    * <span data-ttu-id="7562d-156">Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="7562d-156">You may need to unlock the task guide to change the value in this field.</span></span>  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a><span data-ttu-id="7562d-157">Ställ in land-/regionsparametrar för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-157">Set up country/region parameters for EU sales list reporting</span></span>
1. <span data-ttu-id="7562d-158">Gå till Moms > Inställningar > Moms > Parametrar för land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-158">Go to Tax > Setup > Sales tax > Country/region parameters.</span></span>
2. <span data-ttu-id="7562d-159">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7562d-159">Click New.</span></span>
3. <span data-ttu-id="7562d-160">Skriv PRT i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-160">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="7562d-161">Skriv PT i fältet Moms.</span><span class="sxs-lookup"><span data-stu-id="7562d-161">In the Sales tax field, type 'PT'.</span></span>

## <a name="create-tax-exempt-numbers"></a><span data-ttu-id="7562d-162">Skapa momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="7562d-162">Create tax exempt numbers</span></span>
1. <span data-ttu-id="7562d-163">Gå till Moms > Inställningar > Moms > Momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="7562d-163">Go to Tax > Setup > Sales tax > Tax exempt numbers.</span></span>
2. <span data-ttu-id="7562d-164">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7562d-164">Click New.</span></span>
3. <span data-ttu-id="7562d-165">Skriv PRT i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-165">In the Country/region field, type 'PRT'.</span></span>
4. <span data-ttu-id="7562d-166">Skriv PT12345 i fältet Momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="7562d-166">In the Tax exempt number field, type 'PT12345'.</span></span>

## <a name="set-up-eu-sales-list-reporting-parameters"></a><span data-ttu-id="7562d-167">Ställ in parametrar för rapportering av EU-säljlista</span><span class="sxs-lookup"><span data-stu-id="7562d-167">Set up EU sales list reporting parameters</span></span>
1. <span data-ttu-id="7562d-168">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="7562d-168">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="7562d-169">Klicka på fliken Lista över försäljning inom EU.</span><span class="sxs-lookup"><span data-stu-id="7562d-169">Click the EU sales list tab.</span></span>
3. <span data-ttu-id="7562d-170">Välj Ja i fältet Överför inköp.</span><span class="sxs-lookup"><span data-stu-id="7562d-170">Select Yes in the Transfer purchases field.</span></span>
4. <span data-ttu-id="7562d-171">Expandera avsnittet Avrundningsregler.</span><span class="sxs-lookup"><span data-stu-id="7562d-171">Expand the Rounding rules section.</span></span>
5. <span data-ttu-id="7562d-172">Ange Avrundningsregel till 0,1.</span><span class="sxs-lookup"><span data-stu-id="7562d-172">Set Rounding rule to '0.1'.</span></span>
6. <span data-ttu-id="7562d-173">Välj Ja i fältet Använd lägsta värde.</span><span class="sxs-lookup"><span data-stu-id="7562d-173">Select Yes in the Use minimum value field.</span></span>
7. <span data-ttu-id="7562d-174">Ange 2 i fältet Antal decimaler.</span><span class="sxs-lookup"><span data-stu-id="7562d-174">In the Number of decimals field, enter '2'.</span></span>
8. <span data-ttu-id="7562d-175">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7562d-175">Expand the Electronic reporting section.</span></span>
9. <span data-ttu-id="7562d-176">Välj EU-försäljningslista (DE) i fältet Mappning av filformat.</span><span class="sxs-lookup"><span data-stu-id="7562d-176">In the File format mapping field, select 'EU Sales list (DE)'.</span></span>
10. <span data-ttu-id="7562d-177">I fältet Mappning av rapportformat väljer du Rapport över EU-försäljningslista.</span><span class="sxs-lookup"><span data-stu-id="7562d-177">In the Report format mapping field, select 'EU Sales list by rows report'.</span></span>
11. <span data-ttu-id="7562d-178">Klicka på fliken Egenskaper för land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-178">Click the Country/region properties tab.</span></span>
    * <span data-ttu-id="7562d-179">Kontrollera att fältet Lands-/regiontyp är inställt på Inrikes för land/region DEU.</span><span class="sxs-lookup"><span data-stu-id="7562d-179">Verify that the Country/region type field is set to 'Domestic' for Country/region DEU.</span></span>  
    * <span data-ttu-id="7562d-180">Du kan behöva låsa upp uppgiftsguiden för att ändra värdet i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="7562d-180">You may need to unlock the task guide to change the value in this field.</span></span>  
12. <span data-ttu-id="7562d-181">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7562d-181">Click New.</span></span>
13. <span data-ttu-id="7562d-182">Skriv PRT i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-182">In the Country/region field, type 'PRT'.</span></span>
14. <span data-ttu-id="7562d-183">Skriv PT i fältet Intrastat-kod.</span><span class="sxs-lookup"><span data-stu-id="7562d-183">In the Intrastat code field, type 'PT'.</span></span>
15. <span data-ttu-id="7562d-184">Välj EU i fältet Lands-/regiontyp.</span><span class="sxs-lookup"><span data-stu-id="7562d-184">In the Country/region type field, select 'EU'.</span></span>
16. <span data-ttu-id="7562d-185">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="7562d-185">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="7562d-186">Kontrollera att en nummerseriekod ställts in för referensen Lista över försäljning inom EU.</span><span class="sxs-lookup"><span data-stu-id="7562d-186">Verify that a Number sequence code is specified for the Reference 'EU sales list'.</span></span>  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a><span data-ttu-id="7562d-187">Skapa en kund för rapportering av EU-säljlista för demonstrationsändamål</span><span class="sxs-lookup"><span data-stu-id="7562d-187">Create a customer for EU sales list reporting demo purposes</span></span>
1. <span data-ttu-id="7562d-188">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="7562d-188">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="7562d-189">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7562d-189">Click New.</span></span>
3. <span data-ttu-id="7562d-190">Skriv PRT-001 i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="7562d-190">In the Customer account field, type 'PRT-001'.</span></span>
4. <span data-ttu-id="7562d-191">Skriv En kund från Portugal i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7562d-191">In the Name field, type 'A customer from Portugal'.</span></span>
5. <span data-ttu-id="7562d-192">Välj 10 i fältet Kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="7562d-192">In the Customer group field, select '10'.</span></span>
6. <span data-ttu-id="7562d-193">Välj AR-DOM i gruppen Momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7562d-193">In the Sales tax group field, select 'AR-DOM'.</span></span>
7. <span data-ttu-id="7562d-194">Välj PT12345 i fältet Momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="7562d-194">In the Tax exempt number field, select 'PT12345'.</span></span>
8. <span data-ttu-id="7562d-195">Skriv PRT i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="7562d-195">In the Country/region field, type 'PRT'.</span></span>
9. <span data-ttu-id="7562d-196">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7562d-196">Click Save.</span></span>

