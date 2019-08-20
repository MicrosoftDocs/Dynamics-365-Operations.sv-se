---
title: Produktdimensioner
description: 'Det finns fyra produktdimensioner: färg, konfiguration, storlek och utförande. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.'
author: cvocph
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3391679696c0e1dd84840821480ccbfb544829a6
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2019
ms.locfileid: "1863046"
---
# <a name="product-dimensions"></a><span data-ttu-id="7e595-105">Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="7e595-105">Product dimensions</span></span>

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

<span data-ttu-id="7e595-106">Det finns fyra produktdimensioner: färg, konfiguration, storlek och utförande.</span><span class="sxs-lookup"><span data-stu-id="7e595-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="7e595-107">Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar.</span><span class="sxs-lookup"><span data-stu-id="7e595-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="7e595-108">Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.</span><span class="sxs-lookup"><span data-stu-id="7e595-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="7e595-109">Produktdimensioner är egenskaper som används för att identifiera en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="7e595-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="7e595-110">Du kan använda kombinationer av produktdimensioner för att definiera produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="7e595-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="7e595-111">Du måste definiera minst en produktdimension för en produktmall om du vill skapa en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="7e595-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>

## <a name="product-variants"></a><span data-ttu-id="7e595-112">Produktvarianter</span><span class="sxs-lookup"><span data-stu-id="7e595-112">Product variants</span></span>

<span data-ttu-id="7e595-113">Produktvarianter kallas också för artiklar.</span><span class="sxs-lookup"><span data-stu-id="7e595-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="7e595-114">En artikel är en materiell produkt, vilket inte är detsamma som en tjänst.</span><span class="sxs-lookup"><span data-stu-id="7e595-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="7e595-115">Det är också möjligt att definiera en produktmall med typen Tjänst.</span><span class="sxs-lookup"><span data-stu-id="7e595-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="7e595-116">Med typen Tjänst kan du ange produktvarianter som innehåller tjänster.</span><span class="sxs-lookup"><span data-stu-id="7e595-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="7e595-117">Du kan till exempel ange en produktmall för konsultarbete och produktvarianter för arbete som utförs av seniorkonsulter och juniorkonsulter.</span><span class="sxs-lookup"><span data-stu-id="7e595-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="7e595-118">Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="7e595-118">Product dimensions</span></span>
<span data-ttu-id="7e595-119">Följande produktdimensioner finns: konfiguration, färg, storlek och utförande.</span><span class="sxs-lookup"><span data-stu-id="7e595-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="7e595-120">En produktvariant kan genereras baserat på produktdimensionsvärdena.</span><span class="sxs-lookup"><span data-stu-id="7e595-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="7e595-121">Produktdimensionvärden som till exempel Storlek, Färg och Utförande kan skapas på sidorna **Storlek**, **Färg** och **Utförande** som du öppnar från följande platser: **Produktinformationshantering** &gt; **Inställningar** &gt; **Dimensions- och variantgrupper** &gt; **Storlekar/Färger/Utföranden**.</span><span class="sxs-lookup"><span data-stu-id="7e595-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="7e595-122">Produktdimensionsvärden för konfigurationsdimensionen skapas vanligtvis med hjälp av antingen produktkonfigureraren eller med den dimensionsbaserade konfigureraren.</span><span class="sxs-lookup"><span data-stu-id="7e595-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="7e595-123">Produktdimensioner kan också skapas och underhållas på sidan **Produktdimensioner** som du öppnar från följande platser:</span><span class="sxs-lookup"><span data-stu-id="7e595-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="7e595-124">Klicka på **Produktinformationshantering** &gt; **Produkter** &gt; **Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="7e595-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="7e595-125">I **Åtgärdsfönstret**, klicka på **Produktdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7e595-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="7e595-126">Klicka på **Produktinformationshantering** &gt; **Produkter** &gt; **Alla produkter och produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="7e595-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="7e595-127">Välj en produktmall.</span><span class="sxs-lookup"><span data-stu-id="7e595-127">Select a product master.</span></span> <span data-ttu-id="7e595-128">I **Åtgärdsfönstret**, klicka på **Produktdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7e595-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="7e595-129">Klicka på **Produktinformationshantering** &gt; **Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="7e595-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="7e595-130">Välj en produktmall.</span><span class="sxs-lookup"><span data-stu-id="7e595-130">Select a product master.</span></span> <span data-ttu-id="7e595-131">I **Åtgärdsfönstret**, klicka på **Produkt**.</span><span class="sxs-lookup"><span data-stu-id="7e595-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="7e595-132">I gruppen **Produktmall**, klicka på **Produktdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7e595-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="7e595-133">Antalet varianter som du kan skapa för en artikel begränsas av antalet möjliga produktdimensionskombinationer.</span><span class="sxs-lookup"><span data-stu-id="7e595-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>

| <span data-ttu-id="7e595-134">**Tips!**</span><span class="sxs-lookup"><span data-stu-id="7e595-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7e595-135">När du använder en produkt på till exempel en orderrad väljer du produktdimensioner för att identifiera produktvarianten du vill arbeta med.</span><span class="sxs-lookup"><span data-stu-id="7e595-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="7e595-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="7e595-136">Example</span></span>
<span data-ttu-id="7e595-137">Ett företag säljer jeans.</span><span class="sxs-lookup"><span data-stu-id="7e595-137">A company sells denim jeans.</span></span> <span data-ttu-id="7e595-138">Artikeln jeans använder produktdimensionerna för färg och storlek.</span><span class="sxs-lookup"><span data-stu-id="7e595-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="7e595-139">Jeansen säljs i tre olika färger och i sex olika storlekar.</span><span class="sxs-lookup"><span data-stu-id="7e595-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="7e595-140">Färger: Blått, Svart, Brunt, Storlekar: XS S, XL, L, XL. Alla storlekar är inte tillgängliga i alla tre färger.</span><span class="sxs-lookup"><span data-stu-id="7e595-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="7e595-141">Om alla kombinationerna vore tillgängliga skulle det skapa 18 olika typer av jeans.</span><span class="sxs-lookup"><span data-stu-id="7e595-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="7e595-142">I det här exemplet produceras bara följande nio produktvariantkombinationer.</span><span class="sxs-lookup"><span data-stu-id="7e595-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="7e595-143">Färg</span><span class="sxs-lookup"><span data-stu-id="7e595-143">Color</span></span> | <span data-ttu-id="7e595-144">Storlek</span><span class="sxs-lookup"><span data-stu-id="7e595-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="7e595-145">Blått</span><span class="sxs-lookup"><span data-stu-id="7e595-145">Blue</span></span>  | <span data-ttu-id="7e595-146">XS</span><span class="sxs-lookup"><span data-stu-id="7e595-146">XS</span></span>   |
| <span data-ttu-id="7e595-147">Blått</span><span class="sxs-lookup"><span data-stu-id="7e595-147">Blue</span></span>  | <span data-ttu-id="7e595-148">L</span><span class="sxs-lookup"><span data-stu-id="7e595-148">S</span></span>    |
| <span data-ttu-id="7e595-149">Blått</span><span class="sxs-lookup"><span data-stu-id="7e595-149">Blue</span></span>  | <span data-ttu-id="7e595-150">M</span><span class="sxs-lookup"><span data-stu-id="7e595-150">M</span></span>    |
| <span data-ttu-id="7e595-151">Svart</span><span class="sxs-lookup"><span data-stu-id="7e595-151">Black</span></span> | <span data-ttu-id="7e595-152">M</span><span class="sxs-lookup"><span data-stu-id="7e595-152">M</span></span>    |
| <span data-ttu-id="7e595-153">Svart</span><span class="sxs-lookup"><span data-stu-id="7e595-153">Black</span></span> | <span data-ttu-id="7e595-154">S</span><span class="sxs-lookup"><span data-stu-id="7e595-154">L</span></span>    |
| <span data-ttu-id="7e595-155">Svart</span><span class="sxs-lookup"><span data-stu-id="7e595-155">Black</span></span> | <span data-ttu-id="7e595-156">XL</span><span class="sxs-lookup"><span data-stu-id="7e595-156">XL</span></span>   |
| <span data-ttu-id="7e595-157">Brun</span><span class="sxs-lookup"><span data-stu-id="7e595-157">Brown</span></span> | <span data-ttu-id="7e595-158">S</span><span class="sxs-lookup"><span data-stu-id="7e595-158">L</span></span>    |
| <span data-ttu-id="7e595-159">Brun</span><span class="sxs-lookup"><span data-stu-id="7e595-159">Brown</span></span> | <span data-ttu-id="7e595-160">XL</span><span class="sxs-lookup"><span data-stu-id="7e595-160">XL</span></span>   |
| <span data-ttu-id="7e595-161">Brun</span><span class="sxs-lookup"><span data-stu-id="7e595-161">Brown</span></span> | <span data-ttu-id="7e595-162">XXL</span><span class="sxs-lookup"><span data-stu-id="7e595-162">XXL</span></span>  |





