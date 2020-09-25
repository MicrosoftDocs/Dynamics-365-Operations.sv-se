---
title: Modulen navigeringsmeny
description: Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761424"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="f7903-103">Modulen navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="f7903-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f7903-104">Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7903-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f7903-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="f7903-105">Overview</span></span>

<span data-ttu-id="f7903-106">Det primära syftet med moduler för navigeringsmenyn är att låta användarna söka efter produkter och webbplatssidor i enlighet med den hierarki för kanaler som definierats i Dynamics 365 Commerce administration.</span><span class="sxs-lookup"><span data-stu-id="f7903-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="f7903-107">Objekt som konfigureras i en modul för navigeringsmeny visas som navigering för webbplatshuvud.</span><span class="sxs-lookup"><span data-stu-id="f7903-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="f7903-108">Moduler för navigeringsmenyn stöder även statiska menyalternativ som länkar till andra sidor på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="f7903-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="f7903-109">Du kan lägga till modulen navigeringsmeny på en sidhuvudmodul på en sida.</span><span class="sxs-lookup"><span data-stu-id="f7903-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="f7903-110">I det Fabrikam-temat visar navigeringsmenyn två nivåer som standard.</span><span class="sxs-lookup"><span data-stu-id="f7903-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="f7903-111">I det Starter-temat visar navigeringsmenyn tre nivåer som standard.</span><span class="sxs-lookup"><span data-stu-id="f7903-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="f7903-112">Om du vill ändra antalet nivåer måste du ha ett visningstillägg i temat.</span><span class="sxs-lookup"><span data-stu-id="f7903-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="f7903-113">Följande illustration visar ett exempel på en navigeringsmeny för Fabrikam-webbplatsen med två nivåer av kategorihierarki och vissa statiska menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="f7903-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="f7903-114">![Exempel på en modul för navigeringsmeny](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="f7903-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="f7903-115">Egenskaper för modulen navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="f7903-115">Navigation menu module properties</span></span>

| <span data-ttu-id="f7903-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="f7903-116">Property name</span></span>             | <span data-ttu-id="f7903-117">Värde</span><span class="sxs-lookup"><span data-stu-id="f7903-117">Value</span></span>                 | <span data-ttu-id="f7903-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f7903-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="f7903-119">Källa</span><span class="sxs-lookup"><span data-stu-id="f7903-119">Source</span></span>                  | <span data-ttu-id="f7903-120">**Detaljhandel**, **Manuell redigering**, **Återförsäljning och manuell redigering**</span><span class="sxs-lookup"><span data-stu-id="f7903-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="f7903-121">Med värdet **Detaljhandel** kan kanalnavigeringshierarkin från Commerce-administration visas på navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="f7903-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="f7903-122">Med hjälp av värdet **Manuellt redigering** kan statiska menyalternativ granskas.</span><span class="sxs-lookup"><span data-stu-id="f7903-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="f7903-123">Värdet **Återförsäljning och manuell redigering** tillåter en blandning av båda.</span><span class="sxs-lookup"><span data-stu-id="f7903-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="f7903-124">Visa kategoribilder</span><span class="sxs-lookup"><span data-stu-id="f7903-124">Show category images</span></span> | <span data-ttu-id="f7903-125">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="f7903-125">**True** or **False**</span></span>    | <span data-ttu-id="f7903-126">När den här egenskapen är aktiverad visas kategoribilder på navigeringsmenyn som har definierats i Commerce-administration för varje kategori.</span><span class="sxs-lookup"><span data-stu-id="f7903-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="f7903-127">Lades till i Commerce version 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="f7903-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="f7903-128">Statiskt menyalternativ</span><span class="sxs-lookup"><span data-stu-id="f7903-128">Static menu item</span></span>| <span data-ttu-id="f7903-129">Matris med värden</span><span class="sxs-lookup"><span data-stu-id="f7903-129">Array of values</span></span>| <span data-ttu-id="f7903-130">Statiska menyalternativ som associerar ett menyalternativnamn med en länk till en statisk webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="f7903-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="f7903-131">Du kan skapa menyalternativ under andra menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="f7903-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="f7903-132">Statiska menyer visas som standard på rotnivå och kommer att läggas till i kanalens navigeringshierarki om den finns.</span><span class="sxs-lookup"><span data-stu-id="f7903-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="f7903-133">Följande illustration visar ett exempel på en kategoribild som visas på navigeringsmenyn för webbplatsen Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f7903-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="f7903-134">![Exempel på en navigeringsmodul med kategoribilder](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="f7903-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="f7903-135">Lägg till en modul för navigeringsmeny i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="f7903-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="f7903-136">Mer information om hur du lägger till en modul för navigeringsmeny i en sidhuvudmodul finns i [sidhuvudmodulen](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="f7903-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7903-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f7903-137">Additional resources</span></span>

[<span data-ttu-id="f7903-138">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="f7903-138">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f7903-139">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="f7903-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f7903-140">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="f7903-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="f7903-141">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="f7903-141">Header module</span></span>](author-header-module.md)
