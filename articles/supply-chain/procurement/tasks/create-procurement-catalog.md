---
title: Skapa en anskaffningskatalog
description: Det här ämnet förklarar hur du skapar en anskaffningskatalog.
author: RichardLuan
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaf8b8d8b369aa704344d6984a0f111af6e4285b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016487"
---
# <a name="create-a-procurement-catalog"></a><span data-ttu-id="589a6-103">Skapa en anskaffningskatalog</span><span class="sxs-lookup"><span data-stu-id="589a6-103">Create a procurement catalog</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="589a6-104">Det här ämnet förklarar hur du skapar en anskaffningskatalog.</span><span class="sxs-lookup"><span data-stu-id="589a6-104">This topic explains how to create a procurement catalog.</span></span> <span data-ttu-id="589a6-105">Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="589a6-105">This task would typically be carried out by a procurement professional.</span></span> <span data-ttu-id="589a6-106">Du kan också lära dig om hur medarbetare kan använda katalogen när de skapar en rekvisition.</span><span class="sxs-lookup"><span data-stu-id="589a6-106">You will also learn how employees can use the catalog when they create a requisition.</span></span> <span data-ttu-id="589a6-107">Innan du kan skapa en katalog måste det finnas en anskaffningskategorihierarki i systemet.</span><span class="sxs-lookup"><span data-stu-id="589a6-107">Before you can create a catalog, there must be a procurement category hierarchy in your system.</span></span> <span data-ttu-id="589a6-108">Hierarkin ärvs från den nya katalogen, tillsammans med alla produkter som finns i hierarkin.</span><span class="sxs-lookup"><span data-stu-id="589a6-108">The hierarchy is inherited by the new catalog, along with all the products that are in the hierarchy.</span></span> <span data-ttu-id="589a6-109">Du kan använda den här handboken i demonstrationdataföretaget USMF, där anskaffningskategorihierarkin är tillgänglig, samt i exemplen som används i procedurstegen.</span><span class="sxs-lookup"><span data-stu-id="589a6-109">You can use this guide in demo data company USMF where the procurement category hierarchy is available, as well as the examples used in the procedure steps.</span></span>


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a><span data-ttu-id="589a6-110">Se till att en anskaffningskategorihierarki finns</span><span class="sxs-lookup"><span data-stu-id="589a6-110">Ensure that a procurement category hierarchy exists</span></span>
1. <span data-ttu-id="589a6-111">Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Anskaffningskategorier**.</span><span class="sxs-lookup"><span data-stu-id="589a6-111">Go to **navigation pane > Modules > Procurement and sourcing > Procurement categories**.</span></span> <span data-ttu-id="589a6-112">En anskaffningskategorihierarki är tillgänglig i demoföretaget USMF och produkter har lagts till i kategorin **kontorsmaskiner/datorer**.</span><span class="sxs-lookup"><span data-stu-id="589a6-112">A procurement category hierarchy is available in the USMF demo data company and products have been added to the **Office machines/Computers** category.</span></span> <span data-ttu-id="589a6-113">Om du kör den här proceduren som en uppgiftsguide måste du låsa upp guiden om du vill bläddra genom kategorin.</span><span class="sxs-lookup"><span data-stu-id="589a6-113">If you're running this procedure as a task guide, you'll need to unlock the guide if you want to browse through the category.</span></span> <span data-ttu-id="589a6-114">Om en hierarki inte är tillgänglig kan du skapa den genom att klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="589a6-114">If a hierarchy was not available, you'd create it by clicking **New**.</span></span> <span data-ttu-id="589a6-115">Detta kan bara göras en gång.</span><span class="sxs-lookup"><span data-stu-id="589a6-115">This can only be done once.</span></span>  
2. <span data-ttu-id="589a6-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="589a6-116">Close the page.</span></span>

## <a name="create-a-catalog"></a><span data-ttu-id="589a6-117">Skapa en katalog</span><span class="sxs-lookup"><span data-stu-id="589a6-117">Create a catalog</span></span>
1. <span data-ttu-id="589a6-118">Gå till **Navigeringsfönstret > Moduler > Anskaffning och källa > Kataloger >Anskaffningskataloger**.</span><span class="sxs-lookup"><span data-stu-id="589a6-118">Go to **navigation pane > Modules > Procurement and sourcing > Catalogs > Procurement catalogs**.</span></span>
2. <span data-ttu-id="589a6-119">Välj **Ny anskaffningskatalog** om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="589a6-119">Select **New procurement catalog** to open the drop dialog.</span></span>
3. <span data-ttu-id="589a6-120">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="589a6-120">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="589a6-121">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="589a6-121">Select **OK**.</span></span>
5. <span data-ttu-id="589a6-122">Expandera **ANSKAFFNINGSKATEGORIER FÖR FÖRETAG** i trädet.</span><span class="sxs-lookup"><span data-stu-id="589a6-122">In the tree, expand **CORP PROCUREMENT CATEGORIES**.</span></span>
6. <span data-ttu-id="589a6-123">Expandera **KONTORSMASKINER** i trädet.</span><span class="sxs-lookup"><span data-stu-id="589a6-123">In the tree, expand **OFFICE MACHINES**.</span></span>
7. <span data-ttu-id="589a6-124">Välj **Datorer** i trädet.</span><span class="sxs-lookup"><span data-stu-id="589a6-124">In the tree, select **Computers**.</span></span>

  - <span data-ttu-id="589a6-125">Produkterna från anskaffningkategorin visas i listan.</span><span class="sxs-lookup"><span data-stu-id="589a6-125">The products from the procurement category are displayed in the list.</span></span> <span data-ttu-id="589a6-126">Om du vill lägga till en produkt till en kategori måste du göra detta på sidan **Anskaffningskategorihierarki** eller på sidan **Artikeldetaljer**.</span><span class="sxs-lookup"><span data-stu-id="589a6-126">If you want to add a product to the category you need to do this on the **Procurement category hierarchy** page or on the **Item details** page.</span></span>  
  - <span data-ttu-id="589a6-127">**Standard**-uppdateringstypen bestämmer om nya produkter som har lagts till i anskaffningskategorihierarkin omedelbart är synliga i katalogen.</span><span class="sxs-lookup"><span data-stu-id="589a6-127">The **Default** update type determines whether new products that have been added to the procurement category hierarchy are immediately visible in the catalog.</span></span> <span data-ttu-id="589a6-128">Om uppdateringstypen är inställd på **Dynamisk** kommer ändringar att synas på en gång.</span><span class="sxs-lookup"><span data-stu-id="589a6-128">If the update type is set to **Dynamic**, changes are visible immediately.</span></span> <span data-ttu-id="589a6-129">Om uppdateringstypen är **Statisk** är nya produkter endast synliga för personer som använder katalogen efter att katalogen har publicerats igen.</span><span class="sxs-lookup"><span data-stu-id="589a6-129">If the update type is **Static**, new products are only visible to people using the catalog after the catalog has been re-published.</span></span> <span data-ttu-id="589a6-130">Åtgärden **Publicera** är tillgänglig i åtgärdsfönstret överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="589a6-130">The **Publish** action is available on the Action Pane at the top of the page.</span></span> <span data-ttu-id="589a6-131">Om produkter tas bort från anskaffningskategorihierarkin är ändringen omedelbart synlig oavsett värdet i fältet **Standard**-uppdateringtyp.</span><span class="sxs-lookup"><span data-stu-id="589a6-131">If products are removed from the procurement category hierarchy, the change is immediately visible, regardless of the value in the **Default** update type field.</span></span>  

8. <span data-ttu-id="589a6-132">I åtgärdsfönstret, välj **kategorinavigering** och se till att **aktivera** är markerad.</span><span class="sxs-lookup"><span data-stu-id="589a6-132">On the Action Pane, select **Category navigation** and ensure that **Enable** is selected.</span></span>
9. <span data-ttu-id="589a6-133">Välj **Aktivera katalog**.</span><span class="sxs-lookup"><span data-stu-id="589a6-133">Select **Activate catalog**.</span></span>
10. <span data-ttu-id="589a6-134">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="589a6-134">Close the page.</span></span>

## <a name="make-the-catalog-visible"></a><span data-ttu-id="589a6-135">Gör katalogen synlig</span><span class="sxs-lookup"><span data-stu-id="589a6-135">Make the catalog visible</span></span>
1. <span data-ttu-id="589a6-136">Gå till **navigeringsfönster > moduler > anskaffning och källa > inställningar > principer > inköpspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="589a6-136">Go to **navigation pane > Modules > Procurement and sourcing > Setup > Policies > Purchasing policies**.</span></span>
2. <span data-ttu-id="589a6-137">Välj **anskaffningspolicy USMF**.</span><span class="sxs-lookup"><span data-stu-id="589a6-137">Select **Procurement Policy USMF**.</span></span> <span data-ttu-id="589a6-138">Du måste välja inköpspolicyn för den juridiska person som arbetaren kopplade till din användarprofil, som tillåter att beställa in produkter.</span><span class="sxs-lookup"><span data-stu-id="589a6-138">You need to select the purchasing policy for the legal entity that the worker connected to your user profile is allowed to order products in.</span></span> <span data-ttu-id="589a6-139">I USMF-demonstrationdatan är användaren Admin kopplad till arbetaren som kallas **Julia Funderburk**, och hon beställer produkter i USMF som standard.</span><span class="sxs-lookup"><span data-stu-id="589a6-139">In the USMF demo data, the Admin user is connected to the worker called **Julia Funderburk**, and she orders products in USMF by default.</span></span>  
3. <span data-ttu-id="589a6-140">Välj katalogen som du nyss skapat.</span><span class="sxs-lookup"><span data-stu-id="589a6-140">Select the catalog that you've just created.</span></span>
4. <span data-ttu-id="589a6-141">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="589a6-141">Select **OK**.</span></span>

## <a name="use-the-catalog"></a><span data-ttu-id="589a6-142">Använd katalogen</span><span class="sxs-lookup"><span data-stu-id="589a6-142">Use the catalog</span></span>
1. <span data-ttu-id="589a6-143">Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsrekvisitioner > Alla inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="589a6-143">Go to **navigation pane > Modules > Procurement and sourcing > Purchase requisitions > All purchase requisitions**.</span></span>
2. <span data-ttu-id="589a6-144">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="589a6-144">Select **New**.</span></span>
3. <span data-ttu-id="589a6-145">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="589a6-145">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="589a6-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="589a6-146">Select **OK**.</span></span>
5. <span data-ttu-id="589a6-147">Välj **Lägg till produkter**.</span><span class="sxs-lookup"><span data-stu-id="589a6-147">Select **Add products**.</span></span>
6. <span data-ttu-id="589a6-148">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="589a6-148">In the list, find and select the desired record.</span></span> <span data-ttu-id="589a6-149">Du kan använda kategorihierarkin till vänster eller filtret högst upp i listan om du vill filtrera.</span><span class="sxs-lookup"><span data-stu-id="589a6-149">You can use the category hierarchy on the left or the filter at the top of the list to filter the products.</span></span>  
7. <span data-ttu-id="589a6-150">Välj **Lägg till på rader**.</span><span class="sxs-lookup"><span data-stu-id="589a6-150">Select **Add to lines**.</span></span>
8. <span data-ttu-id="589a6-151">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="589a6-151">Select **OK**.</span></span>

