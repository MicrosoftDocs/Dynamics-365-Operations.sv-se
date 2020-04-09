---
title: Skapa en strukturlista för en dimensionsbaserad produktmall
description: För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: de62c246e022a315852f9b1b21f3378b3408a00f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150181"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="abd0b-103">Skapa en strukturlista för en dimensionsbaserad produktmall</span><span class="sxs-lookup"><span data-stu-id="abd0b-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abd0b-104">För den här proceduren bör du ha slutfört de tidigare 4 guiderna i denna sekvens av åtta inspelningar.</span><span class="sxs-lookup"><span data-stu-id="abd0b-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="abd0b-105">De första 4 inspelningarna anger de data som krävs för att slutföra den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="abd0b-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="abd0b-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="abd0b-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="abd0b-107">Denna uppgift utförs vanligtvis av produktdesignern.</span><span class="sxs-lookup"><span data-stu-id="abd0b-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="abd0b-108">Välj produkten</span><span class="sxs-lookup"><span data-stu-id="abd0b-108">Select the product</span></span>
1. <span data-ttu-id="abd0b-109">Klicka på Underhåll av frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="abd0b-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="abd0b-110">Klicka på Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="abd0b-110">Click Released products.</span></span>
3. <span data-ttu-id="abd0b-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="abd0b-112">Hitta den frisläppta produktmallen med dimensionsbaserad konfigurationsteknologi som du skapade i den första uppgiftsguiden i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="abd0b-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="abd0b-113">Klicka på Konstruera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="abd0b-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="abd0b-114">Klicka på Strukturlisteversioner.</span><span class="sxs-lookup"><span data-stu-id="abd0b-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="abd0b-115">Skapa en ny strukturlista och strukturlisteversion</span><span class="sxs-lookup"><span data-stu-id="abd0b-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="abd0b-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="abd0b-116">Click New.</span></span>
2. <span data-ttu-id="abd0b-117">Klicka på strukturlista och strukturlisteversion.</span><span class="sxs-lookup"><span data-stu-id="abd0b-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="abd0b-118">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="abd0b-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="abd0b-119">Ange en site</span><span class="sxs-lookup"><span data-stu-id="abd0b-119">Setting a site</span></span>  
    * <span data-ttu-id="abd0b-120">I den här proceduren anger vi inte en specifik site för strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="abd0b-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="abd0b-121">Click OK.</span></span>
5. <span data-ttu-id="abd0b-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="abd0b-122">Click New.</span></span>
    * <span data-ttu-id="abd0b-123">I den här proceduren kommer vi att lägga till fyra rader i strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="abd0b-124">Två rader representerar kabelalternativ, och två rader representerar skåpalternativ.</span><span class="sxs-lookup"><span data-stu-id="abd0b-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="abd0b-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="abd0b-126">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="abd0b-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-127">Välj artikelnummer A0001, HDMI 6 tums kablar.</span><span class="sxs-lookup"><span data-stu-id="abd0b-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="abd0b-128">Ange eller välj ett värde i fältet Konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="abd0b-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-129">Välj kabelkonfigurationsgruppen som skapas i guide 4 i denna sekvens.</span><span class="sxs-lookup"><span data-stu-id="abd0b-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="abd0b-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="abd0b-130">Click New.</span></span>
    * <span data-ttu-id="abd0b-131">Välj artikelnummer A0002, HDMI 12 tums kablar.</span><span class="sxs-lookup"><span data-stu-id="abd0b-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="abd0b-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="abd0b-133">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="abd0b-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="abd0b-134">Ange eller välj ett värde i fältet Konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="abd0b-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-135">Markera Kabelkonfigurationsgruppen igen.</span><span class="sxs-lookup"><span data-stu-id="abd0b-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="abd0b-136">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="abd0b-136">Click New.</span></span>
14. <span data-ttu-id="abd0b-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="abd0b-138">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="abd0b-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-139">Välj artikelnummer D0002 Skåp.</span><span class="sxs-lookup"><span data-stu-id="abd0b-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="abd0b-140">Ange eller välj ett värde i fältet Konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="abd0b-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-141">Välj Skåpkonfigurationsgruppen för den här strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="abd0b-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="abd0b-142">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="abd0b-142">Click New.</span></span>
18. <span data-ttu-id="abd0b-143">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="abd0b-144">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="abd0b-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-145">Välj artikelnummer M0007 Standardskåp som sista strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="abd0b-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="abd0b-146">Ange eller välj ett värde i fältet Konfigurationsgrupp.</span><span class="sxs-lookup"><span data-stu-id="abd0b-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="abd0b-147">Välj eller Skåpkonfigurationsgrupp för den sista strukturlisteraden.</span><span class="sxs-lookup"><span data-stu-id="abd0b-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="abd0b-148">Godkänn och aktivera</span><span class="sxs-lookup"><span data-stu-id="abd0b-148">Approve and activate</span></span>
1. <span data-ttu-id="abd0b-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="abd0b-149">Close the page.</span></span>
2. <span data-ttu-id="abd0b-150">Klicka på Godkänn.</span><span class="sxs-lookup"><span data-stu-id="abd0b-150">Click Approve.</span></span>
3. <span data-ttu-id="abd0b-151">Ange eller välj ett värde i fältet Godkänd.</span><span class="sxs-lookup"><span data-stu-id="abd0b-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="abd0b-152">Välj ja i fältet Vill du även godkänna strukturlistan? .</span><span class="sxs-lookup"><span data-stu-id="abd0b-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="abd0b-153">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="abd0b-153">Click OK.</span></span>
6. <span data-ttu-id="abd0b-154">Klicka på Aktivera.</span><span class="sxs-lookup"><span data-stu-id="abd0b-154">Click Activate.</span></span>

