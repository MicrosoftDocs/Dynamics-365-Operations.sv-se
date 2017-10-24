---
title: "Ställ in förutsättningar för hantering"
description: "Använd den här proceduren för att aktivera avvikelsehanteringsprocesser."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 842a9441158defca74d1b203a1b2509773ba8919
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-prerequisites-for-management"></a><span data-ttu-id="da0da-103">Ställ in förutsättningar för hantering</span><span class="sxs-lookup"><span data-stu-id="da0da-103">Set up prerequisites for management</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="da0da-104">Använd den här proceduren för att aktivera avvikelsehanteringsprocesser.</span><span class="sxs-lookup"><span data-stu-id="da0da-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="da0da-105">En avvikelse beskriver en procedur eller artikel med kvalitetsproblem, där beskrivningen innehåller problemets källa och typ.</span><span class="sxs-lookup"><span data-stu-id="da0da-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="da0da-106">I proceduren används demonstrationsföretag USMF.</span><span class="sxs-lookup"><span data-stu-id="da0da-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="da0da-107">Vanligtvis utförs den här proceduren av en Kvalitetschef.</span><span class="sxs-lookup"><span data-stu-id="da0da-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="da0da-108">Aktivera kvalitetshanteringprocesser inom företaget</span><span class="sxs-lookup"><span data-stu-id="da0da-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="da0da-109">Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="da0da-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="da0da-110">Klicka på kvalitetshanteringfliken.</span><span class="sxs-lookup"><span data-stu-id="da0da-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="da0da-111">Välj Ja i fältet Använd kvalitetshantering.</span><span class="sxs-lookup"><span data-stu-id="da0da-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="da0da-112">Välj den här parametern om du vill aktivera kvalitetshanteringprocesser för företaget.</span><span class="sxs-lookup"><span data-stu-id="da0da-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="da0da-113">Skriv ett nummer i fältet Timtariff.</span><span class="sxs-lookup"><span data-stu-id="da0da-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="da0da-114">Använd timlön för att ange lokal valuta i fältet Lokal valuta.</span><span class="sxs-lookup"><span data-stu-id="da0da-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="da0da-115">Timpriset används för beräkning av kostnader för operationer som hör till en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="da0da-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="da0da-116">Timtariffen och de beräknade kostnaderna utgör referensinformation för en avvikelse och påverkar inte andra funktioner.</span><span class="sxs-lookup"><span data-stu-id="da0da-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="da0da-117">Klicka på Rapportinställning.</span><span class="sxs-lookup"><span data-stu-id="da0da-117">Click Report setup.</span></span>
    * <span data-ttu-id="da0da-118">Denna sida låter dig definiera kvalitetsrapportanmärkningstyperna som ska användas för olika slag av kvalitetshanteringrapporter.</span><span class="sxs-lookup"><span data-stu-id="da0da-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="da0da-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-119">Close the page.</span></span>
7. <span data-ttu-id="da0da-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="da0da-121">Gör det möjligt för användare att bearbeta avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="da0da-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-122">Gå till Systemadministration > Användare > Användare.</span><span class="sxs-lookup"><span data-stu-id="da0da-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="da0da-123">För att bearbeta godkännandet av en avvikelse måste användaren som godkänner eller avvisar avvikelser måste ha ett "namn"-värde tilldelat på användarsidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="da0da-124">För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.</span><span class="sxs-lookup"><span data-stu-id="da0da-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="da0da-125">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="da0da-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="da0da-126">Filtrera till exempel i fältet Namn med värdet "Ricardo".</span><span class="sxs-lookup"><span data-stu-id="da0da-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="da0da-127">Använd filtret för att hitta den användare som ska godkänna eller avvisa avvikelseposterna.</span><span class="sxs-lookup"><span data-stu-id="da0da-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="da0da-128">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="da0da-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="da0da-129">För att bearbeta godkännandet av en avvikelse måste användaren som godkänner eller avvisar avvikelser måste ha ett "namn"-värde tilldelat på användarsidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="da0da-130">Klicka på Användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="da0da-130">Click User options.</span></span>
5. <span data-ttu-id="da0da-131">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="da0da-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="da0da-132">Välj Ja i fältet Aktivera dokumenthantering.</span><span class="sxs-lookup"><span data-stu-id="da0da-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="da0da-133">För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen.</span><span class="sxs-lookup"><span data-stu-id="da0da-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="da0da-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-134">Close the page.</span></span>
8. <span data-ttu-id="da0da-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-135">Close the page.</span></span>
9. <span data-ttu-id="da0da-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="da0da-137">Definiera diagnostyper för bearbetning av avvikelse</span><span class="sxs-lookup"><span data-stu-id="da0da-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-138">Gå till Lagerhantering > Inställningar > Kvalitetshantering > Diagnostyper.</span><span class="sxs-lookup"><span data-stu-id="da0da-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="da0da-139">Använd sidan Diagnostyper för att definiera klassificeringen av diagnosåtgärder.</span><span class="sxs-lookup"><span data-stu-id="da0da-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="da0da-140">En korrigering identifierar vilken typ av diagnosåtgärd som ska vidtas vid en godkänd avvikelse, vem som ska genomföra den samt begärt och planerat slutförandedatum.</span><span class="sxs-lookup"><span data-stu-id="da0da-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="da0da-141">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-141">Click New.</span></span>
3. <span data-ttu-id="da0da-142">Ange ett värde i fältet Diagnoser.</span><span class="sxs-lookup"><span data-stu-id="da0da-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="da0da-143">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da0da-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="da0da-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="da0da-145">Definiera kvalitetsavgifter för bearbetning av avvikelse</span><span class="sxs-lookup"><span data-stu-id="da0da-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-146">Gå till Lagerhantering > Inställningar > Kvalitetshantering > Kvalitetsavgifter.</span><span class="sxs-lookup"><span data-stu-id="da0da-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="da0da-147">Använd sidan Kvalitetsavgifter för att definiera klassificeringen av avgifter som ska användas i åtgärder relaterade till avvikelser.</span><span class="sxs-lookup"><span data-stu-id="da0da-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="da0da-148">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-148">Click New.</span></span>
3. <span data-ttu-id="da0da-149">I fältet Kod för avgifter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="da0da-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="da0da-150">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da0da-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="da0da-151">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="da0da-152">Definiera operationer för bearbetning av avvikelse</span><span class="sxs-lookup"><span data-stu-id="da0da-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-153">Gå till Lagerhantering > Inställningar > Kvalitetshantering > Operationer.</span><span class="sxs-lookup"><span data-stu-id="da0da-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="da0da-154">Använd sidan Operationer för att definiera klassificeringen av det arbete som kan utföras vid en godkänd avvikelse.</span><span class="sxs-lookup"><span data-stu-id="da0da-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="da0da-155">När du relaterar en operation till en avvikelse kan du definiera detaljerad information om material, arbetstid och tillägg som krävs för att operationen ska kunna genomföras.</span><span class="sxs-lookup"><span data-stu-id="da0da-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="da0da-156">Denna information utgör beräkningsgrunden när kostnaden för utförandet av operationen ska uppskattas.</span><span class="sxs-lookup"><span data-stu-id="da0da-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="da0da-157">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-157">Click New.</span></span>
3. <span data-ttu-id="da0da-158">Ange ett värde i fältet Operation.</span><span class="sxs-lookup"><span data-stu-id="da0da-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="da0da-159">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da0da-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="da0da-160">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="da0da-161">Definiera problemtyper för bearbetning av avvikelse</span><span class="sxs-lookup"><span data-stu-id="da0da-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-162">Gå till Lagerhantering > Inställningar > Kvalitetshantering > Problemtyper.</span><span class="sxs-lookup"><span data-stu-id="da0da-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="da0da-163">Använd sidan Problemtyper för att definiera en klassificering av kvalitetsproblem som uppstår i de olika avvikelsetyperna.</span><span class="sxs-lookup"><span data-stu-id="da0da-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="da0da-164">Avvikelsetyperna omfattar: Internt, Kund, Leverantör, Servicebegäran, Produktion och Produktion av samprodukt.</span><span class="sxs-lookup"><span data-stu-id="da0da-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="da0da-165">En enskild problemtyp kan kopplas till flera avvikelsetyper.</span><span class="sxs-lookup"><span data-stu-id="da0da-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="da0da-166">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-166">Click New.</span></span>
3. <span data-ttu-id="da0da-167">Ange ett värde i fältet Problemtyp.</span><span class="sxs-lookup"><span data-stu-id="da0da-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="da0da-168">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da0da-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="da0da-169">Klicka på Avvikelsetyper.</span><span class="sxs-lookup"><span data-stu-id="da0da-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="da0da-170">Använd sidan Avvikelsetyper för att auktorisera en problemtyp som ska användas i en eller flera avvikelsetyper.</span><span class="sxs-lookup"><span data-stu-id="da0da-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="da0da-171">Exempelvis kan en problemtyp som har att göra med en defekt kod gälla för alla avvikelsetyper, medan en problemtyp för kundklagomål endast kan gälla för avvikelsetyperna kund och serviceförfrågan.</span><span class="sxs-lookup"><span data-stu-id="da0da-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="da0da-172">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-172">Click New.</span></span>
7. <span data-ttu-id="da0da-173">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="da0da-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="da0da-174">Välj ett alternativ i fältet Typ av avvikelse.</span><span class="sxs-lookup"><span data-stu-id="da0da-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="da0da-175">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-175">Close the page.</span></span>
10. <span data-ttu-id="da0da-176">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="da0da-177">Definiera karantänzoner för bearbetning av avvikelse</span><span class="sxs-lookup"><span data-stu-id="da0da-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="da0da-178">Gå till Lagerhantering > Inställningar > Kvalitetshantering > Karantänzoner.</span><span class="sxs-lookup"><span data-stu-id="da0da-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="da0da-179">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="da0da-179">Click New.</span></span>
3. <span data-ttu-id="da0da-180">Skriv ett värde i fältet Karantänzon.</span><span class="sxs-lookup"><span data-stu-id="da0da-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="da0da-181">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="da0da-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="da0da-182">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="da0da-182">Close the page.</span></span>

