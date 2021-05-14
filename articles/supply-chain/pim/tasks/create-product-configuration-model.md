---
title: Skapa en produktkonfigurationsmodell
description: I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921375"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="ce6eb-103">Skapa en produktkonfigurationsmodell</span><span class="sxs-lookup"><span data-stu-id="ce6eb-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce6eb-104">I den här proceduren visas hur du skapar en modell för produktkonfiguration och anger grundläggande information som attribut och delkomponenter.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="ce6eb-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="ce6eb-106">Skapa en produktmodell</span><span class="sxs-lookup"><span data-stu-id="ce6eb-106">Create a product model</span></span>

1. <span data-ttu-id="ce6eb-107">Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="ce6eb-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-108">Select **New**.</span></span>
1. <span data-ttu-id="ce6eb-109">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="ce6eb-110">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="ce6eb-111">I fältet **Problemlösarstrategi** väljer du ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="ce6eb-112">Problemlösarstrategin bestämmer hur begränsningarna i en begränsningsbaserad modell för produktkonfiguration bearbetas.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="ce6eb-113">Det här valet kan påverka resultatet av produktkonfigurationsmodellen.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="ce6eb-114">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="ce6eb-115">Rotkomponenten representerar produktkonfigurationsmodellen, men den kan även användas i andra produktmodeller.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="ce6eb-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-116">Select **OK**.</span></span>
1. <span data-ttu-id="ce6eb-117">Välj ett alternativ i fältet **Återanvänd konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="ce6eb-118">Om parametern för återanvändningskonfiguration ställs in på Ja, söker systemet efter identiska konfigurationer efter varje konfigurationssession och återanvänder om en exakt matchning hittas.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="ce6eb-119">Lägg till attribut</span><span class="sxs-lookup"><span data-stu-id="ce6eb-119">Add attributes</span></span>

1. <span data-ttu-id="ce6eb-120">Visa avsnittet **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="ce6eb-121">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-121">Select **Add**.</span></span>
3. <span data-ttu-id="ce6eb-122">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ce6eb-123">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ce6eb-124">Ange ett värde i fältet **Problemlösarnamn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="ce6eb-125">Problemlösarnamnet används av begränsningslösaren för produktkonfigureraren.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="ce6eb-126">Det får inte innehålla blanksteg eller specialtecken utom _(understreck).</span><span class="sxs-lookup"><span data-stu-id="ce6eb-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="ce6eb-127">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="ce6eb-128">Beskrivningstexten visas för konfigurationsanvändaren och kan därför fungera som hjälp när rätt attributvärde ska väljas.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="ce6eb-129">Ange eller välj ett värde i fältet **Attributtyp**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="ce6eb-130">Attributtypen avgör vilka värden som är tillgängliga för attributet.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="ce6eb-131">Markera kryssrutan **Inkludera i återanvändning**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="ce6eb-132">Det här alternativet är endast tillgängligt när alternativet Återanvänd konfigurationer har valts.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="ce6eb-133">Kryssrutan för inkludering av attributet i återanvändningen innebär att attribut övervägs när systemet söker efter en exakt träff.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="ce6eb-134">Lägg till delkomponenter</span><span class="sxs-lookup"><span data-stu-id="ce6eb-134">Add subcomponents</span></span>

1. <span data-ttu-id="ce6eb-135">Utöka avsnittet **Delkomponenter**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="ce6eb-136">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-136">Select **Add**.</span></span>
3. <span data-ttu-id="ce6eb-137">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ce6eb-138">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ce6eb-139">Ange ett värde i fältet **Problemlösarnamn**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="ce6eb-140">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="ce6eb-141">Ange eller välj ett värde i fältet **Komponent**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="ce6eb-142">Varje delkomponent måste referera till en komponentdefinition.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="ce6eb-143">Den här designen stöder återvinningsbara komponenter och innebär att när en komponent har definierats så kan den användas i många produktmodeller.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="ce6eb-144">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-144">Select **Save**.</span></span>
9. <span data-ttu-id="ce6eb-145">Välj **Detaljerad information för strukturlisterader**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="ce6eb-146">Raddetaljerna för strukturlistan gör att användaren kan välja egenskaper för delkomponenten.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="ce6eb-147">Varje egenskap kan ges ett fast värde eller mappas till ett attribut.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="ce6eb-148">Mappning till ett attribut leder till att radegenskapen för strukturlistan får olika värden beroende konfigurationsvalet.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="ce6eb-149">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="ce6eb-150">Varje delkomponent representerar en konfigurerbar produktmall med begränsningsbaserad konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="ce6eb-151">Referensen görs via artikelnumret.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="ce6eb-152">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="ce6eb-153">Välj **Ja** i fältet **Beräkning**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="ce6eb-154">Att ställa in beräkningsalternativet gör att produkten tas med när en kostnadsberäkning förs för produkten.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="ce6eb-155">Välj fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="ce6eb-156">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="ce6eb-157">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="ce6eb-158">Kvantitetsfältet bestämmer hur mycket av den här produkten som ska förbrukas i den konfigurerade produkten.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="ce6eb-159">Markera kryssrutan **Ställ in**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="ce6eb-160">Ange ett värde i fältet **Per serie**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="ce6eb-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce6eb-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]