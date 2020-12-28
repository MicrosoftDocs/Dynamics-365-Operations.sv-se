---
title: Skapa en variantgrupp
description: I det här avsnittet beskrivs hur du skapar en variantgrupp för storlek, format eller färg för en produkt i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d9279e1076796bb455429e5ff004c89ec5829e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415830"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="a142c-103">Skapa en variantgrupp</span><span class="sxs-lookup"><span data-stu-id="a142c-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a142c-104">I det här avsnittet beskrivs hur du skapar en variantgrupp för storlek, format eller färg för en produkt i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a142c-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a142c-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a142c-105">Overview</span></span>

<span data-ttu-id="a142c-106">Dynamics 365 Commerce stöder flera varianter av produkter.</span><span class="sxs-lookup"><span data-stu-id="a142c-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="a142c-107">Det är idealiskt att ställa in variantkoder för olika produktkategorier.</span><span class="sxs-lookup"><span data-stu-id="a142c-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="a142c-108">En storleksgrupp kan till exempel skapas för t-shirts med storlekar som är extra small, small, medium, large och extra large eller en färggrupp som innehåller alla tillgängliga färger för en produkt.</span><span class="sxs-lookup"><span data-stu-id="a142c-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="a142c-109">Du bör lägga till variantgrupper innan produkter läggs till.</span><span class="sxs-lookup"><span data-stu-id="a142c-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="a142c-110">I det här avsnittet skapas och konfigureras en storleksgrupp.</span><span class="sxs-lookup"><span data-stu-id="a142c-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="a142c-111">Liknande procedurer kan användas för att lägga till och konfigurera stilgrupper och färggrupper.</span><span class="sxs-lookup"><span data-stu-id="a142c-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="a142c-112">Skapa en storleksgrupp</span><span class="sxs-lookup"><span data-stu-id="a142c-112">Create a size group</span></span>

<span data-ttu-id="a142c-113">Gör så här om du vill skapa en storleksgrupp.</span><span class="sxs-lookup"><span data-stu-id="a142c-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="a142c-114">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Variantgrupper \> Storleksgrupper**.</span><span class="sxs-lookup"><span data-stu-id="a142c-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="a142c-115">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a142c-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a142c-116">I rutan **Stoleksgrupp**, ange ett namn för storleksgruppen.</span><span class="sxs-lookup"><span data-stu-id="a142c-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="a142c-117">I rutan **beskrivning** ange en lämplig beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a142c-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="a142c-118">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a142c-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="a142c-119">Lägga till attribut i storleksgruppen</span><span class="sxs-lookup"><span data-stu-id="a142c-119">Add attributes to the size group</span></span>

<span data-ttu-id="a142c-120">Följ dessa steg om du vill lägga till attribut till en storleksgrupp.</span><span class="sxs-lookup"><span data-stu-id="a142c-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="a142c-121">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Variantgrupper \> Storleksgrupper**</span><span class="sxs-lookup"><span data-stu-id="a142c-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="a142c-122">Välj en storleksgrupp i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a142c-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="a142c-123">Under **Stoleksgrupprader**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a142c-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="a142c-124">I rutan **Stolek**, ange en sträng som representerar storleken (till exempel "XL").</span><span class="sxs-lookup"><span data-stu-id="a142c-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="a142c-125">Ange ett **Storleksnamn** för storleken (till exempel "Extra Large").</span><span class="sxs-lookup"><span data-stu-id="a142c-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="a142c-126">I rutan **Lagerpåfyllnadsvikt** ange ett nummer som representerar lagerpåfyllnadsvikt.</span><span class="sxs-lookup"><span data-stu-id="a142c-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="a142c-127">I rutan **Tal i streckkod** anger du ett tal som representerar streckkoden.</span><span class="sxs-lookup"><span data-stu-id="a142c-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="a142c-128">I rutan **Visningsordning**, ange ett nummer som representerar visningsordningen.</span><span class="sxs-lookup"><span data-stu-id="a142c-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="a142c-129">När du har lagt till alla storlekar väljer du **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a142c-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="a142c-130">I bilden nedan visas ett exempel på en storleksgrupp för "storlekar på vardagsskjortor".</span><span class="sxs-lookup"><span data-stu-id="a142c-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Skapa storleksgrupp](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="a142c-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a142c-132">Additional resources</span></span>

[<span data-ttu-id="a142c-133">Översikt över produktinformation</span><span class="sxs-lookup"><span data-stu-id="a142c-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a142c-134">Ställa in butiksprodukter</span><span class="sxs-lookup"><span data-stu-id="a142c-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="a142c-135">Produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="a142c-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
