--- 
title: Skapa en anskaffningskatalog
description: "Den här guiden visar hur du skapar en anskaffningskatalog."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 071b73b3498bdb346f5916a770a43174ef896568
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="fe596-103">Skapa en anskaffningskatalog</span><span class="sxs-lookup"><span data-stu-id="fe596-103">Create a procurement catalog</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fe596-104">Den här guiden visar hur du skapar en anskaffningskatalog.</span><span class="sxs-lookup"><span data-stu-id="fe596-104">This guide shows you how to create a procurement catalog.</span></span> <span data-ttu-id="fe596-105">Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="fe596-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="fe596-106">Du kan också lära dig om hur medarbetare kan använda katalogen när de skapar en rekvisition.</span><span class="sxs-lookup"><span data-stu-id="fe596-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="fe596-107">Innan du kan skapa en katalog måste det finnas en anskaffningskategorihierarki i systemet.</span><span class="sxs-lookup"><span data-stu-id="fe596-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="fe596-108">Hierarkin ärvs från den nya katalogen, tillsammans med alla produkter som finns i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="fe596-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="fe596-109">Du kan använda den här handboken i demonstrationdataföretaget USMF, där anskaffningskategorihierarkin är tillgänglig, samt i exemplen som används i procedurstegen.</span><span class="sxs-lookup"><span data-stu-id="fe596-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="fe596-110">Se till att en anskaffningskategorihierarki finns</span><span class="sxs-lookup"><span data-stu-id="fe596-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="fe596-111">Gå till Anskaffning och källa > Anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="fe596-111">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="fe596-112">En anskaffningskategorihierarki är tillgänglig i demoföretaget USMF och produkter har lagts till i kategorin kontorsmaskiner/datorer.</span><span class="sxs-lookup"><span data-stu-id="fe596-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the Office machines/Computers category.</span></span> <span data-ttu-id="fe596-113">Om du kör den här proceduren som en uppgiftsguide måste du låsa upp guiden om du vill bläddra genom kategorin.</span><span class="sxs-lookup"><span data-stu-id="fe596-113">If you’re running this procedure as a task guide, you’ll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="fe596-114">Om en hierarki inte är tillgänglig kan du skapa den genom att klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fe596-114">If a hierarchy was not available, you’d create it by clicking New.</span></span> <span data-ttu-id="fe596-115">Detta kan bara göras en gång.</span><span class="sxs-lookup"><span data-stu-id="fe596-115">This can only be done once.</span></span>  
2. <span data-ttu-id="fe596-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fe596-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="fe596-117">Skapa en katalog</span><span class="sxs-lookup"><span data-stu-id="fe596-117">Create a catalog</span></span>
1. <span data-ttu-id="fe596-118">Gå till Anskaffning och källa > Kataloger > Anskaffningskataloger.</span><span class="sxs-lookup"><span data-stu-id="fe596-118">Go to Procurement and sourcing > Catalogs > Procurement catalogs.</span></span>
2. <span data-ttu-id="fe596-119">Klicka på Ny anskaffningskatalog om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="fe596-119">Click New procurement catalog to open the drop dialog.</span></span>
3. <span data-ttu-id="fe596-120">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="fe596-120">In the Name field, type a value.</span></span>
4. <span data-ttu-id="fe596-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fe596-121">Click OK.</span></span>
5. <span data-ttu-id="fe596-122">Expandera ”ANSKAFFNINGSKATEGORIER FÖR FÖRETAG" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fe596-122">In the tree, expand 'CORP PROCUREMENT CATEGORIES'.</span></span>
6. <span data-ttu-id="fe596-123">Expandera "KONTORSMASKINER" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fe596-123">In the tree, expand 'OFFICE MACHINES'.</span></span>
7. <span data-ttu-id="fe596-124">Välj "Datorer" i trädet.</span><span class="sxs-lookup"><span data-stu-id="fe596-124">In the tree, select 'Computers'.</span></span>
    * <span data-ttu-id="fe596-125">Produkterna från anskaffningkategorin visas i listan.</span><span class="sxs-lookup"><span data-stu-id="fe596-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="fe596-126">Om du vill lägga till en produkt till en kategori måste du göra detta på sidan Anskaffningskategorihierarki eller på sidan Artikeldetaljer.</span><span class="sxs-lookup"><span data-stu-id="fe596-126">If you want to add a product to the category you need to do this on the Procurement category hierarchy page or on the Item details page.</span></span>  
    * <span data-ttu-id="fe596-127">Standarduppdateringstypen bestämmer om nya produkter som har lagts till i anskaffningskategorihierarkin omedelbart är synliga i katalogen.</span><span class="sxs-lookup"><span data-stu-id="fe596-127">The Default update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="fe596-128">Om uppdateringstypen är inställd på Dynamisk kommer ändringar att synas på en gång.</span><span class="sxs-lookup"><span data-stu-id="fe596-128">If the update type is set to Dynamic, changes are visible immediately.</span></span> <span data-ttu-id="fe596-129">Om uppdateringstypen är Statisk är nya produkter endast synliga för personer som använder katalogen efter att katalogen har publicerats igen.</span><span class="sxs-lookup"><span data-stu-id="fe596-129">If the update type is Static, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="fe596-130">Åtgärden Publicera är tillgänglig i åtgärdsfönstret överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="fe596-130">The Publish action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="fe596-131">Om produkter tas bort från anskaffningskategorihierarkin är ändringen omedelbart synlig oavsett värdet i fältet Standarduppdateringtyp.</span><span class="sxs-lookup"><span data-stu-id="fe596-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the Default update type field.</span></span>  
8. <span data-ttu-id="fe596-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fe596-132">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="fe596-133">Klicka på Dölj.</span><span class="sxs-lookup"><span data-stu-id="fe596-133">Click Hide.</span></span>
10. <span data-ttu-id="fe596-134">Klicka på Kategorinavigering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fe596-134">On the Action Pane, click Category navigation.</span></span>
11. <span data-ttu-id="fe596-135">Klicka på Avaktivera.</span><span class="sxs-lookup"><span data-stu-id="fe596-135">Click Disable.</span></span>
12. <span data-ttu-id="fe596-136">Klicka på Kategorinavigering i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fe596-136">On the Action Pane, click Category navigation.</span></span>
13. <span data-ttu-id="fe596-137">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="fe596-137">Click Enable.</span></span>
14. <span data-ttu-id="fe596-138">Klicka på Aktivera katalog.</span><span class="sxs-lookup"><span data-stu-id="fe596-138">Click Activate catalog.</span></span>
15. <span data-ttu-id="fe596-139">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fe596-139">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="fe596-140">Gör katalogen synlig</span><span class="sxs-lookup"><span data-stu-id="fe596-140">Make the catalog visible</span></span>
1. <span data-ttu-id="fe596-141">Gå till anskaffning och källa > Inställningar > Policyer > Inköpspolicyer.</span><span class="sxs-lookup"><span data-stu-id="fe596-141">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="fe596-142">Välj anskaffningspolicy USMF.</span><span class="sxs-lookup"><span data-stu-id="fe596-142">Select Procurement Policy USMF.</span></span>
    * <span data-ttu-id="fe596-143">Du måste välja inköpspolicyn för den juridiska person som arbetaren kopplade till din användarprofil, som tillåter att beställa in produkter.</span><span class="sxs-lookup"><span data-stu-id="fe596-143">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="fe596-144">I USMF-demonstrationdatan är användaren Admin kopplad till arbetaren som kallas Julia Funderburk, och hon beställer produkter i USMF som standard.</span><span class="sxs-lookup"><span data-stu-id="fe596-144">In the USMF demo data, the Admin user is connected to the worker called Julia Funderburk, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="fe596-145">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fe596-145">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="fe596-146">Välj katalogen som du nyss skapat.</span><span class="sxs-lookup"><span data-stu-id="fe596-146">Select the catalog that you’ve just created.</span></span>
5. <span data-ttu-id="fe596-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fe596-147">Click OK.</span></span>
6. <span data-ttu-id="fe596-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fe596-148">Close the page.</span></span>
7. <span data-ttu-id="fe596-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="fe596-149">Close the page.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="fe596-150">Använd katalogen</span><span class="sxs-lookup"><span data-stu-id="fe596-150">Use the catalog</span></span>
1. <span data-ttu-id="fe596-151">Gå till Anskaffning och källa > Inköpsrekvisitioner > Alla inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="fe596-151">Go to Procurement and sourcing > Purchase requisitions > All purchase requisitions.</span></span>
2. <span data-ttu-id="fe596-152">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fe596-152">Click New.</span></span>
3. <span data-ttu-id="fe596-153">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="fe596-153">In the Name field, type a value.</span></span>
4. <span data-ttu-id="fe596-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fe596-154">Click OK.</span></span>
5. <span data-ttu-id="fe596-155">Klicka på Lägg till produkter.</span><span class="sxs-lookup"><span data-stu-id="fe596-155">Click Add products.</span></span>
6. <span data-ttu-id="fe596-156">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fe596-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fe596-157">Du kan använda kategorihierarkin till vänster eller filtret högst upp i listan om du vill filtrera).</span><span class="sxs-lookup"><span data-stu-id="fe596-157">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="fe596-158">Klicka på Lägg till på rader.</span><span class="sxs-lookup"><span data-stu-id="fe596-158">Click Add to lines.</span></span>
8. <span data-ttu-id="fe596-159">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fe596-159">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="fe596-160">Klicka på Lägg till på rader.</span><span class="sxs-lookup"><span data-stu-id="fe596-160">Click Add to lines.</span></span>
10. <span data-ttu-id="fe596-161">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="fe596-161">Click OK.</span></span>


