---
title: Skapa en ny produkt i Commerce
description: I det här avsnittet beskrivs hur du skapar en ny produkt i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 44a58da0be280b06d96cdeae6929042bb50ed4a6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795725"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="46749-103">Skapa en ny produkt i Commerce</span><span class="sxs-lookup"><span data-stu-id="46749-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="46749-104">I det här avsnittet beskrivs hur du skapar en ny produkt i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46749-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="46749-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="46749-105">Overview</span></span>

<span data-ttu-id="46749-106">En produkt definieras i första hand med hjälp av ett produktnummer, ett namn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="46749-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="46749-107">Andra data är också nödvändiga för att beskriva en produkt eller tjänst:</span><span class="sxs-lookup"><span data-stu-id="46749-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="46749-108">Skapa en ny produkt</span><span class="sxs-lookup"><span data-stu-id="46749-108">Create a new product</span></span>

1. <span data-ttu-id="46749-109">I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Produkter per kategori**.</span><span class="sxs-lookup"><span data-stu-id="46749-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="46749-110">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="46749-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="46749-111">I listrutan **Produkttyp**, välj antingen **Objekt** eller **Tjänst**.</span><span class="sxs-lookup"><span data-stu-id="46749-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="46749-112">I listrutan **Delprodukttyp**, välj antingen **Produkt** (om produkten inte har några varianter) eller **Produktmall** (om produkten har varianter).</span><span class="sxs-lookup"><span data-stu-id="46749-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="46749-113">I rutan **produktnummer** ange ett produktnummer om ett inte redan är förifyllt.</span><span class="sxs-lookup"><span data-stu-id="46749-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="46749-114">I rutan **Produktnamn** anger du ett produktnamn.</span><span class="sxs-lookup"><span data-stu-id="46749-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="46749-115">I rutan **Söknamn**, ange ett söknamn.</span><span class="sxs-lookup"><span data-stu-id="46749-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="46749-116">I listrutan **Butikskategori**, välj en lämplig kategori.</span><span class="sxs-lookup"><span data-stu-id="46749-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="46749-117">Om produkten är ett paket, välj **Ja** för **Produktpaket**.</span><span class="sxs-lookup"><span data-stu-id="46749-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="46749-118">Om undertypen för produkt är produktmall ställer du in **produktdimensionsgrupp** så att de varianter som stöds inkluderas.</span><span class="sxs-lookup"><span data-stu-id="46749-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="46749-119">Alternativ inkluderar **färg**, **storlek**, **utförande** och **konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="46749-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="46749-120">Du kan behöva skapa ytterligare produktdimensionsgrupper om det behövs.</span><span class="sxs-lookup"><span data-stu-id="46749-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="46749-121">I listrutan **Konfigurationsteknik**, välj ett lämpligt alternativ.</span><span class="sxs-lookup"><span data-stu-id="46749-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="46749-122">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="46749-122">Select **OK**.</span></span>

<span data-ttu-id="46749-123">Följande bild visar en exempelprodukt som läggs till.</span><span class="sxs-lookup"><span data-stu-id="46749-123">The following image shows an example product being added.</span></span>

![Skapa en produkt](media/create-new-product.png)

<span data-ttu-id="46749-125">När en produkt har lagts till kan ytterligare data ställas in för den, t.ex. **produktbeskrivning**, **variantgrupper**, **dimensionsgrupper**, **produktattribut** och **relaterade produkter**.</span><span class="sxs-lookup"><span data-stu-id="46749-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="46749-126">Följande bild visar en produkts ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="46749-126">The following image shows a product's additional details.</span></span>

![Produktdetaljer](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="46749-128">Skapa produktvarianter</span><span class="sxs-lookup"><span data-stu-id="46749-128">Create product variants</span></span>

<span data-ttu-id="46749-129">Om undertypen för produkt är **produktmall** måste specifika varianter skapas.</span><span class="sxs-lookup"><span data-stu-id="46749-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="46749-130">Följ dessa steg för att skapa en produktvariant.</span><span class="sxs-lookup"><span data-stu-id="46749-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="46749-131">Välj **Produktvarianter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="46749-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="46749-132">Om variantgrupper har valts i åtgärdsfönstret väljer du \**variantförslag*.</span><span class="sxs-lookup"><span data-stu-id="46749-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="46749-133">Välj vilka varianter du vill stödja för produkten.</span><span class="sxs-lookup"><span data-stu-id="46749-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="46749-134">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="46749-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="46749-135">Frisläpp en produkt</span><span class="sxs-lookup"><span data-stu-id="46749-135">Release a product</span></span>

<span data-ttu-id="46749-136">Om du vill sälja en produkt måste den först frisläppas till en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="46749-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="46749-137">Välj **frisläppta produkter** på sidan produkt.</span><span class="sxs-lookup"><span data-stu-id="46749-137">From the product page, select **Release products**.</span></span>

    ![Frisläpp produkt](media/create-new-product-3.png)

1. <span data-ttu-id="46749-139">Välj produkten som ska frisläppas och välj sedan **nästa**.</span><span class="sxs-lookup"><span data-stu-id="46749-139">Select the product to release, and then select **Next**.</span></span>

    ![Välj produkt som ska frisläppas](media/create-new-product-4.png)

1. <span data-ttu-id="46749-141">Välj uppsättningen med produktvarianter som ska frisläppas och välj sedan **nästa**.</span><span class="sxs-lookup"><span data-stu-id="46749-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Välj varianter som ska frisläppas](media/create-new-product-5.png)

1. <span data-ttu-id="46749-143">Välj den juridiska personen och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="46749-143">Select the legal entity, and then select **Next**.</span></span>

    ![Välj juridisk person](media/create-new-product-6.png)

1. <span data-ttu-id="46749-145">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="46749-145">Select **Finish**.</span></span>

    ![Slutför produktfrisläppning](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="46749-147">Konfigurera en frisläppt produkt</span><span class="sxs-lookup"><span data-stu-id="46749-147">Configure a released product</span></span>

<span data-ttu-id="46749-148">När en produkt har frisläppts kräver den ytterligare konfiguration som omfattar att lägga till ett pris för produkten.</span><span class="sxs-lookup"><span data-stu-id="46749-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="46749-149">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Frisläppta produkter per kategori**.</span><span class="sxs-lookup"><span data-stu-id="46749-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="46749-150">Välj nod för produktkategori för produkten som släpptes och välj sedan produkten i produktlistan.</span><span class="sxs-lookup"><span data-stu-id="46749-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="46749-151">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="46749-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="46749-152">I avsnittet **inköp** konfigurerar du alla obligatoriska egenskaper inklusive **enhet**, **pris** och **kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="46749-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="46749-153">Välj **validera** i åtgärdsfönstret för att se till att inga fel rapporteras för saknade fält.</span><span class="sxs-lookup"><span data-stu-id="46749-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="46749-154">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="46749-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="46749-155">Följande bild visar ett exempel på en konfiguration för en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="46749-155">The following image shows an example configuration for a released product.</span></span>

![Konfigurera en frisläppt produkt](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="46749-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="46749-157">Additional resources</span></span>

[<span data-ttu-id="46749-158">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="46749-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="46749-159">Skapa en variantgrupp</span><span class="sxs-lookup"><span data-stu-id="46749-159">Create a variant group</span></span>](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]