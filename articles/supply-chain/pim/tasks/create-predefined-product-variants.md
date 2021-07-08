---
title: Skapa fördefinierade produktvarianter
description: Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270490"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="7c428-103">Fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="7c428-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="7c428-104">Exempelscenario: Skapa fördefinierade produktvarianter</span><span class="sxs-lookup"><span data-stu-id="7c428-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="7c428-105">Detta exempelscenario visar hur du skapar produktvarianter för en produktmall med hjälp av kombinationer av produktdimensioner.</span><span class="sxs-lookup"><span data-stu-id="7c428-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="7c428-106">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="7c428-106">Make demo data available</span></span>

<span data-ttu-id="7c428-107">För att följa detta scenario med hjälp av här föreslagna värden måste du ha demonstrationsdata installerade samt välja den juridiska personen *USMF*.</span><span class="sxs-lookup"><span data-stu-id="7c428-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="7c428-108">Steg 1: Skapa en produktmall</span><span class="sxs-lookup"><span data-stu-id="7c428-108">Step 1: Create a product master</span></span>

<span data-ttu-id="7c428-109">För att skapa en produktmall:</span><span class="sxs-lookup"><span data-stu-id="7c428-109">To create a product master:</span></span>

1. <span data-ttu-id="7c428-110">Gå till **Produktinformationshantering > Produkter > Produktmallar**.</span><span class="sxs-lookup"><span data-stu-id="7c428-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="7c428-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="7c428-111">Select **New**.</span></span>
1. <span data-ttu-id="7c428-112">Om fältet **Produktnummer** inte redan visar ett nummer anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="7c428-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="7c428-113">Detta krävs endast om ingen nummerserie har ställts in för detta fält.</span><span class="sxs-lookup"><span data-stu-id="7c428-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="7c428-114">Ange ett namn i fältet **Produktnamn**.</span><span class="sxs-lookup"><span data-stu-id="7c428-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="7c428-115">I fältet **Produktdimensionsgrupp** väljer du produktdimensionsgruppen *SizeCol* (storlek och färg).</span><span class="sxs-lookup"><span data-stu-id="7c428-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="7c428-116">Välj **OK** om du vill skapa och öppna den nya produktmallen.</span><span class="sxs-lookup"><span data-stu-id="7c428-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="7c428-117">Steg 2: Lägg till produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="7c428-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="7c428-118">Det här exemplet visar hur du manuellt anger produktdimensioner.</span><span class="sxs-lookup"><span data-stu-id="7c428-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="7c428-119">Du kan också välja att markera en storlek, färg eller utförandegrupp som innehåller de produktdimensionsvärden som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7c428-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="7c428-120">För att lägga till produktdimensioner:</span><span class="sxs-lookup"><span data-stu-id="7c428-120">To add product dimensions:</span></span>

1. <span data-ttu-id="7c428-121">Med din nya produktmall fortfarande öppen väljer du **Produktdimensioner** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c428-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="7c428-122">Öppna fliken **Storlek** och välj sedan **Ny** i verktygsfältet för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="7c428-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="7c428-123">Gör följande inställningar för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="7c428-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="7c428-124">**Storlek:** Välj ett storleksvärde.</span><span class="sxs-lookup"><span data-stu-id="7c428-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="7c428-125">**Namn:** Ange ett namn för storleken.</span><span class="sxs-lookup"><span data-stu-id="7c428-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="7c428-126">Välj **Ny** i verktygsfältet och lägg till en andra storlek i rutnätet med ny **Storlek** och **Namn**.</span><span class="sxs-lookup"><span data-stu-id="7c428-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="7c428-127">Öppna fliken **Färger** och välj sedan **Ny** i verktygsfältet för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="7c428-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="7c428-128">Gör följande inställningar för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="7c428-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="7c428-129">**Färg:** Välj ett färgvärde.</span><span class="sxs-lookup"><span data-stu-id="7c428-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="7c428-130">**Namn:** Ange ett namn för färgen.</span><span class="sxs-lookup"><span data-stu-id="7c428-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="7c428-131">Välj **Ny** i verktygsfältet och lägg till en andra storlek i rutnätet med en ny **Färg** och ett nytt **Namn**.</span><span class="sxs-lookup"><span data-stu-id="7c428-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="7c428-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7c428-132">Select **Save**.</span></span>
1. <span data-ttu-id="7c428-133">Stäng sidan när du vill återgå till din nya produktmall.</span><span class="sxs-lookup"><span data-stu-id="7c428-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="7c428-134">Steg 3: Skapa produktvarianter</span><span class="sxs-lookup"><span data-stu-id="7c428-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="7c428-135">I det här avsnittet beskrivs hur du skapar produktvarianter när funktionen *Förbättringar av variantförslagssida* inte är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="7c428-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="7c428-136">I nästa avsnitt finns mer information om hur du skapar produktvarianter när den funktionen är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="7c428-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="7c428-137">Så här skapar du produktvarianter:</span><span class="sxs-lookup"><span data-stu-id="7c428-137">To generate product variants:</span></span>

1. <span data-ttu-id="7c428-138">Med din nya produktmall fortfarande öppen väljer du **Produktvarianter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c428-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="7c428-139">Markera **Variantförslag** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c428-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="7c428-140">Systemet skapar en lista med alla möjliga kombinationer av de storlekar och färger du definierat för produkten.</span><span class="sxs-lookup"><span data-stu-id="7c428-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="7c428-141">Välj **Markera alla** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="7c428-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="7c428-142">I det här exemplet väljer du alla möjliga varianter.</span><span class="sxs-lookup"><span data-stu-id="7c428-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="7c428-143">Om du bara vill använda en deluppsättning av de möjliga kombinationerna av produktdimensioner markerar du endast de kryssrutor som behövs.</span><span class="sxs-lookup"><span data-stu-id="7c428-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="7c428-144">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7c428-144">Select **Create**.</span></span>
1. <span data-ttu-id="7c428-145">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7c428-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="7c428-146">Förbättrade variantförslag</span><span class="sxs-lookup"><span data-stu-id="7c428-146">Improved variant suggestions</span></span>

<span data-ttu-id="7c428-147">Funktionen *Förbättringar av förslagssida för varianter* förbättrar sidan **Variantförslag** i syfte att åtgärda problem med prestanda och användbarhet för företag med ett stort antal produktdimensionskombinationer.</span><span class="sxs-lookup"><span data-stu-id="7c428-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="7c428-148">Den förbättrade processen för val av produktdimensionsvärden för vilken variantförslag skapas gör det snabbare och enklare att identifiera och frisläppa relevanta produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="7c428-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="7c428-149">Följande förbättringar läggs till av den här funktionen:</span><span class="sxs-lookup"><span data-stu-id="7c428-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="7c428-150">**Uppskjuten generering av variantförslag:** Sidan **Variantförslag** visar inte längre förslag när du öppnar den första gången.</span><span class="sxs-lookup"><span data-stu-id="7c428-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="7c428-151">Du måste istället explicit välja vilka värden du behöver och sedan välja knappen **Föreslå** för att generera kombinationerna.</span><span class="sxs-lookup"><span data-stu-id="7c428-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="7c428-152">Detta gör processen mer synlig och interaktiv.</span><span class="sxs-lookup"><span data-stu-id="7c428-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="7c428-153">**Val av dimensionsvärden:** När du har många dimensionsvärden är du vanligtvis intresserad av att generera variantförslag som omfattar endast några av dem (till exempel när du inför en ny uppsättning färger eller utföranden).</span><span class="sxs-lookup"><span data-stu-id="7c428-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="7c428-154">Med den förbättrade designen kan du välja de dimensionsvärden för vilka du vill skapa förslag på produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="7c428-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="7c428-155">Detta ökar relevansen för de föreslagna varianterna avsevärt och förbättrar både systemprestanda och användarproduktivitet.</span><span class="sxs-lookup"><span data-stu-id="7c428-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="7c428-156">Aktivera funktionen för förbättrad variantförslagssida</span><span class="sxs-lookup"><span data-stu-id="7c428-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="7c428-157">Innan du kan använda funktionen *Förbättrad variantförslagssida* måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="7c428-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="7c428-158">Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="7c428-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="7c428-159">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="7c428-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7c428-160">**Modul:** *Produktinformationshantering*</span><span class="sxs-lookup"><span data-stu-id="7c428-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="7c428-161">**Funktionsnamn:** *Förbättrad variantförslagssida*</span><span class="sxs-lookup"><span data-stu-id="7c428-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="7c428-162">Arbeta med förbättrade variantförslag</span><span class="sxs-lookup"><span data-stu-id="7c428-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="7c428-163">Så här skapar du förslag på produktvarianter när funktionen *Förbättringar av variantförslagssida* är aktiverad:</span><span class="sxs-lookup"><span data-stu-id="7c428-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="7c428-164">Öppna eller skapa en produktmall och lägg till de produktdimensioner som krävs för den, enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="7c428-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="7c428-165">Med den nya produktmallen öppen väljer du **Produktvarianter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c428-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="7c428-166">Markera **Variantförslag** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7c428-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="7c428-167">Välj de värden som du vill använda för respektive dimension.</span><span class="sxs-lookup"><span data-stu-id="7c428-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="7c428-168">Välj **Föreslå** i det övre verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="7c428-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="7c428-169">Systemet skapar en lista med alla möjliga kombinationer av de storlekar och färger du har valt.</span><span class="sxs-lookup"><span data-stu-id="7c428-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="7c428-170">Markera kryssrutan för varje kombination av produktdimensioner som du vill använda på snabbfliken **Föreslagna varianter** eller välj **Markera alla** i verktygsfältet för att välja samtliga.</span><span class="sxs-lookup"><span data-stu-id="7c428-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="7c428-171">Välj **Skapa** om du vill lägga till varianterna i den aktuella produktmallen.</span><span class="sxs-lookup"><span data-stu-id="7c428-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
