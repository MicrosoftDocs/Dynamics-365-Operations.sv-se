---
title: EUR-00002 Skapa en Intrastat-deklaration för EU
description: I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 170c73d2ace75f990df9d57c658e859dcd30dd36
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538387"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a><span data-ttu-id="55318-103">EUR-00002 Skapa en Intrastat-deklaration för EU</span><span class="sxs-lookup"><span data-stu-id="55318-103">EUR-00002 Generate an EU Intrastat declaration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="55318-104">I den här proceduren går du igenom stegen som krävs för att exportera Intrastat-deklarationen i det elektroniska filformatet och förhandsgranska deklarationdatan i ett Excel-format.</span><span class="sxs-lookup"><span data-stu-id="55318-104">This procedure walks you through the steps required to export the Intrastat declaration in the electronic file format and preview the declaration data in an Excel format.</span></span> 

<span data-ttu-id="55318-105">Innan du kan slutföra proceduren, måste du överföra transaktioner till Intrastat.</span><span class="sxs-lookup"><span data-stu-id="55318-105">Before you can complete this procedure, you must transfer transactions to the Intrastat.</span></span> 

<span data-ttu-id="55318-106">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="55318-106">This procedure was created using the demo data company DEMF.</span></span>


## <a name="import-configurations-with-settings"></a><span data-ttu-id="55318-107">Importera konfigurationer med inställningar</span><span class="sxs-lookup"><span data-stu-id="55318-107">Import configurations with settings</span></span>
1. <span data-ttu-id="55318-108">Gå till Arbetsytor > Elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="55318-108">Go to Workspaces > Electronic reporting</span></span>
2. <span data-ttu-id="55318-109">Klicka på Ställ in aktiv.</span><span class="sxs-lookup"><span data-stu-id="55318-109">Click Set active.</span></span>
3. <span data-ttu-id="55318-110">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="55318-110">Click Repositories.</span></span>
4. <span data-ttu-id="55318-111">Klicka på Öppna.</span><span class="sxs-lookup"><span data-stu-id="55318-111">Click Open.</span></span>
5. <span data-ttu-id="55318-112">Öppna kolumnfiltret för Konfigurationsnamn.</span><span class="sxs-lookup"><span data-stu-id="55318-112">Open Configuration name column filter.</span></span>
6. <span data-ttu-id="55318-113">Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”DIntrastat (DE)", med hjälp av filteroperatorn ”börjar med”.</span><span class="sxs-lookup"><span data-stu-id="55318-113">Apply a filter on the "Configuration name" field, with a value of "Intrastat (DE)", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="55318-114">Du bör välja konfigurationnamnet som gäller för din juridiska persons land.</span><span class="sxs-lookup"><span data-stu-id="55318-114">You should select the configuration name applicable for the country of your legal entity.</span></span> <span data-ttu-id="55318-115">I den här proceduren används den tyska juridiska personen (till exempel DEMF), därför ska ”Intrastat (DE)” väljas.</span><span class="sxs-lookup"><span data-stu-id="55318-115">This procedure uses the German legal entity (DEMF) as an example, therefore "Intrastat (DE)" should be chosen.</span></span>  
    * <span data-ttu-id="55318-116">Klicka på Importera och sedan på Ja.</span><span class="sxs-lookup"><span data-stu-id="55318-116">Click Import and then click Yes.</span></span>  
7. <span data-ttu-id="55318-117">Öppna kolumnfiltret för Konfigurationsnamn.</span><span class="sxs-lookup"><span data-stu-id="55318-117">Open Configuration name column filter.</span></span>
8. <span data-ttu-id="55318-118">Använd ett filter för fältet ”Konfigurationsnamn”, med värdet ”intrastat-rapport", med hjälp av filteroperatorn ”börjar med”.</span><span class="sxs-lookup"><span data-stu-id="55318-118">Apply a filter on the "Configuration name" field, with a value of "intrastat report", using the "begins with" filter operator.</span></span>
    * <span data-ttu-id="55318-119">Klicka på Importera och sedan på Ja.</span><span class="sxs-lookup"><span data-stu-id="55318-119">Click Import and then click Yes.</span></span>  

## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="55318-120">Konfigurera utländska handelsparametrar</span><span class="sxs-lookup"><span data-stu-id="55318-120">Set up Foreign trade parameters</span></span>
1. <span data-ttu-id="55318-121">Gå till Moms > Inställningar > Utländsk handel > Utländska handelsparametrar.</span><span class="sxs-lookup"><span data-stu-id="55318-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
2. <span data-ttu-id="55318-122">Expandera avsnittet Elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="55318-122">Expand the Electronic reporting section.</span></span>
3. <span data-ttu-id="55318-123">Ange eller välj ett värde Intrastat (DE) i fältet Mappning av filformat.</span><span class="sxs-lookup"><span data-stu-id="55318-123">In the File format mapping field, enter or select a value Intrastat (DE)</span></span>
4. <span data-ttu-id="55318-124">Ange eller välj ett värde Intrastat-rapport i fältet Mappning av rapportformat.</span><span class="sxs-lookup"><span data-stu-id="55318-124">In the Report format mapping field, enter or select a value Intrastat report</span></span>
5. <span data-ttu-id="55318-125">Expandera avsnittet Avrundningsregler.</span><span class="sxs-lookup"><span data-stu-id="55318-125">Expand the Rounding rules section.</span></span>
    * <span data-ttu-id="55318-126">Du bör ställa in avrundningregler som kan användas i ditt land/din region för Intrastat-rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="55318-126">You should set up rounding rules that are applicable in your country/region for Intrastat reporting.</span></span>  
6. <span data-ttu-id="55318-127">Ange ett tal i fältet Avrundningsregel.</span><span class="sxs-lookup"><span data-stu-id="55318-127">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="55318-128">Ange avrundningsprecision, till exempel ”0,01 ".</span><span class="sxs-lookup"><span data-stu-id="55318-128">Enter rounding precision, for example, enter '0.01'.</span></span>  
7. <span data-ttu-id="55318-129">Ange ett nummer i fältet Antal decimaler för belopp.</span><span class="sxs-lookup"><span data-stu-id="55318-129">In the Number of decimals for amount field, enter a number.</span></span>
    * <span data-ttu-id="55318-130">Ange t.ex. "2".</span><span class="sxs-lookup"><span data-stu-id="55318-130">For example, enter '2'.</span></span>  
8. <span data-ttu-id="55318-131">Markera ett alternativ i fältet Avrundning under 1 kg.</span><span class="sxs-lookup"><span data-stu-id="55318-131">In the Rounding below 1 kg field, select an option.</span></span>
    * <span data-ttu-id="55318-132">Välj t.ex. ”Avrundning till 1 kg”.</span><span class="sxs-lookup"><span data-stu-id="55318-132">For example, select 'Rounding up to 1 kg'.</span></span>  
9. <span data-ttu-id="55318-133">Ange ett tal i fältet Avrundningsregel.</span><span class="sxs-lookup"><span data-stu-id="55318-133">In the Rounding rule field, enter a number.</span></span>
    * <span data-ttu-id="55318-134">Ange t.ex. "1" för avrundning av vikt till heltal.</span><span class="sxs-lookup"><span data-stu-id="55318-134">For example, enter '1' for rounding weight to the integer.</span></span>  
10. <span data-ttu-id="55318-135">Visa avsnittet Minimigräns.</span><span class="sxs-lookup"><span data-stu-id="55318-135">Expand the Minimum limit section.</span></span>
11. <span data-ttu-id="55318-136">Ange ett nummer i fältet Vikt.</span><span class="sxs-lookup"><span data-stu-id="55318-136">In the Weight field, enter a number.</span></span>
    * <span data-ttu-id="55318-137">Ange ”10” som minsta vikt.</span><span class="sxs-lookup"><span data-stu-id="55318-137">For example, enter '10' as the minimum weight.</span></span>  
12. <span data-ttu-id="55318-138">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="55318-138">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="55318-139">Ange ”200” som minsta belopp.</span><span class="sxs-lookup"><span data-stu-id="55318-139">For example, enter '200' as the minimum amount.</span></span>  
13. <span data-ttu-id="55318-140">Ange eller välj ett värde i fältet Artikel.</span><span class="sxs-lookup"><span data-stu-id="55318-140">In the Commodity field, enter or select a value.</span></span>

## <a name="set-up-compression-of-intrastat"></a><span data-ttu-id="55318-141">Ställ in komprimering av Intrastat</span><span class="sxs-lookup"><span data-stu-id="55318-141">Set up Compression of Intrastat</span></span>
1. <span data-ttu-id="55318-142">Gå till Moms > Inställningar > Utländsk handel > Komprimering av Intrastat.</span><span class="sxs-lookup"><span data-stu-id="55318-142">Go to Tax > Setup > Foreign trade > Compression of Intrastat.</span></span>
2. <span data-ttu-id="55318-143">Klicka på Ta bort.</span><span class="sxs-lookup"><span data-stu-id="55318-143">Click Remove.</span></span>
3. <span data-ttu-id="55318-144">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="55318-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="55318-145">Du kan till exempel välja Artikel i avsnittet Tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="55318-145">For example, select Commodity in the Available section.</span></span>  
4. <span data-ttu-id="55318-146">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="55318-146">Click Add.</span></span>

## <a name="generate-intrastat-declaration"></a><span data-ttu-id="55318-147">Generera en Intrastat-deklaration</span><span class="sxs-lookup"><span data-stu-id="55318-147">Generate Intrastat declaration</span></span>
1. <span data-ttu-id="55318-148">Gå till Moms > Deklarationer > Utländsk handel > Intrastat</span><span class="sxs-lookup"><span data-stu-id="55318-148">Go to Tax > Declarations > Foreign trade > Intrastat</span></span>
2. <span data-ttu-id="55318-149">Klicka på Validera.</span><span class="sxs-lookup"><span data-stu-id="55318-149">Click Validate.</span></span>
    * <span data-ttu-id="55318-150">Valideringen görs i enlighet med fältet Kontrollera inställningar på sidan Utrikeshandelparameter.</span><span class="sxs-lookup"><span data-stu-id="55318-150">The validation is done according to the Check setup field on the Foreign trade parameters page.</span></span>  
3. <span data-ttu-id="55318-151">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55318-151">Click OK.</span></span>
4. <span data-ttu-id="55318-152">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="55318-152">Click Update.</span></span>
5. <span data-ttu-id="55318-153">Klicka på Minimigräns.</span><span class="sxs-lookup"><span data-stu-id="55318-153">Click Minimum limit.</span></span>
6. <span data-ttu-id="55318-154">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="55318-154">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="55318-155">Ange t.ex. januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-155">For example, enter January 1, 2015.</span></span>  
7. <span data-ttu-id="55318-156">Välj Ja i fältet Komprimera.</span><span class="sxs-lookup"><span data-stu-id="55318-156">Select Yes in the Compress field.</span></span>
8. <span data-ttu-id="55318-157">Ange ett datum i fältet Slutdatum.</span><span class="sxs-lookup"><span data-stu-id="55318-157">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="55318-158">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-158">For example, enter January 31, 2015.</span></span>  
9. <span data-ttu-id="55318-159">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55318-159">Click OK.</span></span>
10. <span data-ttu-id="55318-160">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="55318-160">Click Update.</span></span>
11. <span data-ttu-id="55318-161">Klicka på Komprimera.</span><span class="sxs-lookup"><span data-stu-id="55318-161">Click Compress.</span></span>
    * <span data-ttu-id="55318-162">Denna komprimering sker enligt hur du ställer in komprimeringen av Intrastat-inställningar.</span><span class="sxs-lookup"><span data-stu-id="55318-162">This compression happens according to how you set the Compression of intrastate settings.</span></span>  
12. <span data-ttu-id="55318-163">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="55318-163">In the Start date field, enter a date.</span></span>
    * <span data-ttu-id="55318-164">Ange t.ex. januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-164">For example, enter January 1, 2015.</span></span>  
13. <span data-ttu-id="55318-165">Ange ett datum i fältet Slutdatum.</span><span class="sxs-lookup"><span data-stu-id="55318-165">In the End date field, enter a date.</span></span>
    * <span data-ttu-id="55318-166">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-166">For example, enter 31st January 2015.</span></span>  
14. <span data-ttu-id="55318-167">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55318-167">Click OK.</span></span>
15. <span data-ttu-id="55318-168">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="55318-168">Click Update.</span></span>
16. <span data-ttu-id="55318-169">Klicka på Generera om löpnummer.</span><span class="sxs-lookup"><span data-stu-id="55318-169">Click Regenerate sequence numbers.</span></span>
17. <span data-ttu-id="55318-170">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55318-170">Click OK.</span></span>
18. <span data-ttu-id="55318-171">Klicka på Utdata.</span><span class="sxs-lookup"><span data-stu-id="55318-171">Click Output.</span></span>
19. <span data-ttu-id="55318-172">Klicka på Rapport.</span><span class="sxs-lookup"><span data-stu-id="55318-172">Click Report.</span></span>
20. <span data-ttu-id="55318-173">Ange det första datumet i rapporteringperioden i fältet Från-datum.</span><span class="sxs-lookup"><span data-stu-id="55318-173">In the From date field, enter the first date of the reporting period.</span></span>
    * <span data-ttu-id="55318-174">Ange t.ex. datum till 1 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-174">For example, set the date to January 1, 2015.</span></span>  
21. <span data-ttu-id="55318-175">Ange ett datum i fältet Till datum.</span><span class="sxs-lookup"><span data-stu-id="55318-175">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="55318-176">Ange t.ex. 31 januari 2015.</span><span class="sxs-lookup"><span data-stu-id="55318-176">For example, enter January 31, 2015.</span></span>  
22. <span data-ttu-id="55318-177">Välj Ja i fältet Generera fil.</span><span class="sxs-lookup"><span data-stu-id="55318-177">Select Yes in the Generate file field.</span></span>
23. <span data-ttu-id="55318-178">Ange ett värde i fältet Filnamn.</span><span class="sxs-lookup"><span data-stu-id="55318-178">In the File name field, type a value.</span></span>
24. <span data-ttu-id="55318-179">Välj Ja i fältet Generera rapport.</span><span class="sxs-lookup"><span data-stu-id="55318-179">Select Yes in the Generate report field.</span></span>
25. <span data-ttu-id="55318-180">Ange ett värde i fältet Rapportfilnamn.</span><span class="sxs-lookup"><span data-stu-id="55318-180">In the Report file name field, type a value.</span></span>
26. <span data-ttu-id="55318-181">Markera ett alternativ i fältet Riktning.</span><span class="sxs-lookup"><span data-stu-id="55318-181">In the Direction field, select an option.</span></span>
    * <span data-ttu-id="55318-182">Välj till exempel "Utförsel".</span><span class="sxs-lookup"><span data-stu-id="55318-182">For example, select 'Dispatches'.</span></span>  
27. <span data-ttu-id="55318-183">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="55318-183">Click OK.</span></span>

