---
title: Terminologi för produktvariantnummer och namn
description: Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil].
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 90c01e4281246d890ef888c56ca137f83e83741c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980493"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="e77c6-103">Terminologi för produktvariantnummer och namn</span><span class="sxs-lookup"><span data-stu-id="e77c6-103">Nomenclature of product variant numbers and names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e77c6-104">Det här avsnittet beskriver hur du ställer in en produktnummerterminologi för att ersätta det fasta formatet [Produktmallsnummer - Konfiguration - Storlek - Färg - Stil].</span><span class="sxs-lookup"><span data-stu-id="e77c6-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="e77c6-105">Den nya terminologin har ett riktat format som innehåller produktmallsnummer, aktiva produktdimensioner och valfria textavgränsare.</span><span class="sxs-lookup"><span data-stu-id="e77c6-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="e77c6-106">Du kan också skapa en terminologi för produktnamn.</span><span class="sxs-lookup"><span data-stu-id="e77c6-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="e77c6-107">Slutligen kan du också skapa en terminologi för att identifiera konfigurationer som skapas av den begränsningsbaserade produktkonfiguratorn.</span><span class="sxs-lookup"><span data-stu-id="e77c6-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="e77c6-108">Dessa nomenklaturer kan innehålla valfria attribut.</span><span class="sxs-lookup"><span data-stu-id="e77c6-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="e77c6-109">Med nya terminologier för produktvariantnummer och produktvariantnamn kan du inkludera segment i identifierarna för produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="e77c6-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="e77c6-110">Dessa segment kan innehålla produktmallsnummer och -namn, ID för produktdimensioner, nummerserier, textkonstanter och attribut.</span><span class="sxs-lookup"><span data-stu-id="e77c6-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="e77c6-111">Med denna funktion kan du snabbt hitta en specifik produktvariant när du skapar en försäljningsorder eller inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="e77c6-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="e77c6-112">Du skapar terminologier för både produktvariantnummer och produktvariantnamn via sidan **Produktterminologi**.</span><span class="sxs-lookup"><span data-stu-id="e77c6-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="e77c6-113">För att öppna denna sida klickar du på **Produktinformationshantering** &gt; **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="e77c6-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="e77c6-114">Nomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="e77c6-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="e77c6-115">Produktvarianter genereras för produktmallar enligt en av tre konfigurationstekniker:</span><span class="sxs-lookup"><span data-stu-id="e77c6-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="e77c6-116">Fördefinierade varianter</span><span class="sxs-lookup"><span data-stu-id="e77c6-116">Predefined variants</span></span>
-   <span data-ttu-id="e77c6-117">Begränsningsbaserad</span><span class="sxs-lookup"><span data-stu-id="e77c6-117">Constraint-based</span></span>
-   <span data-ttu-id="e77c6-118">Dimensionsbaserad</span><span class="sxs-lookup"><span data-stu-id="e77c6-118">Dimension-based</span></span>

<span data-ttu-id="e77c6-119">Varje produktvariant har ett nummer och ett namn, och med identifieringsterminologin för produktvariant kan du välja de segment som ska inkluderas i respektive produktvariantnummer eller -namn.</span><span class="sxs-lookup"><span data-stu-id="e77c6-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="e77c6-120">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="e77c6-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="e77c6-121">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="e77c6-121">Product master number</span></span>
-   <span data-ttu-id="e77c6-122">Namn på produktmall</span><span class="sxs-lookup"><span data-stu-id="e77c6-122">Product master name</span></span>
-   <span data-ttu-id="e77c6-123">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="e77c6-123">Number sequence value</span></span>
-   <span data-ttu-id="e77c6-124">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="e77c6-124">Text constant</span></span>
-   <span data-ttu-id="e77c6-125">Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="e77c6-125">Product dimensions</span></span>
    -   <span data-ttu-id="e77c6-126">Konfigurations-ID eller -namn</span><span class="sxs-lookup"><span data-stu-id="e77c6-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="e77c6-127">Färg-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="e77c6-127">Color ID or name</span></span>
    -   <span data-ttu-id="e77c6-128">Storleks-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="e77c6-128">Size ID or name</span></span>
    -   <span data-ttu-id="e77c6-129">Stil-ID eller namn</span><span class="sxs-lookup"><span data-stu-id="e77c6-129">Style ID or name</span></span>

<span data-ttu-id="e77c6-130">När du anger en identifieringsnummerterminologi för produktvariant kan du koppla den till en produktdimensionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e77c6-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="e77c6-131">Alla produktmallar som refererar till denna produktdimensionsgrupp kommer sedan att tilldelas produktvariantnummer enligt terminologin.</span><span class="sxs-lookup"><span data-stu-id="e77c6-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="e77c6-132">Produktvariantens namnterminologier kan dock inte associeras med produktdimensionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e77c6-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="e77c6-133">Du kan också tilldela en identifieringsterminologi för produktvariant direkt till en produktmall.</span><span class="sxs-lookup"><span data-stu-id="e77c6-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="e77c6-134">I det här fallet tilldelas de produktvarianter som tillhör produktmallen produktvariantnummer och namn i enlighet med terminologierna.</span><span class="sxs-lookup"><span data-stu-id="e77c6-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="e77c6-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="e77c6-135">Example</span></span>

<span data-ttu-id="e77c6-136">En T-shirt (TS1234) skapas i tre olika storlekar (S, M, L), fyra olika färger (röd, grön, blå, gul) och två olika format (Polo, V).</span><span class="sxs-lookup"><span data-stu-id="e77c6-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="e77c6-137">Därför är 24 produktvarianter möjliga (= 2 × 4 × 3).</span><span class="sxs-lookup"><span data-stu-id="e77c6-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="e77c6-138">Du kan skapa en nummerterminologi för produktvariant med följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="e77c6-139">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="e77c6-139">Product master number</span></span>
2.  <span data-ttu-id="e77c6-140">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="e77c6-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="e77c6-141">Färg</span><span class="sxs-lookup"><span data-stu-id="e77c6-141">Color</span></span>
4.  <span data-ttu-id="e77c6-142">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="e77c6-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="e77c6-143">Storlek</span><span class="sxs-lookup"><span data-stu-id="e77c6-143">Size</span></span>
6.  <span data-ttu-id="e77c6-144">Textkonstant: "-"</span><span class="sxs-lookup"><span data-stu-id="e77c6-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="e77c6-145">Stil</span><span class="sxs-lookup"><span data-stu-id="e77c6-145">Style</span></span>

<span data-ttu-id="e77c6-146">I detta fall blir produktvariantnumret för en röd polo-T-shirt i storlek S: TS1234-Red-Small-T-shirt.</span><span class="sxs-lookup"><span data-stu-id="e77c6-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="e77c6-147">Nomenklatur för begränsningsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="e77c6-148">För begränsningsbaserade konfigurationer kan du skapa en särskild terminologi för konfigurationsproduktdimensionen.</span><span class="sxs-lookup"><span data-stu-id="e77c6-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="e77c6-149">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="e77c6-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="e77c6-150">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="e77c6-150">Number sequence value</span></span>
-   <span data-ttu-id="e77c6-151">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="e77c6-151">Text constant</span></span>
-   <span data-ttu-id="e77c6-152">Attributvärde</span><span class="sxs-lookup"><span data-stu-id="e77c6-152">Attribute value</span></span>

<span data-ttu-id="e77c6-153">Varje komponent i en modell för produktkonfiguration kan ha sin egen konfigurationsnomenklatur.</span><span class="sxs-lookup"><span data-stu-id="e77c6-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="e77c6-154">Endast attribut som tillhör komponenten kan användas.</span><span class="sxs-lookup"><span data-stu-id="e77c6-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="e77c6-155">Attribut från delkomponenter eller användarkrav får inte användas.</span><span class="sxs-lookup"><span data-stu-id="e77c6-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="e77c6-156">Exempel</span><span class="sxs-lookup"><span data-stu-id="e77c6-156">Example</span></span>

<span data-ttu-id="e77c6-157">En produktkonfigurationsmodell har en rotkomponent med två attribut:</span><span class="sxs-lookup"><span data-stu-id="e77c6-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="e77c6-158">Material (plast, trä, stål)</span><span class="sxs-lookup"><span data-stu-id="e77c6-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="e77c6-159">Längd (10...100)</span><span class="sxs-lookup"><span data-stu-id="e77c6-159">Length (10...100)</span></span>

<span data-ttu-id="e77c6-160">Du kan skapa en nummerterminologi för konfiguration med följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="e77c6-161">Attributvärde: Material</span><span class="sxs-lookup"><span data-stu-id="e77c6-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="e77c6-162">Textkonstant: "AAA"</span><span class="sxs-lookup"><span data-stu-id="e77c6-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="e77c6-163">Attributvärde: Längd</span><span class="sxs-lookup"><span data-stu-id="e77c6-163">Attribute value: Length</span></span>

<span data-ttu-id="e77c6-164">I detta fall blir konfigurations-ID för trämaterial med en längd på 78 då WoodAAA78.</span><span class="sxs-lookup"><span data-stu-id="e77c6-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="e77c6-165">Nomenklatur för dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="e77c6-166">För dimensionsbaserade konfigurationer kan du skapa en särskilt avsedd terminologi för konfigurationsproduktdimensionen.</span><span class="sxs-lookup"><span data-stu-id="e77c6-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="e77c6-167">Du kan välja följande segment på sidan **Produktterminologi**:</span><span class="sxs-lookup"><span data-stu-id="e77c6-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="e77c6-168">Nummersekvensvärde</span><span class="sxs-lookup"><span data-stu-id="e77c6-168">Number sequence value</span></span>
-   <span data-ttu-id="e77c6-169">Textkonstant</span><span class="sxs-lookup"><span data-stu-id="e77c6-169">Text constant</span></span>
-   <span data-ttu-id="e77c6-170">Konfigurationsgruppartikel</span><span class="sxs-lookup"><span data-stu-id="e77c6-170">Configuration group item</span></span>

<span data-ttu-id="e77c6-171">Du kan definiera en konfigurationsterminologi för en strukturlista (BOM).</span><span class="sxs-lookup"><span data-stu-id="e77c6-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="e77c6-172">Exempel</span><span class="sxs-lookup"><span data-stu-id="e77c6-172">Example</span></span>

<span data-ttu-id="e77c6-173">En strukturlista har fyra strukturlisterader som är uppdelade i två konfigurationsgrupper:</span><span class="sxs-lookup"><span data-stu-id="e77c6-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="e77c6-174">Strukturlisterad: M0007, standardkabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="e77c6-175">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="e77c6-176">Strukturlisterad: M0008, avancerat kabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="e77c6-177">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="e77c6-178">Strukturlisterad: M0021, framgallerduk</span><span class="sxs-lookup"><span data-stu-id="e77c6-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="e77c6-179">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="e77c6-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="e77c6-180">Strukturlisterad: M0022, framgallermetall</span><span class="sxs-lookup"><span data-stu-id="e77c6-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="e77c6-181">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="e77c6-181">Configuration group: Front grill</span></span>

<span data-ttu-id="e77c6-182">Du kan skapa en nummerterminologi för konfiguration med följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="e77c6-183">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="e77c6-184">Textkonstant: "&"</span><span class="sxs-lookup"><span data-stu-id="e77c6-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="e77c6-185">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="e77c6-185">Configuration group: Front grill</span></span>

<span data-ttu-id="e77c6-186">I detta fall blir konfigurations-ID för ett standardkabinett som har ett dukframgaller: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="e77c6-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="e77c6-187">Terminologi för en kombination av produktvarianter och konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="e77c6-188">När du använder antingen begränsningsbaserad eller dimensionsbaserad konfigurationsteknik för att konfigurera produktvarianter för en produktmall, kan produktvarianternas produktvariantnummer innehålla terminologin från konfigurationsdimensionen.</span><span class="sxs-lookup"><span data-stu-id="e77c6-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="e77c6-189">Om du vill konfigurera varianter, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e77c6-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="e77c6-190">Definiera en nummerterminologi för produktvarianter som innehåller konfigurationsdimensionen på sidan **Produktterminologi**.</span><span class="sxs-lookup"><span data-stu-id="e77c6-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="e77c6-191">Tilldela terminologin till en produktdimensionsgrupp med konfigurationsdimension.</span><span class="sxs-lookup"><span data-stu-id="e77c6-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="e77c6-192">Definiera en konfigurationsterminologi för de komponenter eller strukturlistor som ska användas för att konfigurera produktvarianterna.</span><span class="sxs-lookup"><span data-stu-id="e77c6-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="e77c6-193">Du kan också skapa terminologier för produktvariantnamn.</span><span class="sxs-lookup"><span data-stu-id="e77c6-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="e77c6-194">Produktvariantnamnen kan konfigureras att omfatta konfigurations-ID eller namn.</span><span class="sxs-lookup"><span data-stu-id="e77c6-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="e77c6-195">Exempel på konstantbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="e77c6-196">I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="e77c6-197">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="e77c6-197">Product master number</span></span>
2.  <span data-ttu-id="e77c6-198">Textkonstant "\_"</span><span class="sxs-lookup"><span data-stu-id="e77c6-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="e77c6-199">Inställningar</span><span class="sxs-lookup"><span data-stu-id="e77c6-199">Configuration</span></span>

<span data-ttu-id="e77c6-200">Konfigurationsterminologin består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="e77c6-201">Attributvärde: Material</span><span class="sxs-lookup"><span data-stu-id="e77c6-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="e77c6-202">Textkonstant: "AAA"</span><span class="sxs-lookup"><span data-stu-id="e77c6-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="e77c6-203">Attributvärde: Längd</span><span class="sxs-lookup"><span data-stu-id="e77c6-203">Attribute value: Length</span></span>

<span data-ttu-id="e77c6-204">Du kan ange följande värden för segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="e77c6-205">Produktmallsnummer = **M0099**</span><span class="sxs-lookup"><span data-stu-id="e77c6-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="e77c6-206">Material = **Plast**</span><span class="sxs-lookup"><span data-stu-id="e77c6-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="e77c6-207">Längd = **12**</span><span class="sxs-lookup"><span data-stu-id="e77c6-207">Length = **12**</span></span>

<span data-ttu-id="e77c6-208">I detta fall blir produktvariantnumret M0099\_PlasticAAA12.</span><span class="sxs-lookup"><span data-stu-id="e77c6-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="e77c6-209">Exempel på dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="e77c6-210">I det här exemplet använder du en nummerterminologi för produktvariant som består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="e77c6-211">Produktmallsnummer</span><span class="sxs-lookup"><span data-stu-id="e77c6-211">Product master number</span></span>
2.  <span data-ttu-id="e77c6-212">Textkonstant "//"</span><span class="sxs-lookup"><span data-stu-id="e77c6-212">Text constant "//"</span></span>
3.  <span data-ttu-id="e77c6-213">Inställningar</span><span class="sxs-lookup"><span data-stu-id="e77c6-213">Configuration</span></span>

<span data-ttu-id="e77c6-214">Konfigurationsterminologin består av följande segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="e77c6-215">Konfigurationsgrupp: Kabinett</span><span class="sxs-lookup"><span data-stu-id="e77c6-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="e77c6-216">Textkonstant: "&"</span><span class="sxs-lookup"><span data-stu-id="e77c6-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="e77c6-217">Konfigurationsgrupp: Framgaller</span><span class="sxs-lookup"><span data-stu-id="e77c6-217">Configuration group: Front grill</span></span>

<span data-ttu-id="e77c6-218">Du kan ange följande värden för segment:</span><span class="sxs-lookup"><span data-stu-id="e77c6-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="e77c6-219">Produktmallsnummer = **D0123**</span><span class="sxs-lookup"><span data-stu-id="e77c6-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="e77c6-220">Kabinett = **M0008**</span><span class="sxs-lookup"><span data-stu-id="e77c6-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="e77c6-221">Frontgaller = **M0022**</span><span class="sxs-lookup"><span data-stu-id="e77c6-221">Front grill = **M0022**</span></span>

<span data-ttu-id="e77c6-222">I detta fall blir produktvariantnumret D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="e77c6-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="e77c6-223">Nummerkonflikter</span><span class="sxs-lookup"><span data-stu-id="e77c6-223">Numbering conflicts</span></span>
<span data-ttu-id="e77c6-224">I vissa fall kan ett produktvariantnummer som du skapar komma att inte framställa unika produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="e77c6-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="e77c6-225">Till exempel kommer produktvarianten inte att vara unika om en aktiv produktdimension inte inkluderas i terminologin för en produktmall som använder den fördefinierade variantkonfigurationstekniken.</span><span class="sxs-lookup"><span data-stu-id="e77c6-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="e77c6-226">Hur konflikter hanteras varierar beroende på inställningen för konfigurationsteknik.</span><span class="sxs-lookup"><span data-stu-id="e77c6-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="e77c6-227">Fördefinierade varianter</span><span class="sxs-lookup"><span data-stu-id="e77c6-227">Predefined variants</span></span>

<span data-ttu-id="e77c6-228">Ett fel uppstår om du manuellt skapar eller automatiskt försöker generera produktvarianter , och mer än en produktvariant erhåller samma produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="e77c6-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="e77c6-229">För att undvika detta bör du använda alla aktiva produktdimensioner i produktdimensionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e77c6-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="e77c6-230">Alternativt kan du inkludera en nummerserie för att garantera att produktvariantnumren är unika.</span><span class="sxs-lookup"><span data-stu-id="e77c6-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="e77c6-231">Begränsningsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-231">Constraint-based configurations</span></span>

<span data-ttu-id="e77c6-232">Beroende på terminologin kan systemet komma att försöka tilldela ett icke-unikt produktvariantnummer till en konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e77c6-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="e77c6-233">I så fall kommer systemet att använda nummerserien för konfigurationsdimensionen som produktvariantnummer istället. Om detta händer får du ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e77c6-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="e77c6-234">För att undvika detta scenario bör du inkludera tillräckligt med attribut i terminologin för att garantera unika produktvariantnummer.</span><span class="sxs-lookup"><span data-stu-id="e77c6-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="e77c6-235">Du bör också se till att alternativet **Återanvänd** aktiveras för komponenten.</span><span class="sxs-lookup"><span data-stu-id="e77c6-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="e77c6-236">Dimensionsbaserade konfigurationer</span><span class="sxs-lookup"><span data-stu-id="e77c6-236">Dimension-based configurations</span></span>

<span data-ttu-id="e77c6-237">Under ett steg under konfigurationsprocessen föreslår systemet ett konfigurationsvärde enligt terminologin.</span><span class="sxs-lookup"><span data-stu-id="e77c6-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="e77c6-238">I detta steg kan du ändra konfigurationsvärdet manuellt.</span><span class="sxs-lookup"><span data-stu-id="e77c6-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="e77c6-239">När du sparar konfigurationen kommer systemet att bekräfta att konfigurationsvärdet är unikt.</span><span class="sxs-lookup"><span data-stu-id="e77c6-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="e77c6-240">Du får ett felmeddelande om värdet som du angett inte är unikt.</span><span class="sxs-lookup"><span data-stu-id="e77c6-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="e77c6-241">Du måste ange ett unikt konfigurationsvärde för att spara konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e77c6-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="additional-resources"></a><span data-ttu-id="e77c6-242">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e77c6-242">Additional resources</span></span>
--------

[<span data-ttu-id="e77c6-243">Skapa en produktnummernomenklatur för fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="e77c6-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="e77c6-244">Skapa en produktnummerterminologi för konfigurerade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="e77c6-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

