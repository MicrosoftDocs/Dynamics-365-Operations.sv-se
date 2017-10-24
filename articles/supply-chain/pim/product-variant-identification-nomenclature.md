---
title: "Terminologi för produktvariantnummer och namn"
description: "Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil]. Den nya terminologin har ett riktat format som innehåller produktmallsnummer, aktiva produktdimensioner och valfria textavgränsare. Du kan också skapa en terminologi för produktnamn. Slutligen kan du också skapa en terminologi för att identifiera konfigurationer som skapas av den begränsningsbaserade produktkonfiguratorn. Dessa nomenklaturer kan innehålla valfria attribut."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 4ebebc1d287908dbe8ac7557c34fc6693c88bfae
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="89871-107">Terminologi för produktvariantnummer och namn</span><span class="sxs-lookup"><span data-stu-id="89871-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="89871-108">Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil].</span><span class="sxs-lookup"><span data-stu-id="89871-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="89871-109">Den nya terminologin har ett riktat format som innehåller produktmallsnummer, aktiva produktdimensioner och valfria textavgränsare.</span><span class="sxs-lookup"><span data-stu-id="89871-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="89871-110">Du kan också skapa en terminologi för produktnamn.</span><span class="sxs-lookup"><span data-stu-id="89871-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="89871-111">Slutligen kan du också skapa en terminologi för att identifiera konfigurationer som skapas av den begränsningsbaserade produktkonfiguratorn.</span><span class="sxs-lookup"><span data-stu-id="89871-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="89871-112">Dessa nomenklaturer kan innehålla valfria attribut.</span><span class="sxs-lookup"><span data-stu-id="89871-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="89871-113">Med nya terminologier för produktvariantnummer och produktvariantnamn kan du inkludera segment i identifierarna för produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="89871-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="89871-114">Dessa segment kan innehålla produktmallsnummer och -namn, ID för produktdimensioner, nummerserier, textkonstanter och attribut.</span><span class="sxs-lookup"><span data-stu-id="89871-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="89871-115">Med denna funktion kan du snabbt hitta en specifik produktvariant när du skapar en försäljningsorder eller inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="89871-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="89871-116">Du skapar terminologier för både produktvariantnummer och produktvariantnamn via sidan **Produktterminologi**.</span><span class="sxs-lookup"><span data-stu-id="89871-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="89871-117">För att öppna denna sida klickar du på **Produktinformationshantering** &gt; **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="89871-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="89871-118">Nomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="89871-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="89871-119">Produktvarianter genereras för produktmallar enligt en av tre konfigurationstekniker:</span><span class="sxs-lookup"><span data-stu-id="89871-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="89871-120">Fördefinierade varianter</span><span class="sxs-lookup"><span data-stu-id="89871-120">Predefined variants</span></span>
-   <span data-ttu-id="89871-121">Begränsningsbaserad</span><span class="sxs-lookup"><span data-stu-id="89871-121">Constraint-based</span></span>
-   <span data-ttu-id="89871-122">Dimensionsbaserad</span><span class="sxs-lookup"><span data-stu-id="89871-122">Dimension-based</span></span>

<span data-ttu-id="89871-123">Varje produktvariant har ett nummer och ett namn, och med identifieringsterminologin för produktvariant kan du välja de segment som ska inkluderas i respektive produktvariantnummer eller -namn.</span><span class="sxs-lookup"><span data-stu-id="89871-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="89871-124">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="89871-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="89871-125">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="89871-125">Product master number</span></span>
-   <span data-ttu-id="89871-126">Namn på produktmall</span><span class="sxs-lookup"><span data-stu-id="89871-126">Product master name</span></span>
-   <span data-ttu-id="89871-127">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="89871-127">Number sequence value</span></span>
-   <span data-ttu-id="89871-128">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="89871-128">Text constant</span></span>
-   <span data-ttu-id="89871-129">Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="89871-129">Product dimensions</span></span>
    -   <span data-ttu-id="89871-130">Konfigurations-ID eller -namn</span><span class="sxs-lookup"><span data-stu-id="89871-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="89871-131">Färg-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="89871-131">Color ID or name</span></span>
    -   <span data-ttu-id="89871-132">Storleks-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="89871-132">Size ID or name</span></span>
    -   <span data-ttu-id="89871-133">Stil-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="89871-133">Style ID or name</span></span>

<span data-ttu-id="89871-134">När du anger en identifieringsnummerterminologi för produktvariant kan du koppla den till en produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="89871-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="89871-135">Alla produktmallar som refererar till denna produktdimensionsgrupp kommer sedan att tilldelas produktvariantnummer enligt terminologin.</span><span class="sxs-lookup"><span data-stu-id="89871-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="89871-136">Produktvariantens namnterminologier kan dock inte associeras med produktdimensionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="89871-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="89871-137">Du kan också tilldela en identifieringsterminologi för produktvariant direkt till en produktmall.</span><span class="sxs-lookup"><span data-stu-id="89871-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="89871-138">I det här fallet tilldelas de produktvarianter som tillhör produktmallen produktvariantnummer och namn i enlighet med terminologierna.</span><span class="sxs-lookup"><span data-stu-id="89871-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="89871-139">Exempel</span><span class="sxs-lookup"><span data-stu-id="89871-139">Example</span></span>

<span data-ttu-id="89871-140">En T-shirt (TS1234) skapas i tre olika storlekar (S, M, L), fyra olika färger (röd, grön, blå, gul) och två olika format (Polo, V).</span><span class="sxs-lookup"><span data-stu-id="89871-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="89871-141">Därför är 24 produktvarianter möjliga (= 2 × 4 × 3).</span><span class="sxs-lookup"><span data-stu-id="89871-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="89871-142">Du kan skapa en nummerterminologi för produktvariant med följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="89871-143">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="89871-143">Product master number</span></span>
2.  <span data-ttu-id="89871-144">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="89871-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="89871-145">Färg</span><span class="sxs-lookup"><span data-stu-id="89871-145">Color</span></span>
4.  <span data-ttu-id="89871-146">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="89871-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="89871-147">Storlek</span><span class="sxs-lookup"><span data-stu-id="89871-147">Size</span></span>
6.  <span data-ttu-id="89871-148">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="89871-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="89871-149">Stil</span><span class="sxs-lookup"><span data-stu-id="89871-149">Style</span></span>

<span data-ttu-id="89871-150">I detta fall blir produktvariantnumret för en röd polo-T-shirt i storlek S: TS1234-Red-Small-T-shirt.</span><span class="sxs-lookup"><span data-stu-id="89871-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="89871-151">Nomenklatur för begränsningsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="89871-152">För begränsningsbaserade konfigurationer kan du skapa en särskild terminologi för konfigurationsproduktdimensionen.</span><span class="sxs-lookup"><span data-stu-id="89871-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="89871-153">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="89871-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="89871-154">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="89871-154">Number sequence value</span></span>
-   <span data-ttu-id="89871-155">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="89871-155">Text constant</span></span>
-   <span data-ttu-id="89871-156">Attributvärde</span><span class="sxs-lookup"><span data-stu-id="89871-156">Attribute value</span></span>

<span data-ttu-id="89871-157">Varje komponent i en modell för produktkonfiguration kan ha sin egen konfigurationsnomenklatur.</span><span class="sxs-lookup"><span data-stu-id="89871-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="89871-158">Endast attribut som tillhör komponenten kan användas.</span><span class="sxs-lookup"><span data-stu-id="89871-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="89871-159">Attribut från delkomponenter eller användarkrav får inte användas.</span><span class="sxs-lookup"><span data-stu-id="89871-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="89871-160">Exempel</span><span class="sxs-lookup"><span data-stu-id="89871-160">Example</span></span>

<span data-ttu-id="89871-161">En produktkonfigurationsmodell har en rotkomponent med två attribut:</span><span class="sxs-lookup"><span data-stu-id="89871-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="89871-162">Material (plast, trä, stål)</span><span class="sxs-lookup"><span data-stu-id="89871-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="89871-163">Längd (10...100)</span><span class="sxs-lookup"><span data-stu-id="89871-163">Length (10...100)</span></span>

<span data-ttu-id="89871-164">Du kan skapa en nummerterminologi för konfiguration med följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="89871-165">Attributvärde: Material</span><span class="sxs-lookup"><span data-stu-id="89871-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="89871-166">Textkonstant: "AAA"</span><span class="sxs-lookup"><span data-stu-id="89871-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="89871-167">Attributvärde: Längd</span><span class="sxs-lookup"><span data-stu-id="89871-167">Attribute value: Length</span></span>

<span data-ttu-id="89871-168">I detta fall blir konfigurations-ID för trämaterial med en längd på 78 då WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="89871-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="89871-169">Nomenklatur för dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="89871-170">För dimensionsbaserade konfigurationer kan du skapa en särskilt avsedd terminologi för konfigurationsproduktdimensionen.</span><span class="sxs-lookup"><span data-stu-id="89871-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="89871-171">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="89871-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="89871-172">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="89871-172">Number sequence value</span></span>
-   <span data-ttu-id="89871-173">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="89871-173">Text constant</span></span>
-   <span data-ttu-id="89871-174">Konfigurationsgruppartikel</span><span class="sxs-lookup"><span data-stu-id="89871-174">Configuration group item</span></span>

<span data-ttu-id="89871-175">Du kan definiera en konfigurationsterminologi för en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="89871-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="89871-176">Exempel</span><span class="sxs-lookup"><span data-stu-id="89871-176">Example</span></span>

<span data-ttu-id="89871-177">En strukturlista har fyra strukturlisterader som är uppdelade i två konfigurationsgrupper:</span><span class="sxs-lookup"><span data-stu-id="89871-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="89871-178">Strukturlisterad: M0007, standardkabinett</span><span class="sxs-lookup"><span data-stu-id="89871-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="89871-179">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="89871-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="89871-180">Strukturlisterad: M0008, avancerat kabinett</span><span class="sxs-lookup"><span data-stu-id="89871-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="89871-181">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="89871-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="89871-182">Strukturlisterad: M0021, framgallerduk</span><span class="sxs-lookup"><span data-stu-id="89871-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="89871-183">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="89871-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="89871-184">Strukturlisterad: M0022, framgallermetall</span><span class="sxs-lookup"><span data-stu-id="89871-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="89871-185">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="89871-185">Configuration group: Front grill</span></span>

<span data-ttu-id="89871-186">Du kan skapa en nummerterminologi för konfiguration med följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="89871-187">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="89871-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="89871-188">Textkonstant: "&"</span><span class="sxs-lookup"><span data-stu-id="89871-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="89871-189">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="89871-189">Configuration group: Front grill</span></span>

<span data-ttu-id="89871-190">I detta fall blir konfigurations-ID för ett standardkabinett som har ett dukframgaller: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="89871-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="89871-191">Terminologi för en kombination av produktvarianter och konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="89871-192">När du använder antingen begränsningsbaserad eller dimensionsbaserad konfigurationsteknik för att konfigurera produktvarianter för en produktmall, kan produktvarianternas produktvariantnummer innehålla terminologin från konfigurationsdimensionen.</span><span class="sxs-lookup"><span data-stu-id="89871-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="89871-193">Om du vill konfigurera varianter, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="89871-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="89871-194">Definiera en nummerterminologi för produktvarianter som innehåller konfigurationsdimensionen på sidan **Produktterminologi**.</span><span class="sxs-lookup"><span data-stu-id="89871-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="89871-195">Tilldela terminologin till en produktdimensionsgrupp med konfigurationsdimension.</span><span class="sxs-lookup"><span data-stu-id="89871-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="89871-196">Definiera en konfigurationsterminologi för de komponenter eller strukturlistor som ska användas för att konfigurera produktvarianterna.</span><span class="sxs-lookup"><span data-stu-id="89871-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="89871-197">Du kan också skapa terminologier för produktvariantnamn.</span><span class="sxs-lookup"><span data-stu-id="89871-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="89871-198">Produktvariantnamnen kan konfigureras att omfatta konfigurations-ID eller namn.</span><span class="sxs-lookup"><span data-stu-id="89871-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="89871-199">Exempel på konstantbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="89871-200">I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="89871-201">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="89871-201">Product master number</span></span>
2.  <span data-ttu-id="89871-202">Textkonstant "\_"</span><span class="sxs-lookup"><span data-stu-id="89871-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="89871-203">Inställningar</span><span class="sxs-lookup"><span data-stu-id="89871-203">Configuration</span></span>

<span data-ttu-id="89871-204">Konfigurationsterminologin består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="89871-205">Attributvärde: Material</span><span class="sxs-lookup"><span data-stu-id="89871-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="89871-206">Textkonstant: "AAA"</span><span class="sxs-lookup"><span data-stu-id="89871-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="89871-207">Attributvärde: Längd</span><span class="sxs-lookup"><span data-stu-id="89871-207">Attribute value: Length</span></span>

<span data-ttu-id="89871-208">Du kan ange följande värden för segment:</span><span class="sxs-lookup"><span data-stu-id="89871-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="89871-209">Produktmallsnummer = **M0099**</span><span class="sxs-lookup"><span data-stu-id="89871-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="89871-210">Material = **Plast**</span><span class="sxs-lookup"><span data-stu-id="89871-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="89871-211">Längd = **12**</span><span class="sxs-lookup"><span data-stu-id="89871-211">Length = **12**</span></span>

<span data-ttu-id="89871-212">I detta fall blir produktvariantnumret M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="89871-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="89871-213">Exempel på dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="89871-214">I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="89871-215">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="89871-215">Product master number</span></span>
2.  <span data-ttu-id="89871-216">Textkonstant "//"</span><span class="sxs-lookup"><span data-stu-id="89871-216">Text constant "//"</span></span>
3.  <span data-ttu-id="89871-217">Inställningar</span><span class="sxs-lookup"><span data-stu-id="89871-217">Configuration</span></span>

<span data-ttu-id="89871-218">Konfigurationsterminologin består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="89871-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="89871-219">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="89871-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="89871-220">Textkonstant: "&"</span><span class="sxs-lookup"><span data-stu-id="89871-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="89871-221">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="89871-221">Configuration group: Front grill</span></span>

<span data-ttu-id="89871-222">Du kan ange följande värden för segment:</span><span class="sxs-lookup"><span data-stu-id="89871-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="89871-223">Produktmallsnummer = **D0123**</span><span class="sxs-lookup"><span data-stu-id="89871-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="89871-224">Kabinett = **M0008**</span><span class="sxs-lookup"><span data-stu-id="89871-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="89871-225">Frontgaller = **M0022**</span><span class="sxs-lookup"><span data-stu-id="89871-225">Front grill = **M0022**</span></span>

<span data-ttu-id="89871-226">I detta fall blir produktvariantnumret D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="89871-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="89871-227">Nummerkonflikter</span><span class="sxs-lookup"><span data-stu-id="89871-227">Numbering conflicts</span></span>
<span data-ttu-id="89871-228">I vissa fall kan ett produktvariantnummer som du skapar komma att inte framställa unika produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="89871-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="89871-229">Till exempel kommer produktvarianten inte att vara unika om en aktiv produktdimension inte inkluderas i terminologin för en produktmall som använder den fördefinierade variantkonfigurationstekniken.</span><span class="sxs-lookup"><span data-stu-id="89871-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="89871-230">Hur konflikter hanteras varierar beroende på inställningen för konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="89871-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="89871-231">Fördefinierade varianter</span><span class="sxs-lookup"><span data-stu-id="89871-231">Predefined variants</span></span>

<span data-ttu-id="89871-232">Ett fel uppstår om du manuellt skapar eller automatiskt försöker generera produktvarianter , och mer än en produktvariant erhåller samma produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="89871-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="89871-233">För att undvika detta bör du använda alla aktiva produktdimensioner i produktdimensionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="89871-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="89871-234">Alternativt kan du inkludera en nummerserie för att garantera att produktvariantnumren är unika.</span><span class="sxs-lookup"><span data-stu-id="89871-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="89871-235">Begränsningsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-235">Constraint-based configurations</span></span>

<span data-ttu-id="89871-236">Beroende på terminologin kan systemet komma att försöka tilldela ett icke-unikt produktvariantnummer till en konfiguration.</span><span class="sxs-lookup"><span data-stu-id="89871-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="89871-237">I så fall kommer systemet att använda nummerserien för konfigurationsdimensionen som produktvariantnummer istället. Om detta händer får du ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="89871-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="89871-238">För att undvika detta scenario bör du inkludera tillräckligt med attribut i terminologin för att garantera unika produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="89871-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="89871-239">Du bör också se till att alternativet **Återanvänd** aktiveras för komponenten.</span><span class="sxs-lookup"><span data-stu-id="89871-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="89871-240">Dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="89871-240">Dimension-based configurations</span></span>

<span data-ttu-id="89871-241">Under ett steg under konfigurationsprocessen föreslår systemet ett konfigurationsvärde enligt terminologin.</span><span class="sxs-lookup"><span data-stu-id="89871-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="89871-242">I detta steg kan du ändra konfigurationsvärdet manuellt.</span><span class="sxs-lookup"><span data-stu-id="89871-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="89871-243">När du sparar konfigurationen kommer systemet att bekräfta att konfigurationsvärdet är unikt.</span><span class="sxs-lookup"><span data-stu-id="89871-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="89871-244">Du får ett felmeddelande om värdet som du angett inte är unikt.</span><span class="sxs-lookup"><span data-stu-id="89871-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="89871-245">Du måste ange ett unikt konfigurationsvärde för att spara konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="89871-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="89871-246">Se även</span><span class="sxs-lookup"><span data-stu-id="89871-246">See also</span></span>
--------

[<span data-ttu-id="89871-247">Skapa en produktnummerterminologi för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="89871-247">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="89871-248">Skapa en produktnummerterminologi för konfigurerade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="89871-248">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


