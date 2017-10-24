--- 
title: "Skapa en rekvisition för förbrukning"
description: "I den här proceduren förklaras processen för att skapa en rekvisition."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07fe007005fcbbac1beecadb14dbd752376a0bd4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-requisition-for-consumption"></a><span data-ttu-id="1ceea-103">Skapa en rekvisition för förbrukning</span><span class="sxs-lookup"><span data-stu-id="1ceea-103">Create a requisition for consumption</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ceea-104">I den här proceduren förklaras processen för att skapa en rekvisition.</span><span class="sxs-lookup"><span data-stu-id="1ceea-104">This procedure walks you through the process of creating a requisition.</span></span> <span data-ttu-id="1ceea-105">Den visar olika metoder för att söka efter produkter i din anskaffningskatalog och hur du lägger till en produkt som inte finns i din katalog.</span><span class="sxs-lookup"><span data-stu-id="1ceea-105">It shows you different ways to search for products in your procurement catalogue and how to add a product that isn’t in your catalogue.</span></span> <span data-ttu-id="1ceea-106">Innan du startar den här proceduren måste du ha en inköpspolicy inställd med Förbrukning som standardinställningstyp för rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-106">Before you start this procedure, you must have a purchasing policy set up with Consumption as the default type of requisition.</span></span> <span data-ttu-id="1ceea-107">Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.</span><span class="sxs-lookup"><span data-stu-id="1ceea-107">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="1ceea-108">Proceduren kan bara utföras av en användarprofil som har ställts in som arbetare.</span><span class="sxs-lookup"><span data-stu-id="1ceea-108">The procedure can only be carried out by a user profile that is set up as worker.</span></span>  <span data-ttu-id="1ceea-109">Uppgiften utförs vanligtvis av en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="1ceea-109">This task would normally be carried out by an employee.</span></span> <span data-ttu-id="1ceea-110">Den säkerhetsroll som medarbetaren använder gör det möjligt för dig att utföra uppgifterna. Om du använder USMF kan du även logga in som Alicia.</span><span class="sxs-lookup"><span data-stu-id="1ceea-110">The Employee employ security role will allow you to carry out the tasks, or if you’re using USMF, you can log in as Alicia.</span></span>


## <a name="create-a-new-requisition"></a><span data-ttu-id="1ceea-111">Skapa en ny rekvisition</span><span class="sxs-lookup"><span data-stu-id="1ceea-111">Create a new requisition</span></span>
1. <span data-ttu-id="1ceea-112">Gå till Anskaffning och källa > Inköpsrekvisitioner > Inköpsrekvisitioner som har förberetts av mig.</span><span class="sxs-lookup"><span data-stu-id="1ceea-112">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="1ceea-113">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1ceea-113">Click New.</span></span>
3. <span data-ttu-id="1ceea-114">Ange ett namn på rekvisitionen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="1ceea-114">In the Name field, give the requisition a name.</span></span>
4. <span data-ttu-id="1ceea-115">Ange ett datum i fältet Begärt datum.</span><span class="sxs-lookup"><span data-stu-id="1ceea-115">In the Requested date field, enter a date.</span></span>
    * <span data-ttu-id="1ceea-116">Som standard kopieras det begärda datumet och redovisningsdatumet till inköpsrekvisitionsrader.</span><span class="sxs-lookup"><span data-stu-id="1ceea-116">By default, the requested date and accounting date are copied to the purchase requisition lines.</span></span> <span data-ttu-id="1ceea-117">De kan ändras på radnivå.</span><span class="sxs-lookup"><span data-stu-id="1ceea-117">They can be changed at the line level.</span></span> <span data-ttu-id="1ceea-118">Det begärda datumet är det begärda leveransdatumet.</span><span class="sxs-lookup"><span data-stu-id="1ceea-118">The requested date is the requested delivery date.</span></span>  
5. <span data-ttu-id="1ceea-119">Ange ett datum i fältet Redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="1ceea-119">In the Accounting date field, enter a date.</span></span>
    * <span data-ttu-id="1ceea-120">Redovisningsdatumet används för att registrera redovisningsposten i redovisningen och för att validera att det finns tillgängliga budgetmedel.</span><span class="sxs-lookup"><span data-stu-id="1ceea-120">The accounting date is used to record the accounting entry in the general ledger, and to validate whether budget funds are available.</span></span>  
6. <span data-ttu-id="1ceea-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1ceea-121">Click OK.</span></span>
7. <span data-ttu-id="1ceea-122">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Orsak.</span><span class="sxs-lookup"><span data-stu-id="1ceea-122">In the Reason field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1ceea-123">Affärsmotiveringsorsaken som du väljer visas som standard för raderna på inköpsrekvisitionen, men du kan ändra den på radnivå.</span><span class="sxs-lookup"><span data-stu-id="1ceea-123">By default, the business justification reason that you select appears for the purchase requisition lines, but you can change it at the line level.</span></span>    
8. <span data-ttu-id="1ceea-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-124">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="1ceea-125">Ange orsaken</span><span class="sxs-lookup"><span data-stu-id="1ceea-125">Select the reason</span></span>
10. <span data-ttu-id="1ceea-126">Ange en mer beskrivande justering för rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="1ceea-126">In the details field enter a more descriptive justification for the requisition</span></span>

## <a name="add-a-line-to-the-requisition"></a><span data-ttu-id="1ceea-127">Lägga till en rad i rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="1ceea-127">Add a line to the requisition</span></span>
1. <span data-ttu-id="1ceea-128">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="1ceea-128">Click Add line.</span></span>
    * <span data-ttu-id="1ceea-129">Du kan lägga till rader i inköpsrekvisitionen på två sätt.</span><span class="sxs-lookup"><span data-stu-id="1ceea-129">There are two ways of adding lines to the purchase requisition.</span></span> <span data-ttu-id="1ceea-130">Om du redan känner till produktnumret eller vet att du begär en produkt som inte finns i produktkatalogen kan du lägga till raden direkt med "Lägg till rad".</span><span class="sxs-lookup"><span data-stu-id="1ceea-130">If you already know the product number or you already  know that you are requesting a product that is not in the product catalogueue, then you can add the line directly with "Add line".</span></span> <span data-ttu-id="1ceea-131">Det andra sättet är att använda "Lägg till produkter" där du kan använda sökning och filtrering för att hitta artiklar i produktkatalogen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-131">The other way is to use "Add products" where you can use searching and filtering to find items in the product catalogueue.</span></span>    
2. <span data-ttu-id="1ceea-132">Klicka på den rad som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="1ceea-132">Click on the row you just created.</span></span>
    * <span data-ttu-id="1ceea-133">Beställaren är den arbetare som har begärt rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-133">The requester is the worker that has requested the requisition.</span></span>   
    * <span data-ttu-id="1ceea-134">Som standard är det den arbetare som har begärt rekvisitionen som förbereder den.</span><span class="sxs-lookup"><span data-stu-id="1ceea-134">By default the person preparing the requisition is the worker who has requested it.</span></span> <span data-ttu-id="1ceea-135">Du måste ges behörighet att förbereda en rekvisitionsrad på uppdrag av en annan arbetare.</span><span class="sxs-lookup"><span data-stu-id="1ceea-135">You have to be given permission to prepare a requisition line on behalf of another worker.</span></span> <span data-ttu-id="1ceea-136">Om du har sådana behörigheter visas de andra arbetarna i den här sökningen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-136">If you have such permissions then the other workers will show up in this lookup.</span></span>  
3. <span data-ttu-id="1ceea-137">Skriv ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="1ceea-137">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="1ceea-138">Det antal artiklar som du kan välja begränsas av kategoriåtkomstpolicyn och anskaffningskatalogen för den köpande juridiska personen. </span><span class="sxs-lookup"><span data-stu-id="1ceea-138">The items that are available for you to choose are limited by the category access policy and the procurement catalogue for the buying legal entity.</span></span>   
4. <span data-ttu-id="1ceea-139">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="1ceea-139">In the Quantity field, enter a number.</span></span>

## <a name="add-more-products-to-the-requisition"></a><span data-ttu-id="1ceea-140">Lägg till fler produkter till rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="1ceea-140">Add more products to the requisition</span></span>
1. <span data-ttu-id="1ceea-141">Klicka på Lägg till produkter.</span><span class="sxs-lookup"><span data-stu-id="1ceea-141">Click Add products.</span></span>
    * <span data-ttu-id="1ceea-142">Detta är det alternativ där du kan söka efter produkter i produktkatalogen.  </span><span class="sxs-lookup"><span data-stu-id="1ceea-142">This is the option where you can search for products in the product catalogueue.</span></span>    
2. <span data-ttu-id="1ceea-143">I fältet Hitta anskaffningskategorinod skriver du den första delen av namnet på den kategori som du letar efter och klickar sedan på Enter.</span><span class="sxs-lookup"><span data-stu-id="1ceea-143">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="1ceea-144">Skriv till exempel dat.</span><span class="sxs-lookup"><span data-stu-id="1ceea-144">For example, type comput.</span></span>  
3. <span data-ttu-id="1ceea-145">Använd genvägen InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="1ceea-145">Use the InvokeDefaultButton shortcut.</span></span>
4. <span data-ttu-id="1ceea-146">Använd Filtrera för att filtrera produktlistan i den valda kategorin.</span><span class="sxs-lookup"><span data-stu-id="1ceea-146">Use the Filter to filter the list of products in the selected category.</span></span>
5. <span data-ttu-id="1ceea-147">Välj det produktkort som du vill lägga till i rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-147">Select the product card that you want to add to the requisition.</span></span>
6. <span data-ttu-id="1ceea-148">Klicka på Lägg till på rader.</span><span class="sxs-lookup"><span data-stu-id="1ceea-148">Click Add to lines.</span></span>
7. <span data-ttu-id="1ceea-149">Ange ett nummer i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="1ceea-149">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="1ceea-150">I fältet Hitta anskaffningskategorinod skriver du den första delen av namnet på den kategori som du letar efter och klickar sedan på Enter.</span><span class="sxs-lookup"><span data-stu-id="1ceea-150">In the Find procurement category node field, type the first part of the name of the category that you are looking for, and then click Enter.</span></span>
    * <span data-ttu-id="1ceea-151">Till exempel typen Hög (överstrykningspennor).</span><span class="sxs-lookup"><span data-stu-id="1ceea-151">For example, type High (highlighters).</span></span>  
9. <span data-ttu-id="1ceea-152">Använd genvägen InvokeDefaultButton.</span><span class="sxs-lookup"><span data-stu-id="1ceea-152">Use the InvokeDefaultButton shortcut.</span></span>
10. <span data-ttu-id="1ceea-153">Klicka på Lägg till produkt som inte är listad till rader om du vill lägga till en produkt som inte finns med i anskaffningskatalogen.</span><span class="sxs-lookup"><span data-stu-id="1ceea-153">Click Add unlisted product to lines to add a product that’s not listed in the procurement catalogue.</span></span>
11. <span data-ttu-id="1ceea-154">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="1ceea-154">In the Product name field, type a value.</span></span>
12. <span data-ttu-id="1ceea-155">Skriv ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="1ceea-155">In the Unit field, type a value.</span></span>
13. <span data-ttu-id="1ceea-156">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1ceea-156">Click OK.</span></span>
14. <span data-ttu-id="1ceea-157">Ange en beskrivning av produkten i fältet Artikelbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="1ceea-157">In the Item description field, add a description of the product.</span></span>
15. <span data-ttu-id="1ceea-158">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="1ceea-158">In the Quantity field, enter a number.</span></span>
16. <span data-ttu-id="1ceea-159">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="1ceea-159">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="1ceea-160">Om du känner till priset för en viss leverantör (som du väljer i fältet Leverantörskonto), så kan du ange det priset.</span><span class="sxs-lookup"><span data-stu-id="1ceea-160">If you know the price for a particular vendor (that you select in the vendor account field) then that price can be entered</span></span>   
17. <span data-ttu-id="1ceea-161">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="1ceea-161">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1ceea-162">De leverantörer som är tillgängliga i det här fältet är beroende av inköpspolicyerna och den status som leverantören har för den aktuella anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="1ceea-162">The vendors that are available in this field depend on the purchasing policies and the status that the vendor has for the current procurement category.</span></span> <span data-ttu-id="1ceea-163">Som ett alternativ till att markera en leverantör här kan du klicka på knappen Föreslå leverantör.</span><span class="sxs-lookup"><span data-stu-id="1ceea-163">As an alternative to selecting a vendor here, you can click the Suggest vendor button.</span></span>    
18. <span data-ttu-id="1ceea-164">Välj den leverantör som du vill använda i listan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-164">In the list, select the vendor you want to use.</span></span>
19. <span data-ttu-id="1ceea-165">Skriv ett värde i fältet Externt artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="1ceea-165">In the External item number field, type a value.</span></span>
    * <span data-ttu-id="1ceea-166">Detta är ett referensnummer för den produkt som leverantören känner till.</span><span class="sxs-lookup"><span data-stu-id="1ceea-166">This is a reference number for the product that is known by the vendor.</span></span> <span data-ttu-id="1ceea-167">Detta kan exempelvis vara artikelnumret för produkten i leverantörens egen katalog.</span><span class="sxs-lookup"><span data-stu-id="1ceea-167">For example, this could be the item number of the product in the vendor's own catalogue.</span></span>  
20. <span data-ttu-id="1ceea-168">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="1ceea-168">Click OK.</span></span>

## <a name="distribute-amounts"></a><span data-ttu-id="1ceea-169">Fördela belopp</span><span class="sxs-lookup"><span data-stu-id="1ceea-169">Distribute amounts</span></span>
1. <span data-ttu-id="1ceea-170">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="1ceea-170">Click Financials.</span></span>
2. <span data-ttu-id="1ceea-171">Klicka på Fördela belopp.</span><span class="sxs-lookup"><span data-stu-id="1ceea-171">Click Distribute amounts.</span></span>
    * <span data-ttu-id="1ceea-172">I den här processen visas hur du fördelar kostnaden för den första raden mellan två konton.</span><span class="sxs-lookup"><span data-stu-id="1ceea-172">This process shows you how to distribute the cost for the first line between 2 accounts.</span></span> <span data-ttu-id="1ceea-173">Detta kan även göras vid ett senare tillfälle, när inköpsrekvisitionen granskas.</span><span class="sxs-lookup"><span data-stu-id="1ceea-173">This can also be done later when the requisition is in review.</span></span>  
3. <span data-ttu-id="1ceea-174">Klicka på Dela för att skapa en ny fördelningsrad.</span><span class="sxs-lookup"><span data-stu-id="1ceea-174">Click Split to create a new distribution line.</span></span>
4. <span data-ttu-id="1ceea-175">I fältet Huvudbokskonto väljer du det första kostnadsställe som ska ingå i kostnaden.</span><span class="sxs-lookup"><span data-stu-id="1ceea-175">In the Ledger account field select the first cost centre that should take part of the cost.</span></span>
5. <span data-ttu-id="1ceea-176">Välj den valda fördelningsraden.</span><span class="sxs-lookup"><span data-stu-id="1ceea-176">Select the other distribution line.</span></span>
6. <span data-ttu-id="1ceea-177">Ange det andra kostnadsstället i fältet Huvudbokskonto.</span><span class="sxs-lookup"><span data-stu-id="1ceea-177">In the Ledger account field specify the other cost centre.</span></span>
7. <span data-ttu-id="1ceea-178">Klicka på Fördela lika.</span><span class="sxs-lookup"><span data-stu-id="1ceea-178">Click Distribute equally.</span></span>
8. <span data-ttu-id="1ceea-179">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-179">Close the page.</span></span>

## <a name="view-line-details"></a><span data-ttu-id="1ceea-180">Visa raddetaljer</span><span class="sxs-lookup"><span data-stu-id="1ceea-180">View line details</span></span>
1. <span data-ttu-id="1ceea-181">Växla expanderingen av avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="1ceea-181">Toggle the expansion of the Line details section.</span></span>

## <a name="submit-the-requisition"></a><span data-ttu-id="1ceea-182">Skicka rekvisitionen</span><span class="sxs-lookup"><span data-stu-id="1ceea-182">Submit the requisition</span></span>
1. <span data-ttu-id="1ceea-183">Klicka på Arbetsflöde för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-183">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="1ceea-184">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="1ceea-184">Click Submit.</span></span>
3. <span data-ttu-id="1ceea-185">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-185">Close the page.</span></span>
4. <span data-ttu-id="1ceea-186">Skriv en notering för godkännaren av rekvisitionen i fältet Kommentar.</span><span class="sxs-lookup"><span data-stu-id="1ceea-186">In the Comment field, type a note for the approver of the requisition.</span></span>
5. <span data-ttu-id="1ceea-187">Klicka på Skicka.</span><span class="sxs-lookup"><span data-stu-id="1ceea-187">Click Submit.</span></span>
6. <span data-ttu-id="1ceea-188">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-188">Close the page.</span></span>
7. <span data-ttu-id="1ceea-189">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="1ceea-189">Refresh the page.</span></span>


