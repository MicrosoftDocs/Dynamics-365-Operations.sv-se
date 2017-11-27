--- 
title: "Ställ in en anskaffningskategorihierarki"
description: "I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess."
author: mkirknel
manager: AnnBe
ms.date: 11/06/2017
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
ms.sourcegitcommit: 6ad5c8552a6989e9093d0b1325754bc0f6d19372
ms.openlocfilehash: 4541d029c9c3be3ee42332e5d8ff183dd503f13e
ms.contentlocale: sv-se
ms.lasthandoff: 11/06/2017

---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="e776b-103">Ställ in en anskaffningskategorihierarki</span><span class="sxs-lookup"><span data-stu-id="e776b-103">Set up a procurement category hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e776b-104">I den här proceduren visas hur du skapar nya noder i en anskaffningskategorihierarki och hur du konfigurerar en anskaffningskategori som ska användas i en anskaffningsprocess.</span><span class="sxs-lookup"><span data-stu-id="e776b-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="e776b-105">Dessa uppgifter utförs vanligtvis av en inköpschef.</span><span class="sxs-lookup"><span data-stu-id="e776b-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="e776b-106">Innan du kan starta den här proceduren måste det finnas en kategorihierarki av typen anskaffning.</span><span class="sxs-lookup"><span data-stu-id="e776b-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="e776b-107">Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget.</span><span class="sxs-lookup"><span data-stu-id="e776b-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="e776b-108">Lägg till en ny anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="e776b-108">Add a new procurement category</span></span>
1. <span data-ttu-id="e776b-109">Gå till Anskaffning och källa > Anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="e776b-109">Go to Procurement and sourcing > Procurement categories.</span></span>
2. <span data-ttu-id="e776b-110">Klicka på Redigera kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="e776b-110">Click Edit category hierarchy.</span></span>
    * <span data-ttu-id="e776b-111">Den aktuella anskaffningskategorihierarkin visas till vänster på sidan.</span><span class="sxs-lookup"><span data-stu-id="e776b-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="e776b-112">Du är på väg att ändra hierarkin.</span><span class="sxs-lookup"><span data-stu-id="e776b-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="e776b-113">Klicka på Ny kategorinod.</span><span class="sxs-lookup"><span data-stu-id="e776b-113">Click New category node.</span></span>
    * <span data-ttu-id="e776b-114">Systemet väljer toppnoden som standard.</span><span class="sxs-lookup"><span data-stu-id="e776b-114">The system selects the top node by default.</span></span> <span data-ttu-id="e776b-115">Om du kör den här proceduren som en uppgiftsguide kan du klicka på fliken Lås upp och välja en annan överordnad nod att infoga den nya noden i.</span><span class="sxs-lookup"><span data-stu-id="e776b-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="e776b-116">Lås uppgifthandboken igen och klicka på noden Ny kategori när det är klart.</span><span class="sxs-lookup"><span data-stu-id="e776b-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="e776b-117">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e776b-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e776b-118">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="e776b-118">In the Description field, type a value.</span></span>
6. <span data-ttu-id="e776b-119">Skriv ett värde i fältet Eget namn.</span><span class="sxs-lookup"><span data-stu-id="e776b-119">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="e776b-120">Det egna namnet är valfritt.</span><span class="sxs-lookup"><span data-stu-id="e776b-120">The friendly name is optional.</span></span> <span data-ttu-id="e776b-121">Detta visas i kategorisökningar tillsammans med kategorinamnet.</span><span class="sxs-lookup"><span data-stu-id="e776b-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="e776b-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e776b-122">Click Save.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="e776b-123">Lägg till produkter i den nya anskaffningskategorin</span><span class="sxs-lookup"><span data-stu-id="e776b-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="e776b-124">Gå till Anskaffning och källa > Anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="e776b-124">Go to Procurement and sourcing > Procurement categories.</span></span>
    * <span data-ttu-id="e776b-125">Välj den nod som du precis lade till.</span><span class="sxs-lookup"><span data-stu-id="e776b-125">Select the node you just added.</span></span> <span data-ttu-id="e776b-126">Om du kör den här proceduren som en uppgiftsguide kanske du behöver låsa upp uppgiftsguiden för att välja noden.</span><span class="sxs-lookup"><span data-stu-id="e776b-126">If you’re running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="e776b-127">Växla expansionen av avsnittet Produkter.</span><span class="sxs-lookup"><span data-stu-id="e776b-127">Toggle the expansion of the Products section.</span></span>
3. <span data-ttu-id="e776b-128">Klicka på Lägg till i associerade produkter med anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-128">Click Add to associate products with the procurement category.</span></span>
4. <span data-ttu-id="e776b-129">Välj den produkt som du vill lägga till i anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-129">Select the product you want to add to the procurement category.</span></span>
5. <span data-ttu-id="e776b-130">Klicka på pilen för att välja produkten.</span><span class="sxs-lookup"><span data-stu-id="e776b-130">Click the arrow to select the product.</span></span>
6. <span data-ttu-id="e776b-131">Välj en annan produkt som du vill lägga till i anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-131">Select another product to add to the procurement category.</span></span>
7. <span data-ttu-id="e776b-132">Klicka på pilen för att välja produkten.</span><span class="sxs-lookup"><span data-stu-id="e776b-132">Click the arrow to select the product.</span></span>
8. <span data-ttu-id="e776b-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e776b-133">Click OK.</span></span>

## <a name="add-approved-and-preferred-vendors"></a><span data-ttu-id="e776b-134">Lägg till godkända och prioriterade leverantörer</span><span class="sxs-lookup"><span data-stu-id="e776b-134">Add approved and preferred vendors</span></span>
1. <span data-ttu-id="e776b-135">Växla utökningen av avsnittet Leverantörer.</span><span class="sxs-lookup"><span data-stu-id="e776b-135">Toggle the expansion of the Vendors section.</span></span>
2. <span data-ttu-id="e776b-136">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="e776b-136">Click Add.</span></span>
    * <span data-ttu-id="e776b-137">Du kan lägga till en leverantör i en anskaffningskategori och ange om en leverantör är prioriterad eller precis godkänd för kategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-137">You can add a vendor to a procurement category and specify whether a vendor is preferred or just approved for the category.</span></span> <span data-ttu-id="e776b-138">När du tar bort en leverantör från en kategori, tas historiska transaktioner med leverantör i kategorin inte bort.</span><span class="sxs-lookup"><span data-stu-id="e776b-138">When you delete a vendor from a category, the historical transactions with the vendor in the category are not deleted.</span></span>   
3. <span data-ttu-id="e776b-139">Sök efter den leverantör som du vill lägga till i kategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-139">Find the vendor you want to add to the category.</span></span>
4. <span data-ttu-id="e776b-140">Klicka på pilen för att välja leverantören.</span><span class="sxs-lookup"><span data-stu-id="e776b-140">Click the arrow to select the vendor.</span></span>
5. <span data-ttu-id="e776b-141">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e776b-141">Click OK.</span></span>
6. <span data-ttu-id="e776b-142">Välj den leverantörsrad som du vill ändra.</span><span class="sxs-lookup"><span data-stu-id="e776b-142">Select the vendor row that you want to modify.</span></span>
7. <span data-ttu-id="e776b-143">Välj ett alternativ i fältet Leverantörsstatus.</span><span class="sxs-lookup"><span data-stu-id="e776b-143">In the Vendor status field, select an option.</span></span>
    * <span data-ttu-id="e776b-144">Inställningen av leverantörsurval i kategoripolicyregeln styr om prioriterade, godkända eller alla leverantörer är tillgängliga på inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="e776b-144">The vendor selection setting in the Category policy rule governs whether preferred, approved, or all vendors are available on purchase requisitions.</span></span>   

## <a name="add-additional-information-to-the-category"></a><span data-ttu-id="e776b-145">Lägg till ytterligare information till kategorin</span><span class="sxs-lookup"><span data-stu-id="e776b-145">Add additional information to the category</span></span>
1. <span data-ttu-id="e776b-146">Växla expansionen av avsnittet Kriteriegrupper för leverantörsutvärdering.</span><span class="sxs-lookup"><span data-stu-id="e776b-146">Toggle the expansion of the Vendor evaluation criterion groups section.</span></span>
    * <span data-ttu-id="e776b-147">På den här fliken kan du definiera vilka kriterier som leverantörerna i anskaffningskategorin ska bedömas mot.</span><span class="sxs-lookup"><span data-stu-id="e776b-147">This tab allows you to define which criteria the vendors in the procurement category should be rated against.</span></span> <span data-ttu-id="e776b-148">Om du vill göra det måste du först klicka på Lägg till och sedan välja en leverantörsutvärderingsgrupp som innehåller de kriterier du vill använda.</span><span class="sxs-lookup"><span data-stu-id="e776b-148">To do this you would click Add and then select a vendor evaluation group that contains the criteria you want.</span></span>  
2. <span data-ttu-id="e776b-149">Växla utökningen av avsnittet Enkäter.</span><span class="sxs-lookup"><span data-stu-id="e776b-149">Toggle the expansion of the Questionnaires section.</span></span>
    * <span data-ttu-id="e776b-150">På den här fliken kan du lägga till enkäter som ska visas på rekvisitionen så länge som du har ställt in aktivitetstypen till ”Rekvisition”.</span><span class="sxs-lookup"><span data-stu-id="e776b-150">This tab allows you to add questionnaires that will appear on the requisition, as long as you set the Activity type to "Requisition".</span></span> <span data-ttu-id="e776b-151">Beställaren måste sedan fylla i ett frågeformulär innan han/hon skickar en rekvisition för den specifika produkten eller produkterna i anskaffningskategorin.</span><span class="sxs-lookup"><span data-stu-id="e776b-151">The requester then has to fill out a questionnaire before they submit a requisition for the specific product or products in the procurement category.</span></span>  
3. <span data-ttu-id="e776b-152">Växla expansionen av avsnittet Artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e776b-152">Toggle the expansion of the Item sales tax groups section.</span></span>
4. <span data-ttu-id="e776b-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e776b-153">In the Item sales tax group: field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e776b-154">Välj en momsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e776b-154">Select a sales tax group.</span></span>
6. <span data-ttu-id="e776b-155">Växla utökningen av avsnittet Kategorisida.</span><span class="sxs-lookup"><span data-stu-id="e776b-155">Toggle the expansion of the Category page section.</span></span>
    * <span data-ttu-id="e776b-156">Kategorisidor skapas på sidan Kategorihierarki.</span><span class="sxs-lookup"><span data-stu-id="e776b-156">Category pages are created in the Category hierarchy page.</span></span> <span data-ttu-id="e776b-157">De innehåller information om anskaffningskategorin, till exempel information om typen av produkter i en kategori, bilder av produkter i en kategori eller meddelanden som till exempel vilka rabatter som är tillgängliga i en kategori.</span><span class="sxs-lookup"><span data-stu-id="e776b-157">They contain information about the procurement category such as information about the type of products in a category, images of products in a category, or announcements such as the discounts that are available in a category.</span></span> <span data-ttu-id="e776b-158">Informationen på en kategorisida visas på inköpsrekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="e776b-158">The information in a category page is displayed on purchase requisitions.</span></span>  
7. <span data-ttu-id="e776b-159">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e776b-159">Close the page.</span></span>


