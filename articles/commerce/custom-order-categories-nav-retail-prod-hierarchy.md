---
title: Ändra sorteringsordning för marknadsföringsenheter
description: I det här avsnittet beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter i Dynamics 365 Commerce.
author: josaw1
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 31798508e4cc71e31a30dc91acebfdde8226b16c
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "5937072"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="faf1c-103">Ändra sorteringsordning för marknadsföringsenheter</span><span class="sxs-lookup"><span data-stu-id="faf1c-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="faf1c-104">Återförsäljare betraktar produktidentifiering som ett primärt verktyg för kundinteraktion i alla kanaler.</span><span class="sxs-lookup"><span data-stu-id="faf1c-104">Retailers consider product discovery a primary tool for customer interaction across all channels.</span></span> <span data-ttu-id="faf1c-105">Olika funktioner kan hjälpa kunder att enkelt hitta produkter.</span><span class="sxs-lookup"><span data-stu-id="faf1c-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="faf1c-106">De kan till exempel bläddra bland kategorier, söka och filtrera.</span><span class="sxs-lookup"><span data-stu-id="faf1c-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="faf1c-107">I det här avsnittet beskrivs begreppen för att styra visningsordningen för olika marknadsföringsrelaterade entiteter.</span><span class="sxs-lookup"><span data-stu-id="faf1c-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="faf1c-108">Det innehåller även information om hur du ändrar sorteringsordning.</span><span class="sxs-lookup"><span data-stu-id="faf1c-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="faf1c-109">Översikt</span><span class="sxs-lookup"><span data-stu-id="faf1c-109">Overview</span></span>

<span data-ttu-id="faf1c-110">Stödet för sortering av olika marknadsföringsrelaterade entiteter har förbättrats.</span><span class="sxs-lookup"><span data-stu-id="faf1c-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="faf1c-111">Det här stödet är nu bättre justerat med befintliga kundscenarier som tidigare krävde tillägg från implementeringspartners.</span><span class="sxs-lookup"><span data-stu-id="faf1c-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="faf1c-112">I tidigare versioner av Retail än version 10.0.5 var sorteringsordningen för kategorier i navigeringsvyn alfabetisk.</span><span class="sxs-lookup"><span data-stu-id="faf1c-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="faf1c-113">Med den nya anpassade sorteringsordningen kan du konfigurera sorteringsordningen för olika marknadsföringsrelaterade enheter för alla slutanvändarklienter.</span><span class="sxs-lookup"><span data-stu-id="faf1c-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="faf1c-114">Dessa klienter inkluderar huvudkontor (HQ) och kundtjänster.</span><span class="sxs-lookup"><span data-stu-id="faf1c-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a><span data-ttu-id="faf1c-115">Konfigurera visningsordningen för kategorier i produkthierarki</span><span class="sxs-lookup"><span data-stu-id="faf1c-115">Configure the display order for categories in the product hierarchy</span></span>

<span data-ttu-id="faf1c-116">Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.</span><span class="sxs-lookup"><span data-stu-id="faf1c-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="faf1c-117">Gå till **Retail and Commerce \> Produkter och kategorier \> Produkthierarki och handel**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-117">Go to **Retail and Commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
2. <span data-ttu-id="faf1c-118">Klicka på **Redigera kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="faf1c-119">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-119">Click **Edit**.</span></span>
4. <span data-ttu-id="faf1c-120">Expandera **ALLA \> Actionsporter** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="faf1c-121">Expandera **ALLA \> Lagsporter** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="faf1c-122">Ange ett tal i fältet **Visningsordning**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="faf1c-123">(Talet kan vara negativt.)</span><span class="sxs-lookup"><span data-stu-id="faf1c-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="faf1c-124">Upprepa steg 4 till och med 6 för alla ytterligare kategorier som du vill ändra ordningen för.</span><span class="sxs-lookup"><span data-stu-id="faf1c-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="faf1c-125">Visningsordningen för kanalensnavigeringshierarkin kommer att avspeglas i huvudkontoret för handelsprodukthierarkin och frisläppta produkter efter kategori.</span><span class="sxs-lookup"><span data-stu-id="faf1c-125">The display order for the channel navigation hierarchy will be reflected in HQ for the commerce product hierarchy and released products by category.</span></span>

![Produkthierarki anpassat sorterad med negativa värden](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produkter som frisläppts efter kategori sorteras baserat på produkthierarki](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="faf1c-128">Konfigurera visningsordningen för kategorier i kanalnavigeringshierarkin</span><span class="sxs-lookup"><span data-stu-id="faf1c-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="faf1c-129">Innan du kan slutföra den här proceduren måste demonstrationsdata vara installerade i din miljö.</span><span class="sxs-lookup"><span data-stu-id="faf1c-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="faf1c-130">Gå till **Retail and Commerce \> Produkter och kategorier \> Navigeringskategorier för kanal**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-130">Go to **Retail and Commerce \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="faf1c-131">Välj hierarkin **Modenavigering** i listan.</span><span class="sxs-lookup"><span data-stu-id="faf1c-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="faf1c-132">Klicka på **Redigera kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="faf1c-133">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-133">Click **Edit**.</span></span>
5. <span data-ttu-id="faf1c-134">Välj **Mode \> Damkläder \> Damskor** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="faf1c-135">Ange ett tal i fältet **Visningsordning**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="faf1c-136">Välj **Mode \> Damkläder \> Överdelar** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="faf1c-137">På samma sätt kan du definiera sorteringsordningen för underkategorierna.</span><span class="sxs-lookup"><span data-stu-id="faf1c-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="faf1c-138">Välj **Mode \> Herrkläder \> Lediga skjortor** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="faf1c-139">Ange ett tal i fältet **Visningsordning**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="faf1c-140">Välj **Mode \> Herrkläder \> Jackor** i trädet.</span><span class="sxs-lookup"><span data-stu-id="faf1c-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="faf1c-141">Ange ett tal i fältet **Visningsordning**.</span><span class="sxs-lookup"><span data-stu-id="faf1c-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="faf1c-142">Upprepa för alla ytterligare kategorier som du vill ändra ordningen för.</span><span class="sxs-lookup"><span data-stu-id="faf1c-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="faf1c-143">Visningsordningen för kanalnavigeringshierarkin visas i huvudkontor, katalog och kanalerna.</span><span class="sxs-lookup"><span data-stu-id="faf1c-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and channels.</span></span>

![Anpassat sorterad kanalnavigeringshierarki](./media/ChannelNavCustomSorted.png)

![Anpassat sorterad katalognavigeringshierarki baserat på kanalnavigeringshierarkin](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![Kassa med anpassade, sorterade kategorier](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="faf1c-147">Funktionen för anpassad sorteringsordning är avstängd som standard.</span><span class="sxs-lookup"><span data-stu-id="faf1c-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="faf1c-148">Mer information om hur du aktiverar den här funktionen och andra funktioner finns i [Funktionshantering](/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="faf1c-148">To learn how to turn on this feature and other features, see [Feature management](/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]