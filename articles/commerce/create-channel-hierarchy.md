---
title: Skapa en navigeringshierarki för kanal
description: I det här avsnittet beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
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
ms.openlocfilehash: 5df46de9dadfa0b7160a9b340ef36fdf963a0ad3
ms.sourcegitcommit: 6c2f5c3b038f696532c335e20b0fbafa155d6858
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "5951918"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="0f0fb-103">Skapa en kanalnavigeringshierarki</span><span class="sxs-lookup"><span data-stu-id="0f0fb-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0f0fb-104">I det här avsnittet beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0f0fb-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0f0fb-105">Overview</span></span>

<span data-ttu-id="0f0fb-106">En navigeringshierarki för kanal används för att gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller i POS.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="0f0fb-107">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="0f0fb-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="0f0fb-108">Följ stegen nedan om du vill skapa en navigeringshierarki för kanaler.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="0f0fb-109">I Navigeringsfönstret, gå till **Moduler \> Retail and Commerce \> Produkter och kategorier \> Navigeringskategorier för kanal**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="0f0fb-110">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="0f0fb-111">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="0f0fb-112">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="0f0fb-113">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-113">Select **Create**.</span></span>
1. <span data-ttu-id="0f0fb-114">I åtgärdsfönstret, välj **Ny kategorinod** för att skapa en rotnod.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="0f0fb-115">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="0f0fb-116">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="0f0fb-117">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="0f0fb-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="0f0fb-119">I bilden nedan visas ett exempel på en rotnod.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-119">The following image shows a example root node.</span></span>

![Exempel på rotnod](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="0f0fb-121">Skapa navigeringskategorinoder</span><span class="sxs-lookup"><span data-stu-id="0f0fb-121">Create navigation category nodes</span></span>

<span data-ttu-id="0f0fb-122">Om du vill skapa ytterligare navigeringskategorinoder som representerar produktkategorierna på kanalen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="0f0fb-123">I navigeringsfönstret väljer du den överordnade noden för att lägga till en kategori.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="0f0fb-124">I åtgärdsfönstret klickar du på **Ny kategorinod**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="0f0fb-125">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="0f0fb-126">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="0f0fb-127">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="0f0fb-128">I rutan **Visningsordning**, ange en visningsordning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="0f0fb-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="0f0fb-129">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="0f0fb-130">Följande bild visar ett exempel på en slutförd navigeringshierarkin för butikskanal.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Exempel på kanalhierarki](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="0f0fb-132">Lägg till produkter i kategorinoder</span><span class="sxs-lookup"><span data-stu-id="0f0fb-132">Add products to category nodes</span></span>

<span data-ttu-id="0f0fb-133">Följ stegen nedan om du vill lägga till produkter till kategorinoder.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="0f0fb-134">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-134">Select a category node.</span></span>
1. <span data-ttu-id="0f0fb-135">Under **Produkter**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="0f0fb-136">Sök efter de nya produkter som du vill lägga till med produktnummer eller produktnamn och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="0f0fb-137">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0f0fb-138">Det räcker inte att lägga till produkter i en nod i modulen för kanalnavigering för att produkterna ska visas på en vald kanal – produkterna måste också vara utvalda för en kanal.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a channel.</span></span> <span data-ttu-id="0f0fb-139">Mer information om urval finns i [Urvalshantering](assortments.md).</span><span class="sxs-lookup"><span data-stu-id="0f0fb-139">For more information on assortments, see [Assortment management](assortments.md).</span></span>

<span data-ttu-id="0f0fb-140">Följande bild visar en exempelnod med produkter som läggs till.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-140">The following image shows an example node with products added.</span></span>

![Produkter i som lagts till i en kategorinod](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="0f0fb-142">Lägg till produktattributgrupper till kategorinoder</span><span class="sxs-lookup"><span data-stu-id="0f0fb-142">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="0f0fb-143">Attributgrupper måste skapas innan du kan lägga till dem i en nod i kanalnavigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-143">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="0f0fb-144">För att lägga till en attributgrupp till en kategorinod, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-144">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="0f0fb-145">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-145">Select a category node.</span></span>
1. <span data-ttu-id="0f0fb-146">Under **Produktattributgrupper**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-146">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="0f0fb-147">Sök efter de attributgrupper du vill lägga till och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-147">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="0f0fb-148">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="0f0fb-149">Följande bild visar en exempelnod med produktattributgrupper som läggs till.</span><span class="sxs-lookup"><span data-stu-id="0f0fb-149">The following image shows a sample node with product attribute groups added.</span></span>

![Produktattributgrupper på en nod](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="0f0fb-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0f0fb-151">Additional resources</span></span>

[<span data-ttu-id="0f0fb-152">Ställa in sortiment</span><span class="sxs-lookup"><span data-stu-id="0f0fb-152">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="0f0fb-153">Hantera attribut och attributsgrupper</span><span class="sxs-lookup"><span data-stu-id="0f0fb-153">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
