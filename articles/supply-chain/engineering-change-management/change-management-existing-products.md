---
title: Aktivera ändringshantering för befintliga produkter
description: I det här avsnittet beskrivs hur du aktiverar ändringshantering för befintliga produkter. Det beskriver också fall där möjligheten att aktivera ändringshantering är begränsad.
author: t-benebo
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8b9f34f5980937da62610d9668a95816ba6054ef
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500872"
---
# <a name="enable-change-management-on-existing-products"></a><span data-ttu-id="2cd81-104">Aktivera ändringshantering för befintliga produkter</span><span class="sxs-lookup"><span data-stu-id="2cd81-104">Enable change management on existing products</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="2cd81-105">I det här avsnittet beskrivs hur du aktiverar ändringshantering för befintliga produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-105">This topic explains how you can enable change management for existing products.</span></span> <span data-ttu-id="2cd81-106">Det beskriver också fall där möjligheten att aktivera ändringshantering är begränsad.</span><span class="sxs-lookup"><span data-stu-id="2cd81-106">It also describes cases where your ability to enable change management is limited.</span></span>

<span data-ttu-id="2cd81-107">När du aktiverar ändringshantering för en befintlig produkt, kan du skapa versioner av produkten och spåra ändringar som gjorts i den under hela dess livslängd.</span><span class="sxs-lookup"><span data-stu-id="2cd81-107">When you enable change management for an existing product, you can create versions of that product and trace changes that are made to it throughout its life.</span></span> <span data-ttu-id="2cd81-108">Därför kan du spåra dessa ändringar genom att använda ändringsorder.</span><span class="sxs-lookup"><span data-stu-id="2cd81-108">Therefore, you can track those changes by using change orders.</span></span> <span data-ttu-id="2cd81-109">Om du vill aktivera ändringshantering måste du konvertera relevanta produkter till *tekniska artiklar* (även kallade tekniska produkter).</span><span class="sxs-lookup"><span data-stu-id="2cd81-109">To enable change management, you must convert the relevant products to *engineering items* (also referred to as engineering products).</span></span> <span data-ttu-id="2cd81-110">Teknikprodukter är produkter som versioneras och hanteras med hjälp av ändringshantering.</span><span class="sxs-lookup"><span data-stu-id="2cd81-110">Engineering products are products that are versioned and managed through change management.</span></span> <span data-ttu-id="2cd81-111">Här finns en guide som vägleder dig genom konverteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2cd81-111">A wizard is provided to guide you through the conversion process.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="2cd81-112">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="2cd81-112">Turn on the feature in your system</span></span>

<span data-ttu-id="2cd81-113">Om du vill använda denna funktion måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="2cd81-113">To use this capability, you must complete the following tasks:</span></span>

1. <span data-ttu-id="2cd81-114">Aktivera konstruktionsändringshantering-funktionen och dess konfigurationsnyckel som beskrivs i [Översikt över konstruktionsändringshantering](product-engineering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-114">Enable the Engineering change management feature and its configuration key as described in [Engineering change management overview](product-engineering-overview.md).</span></span>
1. <span data-ttu-id="2cd81-115">Aktivera funktionen *Aktivera ändringshantering av befintliga produkter* i funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="2cd81-115">Turn on the *Enable change management on existing products* feature in feature management.</span></span> <span data-ttu-id="2cd81-116">Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-116">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="restrictions-and-limitations"></a><span data-ttu-id="2cd81-117">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="2cd81-117">Restrictions and limitations</span></span>

<span data-ttu-id="2cd81-118">Alla produkttyper kan inte konverteras till alla andra typer.</span><span class="sxs-lookup"><span data-stu-id="2cd81-118">Not all product types can be converted to all other types.</span></span> <span data-ttu-id="2cd81-119">Följande begränsningar gäller:</span><span class="sxs-lookup"><span data-stu-id="2cd81-119">The following restrictions and limitations apply:</span></span>

- <span data-ttu-id="2cd81-120">När du konverterar en produkt till en teknisk produkt, förblir den en *produkt*.</span><span class="sxs-lookup"><span data-stu-id="2cd81-120">When you convert a product to an engineering product, it remains a *product*.</span></span> <span data-ttu-id="2cd81-121">Den blir inte en *produktmall*.</span><span class="sxs-lookup"><span data-stu-id="2cd81-121">It doesn't become a *product master*.</span></span>
- <span data-ttu-id="2cd81-122">När du konverterar en produktmall som har en viss dimensionsuppsättning, underhålls dessa dimensioner efter ändringen.</span><span class="sxs-lookup"><span data-stu-id="2cd81-122">When you convert a product master that has a specific set of dimensions, those dimensions are maintained after the change.</span></span> <span data-ttu-id="2cd81-123">Om du till exempel konverterar en produktmall som har storleksdimensionen behåller den storleksdimensionen.</span><span class="sxs-lookup"><span data-stu-id="2cd81-123">For example, if you convert a product master that has the size dimension, it will keep the size dimension.</span></span>

<span data-ttu-id="2cd81-124">Om du har en specifik produkt kan du därför endast ändra den till en teknisk produkt som inte spårar produktdimensionen i transaktioner (det vill säga den versionsdimension som inte används).</span><span class="sxs-lookup"><span data-stu-id="2cd81-124">Therefore, if you have a distinct product, you can change it only to an engineering product that doesn't track the product dimension in transactions (that is, the version dimension isn't used).</span></span> <span data-ttu-id="2cd81-125">Se de återstående delarna av detta ämne för mer information om dessa problem.</span><span class="sxs-lookup"><span data-stu-id="2cd81-125">See the remaining sections of this topic for more information about these issues.</span></span>

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a><span data-ttu-id="2cd81-126">Förbered konvertering genom att skapa alla nödvändiga kategorier för tekniska produkter</span><span class="sxs-lookup"><span data-stu-id="2cd81-126">Prepare for conversion by creating all required engineering product categories</span></span>

<span data-ttu-id="2cd81-127">En *teknisk produktkategori* måste tilldelas varje teknisk produkt.</span><span class="sxs-lookup"><span data-stu-id="2cd81-127">An *engineering product category* must be assigned to every engineering product.</span></span> <span data-ttu-id="2cd81-128">Du gör den här tilldelningen när du kör guiden **Omvandla till teknisk produkt**.</span><span class="sxs-lookup"><span data-stu-id="2cd81-128">You will do this assignment when you run the **Convert to engineering product** wizard.</span></span> <span data-ttu-id="2cd81-129">Teknikproduktkategorier måste finnas för alla relevanta standardprodukter *innan* du kan konvertera dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-129">Engineering product categories must exist for all relevant standard products *before* you can convert those products.</span></span>

<span data-ttu-id="2cd81-130">Den tekniska produktkategorin utgör grunden för att skapa en teknisk produkt, och den förser en uppsättning standardvärden och principer.</span><span class="sxs-lookup"><span data-stu-id="2cd81-130">The engineering product category provides a basis for creating an engineering product, and it establishes a set of default values and policies.</span></span> <span data-ttu-id="2cd81-131">Den tekniska produktkategorin måste matcha den produkt som du tilldelar den.</span><span class="sxs-lookup"><span data-stu-id="2cd81-131">The engineering product category must match the product that you assign it to.</span></span> <span data-ttu-id="2cd81-132">Produkttypen och dimensionsgruppen måste till exempel matcha både produkten och den tekniska produktkategorin.</span><span class="sxs-lookup"><span data-stu-id="2cd81-132">For example, the product type and dimension group must match both the product and its engineering product category.</span></span> <span data-ttu-id="2cd81-133">För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-133">For more information, see [Engineering versions and engineering product categories](engineering-versions-product-category.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2cd81-134">Guiden **Omvandla till teknisk produkt** kan bara konvertera produkt till teknikprodukter där versionen inte spåras i transaktioner.</span><span class="sxs-lookup"><span data-stu-id="2cd81-134">The **Convert to engineering product** wizard can convert product only to engineering products where the version isn't tracked in transactions.</span></span> <span data-ttu-id="2cd81-135">Därför måste alternativet **Spåra version i transaktioner** ställas in *Nej* för att konstruera produktkategorier som du skapar för att konvertera befintliga produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-135">Therefore, the **Track version in transactions** option must be set to *No* for engineering product categories that you create to convert existing products.</span></span>

<span data-ttu-id="2cd81-136">För information om hur du skapar tekniska produktkategorier finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-136">For information about how to create engineering product categories, see [Engineering versions and engineering product categories](engineering-versions-product-category.md).</span></span>

## <a name="run-the-convert-to-engineering-product-wizard"></a><span data-ttu-id="2cd81-137">Köra guiden Konvertera till teknikprodukt</span><span class="sxs-lookup"><span data-stu-id="2cd81-137">Run the Convert to engineering product wizard</span></span>

<span data-ttu-id="2cd81-138">Med guiden **Omvandla till teknisk produkt** hjälper dig att konvertera en eller flera befintliga produkter till tekniska produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-138">The **Convert to engineering product** wizard helps you convert one or more existing products to engineering products.</span></span> <span data-ttu-id="2cd81-139">Produkter omvandlas till tekniska produkter (versionerade produkter) där versionen inte spåras i transaktioner (det vill säga den versionsdimension som inte används).</span><span class="sxs-lookup"><span data-stu-id="2cd81-139">It converts the products into engineering products (versioned products) where the version isn't tracked in transactions (that is, the version dimension isn't used).</span></span> <span data-ttu-id="2cd81-140">När konverteringen är klar kan du hantera produkterna med hjälp av teknikändringshantering.</span><span class="sxs-lookup"><span data-stu-id="2cd81-140">After the conversion is completed, you can manage the products by using Engineering change management.</span></span>

<span data-ttu-id="2cd81-141">Konverteringen är permanent.</span><span class="sxs-lookup"><span data-stu-id="2cd81-141">The conversion is permanent.</span></span> <span data-ttu-id="2cd81-142">Därför kan du inte återföra det senare.</span><span class="sxs-lookup"><span data-stu-id="2cd81-142">Therefore, you won't be able to reverse it later.</span></span> 

<span data-ttu-id="2cd81-143">Varje konverterad teknikprodukt kommer att fortsätta att frisläppas i samma företag som den ursprungliga produkten frisläppdes i.</span><span class="sxs-lookup"><span data-stu-id="2cd81-143">Each converted engineering product will continue to be released in the same companies that the original product was released in.</span></span> <span data-ttu-id="2cd81-144">Emellertid kommer strukturlista (BOM) och rutter inte automatiskt att släppas till dessa företag.</span><span class="sxs-lookup"><span data-stu-id="2cd81-144">However, the engineering bill of materials (BOM) and routes won't automatically be released to those companies.</span></span>

<span data-ttu-id="2cd81-145">Följ dessa steg för att köra guiden **Omvandla till teknisk produkt** och konvertera en produkt till en ingenjörsprodukt.</span><span class="sxs-lookup"><span data-stu-id="2cd81-145">Follow these steps to run the **Convert to engineering product** wizard and convert a product to an engineering product.</span></span>

1. <span data-ttu-id="2cd81-146">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="2cd81-146">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="2cd81-147">Markera kryssrutan i rutnätet för varje produkt som du vill konvertera.</span><span class="sxs-lookup"><span data-stu-id="2cd81-147">In the grid, select the check box for each product that you want to convert.</span></span>
1. <span data-ttu-id="2cd81-148">I åtgärdsfönstret på fliken **Tekniker** i grupp **Konstruktionsändringshantering** välj **Omvandla till teknisk produkt** för att öppna guiden.</span><span class="sxs-lookup"><span data-stu-id="2cd81-148">On the Action Pane, on the **Engineer** tab, in the **Engineering change management** group, select **Convert to engineering product** to open the wizard.</span></span>
1. <span data-ttu-id="2cd81-149">Den första sidan i guiden är **välkomstsidan**.</span><span class="sxs-lookup"><span data-stu-id="2cd81-149">The first page of the wizard is the **Welcome** page.</span></span> <span data-ttu-id="2cd81-150">Om du inte redan känner till konverteringsprocessen läser du informationen noggrant på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="2cd81-150">If you aren't already familiar with the conversion process, carefully read the information on this page.</span></span> <span data-ttu-id="2cd81-151">När du är redo att fortsätta väljer du **nästa**.</span><span class="sxs-lookup"><span data-stu-id="2cd81-151">When you're ready to continue, select **Next**.</span></span>
1. <span data-ttu-id="2cd81-152">På sidan **Välj detaljer för de produkter som ska konverteras** visas varje produkt som du valde innan du öppnade guiden.</span><span class="sxs-lookup"><span data-stu-id="2cd81-152">The **Select details for the products to be converted** page shows each product that you selected before you opened the wizard.</span></span> <span data-ttu-id="2cd81-153">Inspektera listan.</span><span class="sxs-lookup"><span data-stu-id="2cd81-153">Inspect the list.</span></span> <span data-ttu-id="2cd81-154">Använd knappar **Ny** och **Ta bort** i verktygsfältet för att lägga till eller ta bort produkter efter behov.</span><span class="sxs-lookup"><span data-stu-id="2cd81-154">Use the **New** and **Delete** buttons on the toolbar to add or remove products as you require.</span></span>
1. <span data-ttu-id="2cd81-155">Använd följande fält högst upp i rutnätet om du vill tilldela standardvärden till varje produkt som visas.</span><span class="sxs-lookup"><span data-stu-id="2cd81-155">Use the following fields at the top of the grid to assign default values to every product that is listed.</span></span> <span data-ttu-id="2cd81-156">(Du kan ändra dessa värden för enskilda produkter när konverteringen är klar.) Standardvärden tilldelas inte produkter där ett relevant värde redan har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="2cd81-156">(You will be able to change these values for individual products after the conversion is completed.) Default values won't be assigned to products where a relevant value has already been assigned.</span></span>

    - <span data-ttu-id="2cd81-157">**Standardteknikkategori** – Välj en grundläggande teknisk produktkategori att tilldela till alla listade produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-157">**Default engineering category** – Select an initial engineering product category to assign to every listed product.</span></span> <span data-ttu-id="2cd81-158">Den kategori du väljer tillämpas endast på produkter som är kompatibla med den.</span><span class="sxs-lookup"><span data-stu-id="2cd81-158">The category that you select will be applied only to products that are compatible with it.</span></span>
    - <span data-ttu-id="2cd81-159">**Standardversion** – Ange den ursprungliga produktversionen som ska tilldelas varje listad produkt.</span><span class="sxs-lookup"><span data-stu-id="2cd81-159">**Default version** – Enter the initial product version to assign to every listed product.</span></span> <span data-ttu-id="2cd81-160">Alla tekniska produkter har minst en teknisk version.</span><span class="sxs-lookup"><span data-stu-id="2cd81-160">Every engineering product has at least one engineering version.</span></span>
    - <span data-ttu-id="2cd81-161">**Standard livscykeltillstånd** – Välj det ursprungliga livscykeltillståndet för produkten som ska tilldelas varje listad produkt.</span><span class="sxs-lookup"><span data-stu-id="2cd81-161">**Default lifecycle state** – Select the initial product lifecycle state to assign to every listed product.</span></span>
    - <span data-ttu-id="2cd81-162">**Nuvarande strukturlista kommer att ingå i teknikprodukten** – Markera den här kryssrutan om den aktuella strukturlistan för varje listad produkt ska användas som en strukturlista för teknikprodukten.</span><span class="sxs-lookup"><span data-stu-id="2cd81-162">**Current BOM will be part of the engineering product** – Select this check box if the current BOM for each listed product should be used as a BOM for the engineering product.</span></span>

    <span data-ttu-id="2cd81-163">Mer information om inställning av produkt finns i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="2cd81-163">For more information about product settings, see the next step.</span></span>

1. <span data-ttu-id="2cd81-164">Granska varje produkt som listas i rutnätet och utvärdera hur väl de standardvärden som du har tilldelats gäller för den.</span><span class="sxs-lookup"><span data-stu-id="2cd81-164">Review each product that is listed in the grid, and evaluate how well the default values that you assigned apply to it.</span></span> <span data-ttu-id="2cd81-165">Granska följande information för varje rad och ställ in relevanta fält:</span><span class="sxs-lookup"><span data-stu-id="2cd81-165">For each row, review the following information and set any relevant fields:</span></span>

    - <span data-ttu-id="2cd81-166">**Produktnummer** – produktnummer.</span><span class="sxs-lookup"><span data-stu-id="2cd81-166">**Product number** – The product number.</span></span>
    - <span data-ttu-id="2cd81-167">**Produktnamn** – Produktens namn.</span><span class="sxs-lookup"><span data-stu-id="2cd81-167">**Product name** – The name of the product.</span></span>
    - <span data-ttu-id="2cd81-168">**Teknikkategori** – Välj den tekniska produktkategorin som produkten ska tillhöra när den har konverterats.</span><span class="sxs-lookup"><span data-stu-id="2cd81-168">**Engineering category** – Select the engineering product category that the product should belong to after it's converted.</span></span> <span data-ttu-id="2cd81-169">Det måste redan finnas en lämplig kategori för varje produkt, vilket beskrivs i det föregående avsnittet av det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2cd81-169">An appropriate category must already exist for each product, as was explained in the previous section of this topic.</span></span> <span data-ttu-id="2cd81-170">Du måste tilldela en kategori till varje produkt.</span><span class="sxs-lookup"><span data-stu-id="2cd81-170">You must assign a category to every product.</span></span>
    - <span data-ttu-id="2cd81-171">**Version** – Ange produktversionen för att tilldela produkten efter att den har konverterats.</span><span class="sxs-lookup"><span data-stu-id="2cd81-171">**Version** – Enter the product version to assign to the product after it's converted.</span></span> <span data-ttu-id="2cd81-172">Du kan till exempel välja ett nummer som passar in i den nummerserie som din kategori redan använder.</span><span class="sxs-lookup"><span data-stu-id="2cd81-172">For example, you might select a number that fits in the number sequence that your category already uses.</span></span> <span data-ttu-id="2cd81-173">I varje konstruktionsversion lagras de tekniska relevanta data som är specifika för den versionen.</span><span class="sxs-lookup"><span data-stu-id="2cd81-173">Each engineering version stores the engineering-relevant data that is specific to that version.</span></span> <span data-ttu-id="2cd81-174">För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-174">For more information, see [Engineering versions and engineering product categories](engineering-versions-product-category.md).</span></span>
    - <span data-ttu-id="2cd81-175">**Produktens livscykeltillstånd** – Välj produktens livscykeltillstånd som produkten ska vara i efter att den har konverterats.</span><span class="sxs-lookup"><span data-stu-id="2cd81-175">**Product lifecycle state** – Select the product lifecycle state that the product should be in after it's converted.</span></span> <span data-ttu-id="2cd81-176">I produkts livscykeltillstånd kan du kontrollera vilka transaktioner som är tillåtna för en given teknisk version.</span><span class="sxs-lookup"><span data-stu-id="2cd81-176">The product lifecycle state lets you to control which transactions are allowed for a given engineering version.</span></span> <span data-ttu-id="2cd81-177">Mer information finns i [produktens livscykeltillstånd och transaktioner](product-lifecycle-state-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="2cd81-177">For more information, see [Product lifecycle states and transactions](product-lifecycle-state-transactions.md).</span></span>
    - <span data-ttu-id="2cd81-178">**Har strukturlista** – En markerad kryssruta visar att produkten har en strukturlista.</span><span class="sxs-lookup"><span data-stu-id="2cd81-178">**Has BOM** – A selected check box indicates that the product has a BOM.</span></span> <span data-ttu-id="2cd81-179">Om du ställer in den här kryssrutan kan du bestämma hur du anger kryssrutan **aktuell strukturlista ska ingå i den tekniska produkten**.</span><span class="sxs-lookup"><span data-stu-id="2cd81-179">The setting of this check box can help you decide how to set the **Current BOM will be part of the engineering product** check box.</span></span>
    - <span data-ttu-id="2cd81-180">**Nuvarande strukturlista kommer att ingå i teknikprodukten** – Markera den här kryssrutan om den aktuella strukturlistan för produkt ska användas som en strukturlista för teknikprodukten.</span><span class="sxs-lookup"><span data-stu-id="2cd81-180">**Current BOM will be part of the engineering product** – Select this check box if the current BOM of the product should be used as a BOM for the engineering product.</span></span> <span data-ttu-id="2cd81-181">Denna strukturlista hanteras sedan av konstruktionsändringshantering.</span><span class="sxs-lookup"><span data-stu-id="2cd81-181">That BOM will then be managed by Engineering change management.</span></span> <span data-ttu-id="2cd81-182">Om produkten inte har någon strukturlista eller om du föredrar att skapa en strukturlista manuellt för den konverterade produkten senare avmarkerar du den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="2cd81-182">If the product doesn't have a BOM, or if you prefer to manually create a BOM for the converted product later, clear this check box.</span></span>
    - <span data-ttu-id="2cd81-183">**Innehåller fel** – En markerad kryssruta anger att produktinställningen har ett eller flera fel.</span><span class="sxs-lookup"><span data-stu-id="2cd81-183">**Has errors** – A selected check box indicates that the product setup has one or more errors.</span></span> <span data-ttu-id="2cd81-184">Till exempel kanske produkttypen eller dimensionsgruppen inte matchar kategorin.</span><span class="sxs-lookup"><span data-stu-id="2cd81-184">For example, the product type or the dimension group might not match in the category.</span></span> <span data-ttu-id="2cd81-185">Produkter som har fel hoppas över och konverteras inte.</span><span class="sxs-lookup"><span data-stu-id="2cd81-185">Products that have errors will be skipped and won't be converted.</span></span>

1. <span data-ttu-id="2cd81-186">När du är klar väljer du **Validera** i verktygsfältet för att validera produktinställningarna.</span><span class="sxs-lookup"><span data-stu-id="2cd81-186">When you've finished, select **Validate** on the toolbar to validate the product setup.</span></span> <span data-ttu-id="2cd81-187">För varje rad uppdateras kryssrutan **Har fel** för att indikera produktens status.</span><span class="sxs-lookup"><span data-stu-id="2cd81-187">For each row, the **Has errors** check box will be updated to indicate the product's status.</span></span> <span data-ttu-id="2cd81-188">Justera värdena tills inställningarna för varje produkt är felfria.</span><span class="sxs-lookup"><span data-stu-id="2cd81-188">Adjust the values until the setup of every product is free of errors.</span></span>
1. <span data-ttu-id="2cd81-189">När alla produkter har ställts in på rätt sätt väljer du **Nästa** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="2cd81-189">When all the products are set up correctly, select **Next** to continue.</span></span>
1. <span data-ttu-id="2cd81-190">Sidan **Bekräfta val** visas antalet produkter som inte har några fel i inställningarna och därför är klara för konvertering.</span><span class="sxs-lookup"><span data-stu-id="2cd81-190">The **Confirm selection** page shows the number of products that have no errors in their setup and are therefore ready for conversion.</span></span> <span data-ttu-id="2cd81-191">Här visas också antalet produkter som kommer att hoppas över på grund av fel.</span><span class="sxs-lookup"><span data-stu-id="2cd81-191">It also shows the number of products that will be skipped because of errors.</span></span> <span data-ttu-id="2cd81-192">Om du vill köra konverteringen som ett batchjobb ställer du in batchalternativet **Kör i batch** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2cd81-192">To run the conversion as a batch job, set the **Run in batch** option to *Yes*.</span></span>
1. <span data-ttu-id="2cd81-193">Välj **Slutför** om du vill använda dina inställningar och börja konvertera produkterna till tekniska produkter.</span><span class="sxs-lookup"><span data-stu-id="2cd81-193">Select **Finish** to apply your settings and start to convert the products to engineering products.</span></span>

> [!NOTE]
> <span data-ttu-id="2cd81-194">Om ditt system har ställts in för att acceptera produkter manuellt innan de frisläpps måste du acceptera varje konverterad produkt genom att använda sidan **Öppna produktfrisläppningar** i lämpliga företag.</span><span class="sxs-lookup"><span data-stu-id="2cd81-194">If your system is set up to manually accept products before they are released, you must accept each converted product by using the **Open product releases** page in the appropriate companies.</span></span> <span data-ttu-id="2cd81-195">För mer information, se [Granska och acceptera produkten innan du släpper den i det lokala företaget](engineering-scenarios.md#accept).</span><span class="sxs-lookup"><span data-stu-id="2cd81-195">For more information, see [Review and accept the product before you release it in the local company](engineering-scenarios.md#accept).</span></span>