--- 
title: Generera en EU Intrastat-deklaration
description: "I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: be094425de50e3919e97e9f2baf636c498768a47
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="generate-an-eu-intrastat-declaration"></a><span data-ttu-id="d76a7-103">Generera en EU Intrastat-deklaration</span><span class="sxs-lookup"><span data-stu-id="d76a7-103">Generate an EU Intrastat declaration</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d76a7-104">I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format.</span><span class="sxs-lookup"><span data-stu-id="d76a7-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="d76a7-105">Innan du kan slutföra proceduren, måste du överföra transaktioner till Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d76a7-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="d76a7-106">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="d76a7-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="d76a7-107">Importera konfigurationer med inställningar</span><span class="sxs-lookup"><span data-stu-id="d76a7-107">Import configurations with settings</span></span>
1. <span data-ttu-id="d76a7-108">Gå till Arbetsytor > Elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="d76a7-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="d76a7-109">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="d76a7-109">Click Set active.</span></span>
3. <span data-ttu-id="d76a7-110">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="d76a7-110">Click Repositories.</span></span>
4. <span data-ttu-id="d76a7-111">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="d76a7-111">Click Open.</span></span>
5. <span data-ttu-id="d76a7-112">Öppna kolumnfiltret för Konfigurationsnamn.</span><span class="sxs-lookup"><span data-stu-id="d76a7-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="d76a7-113">Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”DIntrastat (DE)", med hjälp av filteroperatorn ”börjar med”.</span><span class="sxs-lookup"><span data-stu-id="d76a7-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="d76a7-114">Du bör välja konfigurationnamnet som gäller för din juridiska persons land.</span><span class="sxs-lookup"><span data-stu-id="d76a7-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="d76a7-115">I den här proceduren används den tyska juridiska personen (till exempel DEMF), därför ska ”Intrastat (DE)” väljas.</span><span class="sxs-lookup"><span data-stu-id="d76a7-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="d76a7-116">Klicka på Importera och sedan på Ja.</span><span class="sxs-lookup"><span data-stu-id="d76a7-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="d76a7-117">Öppna kolumnfiltret för Konfigurationsnamn.</span><span class="sxs-lookup"><span data-stu-id="d76a7-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="d76a7-118">Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”intrastat-rapport", med hjälp av filteroperatorn ”börjar med”.</span><span class="sxs-lookup"><span data-stu-id="d76a7-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="d76a7-119">Klicka på Importera och sedan på Ja.</span><span class="sxs-lookup"><span data-stu-id="d76a7-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="d76a7-120">Konfigurera utländska handelsparametrar</span><span class="sxs-lookup"><span data-stu-id="d76a7-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="d76a7-121">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="d76a7-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="d76a7-122">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="d76a7-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="d76a7-123">Ange eller välj ett värde Intrastat (DE) i fältet Mappning av filformat.</span><span class="sxs-lookup"><span data-stu-id="d76a7-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="d76a7-124">Ange eller välj ett värde Intrastat-rapport i fältet Mappning av rapportformat.</span><span class="sxs-lookup"><span data-stu-id="d76a7-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="d76a7-125">Expandera avsnittet Avrundningsregler.</span><span class="sxs-lookup"><span data-stu-id="d76a7-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="d76a7-126">Du bör ställa in avrundningregler som kan användas i ditt land/din region för Intrastat-rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="d76a7-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="d76a7-127">Ange ett tal i fältet Avrundningsregel.</span><span class="sxs-lookup"><span data-stu-id="d76a7-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="d76a7-128">Ange avrundningsprecision, till exempel ”0,01 ".</span><span class="sxs-lookup"><span data-stu-id="d76a7-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="d76a7-129">Ange ett nummer i fältet Antal decimaler för belopp.</span><span class="sxs-lookup"><span data-stu-id="d76a7-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="d76a7-130">Ange t.ex. "2".</span><span class="sxs-lookup"><span data-stu-id="d76a7-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="d76a7-131">Markera ett alternativ i fältet Avrundning under 1 kg.</span><span class="sxs-lookup"><span data-stu-id="d76a7-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="d76a7-132">Välj t.ex. ”Avrundning till 1 kg”.</span><span class="sxs-lookup"><span data-stu-id="d76a7-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="d76a7-133">Ange ett tal i fältet Avrundningsregel.</span><span class="sxs-lookup"><span data-stu-id="d76a7-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="d76a7-134">Ange t.ex. "1" för avrundning av vikt till heltal.</span><span class="sxs-lookup"><span data-stu-id="d76a7-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="d76a7-135">Visa avsnittet Minimigräns.</span><span class="sxs-lookup"><span data-stu-id="d76a7-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="d76a7-136">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="d76a7-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="d76a7-137">Ange ”10” som minsta vikt.</span><span class="sxs-lookup"><span data-stu-id="d76a7-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="d76a7-138">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="d76a7-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="d76a7-139">Ange ”200” som minsta belopp.</span><span class="sxs-lookup"><span data-stu-id="d76a7-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="d76a7-140">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="d76a7-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="d76a7-141">Ställ in komprimering av Intrastat</span><span class="sxs-lookup"><span data-stu-id="d76a7-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="d76a7-142">Gå till Moms > Inställningar > Utländsk handel > Komprimering av Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d76a7-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="d76a7-143">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="d76a7-143">Click Remove.</span></span>
3. <span data-ttu-id="d76a7-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d76a7-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d76a7-145">Du kan till exempel välja Artikel i avsnittet Tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d76a7-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="d76a7-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d76a7-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="d76a7-147">Generera en Intrastat-deklaration</span><span class="sxs-lookup"><span data-stu-id="d76a7-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="d76a7-148">Gå till Moms > Deklarationer > Utländsk handel > Intrastat</span><span class="sxs-lookup"><span data-stu-id="d76a7-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="d76a7-149">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-149">Click Validate.</span></span>
    * <span data-ttu-id="d76a7-150">Valideringen görs i enlighet med fältet Kontrollera inställningar på sidan Utrikeshandelparameter.</span><span class="sxs-lookup"><span data-stu-id="d76a7-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="d76a7-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d76a7-151">Click OK.</span></span>
4. <span data-ttu-id="d76a7-152">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-152">Click Update.</span></span>
5. <span data-ttu-id="d76a7-153">Klicka på Minimigräns.</span><span class="sxs-lookup"><span data-stu-id="d76a7-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="d76a7-154">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="d76a7-155">Ange t.ex. januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="d76a7-156">Välj Ja i fältet Komprimera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="d76a7-157">Ange ett datum i fältet Slutdatum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="d76a7-158">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="d76a7-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d76a7-159">Click OK.</span></span>
10. <span data-ttu-id="d76a7-160">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-160">Click Update.</span></span>
11. <span data-ttu-id="d76a7-161">Klicka på Komprimera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-161">Click Compress.</span></span>
    * <span data-ttu-id="d76a7-162">Denna komprimering sker enligt hur du ställer in komprimeringen av Intrastat-inställningar.</span><span class="sxs-lookup"><span data-stu-id="d76a7-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="d76a7-163">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="d76a7-164">Ange t.ex. januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="d76a7-165">Ange ett datum i fältet Slutdatum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="d76a7-166">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="d76a7-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d76a7-167">Click OK.</span></span>
15. <span data-ttu-id="d76a7-168">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="d76a7-168">Click Update.</span></span>
16. <span data-ttu-id="d76a7-169">Klicka på Generera om löpnummer.</span><span class="sxs-lookup"><span data-stu-id="d76a7-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="d76a7-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d76a7-170">Click OK.</span></span>
18. <span data-ttu-id="d76a7-171">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="d76a7-171">Click Output.</span></span>
19. <span data-ttu-id="d76a7-172">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="d76a7-172">Click Report.</span></span>
20. <span data-ttu-id="d76a7-173">Ange det första datumet i rapporteringperioden i fältet Från-datum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="d76a7-174">Ange t.ex. datum till 1 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="d76a7-175">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="d76a7-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="d76a7-176">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="d76a7-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="d76a7-177">Välj Ja i fältet Generera fil.</span><span class="sxs-lookup"><span data-stu-id="d76a7-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="d76a7-178">Ange ett värde i fältet Filnamn.</span><span class="sxs-lookup"><span data-stu-id="d76a7-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="d76a7-179">Välj Ja i fältet Generera rapport.</span><span class="sxs-lookup"><span data-stu-id="d76a7-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="d76a7-180">Ange ett värde i fältet Rapportfilnamn.</span><span class="sxs-lookup"><span data-stu-id="d76a7-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="d76a7-181">Markera ett alternativ i fältet Riktning.</span><span class="sxs-lookup"><span data-stu-id="d76a7-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="d76a7-182">Välj till exempel "Utförsel".</span><span class="sxs-lookup"><span data-stu-id="d76a7-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="d76a7-183">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d76a7-183">Click OK.</span></span>


