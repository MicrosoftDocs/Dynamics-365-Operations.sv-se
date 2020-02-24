---
title: Skapa en navigeringshierarki för kanal
description: I det här avsnittet beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e83860667f142adcc85cd8542d521e18f16dbc2c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002046"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="3fe32-103">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="3fe32-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3fe32-104">I det här avsnittet beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3fe32-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3fe32-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="3fe32-105">Overview</span></span>

<span data-ttu-id="3fe32-106">En navigeringshierarki för kanal används för att gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller i kassan.</span><span class="sxs-lookup"><span data-stu-id="3fe32-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="3fe32-107">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="3fe32-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="3fe32-108">Följ stegen nedan om du vill skapa en navigeringshierarki för kanaler.</span><span class="sxs-lookup"><span data-stu-id="3fe32-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="3fe32-109">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Navigeringskategorier för kanal**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="3fe32-110">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3fe32-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="3fe32-111">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="3fe32-112">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="3fe32-113">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-113">Select **Create**.</span></span>
1. <span data-ttu-id="3fe32-114">I åtgärdsfönstret, välj **Ny kategorinod** för att skapa en rotnod.</span><span class="sxs-lookup"><span data-stu-id="3fe32-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="3fe32-115">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="3fe32-116">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="3fe32-117">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="3fe32-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="3fe32-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3fe32-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3fe32-119">I bilden nedan visas ett exempel på en rotnod.</span><span class="sxs-lookup"><span data-stu-id="3fe32-119">The following image shows a example root node.</span></span>

![Exempel på rotnod](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="3fe32-121">Skapa navigeringskategorinoder</span><span class="sxs-lookup"><span data-stu-id="3fe32-121">Create navigation category nodes</span></span>

<span data-ttu-id="3fe32-122">Om du vill skapa ytterligare navigeringskategorinoder som representerar produktkategorierna på kanalen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3fe32-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="3fe32-123">I navigeringsfönstret väljer du den överordnade noden för att lägga till en kategori.</span><span class="sxs-lookup"><span data-stu-id="3fe32-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="3fe32-124">I åtgärdsfönstret klickar du på **Ny kategorinod**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="3fe32-125">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="3fe32-126">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="3fe32-127">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="3fe32-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="3fe32-128">I rutan **Visningsordning**, ange en visningsordning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="3fe32-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="3fe32-129">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3fe32-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3fe32-130">Följande bild visar ett exempel på en slutförd navigeringshierarkin för butikskanal.</span><span class="sxs-lookup"><span data-stu-id="3fe32-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Exempel på kanalhierarki](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="3fe32-132">Lägg till produkter i kategorinoder</span><span class="sxs-lookup"><span data-stu-id="3fe32-132">Add products to category nodes</span></span>

<span data-ttu-id="3fe32-133">Följ stegen nedan om du vill lägga till produkter till kategorinoder.</span><span class="sxs-lookup"><span data-stu-id="3fe32-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="3fe32-134">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="3fe32-134">Select a category node.</span></span>
1. <span data-ttu-id="3fe32-135">Under **Produkter**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="3fe32-136">Sök efter de nya produkter som du vill lägga till med produktnummer eller produktnamn och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="3fe32-137">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3fe32-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3fe32-138">Det räcker inte att lägga till produkter i en nod i modulen för kanalnavigering för att produkterna ska visas på en vald kanal, produkterna måste också vara utvalda för en produkt.</span><span class="sxs-lookup"><span data-stu-id="3fe32-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="3fe32-139">Följande bild visar en exempelnod med produkter som läggs till.</span><span class="sxs-lookup"><span data-stu-id="3fe32-139">The following image shows an example node with products added.</span></span>

![Produkter i som lagts till i en kategorinod](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="3fe32-141">Lägg till produktattributgrupper till kategorinoder</span><span class="sxs-lookup"><span data-stu-id="3fe32-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="3fe32-142">Attributgrupper måste skapas innan du kan lägga till dem i en nod i kanalnavigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="3fe32-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="3fe32-143">För att lägga till en attributgrupp till en kategorinod, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3fe32-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="3fe32-144">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="3fe32-144">Select a category node.</span></span>
1. <span data-ttu-id="3fe32-145">Under **Produktattributgrupper**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="3fe32-146">Sök efter de attributgrupper du vill lägga till och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3fe32-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="3fe32-147">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3fe32-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="3fe32-148">Följande bild visar en exempelnod med produktattributgrupper som läggs till.</span><span class="sxs-lookup"><span data-stu-id="3fe32-148">The following image shows a sample node with product attribute groups added.</span></span>

![Produktattributgrupper på en nod](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="3fe32-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3fe32-150">Additional resources</span></span>

[<span data-ttu-id="3fe32-151">Ställa in sortiment</span><span class="sxs-lookup"><span data-stu-id="3fe32-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="3fe32-152">Hantera attribut och attributsgrupper</span><span class="sxs-lookup"><span data-stu-id="3fe32-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)
