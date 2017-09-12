--- 
title: "Skapa fördefinierade produktvarianter"
description: "Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner."
author: BibiSp
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: fa23f1449e750b4ed1c0f631a98c42b18b7dbb40
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="5d5fe-103">Skapa fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="5d5fe-103">Create predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5d5fe-104">Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="5d5fe-105">Demonstrationsdataföretaget som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="5d5fe-106">Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="5d5fe-106">Create a product master</span></span>
1. <span data-ttu-id="5d5fe-107">Gå till Produktinformationshantering > Produkter > Produktmallar.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="5d5fe-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-108">Click New.</span></span>
3. <span data-ttu-id="5d5fe-109">Skriv ett värde i fältet Produktnummer.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5d5fe-110">Att ange ett produktnummer manuellt krävs endast om ingen nummerserie har ställts in för produktnummerfältet.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="5d5fe-111">Hoppa över steget om nummerserien har angetts för fältet.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="5d5fe-112">Skriv ett värde i fältet Produktnamn.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="5d5fe-113">Ange eller välj ett värde i fältet Produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5d5fe-114">Välj produktdimensiongruppen SizeCol (storlek och färg).</span><span class="sxs-lookup"><span data-stu-id="5d5fe-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="5d5fe-115">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="5d5fe-116">Lägg till Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="5d5fe-116">Add product dimensions</span></span>
1. <span data-ttu-id="5d5fe-117">Klicka på produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="5d5fe-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="5d5fe-118">Det här exemplet visar hur du manuellt anger produktdimensioner.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="5d5fe-119">Du kan också välja att markera en Storlek, Färg eller utförandegrupp som innehåller produktdimensionvärdena, som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="5d5fe-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-120">Click New.</span></span>
3. <span data-ttu-id="5d5fe-121">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5d5fe-122">Ange eller välj ett värde i fältet Storlek.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="5d5fe-123">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="5d5fe-124">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-124">Click New.</span></span>
7. <span data-ttu-id="5d5fe-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="5d5fe-126">Ange eller välj ett värde i fältet Storlek.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="5d5fe-127">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="5d5fe-128">Klicka på fliken Färger.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="5d5fe-129">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-129">Click New.</span></span>
12. <span data-ttu-id="5d5fe-130">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="5d5fe-131">Ange eller välj ett värde i fältet Färg.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="5d5fe-132">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="5d5fe-133">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-133">Click New.</span></span>
16. <span data-ttu-id="5d5fe-134">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="5d5fe-135">Ange eller välj ett värde i fältet Färg.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="5d5fe-136">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="5d5fe-137">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-137">Click Save.</span></span>
20. <span data-ttu-id="5d5fe-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="5d5fe-139">Skapa produktvarianter</span><span class="sxs-lookup"><span data-stu-id="5d5fe-139">Generate product variants</span></span>
1. <span data-ttu-id="5d5fe-140">Klicka på Produktvarianter</span><span class="sxs-lookup"><span data-stu-id="5d5fe-140">Click Product variants.</span></span>
2. <span data-ttu-id="5d5fe-141">Klicka på Variantförslag</span><span class="sxs-lookup"><span data-stu-id="5d5fe-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="5d5fe-142">Klicka på Markera alla.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-142">Click Select all.</span></span>
    * <span data-ttu-id="5d5fe-143">I det här exemplet väljs alla möjliga varianter.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="5d5fe-144">Om bara en delmängd av de möjliga produktdimensionkombinationerna ska användas för att skapa varianter, kan du välja de enskilda posterna.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="5d5fe-145">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-145">Click Create.</span></span>
    * <span data-ttu-id="5d5fe-146">Du kan generera beskrivningar av alla dina varianter baserat på kombinationen av produktdimensionvärden.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="5d5fe-147">Beskrivningar är valfria.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="5d5fe-148">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5d5fe-148">Click Save.</span></span>


