---
title: Skapa en arbetsgrupp för legotillverkning för lean manufacturing
description: Om du vill modellera legotillverkningsarbete för lean manufacturing måste du skapa en arbetsgrupp som är kopplad till den leverantör som tillhandahåller arbetet.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2bc1e8551bbebd11cad18d47f9e74a2dedcb908d
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983336"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="b3531-103">Skapa en arbetsgrupp för legotillverkning för lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="b3531-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3531-104">Om du vill modellera legotillverkningsarbete för lean manufacturing måste du skapa en arbetsgrupp som är kopplad till den leverantör som tillhandahåller arbetet.</span><span class="sxs-lookup"><span data-stu-id="b3531-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="b3531-105">En arbetsgrupp för legotillverkning är kopplad till leverantören genom associationen med en resurs av typen Leverantör.</span><span class="sxs-lookup"><span data-stu-id="b3531-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="b3531-106">Om du spelar upp den här inspelningen i demonstrationsföretaget USMF kan du välja leverantörskonto-ID 1002 och plats 1.</span><span class="sxs-lookup"><span data-stu-id="b3531-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="b3531-107">Skapa en leverantörsresurs</span><span class="sxs-lookup"><span data-stu-id="b3531-107">Create a vendor resource</span></span>
1. <span data-ttu-id="b3531-108">Gå till Resurser.</span><span class="sxs-lookup"><span data-stu-id="b3531-108">Go to Resources.</span></span>
2. <span data-ttu-id="b3531-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b3531-109">Click New.</span></span>
3. <span data-ttu-id="b3531-110">Ange ett värde i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="b3531-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="b3531-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b3531-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b3531-112">Välj Leverantör i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="b3531-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="b3531-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantör.</span><span class="sxs-lookup"><span data-stu-id="b3531-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="b3531-114">Skapa resursgruppen</span><span class="sxs-lookup"><span data-stu-id="b3531-114">Create the resource group</span></span>
1. <span data-ttu-id="b3531-115">Gå till Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="b3531-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="b3531-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b3531-116">Click New.</span></span>
3. <span data-ttu-id="b3531-117">Skriv ett värde i fältet Resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="b3531-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="b3531-118">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b3531-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b3531-119">Öppna sökningen genom att klicka på listruteknappen i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="b3531-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b3531-120">Välj den plats som arbetsgruppen ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="b3531-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="b3531-121">I teorin kan en plats representera en enskild plats som drivs av en leverantör.</span><span class="sxs-lookup"><span data-stu-id="b3531-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="b3531-122">Men i de flesta fall allokeras resurser på entreprenad bara till den plats som beställer entreprenadarbetet.</span><span class="sxs-lookup"><span data-stu-id="b3531-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="b3531-123">Observera att inkommande och utgående lagerställen för arbetsgrupper för legotillverkning måste finnas på samma plats.</span><span class="sxs-lookup"><span data-stu-id="b3531-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="b3531-124">Ange ett värde i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="b3531-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="b3531-125">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="b3531-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="b3531-126">Markera eller avmarkera kryssrutan Arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b3531-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="b3531-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inleveranslagerställe.</span><span class="sxs-lookup"><span data-stu-id="b3531-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b3531-128">Välj lagerstället och platsen som används för att mellanlagra materialet för arbetsgruppen som hanteras av leverantören.</span><span class="sxs-lookup"><span data-stu-id="b3531-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="b3531-129">I de flesta fall modelleras lagerstället och platsen genom att använda ett separat lagerställe per leverantör och ett lagerställe per arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b3531-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="b3531-130">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats för inleverans.</span><span class="sxs-lookup"><span data-stu-id="b3531-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="b3531-131">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveranslagerställe.</span><span class="sxs-lookup"><span data-stu-id="b3531-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b3531-132">Ange lagerstället och platsen där materialet bokförs när arbetsgruppens legotillverkningsaktiviteter bokförs.</span><span class="sxs-lookup"><span data-stu-id="b3531-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="b3531-133">Lagerstället och platsen kan finnas på leverantörens plats om leverantören rapporterar kanban-jobb.</span><span class="sxs-lookup"><span data-stu-id="b3531-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="b3531-134">Alternativt kan vara lagerstället och platsen vara inleveransplatsen som hör till nästa steg i produktionsflödet.</span><span class="sxs-lookup"><span data-stu-id="b3531-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="b3531-135">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveransplats.</span><span class="sxs-lookup"><span data-stu-id="b3531-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="b3531-136">Utöka eller komprimera avsnittet Kalendrar.</span><span class="sxs-lookup"><span data-stu-id="b3531-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="b3531-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b3531-137">Click Add.</span></span>
15. <span data-ttu-id="b3531-138">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.</span><span class="sxs-lookup"><span data-stu-id="b3531-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b3531-139">Associera arbetsgruppens arbetstidskalender till resursgruppen.</span><span class="sxs-lookup"><span data-stu-id="b3531-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="b3531-140">För viktiga resurser rekommenderar vi att du definierar specifika kalendrar som motsvarar exakta arbetstider och relaterade kapaciteter för arbetsgrupp eller leverantörsplats.</span><span class="sxs-lookup"><span data-stu-id="b3531-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="b3531-141">Expandera eller komprimera avsnittet Resurser.</span><span class="sxs-lookup"><span data-stu-id="b3531-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="b3531-142">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b3531-142">Click Add.</span></span>
    * <span data-ttu-id="b3531-143">En legotillverkningsresursgrupp måste ha en associerad resurs av typen Leverantör som länkar resursgruppen till leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="b3531-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="b3531-144">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Resurs.</span><span class="sxs-lookup"><span data-stu-id="b3531-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b3531-145">Välj eller ange leverantörsresursen som du skapade i föregående underuppgift.</span><span class="sxs-lookup"><span data-stu-id="b3531-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="b3531-146">Expandera eller komprimera avsnittet Kapacitet för arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="b3531-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="b3531-147">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="b3531-147">Click Add.</span></span>
    * <span data-ttu-id="b3531-148">En arbetsgrupp måste ha en definierad kapacitet.</span><span class="sxs-lookup"><span data-stu-id="b3531-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="b3531-149">I det här exemplet ska vi skapa en genomflödeskapacitet på 100 stycken per vanlig arbetsdag.</span><span class="sxs-lookup"><span data-stu-id="b3531-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="b3531-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsflödesmodell.</span><span class="sxs-lookup"><span data-stu-id="b3531-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="b3531-151">Markera ett alternativ i fältet Kapacitetsperiod.</span><span class="sxs-lookup"><span data-stu-id="b3531-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="b3531-152">Ange ett värde i fältet Genomsnittlig genomflödeskvantitet.</span><span class="sxs-lookup"><span data-stu-id="b3531-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="b3531-153">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="b3531-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="b3531-154">ResolveChanges enheten.</span><span class="sxs-lookup"><span data-stu-id="b3531-154">ResolveChanges the Unit.</span></span>

