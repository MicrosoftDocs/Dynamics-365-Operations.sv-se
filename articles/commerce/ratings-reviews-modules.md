---
title: Moduler för omdömen och moduler
description: I det här avsnittet beskrivs klassificeringar och recensioner som används på produktinformationssidor i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: dee9a6a7e2a5278f069958ce00689b1beb9b1bd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792157"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="ab91b-103">Moduler för omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="ab91b-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ab91b-104">I det här avsnittet beskrivs klassificeringar och recensioner som används på produktinformationssidor (PDPs) i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ab91b-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ab91b-105">Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, och är också en mekanism för att samla in feedback från kunder om produkter.</span><span class="sxs-lookup"><span data-stu-id="ab91b-105">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="ab91b-106">Omdömen visas på produktlistsidor, kategorilistsidor, sökresultatsidor och andra webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="ab91b-106">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="ab91b-107">Omdömeshistogram och produktrecensioner visas på PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-107">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="ab91b-108">Knappen **Skriv ett omdöme** låter kunder skicka in omdömen och recensioner om en produkt.</span><span class="sxs-lookup"><span data-stu-id="ab91b-108">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="ab91b-109">Dessa PDP-funktioner styrs av klassificerings- och granskningsmoduler.</span><span class="sxs-lookup"><span data-stu-id="ab91b-109">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="ab91b-110">Moduler för omdömen och recensioner på PDP</span><span class="sxs-lookup"><span data-stu-id="ab91b-110">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="ab91b-111">Tre moduler visar sammanfattningen av omdömen och recensioner i PDP:</span><span class="sxs-lookup"><span data-stu-id="ab91b-111">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="ab91b-112">Modulen skriv recension</span><span class="sxs-lookup"><span data-stu-id="ab91b-112">Write review module</span></span>
- <span data-ttu-id="ab91b-113">Modulen produktrecensionslista</span><span class="sxs-lookup"><span data-stu-id="ab91b-113">Product reviews list module</span></span>
- <span data-ttu-id="ab91b-114">Modul för omdömeshistogram</span><span class="sxs-lookup"><span data-stu-id="ab91b-114">Ratings histogram module</span></span>
 
<span data-ttu-id="ab91b-115">I bilden nedan visas hur modulerna omdömen och recensioner ser ut på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-115">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Moduler för omdömen och recensioner på en PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="ab91b-117">Information om hur du optimerar mallar och layouter i PDP så att du kan dela med dig av konfigurationerna för omdömen och recensioner av moduler mellan flera PDP på din näthandelssajt finns på [Översikt över mallar och layouter](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ab91b-117">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="ab91b-118">Följande illustration visar hur dialogrutan **Lägg till modul** presenterar moduler för omdömen och recensioner i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ab91b-118">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="ab91b-119">![Dialogrutan Lägg till modul](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="ab91b-119">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="ab91b-120">Modulen skriv recension</span><span class="sxs-lookup"><span data-stu-id="ab91b-120">Write review module</span></span>

<span data-ttu-id="ab91b-121">Modulen skriv recension inkluderar knappen **Skriv en recension**, där användarna kan logga in, tilldela ett omdöme och skriva en recension av en produkt.</span><span class="sxs-lookup"><span data-stu-id="ab91b-121">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="ab91b-122">Med hjälp av modulen kan du också redigera ett omdöme eller granska de som tidigare har skickat in dem.</span><span class="sxs-lookup"><span data-stu-id="ab91b-122">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="ab91b-123">Den här modulen visas normalt ovanför modulerna omdömeshistogram och produktrecensioner i en PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-123">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="ab91b-124">Bilden nedan visar dialog rutan **Skriv en recension** som visas när en kund väljer **skriva en recension**.</span><span class="sxs-lookup"><span data-stu-id="ab91b-124">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="ab91b-125">Kunden kan använda den här dialogrutan för att skicka ett omdöme och en recension.</span><span class="sxs-lookup"><span data-stu-id="ab91b-125">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="ab91b-126">![Dialogrutan Skriv en recension](media/rnr-eCommerce-write-review-module.png) I följande tabell visas den egenskap för modulen skriv recension som måste konfigureras i utvecklingsverktyget.</span><span class="sxs-lookup"><span data-stu-id="ab91b-126">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="ab91b-127">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="ab91b-127">Property name</span></span> | <span data-ttu-id="ab91b-128">Värde</span><span class="sxs-lookup"><span data-stu-id="ab91b-128">Value</span></span>        | <span data-ttu-id="ab91b-129">Egenskapsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ab91b-129">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="ab91b-130">Namn</span><span class="sxs-lookup"><span data-stu-id="ab91b-130">Name</span></span>          | <span data-ttu-id="ab91b-131">Skriv recension</span><span class="sxs-lookup"><span data-stu-id="ab91b-131">Write review</span></span> | <span data-ttu-id="ab91b-132">Namnet på modulen för skriv en recension.</span><span class="sxs-lookup"><span data-stu-id="ab91b-132">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="ab91b-133">Modul för omdömeshistogram</span><span class="sxs-lookup"><span data-stu-id="ab91b-133">Ratings histogram module</span></span>

<span data-ttu-id="ab91b-134">Modulen omdömeshistogram visar ett histogram med omdömet.</span><span class="sxs-lookup"><span data-stu-id="ab91b-134">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="ab91b-135">Den här modulen visas normalt mellan modulen skriv recension och produktrecensionslistan på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-135">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="ab91b-136">Modulen omdömeshistogram kräver ingen konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ab91b-136">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="ab91b-137">Du behöver bara lägga till modulen i PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="ab91b-137">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="ab91b-138">Följande illustrationer visar hur en PDP-mall ser ut i Dynamics 365 Commerce när moduler för omdömen och recensioner konfigureras för visning på PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-138">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="ab91b-139">![PDP-mall när omdömen och recensioner konfigureras för visning på PDP](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="ab91b-139">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="ab91b-140">Modulen produktrecensionslista</span><span class="sxs-lookup"><span data-stu-id="ab91b-140">Product reviews list module</span></span>

<span data-ttu-id="ab91b-141">I modulen produktrecensionslista visas en lista med produktrecensioner tillsammans med alternativen sortera, filtrera och sidbrytning.</span><span class="sxs-lookup"><span data-stu-id="ab91b-141">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="ab91b-142">Den här modulen visas normalt efter modulen för omdömeshistogram på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-142">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="ab91b-143">I följande tabell visas de egenskaper för modulen produktrecensionslista som måste konfigureras i utvecklingsverktyget.</span><span class="sxs-lookup"><span data-stu-id="ab91b-143">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="ab91b-144">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="ab91b-144">Property name</span></span>              | <span data-ttu-id="ab91b-145">Värde</span><span class="sxs-lookup"><span data-stu-id="ab91b-145">Value</span></span> | <span data-ttu-id="ab91b-146">Egenskapsbeskrivning</span><span class="sxs-lookup"><span data-stu-id="ab91b-146">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="ab91b-147">Recensioner som visas på varje sida</span><span class="sxs-lookup"><span data-stu-id="ab91b-147">Reviews shown on each page</span></span> | <span data-ttu-id="ab91b-148">10</span><span class="sxs-lookup"><span data-stu-id="ab91b-148">10</span></span>    | <span data-ttu-id="ab91b-149">Antalet recensioner som ska visas i taget på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="ab91b-149">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="ab91b-150">Knapparna **Nästa** och **föregående** inkluderas så att användarna kan förflytta sig genom sidorna i recensioner.</span><span class="sxs-lookup"><span data-stu-id="ab91b-150">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="ab91b-151">Omdömeshistogram – sammanfattningsvy</span><span class="sxs-lookup"><span data-stu-id="ab91b-151">Ratings histogram – Summary view</span></span>

<span data-ttu-id="ab91b-152">Modulen produktrecensionslista innehåller en plats där du kan lägga till en modul för ett omdöme i histogram.</span><span class="sxs-lookup"><span data-stu-id="ab91b-152">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="ab91b-153">Följande illustration visar hur du kan lägga till en modul för omdömeshistogram i modulen produktrecensionslista i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ab91b-153">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Lägga till modulen omdömeshistogram i modulen produktrecensionslista](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="ab91b-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ab91b-155">Additional resources</span></span>

[<span data-ttu-id="ab91b-156">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="ab91b-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ab91b-157">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="ab91b-157">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ab91b-158">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="ab91b-158">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ab91b-159">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="ab91b-159">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ab91b-160">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ab91b-160">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ab91b-161">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="ab91b-161">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ab91b-162">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="ab91b-162">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]