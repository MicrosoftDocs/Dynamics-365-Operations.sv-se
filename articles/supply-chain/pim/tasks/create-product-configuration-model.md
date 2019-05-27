---
title: Skapa en produktkonfigurationsmodell
description: I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5b3d19c680e14fe4074314a95937d30d4ad2c7a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550639"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="d3fb9-103">Skapa en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="d3fb9-103">Create a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3fb9-104">I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="d3fb9-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="d3fb9-106">Skapa en produktmodell</span><span class="sxs-lookup"><span data-stu-id="d3fb9-106">Create a product model</span></span>
1. <span data-ttu-id="d3fb9-107">Klicka på Definition av produktvariantmodell.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="d3fb9-108">Klicka på Modeller för produktkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="d3fb9-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-109">Click New.</span></span>
4. <span data-ttu-id="d3fb9-110">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d3fb9-111">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="d3fb9-112">Markera ett alternativ i fältet Lösarstrategi.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="d3fb9-113">Problemlösarstrategin bestämmer hur begränsningarna i en begränsningsbaserad modell för produktkonfiguration bearbetas.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="d3fb9-114">Det här valet kan påverka resultatet av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="d3fb9-115">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="d3fb9-116">Rotkomponenten representerar produktkonfigurationsmodellen, men den kan även användas i andra produktmodeller.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="d3fb9-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-117">Click OK.</span></span>
9. <span data-ttu-id="d3fb9-118">Markera ett alternativ i fältet Återanvänd konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="d3fb9-119">Om parametern för återanvändningskonfiguration ställs in på Ja, söker systemet efter identiska konfigurationer efter varje konfigurationssession och återanvänder om en exakt matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="d3fb9-120">Lägg till attribut</span><span class="sxs-lookup"><span data-stu-id="d3fb9-120">Add attributes</span></span>
1. <span data-ttu-id="d3fb9-121">Expandera avsnittet Attribut.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="d3fb9-122">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-122">Click Add.</span></span>
3. <span data-ttu-id="d3fb9-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d3fb9-124">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d3fb9-125">Skriv ett värde i fältet Lösarnamn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="d3fb9-126">Problemlösarnamnet används av begränsningslösaren för produktkonfigureraren.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="d3fb9-127">Det får inte innehålla blanksteg eller specialtecken utom _(understreck).</span><span class="sxs-lookup"><span data-stu-id="d3fb9-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="d3fb9-128">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d3fb9-129">Beskrivningstexten visas för konfigurationsanvändaren och kan därför fungera som hjälp när rätt attributvärde ska väljas.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="d3fb9-130">Ange eller välj ett värde i fältet Attributtyp.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="d3fb9-131">Attributtypen avgör vilka värden som är tillgängliga för attributet.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="d3fb9-132">Markera kryssrutan Inkludera i återanvändning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="d3fb9-133">Det här alternativet är endast tillgängligt när alternativet Återanvänd konfigurationer har valts.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="d3fb9-134">Kryssrutan för inkludering av attributet i återanvändningen innebär att attribut övervägs när systemet söker efter en exakt träff.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="d3fb9-135">Lägg till delkomponenter</span><span class="sxs-lookup"><span data-stu-id="d3fb9-135">Add subcomponents</span></span>
1. <span data-ttu-id="d3fb9-136">Utöka avsnittet Delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="d3fb9-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-137">Click Add.</span></span>
3. <span data-ttu-id="d3fb9-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d3fb9-139">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d3fb9-140">Skriv ett värde i fältet Lösarnamn.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="d3fb9-141">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="d3fb9-142">Ange eller välj ett värde i fältet Komponent.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="d3fb9-143">Varje delkomponent måste referera till en komponentdefinition.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="d3fb9-144">Den här designen stöder återvinningsbara komponenter och innebär att när en komponent har definierats så kan den användas i många produktmodeller.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="d3fb9-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-145">Click Save.</span></span>
9. <span data-ttu-id="d3fb9-146">Klicka på Information för strukturlisterad.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-146">Click BOM line details.</span></span>
    * <span data-ttu-id="d3fb9-147">Raddetaljerna för strukturlistan gör att användaren kan välja egenskaper för delkomponenten.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="d3fb9-148">Varje egenskap kan ges ett fast värde eller mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="d3fb9-149">Mappning till ett attribut leder till att radegenskapen för strukturlistan får olika värden beroende konfigurationsvalet.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="d3fb9-150">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="d3fb9-151">Varje delkomponent representerar en konfigurerbar produktmall med begränsningsbaserad konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="d3fb9-152">Referensen görs via artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="d3fb9-153">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-153">Select the Set check box.</span></span>
12. <span data-ttu-id="d3fb9-154">Välj Ja i fältet Beräkning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="d3fb9-155">Att ställa in beräkningsalternativet gör att produkten tas med när en kostnadsberäkning förs för produkten.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="d3fb9-156">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="d3fb9-157">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-157">Select the Set check box.</span></span>
15. <span data-ttu-id="d3fb9-158">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="d3fb9-159">Kvantitetsfältet bestämmer hur mycket av den här produkten som ska förbrukas i den konfigurerade produkten.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="d3fb9-160">Markera kryssrutan Uppsättning.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-160">Select the Set check box.</span></span>
17. <span data-ttu-id="d3fb9-161">Ange ett värde i fältet Per serie.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="d3fb9-162">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d3fb9-162">Click OK.</span></span>

