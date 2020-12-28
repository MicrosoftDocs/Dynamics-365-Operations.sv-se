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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415728"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="69ca6-103">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="69ca6-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="69ca6-104">I det här avsnittet beskrivs hur du skapar en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69ca6-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="69ca6-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="69ca6-105">Overview</span></span>

<span data-ttu-id="69ca6-106">En navigeringshierarki för kanal används för att gruppera och ordna produkter till kategorier, så att du kan bläddra bland produkterna online eller i kassan.</span><span class="sxs-lookup"><span data-stu-id="69ca6-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="69ca6-107">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="69ca6-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="69ca6-108">Följ stegen nedan om du vill skapa en navigeringshierarki för kanaler.</span><span class="sxs-lookup"><span data-stu-id="69ca6-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="69ca6-109">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Navigeringskategorier för kanal**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="69ca6-110">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69ca6-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="69ca6-111">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="69ca6-112">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="69ca6-113">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-113">Select **Create**.</span></span>
1. <span data-ttu-id="69ca6-114">I åtgärdsfönstret, välj **Ny kategorinod** för att skapa en rotnod.</span><span class="sxs-lookup"><span data-stu-id="69ca6-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="69ca6-115">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="69ca6-116">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="69ca6-117">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="69ca6-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="69ca6-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69ca6-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="69ca6-119">I bilden nedan visas ett exempel på en rotnod.</span><span class="sxs-lookup"><span data-stu-id="69ca6-119">The following image shows a example root node.</span></span>

![Exempel på rotnod](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="69ca6-121">Skapa navigeringskategorinoder</span><span class="sxs-lookup"><span data-stu-id="69ca6-121">Create navigation category nodes</span></span>

<span data-ttu-id="69ca6-122">Om du vill skapa ytterligare navigeringskategorinoder som representerar produktkategorierna på kanalen följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="69ca6-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="69ca6-123">I navigeringsfönstret väljer du den överordnade noden för att lägga till en kategori.</span><span class="sxs-lookup"><span data-stu-id="69ca6-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="69ca6-124">I åtgärdsfönstret klickar du på **Ny kategorinod**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="69ca6-125">Ange sedan ett namn i rutan **Namn**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="69ca6-126">Ange en beskrivning i rutan **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="69ca6-127">I rutan **Eget namn** anger du ett eget namn.</span><span class="sxs-lookup"><span data-stu-id="69ca6-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="69ca6-128">I rutan **Visningsordning**, ange en visningsordning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="69ca6-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="69ca6-129">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69ca6-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="69ca6-130">Följande bild visar ett exempel på en slutförd navigeringshierarkin för butikskanal.</span><span class="sxs-lookup"><span data-stu-id="69ca6-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Exempel på kanalhierarki](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="69ca6-132">Lägg till produkter i kategorinoder</span><span class="sxs-lookup"><span data-stu-id="69ca6-132">Add products to category nodes</span></span>

<span data-ttu-id="69ca6-133">Följ stegen nedan om du vill lägga till produkter till kategorinoder.</span><span class="sxs-lookup"><span data-stu-id="69ca6-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="69ca6-134">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="69ca6-134">Select a category node.</span></span>
1. <span data-ttu-id="69ca6-135">Under **Produkter**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="69ca6-136">Sök efter de nya produkter som du vill lägga till med produktnummer eller produktnamn och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="69ca6-137">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69ca6-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="69ca6-138">Det räcker inte att lägga till produkter i en nod i modulen för kanalnavigering för att produkterna ska visas på en vald kanal, produkterna måste också vara utvalda för en produkt.</span><span class="sxs-lookup"><span data-stu-id="69ca6-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="69ca6-139">Följande bild visar en exempelnod med produkter som läggs till.</span><span class="sxs-lookup"><span data-stu-id="69ca6-139">The following image shows an example node with products added.</span></span>

![Produkter i som lagts till i en kategorinod](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="69ca6-141">Lägg till produktattributgrupper till kategorinoder</span><span class="sxs-lookup"><span data-stu-id="69ca6-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="69ca6-142">Attributgrupper måste skapas innan du kan lägga till dem i en nod i kanalnavigeringshierarkin.</span><span class="sxs-lookup"><span data-stu-id="69ca6-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="69ca6-143">För att lägga till en attributgrupp till en kategorinod, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="69ca6-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="69ca6-144">Välj en kategorinod.</span><span class="sxs-lookup"><span data-stu-id="69ca6-144">Select a category node.</span></span>
1. <span data-ttu-id="69ca6-145">Under **Produktattributgrupper**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="69ca6-146">Sök efter de attributgrupper du vill lägga till och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="69ca6-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="69ca6-147">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="69ca6-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="69ca6-148">Följande bild visar en exempelnod med produktattributgrupper som läggs till.</span><span class="sxs-lookup"><span data-stu-id="69ca6-148">The following image shows a sample node with product attribute groups added.</span></span>

![Produktattributgrupper på en nod](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="69ca6-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="69ca6-150">Additional resources</span></span>

[<span data-ttu-id="69ca6-151">Ställa in sortiment</span><span class="sxs-lookup"><span data-stu-id="69ca6-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="69ca6-152">Hantera attribut och attributsgrupper</span><span class="sxs-lookup"><span data-stu-id="69ca6-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)
