---
title: Konfigurera produktkvantitetsgränser på nätandelsplatser för B2B
description: I detta ämne beskrivs hur du ställer in produktkvantitetsgränser för B2B-näthandelssajter.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e70648da2cc1c526625b6e34fd0867d40abb5a85
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035967"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a><span data-ttu-id="96c83-103">Konfigurera produktkvantitetsgränser på nätandelsplatser för B2B</span><span class="sxs-lookup"><span data-stu-id="96c83-103">Set product quantity limits for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="96c83-104">I detta ämne beskrivs hur du ställer in produktkvantitetsgränser för B2B-näthandelssajter.</span><span class="sxs-lookup"><span data-stu-id="96c83-104">This topic describes how to set product quantity limits for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="96c83-105">De flesta produkter har en måttenhet som definierar deras gruppering.</span><span class="sxs-lookup"><span data-stu-id="96c83-105">Most products have a unit of measure that defines their grouping.</span></span> <span data-ttu-id="96c83-106">Grupperingen påverkar hur produkterna kan säljas.</span><span class="sxs-lookup"><span data-stu-id="96c83-106">The grouping affects how the products can be sold.</span></span> <span data-ttu-id="96c83-107">För en del produkter kan det finnas en ytterligare gruppering för kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="96c83-107">Some products might have an additional grouping for quantities.</span></span> <span data-ttu-id="96c83-108">Denna gruppering fastställer huruvida produkterna kan säljas som enskilda enheter eller multiplar, och om det finns en minsta eller högsta orderkvantitetsgräns som måste innehållas.</span><span class="sxs-lookup"><span data-stu-id="96c83-108">This grouping determines whether the products can be sold as individual units or multiples, and whether there is a minimum or maximum order quantity limit that must be followed.</span></span>

<span data-ttu-id="96c83-109">Funktionen för kvantitetsbegränsning säkerställer att de minsta, högsta, multipla och standardkvantiteter som konfigureras i Microsoft Dynamics 365 Commerce (i standardorderinställningarna eller webbplatsinställningarna för Commerce-webbplatsbyggaren) tillämpas på kundorder som placeras på en näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="96c83-109">The quantity limiting feature ensures that the minimum, maximum, multiple, and standard quantities that are configured in Microsoft Dynamics 365 Commerce (in the default order settings or the Commerce site builder site settings) are applied to customer orders that are placed on an e-commerce site.</span></span> <span data-ttu-id="96c83-110">Produktkvantitetsgränserna stöds för närvarande inte för kassa (POS) och kundtjänst.</span><span class="sxs-lookup"><span data-stu-id="96c83-110">Product quantity limits aren't currently supported for the point of sale (POS) and call centers.</span></span>

<span data-ttu-id="96c83-111">Många återförsäljare ger möjlighet till kundorder (även kallade specialorder) att uppfylla diverse produkt- och uppfyllandekrav.</span><span class="sxs-lookup"><span data-stu-id="96c83-111">Many retailers provide the option of customer orders (also known as special orders) to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="96c83-112">Här följer några vanliga scenarier:</span><span class="sxs-lookup"><span data-stu-id="96c83-112">Here are some typical scenarios:</span></span>

- <span data-ttu-id="96c83-113">En kund vill att produkter av vissa varianter ska säljas i grupper om flera.</span><span class="sxs-lookup"><span data-stu-id="96c83-113">A customer wants products of specific variants to be sold in multiples of a few.</span></span>
- <span data-ttu-id="96c83-114">En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna.</span><span class="sxs-lookup"><span data-stu-id="96c83-114">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span> <span data-ttu-id="96c83-115">Förpackningsstandarderna för butikerna skiljer sig dock från förpackningsstandarderna för onlineförsäljningsdistribution.</span><span class="sxs-lookup"><span data-stu-id="96c83-115">However, the packing standards for the stores differ from the packing standards for online sales distribution.</span></span>
- <span data-ttu-id="96c83-116">En kund vill köpa en begränsad produkt ("limited edition") som har en maxkvantitetsgräns för artiklar som går att köpa.</span><span class="sxs-lookup"><span data-stu-id="96c83-116">A customer wants to buy a limited-edition product that has a maximum quantity limit for items that can be purchased.</span></span>

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a><span data-ttu-id="96c83-117">Aktivera funktionen för standardinställningar för order i Commerce-administrationen</span><span class="sxs-lookup"><span data-stu-id="96c83-117">Turn on the default order settings feature in Commerce headquarters</span></span>

<span data-ttu-id="96c83-118">Innan du kan ställa in produktkvantitetsgränser måste funktionen för standardorderinställningar aktiveras i Commerce-administrationen.</span><span class="sxs-lookup"><span data-stu-id="96c83-118">Before you can set product quantity limits, the default order settings feature must be turned on in Commerce headquarters.</span></span>

<span data-ttu-id="96c83-119">Följ de här stegen för att aktivera funktionen för inställningar för standardorder.</span><span class="sxs-lookup"><span data-stu-id="96c83-119">To turn on the default order settings feature, follow these steps.</span></span>

1. <span data-ttu-id="96c83-120">Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="96c83-120">Go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="96c83-121">Sök efter och välj funktionen **Stöd för inställningar för webbplats och standardorder i kundorder**.</span><span class="sxs-lookup"><span data-stu-id="96c83-121">Find and select the **Support the Site and Default order settings in the customer order** feature.</span></span>
1. <span data-ttu-id="96c83-122">Markera **Aktivera nu** längst ner i höger fönster.</span><span class="sxs-lookup"><span data-stu-id="96c83-122">At the bottom of the right pane, select **Enable now**.</span></span> 

## <a name="define-quantity-settings"></a><span data-ttu-id="96c83-123">Definiera kvantitetsinställningar</span><span class="sxs-lookup"><span data-stu-id="96c83-123">Define quantity settings</span></span> 

<span data-ttu-id="96c83-124">Du kan definiera kvantitetsinställningarna på sidan **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="96c83-124">You can define the quantity settings on the **Default order settings** page.</span></span>

<span data-ttu-id="96c83-125">Gör på följande sätt om du vill definiera kvantitetsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="96c83-125">To define the quantity settings, follow these steps.</span></span> 

1. <span data-ttu-id="96c83-126">Gå till Produkt **Butik och Handel \> Produkter och kategorier \> Frisläppta produkter efter kategori**.</span><span class="sxs-lookup"><span data-stu-id="96c83-126">Go to Product **Retail and Commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="96c83-127">Välj en frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="96c83-127">Select a released product.</span></span>
1. <span data-ttu-id="96c83-128">I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Orderinställningar**, väljer du **Standardorderinställningar**.</span><span class="sxs-lookup"><span data-stu-id="96c83-128">On the Action Pane, on the **Manage inventory** tab, in the **Order settings** group, select **Default order settings**.</span></span> 
1. <span data-ttu-id="96c83-129">På sidan **Standardorderinställningar**, på snabbfliken **Försäljningsorder** i avsnittet **Försäljningskvantitet**, anger du försäljningskvantiteterna för produkten:</span><span class="sxs-lookup"><span data-stu-id="96c83-129">On the **Default order settings** page, on the **Sales order** FastTab, in the **Sales quantity** section, set the product sales quantities:</span></span>

    - <span data-ttu-id="96c83-130">**Multipel** – Den kvantitet som produkten kan köpas i multiplar av.</span><span class="sxs-lookup"><span data-stu-id="96c83-130">**Multiple** – The quantity that the product can be bought in multiples of.</span></span>
    - <span data-ttu-id="96c83-131">**Minsta orderkvantitet** – Det minsta antal produkter som måste köpas in.</span><span class="sxs-lookup"><span data-stu-id="96c83-131">**Minimum Order Quantity** – The minimum number of products that must be purchased.</span></span>
    - <span data-ttu-id="96c83-132">**Högsta orderkvantitet** – Det högsta antal produkter som kan köpas in.</span><span class="sxs-lookup"><span data-stu-id="96c83-132">**Maximum Order Quantity** – The maximum number of products that can be purchased.</span></span>
    - <span data-ttu-id="96c83-133">**Standardorderkvantitet** – Standardkvantiteten som anges automatiskt när produkten väljs.</span><span class="sxs-lookup"><span data-stu-id="96c83-133">**Standard Order Quantity** – The default quantity that is automatically entered when the product is selected.</span></span>

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a><span data-ttu-id="96c83-134">Aktivera funktionen för B2B-orderkvantitetsgränser i Commerce-webbplatsbyggaren</span><span class="sxs-lookup"><span data-stu-id="96c83-134">Turn on the B2B order quantity limits feature in Commerce site builder</span></span>

<span data-ttu-id="96c83-135">Följ dessa steg om du vill aktivera funktionen för B2B-orderkvantiteter i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="96c83-135">To turn on the B2B order quantity limits feature in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="96c83-136">Gå till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="96c83-136">Go to **Site settings \> Extensions**</span></span>
1. <span data-ttu-id="96c83-137">Under **Aktivera orderkvantitetsgeänser** väljer du **Aktiverat för B2B-kunder** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="96c83-137">Under **Enable Order Quantity Limits**, select **Enabled for B2B customers** in the drop-down menu.</span></span> 

> [!NOTE] 
> <span data-ttu-id="96c83-138">Uppdaterade inställningar för webbplatsbyggare gäller bara när filen app.settings.json har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="96c83-138">Updated site builder settings take effect only after the app.settings.json file has been updated.</span></span> <span data-ttu-id="96c83-139">Mer information finns i [SDK- och modulbiblioteksuppdateringar](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="96c83-139">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="96c83-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="96c83-140">Additional resources</span></span>

[<span data-ttu-id="96c83-141">Konfigurera en B2B-näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="96c83-141">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="96c83-142">Skapa org-modellhierarkier för B2B-organisationer</span><span class="sxs-lookup"><span data-stu-id="96c83-142">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="96c83-143">Hantera affärspartneranvändare på B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="96c83-143">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="96c83-144">Konfigurera betalsätt för kundkonto för B2B-näthandelssajter</span><span class="sxs-lookup"><span data-stu-id="96c83-144">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)
