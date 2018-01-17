---
title: "Produktens livscykeltillstånd"
description: "Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant."
author: cvocph
manager: AnnBe
ms.date: 12/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core (Operations, Core)
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: cvocph
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: b5bb91c809c2130ea71adb80d637e8a5f51a6e93
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---

# <a name="product-lifecycle-state"></a><span data-ttu-id="ccd30-103">Produktens livscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="ccd30-103">Product lifecycle state</span></span> 

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ccd30-104">Ett livscykeltillstånd för produkt beskriver livscykelstatusen för en frisläppt produkt eller produktvariant.</span><span class="sxs-lookup"><span data-stu-id="ccd30-104">A product lifecycle state documents the lifecycle state of a released product or product variant.</span></span> <span data-ttu-id="ccd30-105">Produktens livscykeltillstånd definieras av användaren, vanligtvis en produktchef eller en produktmallchef.</span><span class="sxs-lookup"><span data-stu-id="ccd30-105">Product lifecycle states are defined by the user, typically a product manager or a product master data manager.</span></span> <span data-ttu-id="ccd30-106">Specifika affärsprocesser, t.ex. huvudplanering kan påverkas av ett visst livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="ccd30-106">Specific business processes, such as master planning, can be affected by a specific lifecycle state.</span></span>   
 
<span data-ttu-id="ccd30-107">En frisläppt produkt eller produktvariant kan vara kopplade till ett livscykeltillstånd för produkten som dokumenterar med vilket livscykeltillstånd för en viss produkt eller variant används för närvarande.</span><span class="sxs-lookup"><span data-stu-id="ccd30-107">A released product or product variant can be associated with a product lifecycle state that documents in which lifecycle state a specific product or variant is currently in.</span></span> <span data-ttu-id="ccd30-108">Du kan definiera valfritt antal produktlivscykeltillstånd genom att tilldela ett tillståndsnamn och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ccd30-108">You can define any number of product lifecycle states by assigning a state name and description.</span></span> <span data-ttu-id="ccd30-109">Du kan välja ett livscykeltillstånd som standardläge för nya frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="ccd30-109">You can select one lifecycle state as the default state for new released products.</span></span> <span data-ttu-id="ccd30-110">Frisläppta produktvarianter ärver deras produktlivscykeltillstånd från deras frisläppa produktmallar när de skapas.</span><span class="sxs-lookup"><span data-stu-id="ccd30-110">Released product variants inherit their product lifecycle state from their released product master on creation.</span></span> <span data-ttu-id="ccd30-111">När du ändrar livscykeltillståndet i en frisläppt produktmall kan du välja att uppdatera alla befintliga varianter som har samma ursprungliga tillstånd.</span><span class="sxs-lookup"><span data-stu-id="ccd30-111">When changing the lifecycle state on a released product master, you can choose to update all existing variants that have the same original state.</span></span>  

## <a name="create-a-new-product-lifecycle-state"></a><span data-ttu-id="ccd30-112">Skapa ett nytt produktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="ccd30-112">Create a new product lifecycle state</span></span> 
 
- <span data-ttu-id="ccd30-113">För att skapa ett nytt produktlivscykeltillstånd spelar du upp eller läser uppgiftsguiden **Skapa ett nytt produktlivscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-113">To create a new product lifecycle state, play or read the task guide **Create a new product lifecycle state**.</span></span> 

-  <span data-ttu-id="ccd30-114">För att skapa ett standardproduktlivscykeltillstånd spelar du upp eller läser uppgiftsguiden **Skapa ett standardproduktlivscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-114">To create a default product lifecycle state, play or read the task guide **Create a default product lifecycle state**.</span></span>   

## <a name="associate-product-lifecycle-states-to-released-products"></a><span data-ttu-id="ccd30-115">Associera produktlivscykeltillstånd till frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="ccd30-115">Associate product lifecycle states to released products</span></span>  

<span data-ttu-id="ccd30-116">Det finns flera sätt att associera ett produktlivscykeltillstånd till frisläppta produkter eller produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="ccd30-116">There are multiple ways to associate a product lifecycle state to released products or product variants.</span></span>

-  <span data-ttu-id="ccd30-117">Vid skapandet av en ny frisläppt produkt tilldelas standard **produktlivscykeltillstånd** automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ccd30-117">On creation of a new released product, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="ccd30-118">Vid frisläppning av en produkt till en juridisk person kommer standard **produktlivscykeltillstånd** tilldelas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ccd30-118">On release of a product to a legal entity, the default **Product lifecycle state** is automatically assigned.</span></span> 
-  <span data-ttu-id="ccd30-119">Vid frisläppning av en produktvariant för en juridisk person i **produktlivscykeltillstånd** som associeras med den utgivna produktmallen i den här juridiska personen tilldelas automatiskt till den nya varianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-119">On release of a product variant to a legal entity, the **Product lifecycle state** associated to the released product master in this legal entity is automatically assigned to the new variant.</span></span> 

<span data-ttu-id="ccd30-120">Du kan uppdatera produktlivscykeltillståndet manuellt med hjälp av:</span><span class="sxs-lookup"><span data-stu-id="ccd30-120">You can manually update the product lifecycle state by using:</span></span> 

-    <span data-ttu-id="ccd30-121">Listsidan **frisläppta produkter** eller **detaljvy**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-121">The **Released products** list page or **Details view**.</span></span> 
-  <span data-ttu-id="ccd30-122">Listsidan **frisläppta produktvarianter** eller **detaljvy**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-122">The **Released product variants** list page or **Details view**.</span></span> 
-  <span data-ttu-id="ccd30-123">Söka efter föråldrade produkter eller produktvarianter baserat på behov och associera ett livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="ccd30-123">Find the obsolete products or product variants based on demand and associate a lifecycle state.</span></span>  

<span data-ttu-id="ccd30-124">För detaljerad information om hur du associerar ett produktlivscykeltillstånd, spela upp eller läs följande två uppgiftsguider.</span><span class="sxs-lookup"><span data-stu-id="ccd30-124">For detailed information about how to associate product lifecycle states, play or read the following two task guides.</span></span>

-  <span data-ttu-id="ccd30-125">För att associera ett produktlivscykeltillstånd till en frisläppt produktmall, spela upp eller läs uppgiftsguiden **tilldela produktlivscykeltillstånd till en frisläppt produktmall**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-125">To associate a product lifecycle state to a released product master, play or read the task guide **Assign a product lifecycle state to a released product master**.</span></span> 

-  <span data-ttu-id="ccd30-126">För att associera ett produktlivscykeltillstånd till en frisläppt produkt, spela upp eller läs uppgiftsguiden **tilldela produktlivscykeltillstånd till en frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-126">To associate a product lifecycle state to a release product, play or read the task guide **Assign a product lifecycle state to a released product**.</span></span> 

## <a name="impact-on-master-planning"></a><span data-ttu-id="ccd30-127">Påverkan på huvudplanering</span><span class="sxs-lookup"><span data-stu-id="ccd30-127">Impact on master planning</span></span> 

<span data-ttu-id="ccd30-128">Produktlivscykeltillståndet har bara en kontrollflagga: **är aktiv för planeringtillstånd**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-128">The product lifecycle state has only one control flag: **Is active for planning**.</span></span> <span data-ttu-id="ccd30-129">Som standard är inställt på **Ja** för alla skapade produktlivscykeltillstånd, men kan ändras till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-129">By default, this is set to **Yes** for all created product lifecycle states, but it can be changed to **No**.</span></span> <span data-ttu-id="ccd30-130">Om den är inställd på **Nej**, är de associerade produkterna eller frisläppta produktvarianterna:</span><span class="sxs-lookup"><span data-stu-id="ccd30-130">When set to **No**, the associated released products or released product variants are:</span></span> 

-  <span data-ttu-id="ccd30-131">Undantagna från huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="ccd30-131">Excluded from master planning.</span></span> 
-  <span data-ttu-id="ccd30-132">Undantagna från strukturlistenivåberäkningen.</span><span class="sxs-lookup"><span data-stu-id="ccd30-132">Excluded from BOM-level calculation.</span></span> 

<span data-ttu-id="ccd30-133">Detaljerad information om hur du använder produktlivscykeltillstånd för att undanta produkter från huvudplanering och strukturlistenivåberäkningen, spela upp eller läs uppgiftsguiden **skapa ett produktlivscykeltillstånd från huvudplaneringen**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-133">For detailed information about how to use product lifecycle state to exclude products from master planning and BOM-level calculation, play or read the task guide **Create a product lifecycle state to exclude products from Master planning**.</span></span>

> [!NOTE]
> <span data-ttu-id="ccd30-134">Av prestandaskäl rekommenderas att koppla alla föråldrade frisläppta produkter eller produktvarianter, särskilt när du arbetar med icke-återanvändningsbara produktkonfigurationsvarianter med produktlivscykeltillstånd som inaktiveras för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="ccd30-134">For performance reasons, it is highly recommended to associate all obsolete released products or product variants, especially when working with non-reusable product configuration variants, with a product lifecycle state that is deactivated for master planning.</span></span>  
 
## <a name="default-migration-import-and-export"></a><span data-ttu-id="ccd30-135">Standardmigrering, import och export</span><span class="sxs-lookup"><span data-stu-id="ccd30-135">Default migration, import, and export</span></span> 

<span data-ttu-id="ccd30-136">Produktlivscykeltillstånd stöds inte av datatabeller och livscykeltillståndet kan inte anges till ett variabelläge via de frisläppta produktdatatabellerna.</span><span class="sxs-lookup"><span data-stu-id="ccd30-136">The product lifecycle states are not supported by data entities, and the lifecycle state cannot be set to a variable state through the released product data entities.</span></span>

-  <span data-ttu-id="ccd30-137">Vid migration från tidigare frisläppningar är livscykeltillståndet för alla produkter och produktvarianter tomt.</span><span class="sxs-lookup"><span data-stu-id="ccd30-137">On migration from previous releases, the lifecycle state of all products and product variants will be blank.</span></span>  
-  <span data-ttu-id="ccd30-138">När du importerar frisläppta produkter via en datatabell, används standard livscykeltillståndet när de skapas.</span><span class="sxs-lookup"><span data-stu-id="ccd30-138">When importing released products through a data entity, the default lifecycle state will be applied on creation.</span></span>  
-  <span data-ttu-id="ccd30-139">När du importerar frisläppta produktvarianter via en datatabell, importeras livscykeltillstånd för den frisläppta produktmallen.</span><span class="sxs-lookup"><span data-stu-id="ccd30-139">When importing released product variants through a data entity, the product lifecycle state of the released product master will be imported.</span></span>   
 
## <a name="find-obsolete-products-and-products-variants"></a><span data-ttu-id="ccd30-140">Söka efter föråldrade produkter och produktvarianter</span><span class="sxs-lookup"><span data-stu-id="ccd30-140">Find obsolete products and products variants</span></span> 
 
<span data-ttu-id="ccd30-141">Du kan köra en simuleringsanalys om du vill söka efter föråldrade frisläppta produkter eller produktvarianter och sedan uppdatera deras status för produktlivscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="ccd30-141">You can run a simulation analysis to find the obsolete released products or product variants and then update their product lifecycle status.</span></span> <span data-ttu-id="ccd30-142">Om du vill hitta föråldrade produkter, spela upp och läs uppgiftsguiden **Sök föråldrade produktvarianter och tilldela ett produktlivscykeltillstånd**.</span><span class="sxs-lookup"><span data-stu-id="ccd30-142">To find obsolete products, play and read the task guide **Find obsolete product variants and assign a product lifecycle state**.</span></span> <span data-ttu-id="ccd30-143">Den här uppgiftsguiden visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna.</span><span class="sxs-lookup"><span data-stu-id="ccd30-143">This task guide shows how to find obsolete released products or product variants and how to associate a product lifecycle state to the obsolete products.</span></span> <span data-ttu-id="ccd30-144">Här visas också hur du visar resultaten för simulering och bedömer hur många produkter och produktvarianter som ska kopplas till ett nytt produktlivscykeltillstånd när du kör uppdateringen utan simulering.</span><span class="sxs-lookup"><span data-stu-id="ccd30-144">It also shows hot to view the simulation results and assess how many products and product variants will be associated with a new product lifecycle state when running the update without simulation.</span></span>  
 
<span data-ttu-id="ccd30-145">Genom att köra analysen i ett simuleringsläge, identifieras produkterna och produktvarianterna som föråldrade och visas i en specifik form där de enkelt kan granskas.</span><span class="sxs-lookup"><span data-stu-id="ccd30-145">By running the analysis in a simulation mode, the products and product variants identified as obsolete are displayed in a specific form, where they can easily be reviewed.</span></span> <span data-ttu-id="ccd30-146">Analysen söker efter transaktioner och specifika huvuddata för att identifiera produkter som inte har några behov inom variabel period och inga huvuddata som kan leda till efterfrågan.</span><span class="sxs-lookup"><span data-stu-id="ccd30-146">The analysis searches for transactions and specific master data to identify products that have no demand within a variable period and no master data that can result in demand.</span></span> <span data-ttu-id="ccd30-147">Nya frisläppta produkter inom variabelperiod kan uteslutas från analysen.</span><span class="sxs-lookup"><span data-stu-id="ccd30-147">New released products within a variable period can be excluded from the analysis.</span></span> <span data-ttu-id="ccd30-148">När analysissimuleringen returnerar det förväntade resultatet kan användaren köra analysen och ange ett nytt produktlivscykeltillstånd för alla produkter som identifieras som föråldrade av analysen.</span><span class="sxs-lookup"><span data-stu-id="ccd30-148">When the analysis simulation returns the expected result, the user can run the analysis and set a new product lifecycle state to all products identified as obsolete by the analysis.</span></span>  
 
> [!NOTE]
> <span data-ttu-id="ccd30-149">Observera att alla analyser och uppdateringar måste utföras inom samma juridiska person.</span><span class="sxs-lookup"><span data-stu-id="ccd30-149">Note that all analysis and updates must be done within the same legal entity.</span></span>  
 
## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a><span data-ttu-id="ccd30-150">Kriterier för att välja och uppdatera frisläppta produkter eller produktvarianter</span><span class="sxs-lookup"><span data-stu-id="ccd30-150">Criteria to select and update released products or product variants</span></span> 
 
<span data-ttu-id="ccd30-151">Använd följande kriterier för att välja och uppdatera frisläppta produkter och produktvarianter:</span><span class="sxs-lookup"><span data-stu-id="ccd30-151">Use the following criteria to select and update the released products and product variants:</span></span> 

-    <span data-ttu-id="ccd30-152">Produktlivscykeltillstånd för produkten eller produktvarianten måste skilja sig från det önskade tillståndet.</span><span class="sxs-lookup"><span data-stu-id="ccd30-152">The product lifecycle state of the product or product variant must be different from the new desired state.</span></span> 
-  <span data-ttu-id="ccd30-153">Produkten eller produktvarianten skapades för några dagar sedan baserat på hur många dagar som du anger i urvalsdialogrutan.</span><span class="sxs-lookup"><span data-stu-id="ccd30-153">The product or product variant was created some days ago based on the number of days that you enter in the selection dialog box.</span></span> 
-  <span data-ttu-id="ccd30-154">Det finns inga öppna produktionsorder (status = < avslutas) för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-154">There are no open production orders (= status < ended) for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-155">Det finns inga öppna lagertransaktioner (= statusproblem ReservPhysical till QuotationIssue eller statusmottagande registrerad till QuotationReceipt) för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-155">There are no open inventory transactions (= status issue ReservPhysical to QuotationIssue or status receipt Registrered to QuotationReceipt) for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-156">Det finns inga lagertransaktioner inom sista antalet dagar för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-156">There are no inventory transactions within the last number of days for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-157">Det finns ingen framtida efterfrågan eller leveransprognos för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-157">There is no future demand or supply forecast for the product or product variant.</span></span>  
-  <span data-ttu-id="ccd30-158">Inget minsta lagernivå har ställts in i artikeldisponering för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-158">No minimum stock level has been set in item coverage for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-159">Ingen aktiv fast kvantitetkanbanregel för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-159">No active fixed quantity kanban rule for the product or product variant.</span></span>  
-  <span data-ttu-id="ccd30-160">Ingen serviceorderrad för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-160">No service order line for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-161">Inga aktiva och framtida försäljnings- eller inköpsrader för produkten eller produktvarianten.</span><span class="sxs-lookup"><span data-stu-id="ccd30-161">No active or future sales or purchase agreement lines for the product or product variant.</span></span> 
-  <span data-ttu-id="ccd30-162">Produkten eller produktvarianten används inte i en strukturlista som är kopplad till en ej förfallen godkänd strukturlisteversion för en produkt eller variant som är aktiv för planering.</span><span class="sxs-lookup"><span data-stu-id="ccd30-162">The product or product variant is not used in a BOM that is associated with a non-expired approved BOM version for a product or variant that is active for planning.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccd30-163">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ccd30-163">Related topics</span></span>

-  <span data-ttu-id="ccd30-164">Skapa ett nytt produktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="ccd30-164">Create a new product lifecycle state</span></span>
-  <span data-ttu-id="ccd30-165">Skapa ett nytt standardproduktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="ccd30-165">Create a default new product lifecycle state</span></span>
-  <span data-ttu-id="ccd30-166">Associera ett produktlivscykeltillstånd till en frisläppt produktmall</span><span class="sxs-lookup"><span data-stu-id="ccd30-166">Assign a product lifecycle state to a released product master</span></span>
-  <span data-ttu-id="ccd30-167">Associera ett produktlivscykeltillstånd till en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="ccd30-167">Assign a product lifecycle state to a released product</span></span>
-  <span data-ttu-id="ccd30-168">Söka efter föråldrade produktvarianter och tilldela ett produktlivscykeltillstånd</span><span class="sxs-lookup"><span data-stu-id="ccd30-168">Find obsolete product variants and assign a product lifecycle state</span></span>
-  <span data-ttu-id="ccd30-169">Skapa ett produktlivscykeltillstånd för att utesluta produkter från huvudplanering</span><span class="sxs-lookup"><span data-stu-id="ccd30-169">Create a product lifecycle state to exclude products from Master planning</span></span>

