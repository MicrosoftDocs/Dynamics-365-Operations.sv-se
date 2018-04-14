---
title: "Skapa en ny layout för lagerställe"
description: "I den här proceduren visas hur du ställer in information om platserna i ett lagerställe."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4a9c75bf84bf2bf8d92be23573cc0477209c2378
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="179cd-103">Skapa en ny layout för lagerställe</span><span class="sxs-lookup"><span data-stu-id="179cd-103">Create a new warehouse layout</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="179cd-104">I den här proceduren visas hur du ställer in information om platserna i ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="179cd-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="179cd-105">Detta gäller endast lagerställen som skapats med hjälp av ”grundläggande lagerstyrning” i lagerhanteringmodulen och inte för lagerställen som skapats i lagerstyrningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="179cd-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="179cd-106">Du kan använda den här proceduren i demonstrationsföretaget USMF eller med dina egna data.</span><span class="sxs-lookup"><span data-stu-id="179cd-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="179cd-107">Ange standardplatskapaciteten</span><span class="sxs-lookup"><span data-stu-id="179cd-107">Set the default location capacity</span></span>
1. <span data-ttu-id="179cd-108">Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="179cd-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="179cd-109">Klicka på fliken Platser.</span><span class="sxs-lookup"><span data-stu-id="179cd-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="179cd-110">Välj ett nummer i fältet Standardbredd.</span><span class="sxs-lookup"><span data-stu-id="179cd-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="179cd-111">Välj ett nummer i fältet Standarddjup.</span><span class="sxs-lookup"><span data-stu-id="179cd-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="179cd-112">Välj ett nummer i fältet Standardhöjd.</span><span class="sxs-lookup"><span data-stu-id="179cd-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="179cd-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="179cd-113">Click Save.</span></span>
7. <span data-ttu-id="179cd-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="179cd-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="179cd-115">Definiera platsnamnformatet</span><span class="sxs-lookup"><span data-stu-id="179cd-115">Define the location name format</span></span>
1. <span data-ttu-id="179cd-116">Gå till Lagerhantering > Inställningar > Lagerindelning > Lagerställen.</span><span class="sxs-lookup"><span data-stu-id="179cd-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="179cd-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="179cd-117">Click New.</span></span>
3. <span data-ttu-id="179cd-118">Ange ett värde i fältet Lagerställe.</span><span class="sxs-lookup"><span data-stu-id="179cd-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="179cd-119">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="179cd-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="179cd-120">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="179cd-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="179cd-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="179cd-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="179cd-122">Växla utökningen av avsnittet Platsnamn.</span><span class="sxs-lookup"><span data-stu-id="179cd-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="179cd-123">Alternativen i detta avsnitt definierar standardformatet på platsnamn.</span><span class="sxs-lookup"><span data-stu-id="179cd-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="179cd-124">I vårt exempel ska vi inkludera gångnummer, ställningsnummer och hyllnummer.</span><span class="sxs-lookup"><span data-stu-id="179cd-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="179cd-125">Ange alternativet Inkludera gång som Ja.</span><span class="sxs-lookup"><span data-stu-id="179cd-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="179cd-126">Ange alternativet Inkludera ställning som Ja.</span><span class="sxs-lookup"><span data-stu-id="179cd-126">Set the Include rack option to Yes.</span></span>
10. <span data-ttu-id="179cd-127">I fältet Format skriver du in ett värde för ställningen.</span><span class="sxs-lookup"><span data-stu-id="179cd-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="179cd-128">Exempel: -##</span><span class="sxs-lookup"><span data-stu-id="179cd-128">For example: -##</span></span>  
11. <span data-ttu-id="179cd-129">Ange alternativet Inkludera hylla som Ja.</span><span class="sxs-lookup"><span data-stu-id="179cd-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="179cd-130">I fältet Format skriver du in ett värde för hyllan.</span><span class="sxs-lookup"><span data-stu-id="179cd-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="179cd-131">Exempel: -##</span><span class="sxs-lookup"><span data-stu-id="179cd-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="179cd-132">Definiera lagerställesplatser</span><span class="sxs-lookup"><span data-stu-id="179cd-132">Define warehouse locations</span></span>
1. <span data-ttu-id="179cd-133">Klicka på Lagerställe i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="179cd-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="179cd-134">Klicka på Platsguide.</span><span class="sxs-lookup"><span data-stu-id="179cd-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="179cd-135">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-135">Click Next.</span></span>
4. <span data-ttu-id="179cd-136">Avmarkera alternativet Utlastningsplatser</span><span class="sxs-lookup"><span data-stu-id="179cd-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="179cd-137">Avmarkera alternativet Bulkplatser</span><span class="sxs-lookup"><span data-stu-id="179cd-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="179cd-138">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-138">Click Next.</span></span>
7. <span data-ttu-id="179cd-139">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-139">Click Next.</span></span>
8. <span data-ttu-id="179cd-140">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-140">Click Next.</span></span>
9. <span data-ttu-id="179cd-141">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-141">Click Next.</span></span>
10. <span data-ttu-id="179cd-142">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-142">Click Next.</span></span>
11. <span data-ttu-id="179cd-143">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-143">Click Next.</span></span>
12. <span data-ttu-id="179cd-144">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-144">Click Next.</span></span>
    * <span data-ttu-id="179cd-145">Observera att de fysiska dimensionerna som visas på den här sidan är dem som du angett i början av den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="179cd-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="179cd-146">Klicka på Nästa.</span><span class="sxs-lookup"><span data-stu-id="179cd-146">Click Next.</span></span>
14. <span data-ttu-id="179cd-147">Klicka på Avsluta.</span><span class="sxs-lookup"><span data-stu-id="179cd-147">Click Finish.</span></span>
15. <span data-ttu-id="179cd-148">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="179cd-148">Close the page.</span></span>
16. <span data-ttu-id="179cd-149">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="179cd-149">Refresh the page.</span></span>

