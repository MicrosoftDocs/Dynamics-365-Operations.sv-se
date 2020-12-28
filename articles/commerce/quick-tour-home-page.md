---
title: Översikt över startsidan
description: Det här ämnet innehåller en översikt över startsidan i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ebc8b4ebd3720815cdaaab708fbfdd8302cbea1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415939"
---
# <a name="home-page-overview"></a><span data-ttu-id="1d791-103">Översikt över startsidan</span><span class="sxs-lookup"><span data-stu-id="1d791-103">Home page overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d791-104">Det här ämnet innehåller en översikt över startsidan i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d791-104">This topic provides an overview of the home page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1d791-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="1d791-105">Overview</span></span>

<span data-ttu-id="1d791-106">Startsidan är den standardsida som köparen går till när han eller hon besöker en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="1d791-106">The home page is the default page that shoppers go to when they visit an e-Commerce site.</span></span> <span data-ttu-id="1d791-107">Den här sidan visar vanligtvis produkter och erbjudanden med hjälp av en kombination av marknadsföringsmoduler.</span><span class="sxs-lookup"><span data-stu-id="1d791-107">Typically, this page showcases products and promotions by using a combination of marketing modules.</span></span> <span data-ttu-id="1d791-108">Startsidan ska vara rik med bilder och text för att hålla köparen sysselsatt.</span><span class="sxs-lookup"><span data-stu-id="1d791-108">The home page should be rich with images and text to keep shoppers engaged.</span></span>

<span data-ttu-id="1d791-109">Följande illustration visar ett exempel på en startsida som har skapats med hjälp av modulbibliotek och temat "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="1d791-109">The following illustration shows an example of a home page that was built by using the module library and the "Fabrikam" theme.</span></span>

![Exempel på en startsida](./media/Homepage2.PNG)

<span data-ttu-id="1d791-111">Den övre delen av startsidan har en rubrik som visar alla produktkategorier och andra sidor som återförsäljaren vill att kunderna ska bläddra i.</span><span class="sxs-lookup"><span data-stu-id="1d791-111">The top of the home page has a header that shows all the product categories and other pages that the retailer wants customers to browse.</span></span> <span data-ttu-id="1d791-112">Startsidans nedre del har en sidfot som innehåller snabblänkar till olika ämnen som kan vara intressanta för kunderna.</span><span class="sxs-lookup"><span data-stu-id="1d791-112">The bottom of the home page has a footer that contains quick links to various topics that might interest customers.</span></span>

<span data-ttu-id="1d791-113">I huvudavsnittet på startsidan kan du markera produkter, kategorier eller kampanjer med hjälp av olika Dynamics 365 Commerce-moduler:</span><span class="sxs-lookup"><span data-stu-id="1d791-113">The main section of the home page can highlight products, categories, or promotions by using various Dynamics 365 Commerce modules:</span></span>

- <span data-ttu-id="1d791-114">**Fokus** – vanligtvis visar det första objektet högst upp i huvudavsnittet en eller flera "fokus"-bilder som markerar nya produkter och erbjudanden i butiken.</span><span class="sxs-lookup"><span data-stu-id="1d791-114">**Hero** – Typically, the first item at the top of the main section shows one or more "hero" images that highlight new products and promotions in the store.</span></span> <span data-ttu-id="1d791-115">Om det finns flera fokusbilder finns de i en karusellmodul så att användarna kan bläddra i dem.</span><span class="sxs-lookup"><span data-stu-id="1d791-115">If there are multiple hero images, they are hosted in a carousel module so that users can browse them.</span></span>

    <span data-ttu-id="1d791-116">Följande illustration visar ett exempel på en startsida där det första objektet i huvudavsnittet är en fokuslayout av innehållsblockmodul som kallas ny införsel.</span><span class="sxs-lookup"><span data-stu-id="1d791-116">The following illustration shows an example of a home page where the first item in the main section is a hero layout of a content block module that is named "New Arrival."</span></span>

    ![Exempel på en fokusmodul](./media/Hero.PNG)

- <span data-ttu-id="1d791-118">**Funktion** – en funktionslayout av innehållsblockmodul används för att marknadsföra produkter eller erbjudanden genom att använda en kombination av bilder och text.</span><span class="sxs-lookup"><span data-stu-id="1d791-118">**Feature** – A feature layout of a content block module is used to market products or promotions by using a combination of images and text.</span></span> <span data-ttu-id="1d791-119">Funktionslayouter kan användas oberoende av varandra, eller också kan de finnas i en karusellmodul.</span><span class="sxs-lookup"><span data-stu-id="1d791-119">Features layouts can be used independently, or they can be hosted in a carousel module.</span></span>

    <span data-ttu-id="1d791-120">Följande illustration visar ett exempel på funktionslayouter av innehållsblockmodul på en startsida.</span><span class="sxs-lookup"><span data-stu-id="1d791-120">The following illustration shows an example of feature layout of a content block module on a home page.</span></span>

    ![Exempel på funktionsmoduler](./media/Feature.PNG)

- <span data-ttu-id="1d791-122">**Panel** – en panellayout för innehållsblockmodul används för att presentera flera produkter eller kategorier med produkter genom att använda en kombination av bilder och text i en layout med flera kolumner.</span><span class="sxs-lookup"><span data-stu-id="1d791-122">**Tile** – A tile layout of a content block module is used to showcase multiple products or category of products by using a combination of images and text in a multicolumn layout.</span></span> <span data-ttu-id="1d791-123">I illustrationen av en startsida som visas tidigare i det här avsnittet används en panellayout med tre kolumner som återger objekten **Handla kvinna**, **Handla man** och **Handla tillbehör**.</span><span class="sxs-lookup"><span data-stu-id="1d791-123">In the illustration of a home page that appears earlier in this topic, a tile  layout is used for the three-column rendering of the **Shop Women**, **Shop Men**, and **Shop Accessories** items.</span></span>
- <span data-ttu-id="1d791-124">**Videospelare** – en videospelarmodul kan användas för att presentera videoinnehåll på startsidan.</span><span class="sxs-lookup"><span data-stu-id="1d791-124">**Video player** – A video player module can be used to showcase video content on the home page.</span></span> <span data-ttu-id="1d791-125">En illustration av en startsida som finns tidigare i det här avsnittet innehåller en videospelarmodul.</span><span class="sxs-lookup"><span data-stu-id="1d791-125">The illustration of a home page that appears earlier in this topic includes a video player module.</span></span>
- <span data-ttu-id="1d791-126">**Textblock** – en innehållsrik blockmodul kan användas för att visa text innehåll på startsidan i en layout med en kolumn eller flera kolumner.</span><span class="sxs-lookup"><span data-stu-id="1d791-126">**Text block** – A content rich block module can be used to present text content on the home page in a single-column or multicolumn layout.</span></span>
- <span data-ttu-id="1d791-127">**Produktrekommendationer** – moduler för produktrekommendationer används för att visa listor som **ny**, **trend** och **bästsäljande** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="1d791-127">**Product recommendations** – Product recommendations modules are used to show lists, such as **New**, **Trending**, and **Best Selling** on the home page.</span></span> <span data-ttu-id="1d791-128">Dessa listor visar en demonstration av produkter som bygger på köptrender, och de kan genereras med algoritm eller granskas manuellt.</span><span class="sxs-lookup"><span data-stu-id="1d791-128">These lists showcase products based on shopping trends, and they can be algorithmically generated or manually curated.</span></span> <span data-ttu-id="1d791-129">De hjälper kunderna att snabbt upptäcka de populära produkterna och sedan fortsätta att handla.</span><span class="sxs-lookup"><span data-stu-id="1d791-129">They help customers quickly discover top products and then continue to shop.</span></span>

    <span data-ttu-id="1d791-130">Följande illustration visar ett exempel på moduler för produktrekommendationer på en startsida.</span><span class="sxs-lookup"><span data-stu-id="1d791-130">The following illustration shows an example of product recommendations modules on a home page.</span></span>

    ![Exempel på moduler för produktrekommendationer](./media/Recommendations.PNG)

> [!NOTE]
> <span data-ttu-id="1d791-132">Alla moduler som anges här kan användas på alla webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="1d791-132">All the modules that are listed here can be used on any site page.</span></span> <span data-ttu-id="1d791-133">Det är dock viktigt att deras placering på startsidan är viktig eftersom kunderna först interagerar med din webbplats.</span><span class="sxs-lookup"><span data-stu-id="1d791-133">However, their placement on the home page is important because that page is where customers first interact with your site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1d791-134">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1d791-134">Additional resources</span></span>

[<span data-ttu-id="1d791-135">Översikt över sidor med produktinformation</span><span class="sxs-lookup"><span data-stu-id="1d791-135">Product details pages overview</span></span>](quick-tour-pdp.md)

[<span data-ttu-id="1d791-136">Översikt över sidor för kundvagn och kassa</span><span class="sxs-lookup"><span data-stu-id="1d791-136">Cart and checkout pages overview</span></span>](quick-tour-cart-checkout.md)

[<span data-ttu-id="1d791-137">Översikt över sidor för kontohantering</span><span class="sxs-lookup"><span data-stu-id="1d791-137">Account management pages overview</span></span>](quick-tour-account-management.md)
