---
title: Modulen navigeringsmeny
description: Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "4415968"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="9e859-103">Modulen navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="9e859-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9e859-104">Det här avsnittet handlar om modul för navigeringsmenyn och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9e859-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9e859-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="9e859-105">Overview</span></span>

<span data-ttu-id="9e859-106">Det primära syftet med moduler för navigeringsmenyn är att låta användarna söka efter produkter och webbplatssidor i enlighet med den hierarki för kanaler som definierats i Dynamics 365 Commerce administration.</span><span class="sxs-lookup"><span data-stu-id="9e859-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="9e859-107">Objekt som konfigureras i en modul för navigeringsmeny visas som navigering för webbplatshuvud.</span><span class="sxs-lookup"><span data-stu-id="9e859-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="9e859-108">Moduler för navigeringsmenyn stöder även statiska menyalternativ som länkar till andra sidor på en näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="9e859-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="9e859-109">Du kan lägga till modulen navigeringsmeny på en sidhuvudmodul på en sida.</span><span class="sxs-lookup"><span data-stu-id="9e859-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="9e859-110">I det Fabrikam-temat visar navigeringsmenyn två nivåer som standard.</span><span class="sxs-lookup"><span data-stu-id="9e859-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="9e859-111">I det Starter-temat visar navigeringsmenyn tre nivåer som standard.</span><span class="sxs-lookup"><span data-stu-id="9e859-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="9e859-112">Om du vill ändra antalet nivåer måste du ha ett visningstillägg i temat.</span><span class="sxs-lookup"><span data-stu-id="9e859-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="9e859-113">Följande illustration visar ett exempel på en navigeringsmeny för Fabrikam-webbplatsen med två nivåer av kategorihierarki och vissa statiska menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="9e859-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="9e859-114">![Exempel på en modul för navigeringsmeny](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="9e859-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="9e859-115">Egenskaper för modulen navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="9e859-115">Navigation menu module properties</span></span>

| <span data-ttu-id="9e859-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="9e859-116">Property name</span></span>             | <span data-ttu-id="9e859-117">Värde</span><span class="sxs-lookup"><span data-stu-id="9e859-117">Value</span></span>                 | <span data-ttu-id="9e859-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e859-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="9e859-119">Källa</span><span class="sxs-lookup"><span data-stu-id="9e859-119">Source</span></span>                  | <span data-ttu-id="9e859-120">**Detaljhandel**, **Manuell redigering**, **Återförsäljning och manuell redigering**</span><span class="sxs-lookup"><span data-stu-id="9e859-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="9e859-121">Med värdet **Detaljhandel** kan kanalnavigeringshierarkin från Commerce-administration visas på navigeringsmenyn.</span><span class="sxs-lookup"><span data-stu-id="9e859-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="9e859-122">Med hjälp av värdet **Manuellt redigering** kan statiska menyalternativ granskas.</span><span class="sxs-lookup"><span data-stu-id="9e859-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="9e859-123">Värdet **Återförsäljning och manuell redigering** tillåter en blandning av båda.</span><span class="sxs-lookup"><span data-stu-id="9e859-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="9e859-124">Visa kategoribilder</span><span class="sxs-lookup"><span data-stu-id="9e859-124">Show category images</span></span> | <span data-ttu-id="9e859-125">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="9e859-125">**True** or **False**</span></span>    | <span data-ttu-id="9e859-126">När den här egenskapen är aktiverad visas kategoribilder på navigeringsmenyn som har definierats i Commerce-administration för varje kategori.</span><span class="sxs-lookup"><span data-stu-id="9e859-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="9e859-127">Lades till i Commerce version 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="9e859-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="9e859-128">Aktivera navigeringsmeny med flera nivåer</span><span class="sxs-lookup"><span data-stu-id="9e859-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="9e859-129">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="9e859-129">**True** or **False**</span></span> | <span data-ttu-id="9e859-130">När den här egenskapen är aktiverad kan navigeringsmenyn visa flera nivåer i navigeringsvyn.</span><span class="sxs-lookup"><span data-stu-id="9e859-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="9e859-131">Den här funktionen är endast i Dynamics 365 Commerce version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="9e859-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="9e859-132">Antal nivåer</span><span class="sxs-lookup"><span data-stu-id="9e859-132">Number of levels</span></span> | <span data-ttu-id="9e859-133">heltal</span><span class="sxs-lookup"><span data-stu-id="9e859-133">integer</span></span> | <span data-ttu-id="9e859-134">Den här egenskapen definierar antalet nivåer som ska visas om egenskapen **Aktivera navigering i flera nivåer** är inställd på **True**.</span><span class="sxs-lookup"><span data-stu-id="9e859-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="9e859-135">Statiskt menyalternativ</span><span class="sxs-lookup"><span data-stu-id="9e859-135">Static menu item</span></span>| <span data-ttu-id="9e859-136">Matris med värden</span><span class="sxs-lookup"><span data-stu-id="9e859-136">Array of values</span></span>| <span data-ttu-id="9e859-137">Statiska menyalternativ som associerar ett menyalternativnamn med en länk till en statisk webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="9e859-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="9e859-138">Du kan skapa menyalternativ under andra menyalternativ.</span><span class="sxs-lookup"><span data-stu-id="9e859-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="9e859-139">Statiska menyer visas som standard på rotnivå och kommer att läggas till i kanalens navigeringshierarki om den finns.</span><span class="sxs-lookup"><span data-stu-id="9e859-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="9e859-140">Visa rotmenyn</span><span class="sxs-lookup"><span data-stu-id="9e859-140">Show root menu</span></span> | <span data-ttu-id="9e859-141">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="9e859-141">**True** or **False**</span></span> | <span data-ttu-id="9e859-142">När den här egenskapen är aktiverad kan navigeringsmenyn definieras under en anpassad rot (t.ex. **handla nu**).</span><span class="sxs-lookup"><span data-stu-id="9e859-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now**).</span></span> <span data-ttu-id="9e859-143">Den här funktionen är endast i Dynamics 365 Commerce version 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="9e859-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="9e859-144">Rotmeny</span><span class="sxs-lookup"><span data-stu-id="9e859-144">Root menu</span></span> | <span data-ttu-id="9e859-145">sträng</span><span class="sxs-lookup"><span data-stu-id="9e859-145">string</span></span> | <span data-ttu-id="9e859-146">Den här egenskapen kan användas för att definiera text för en anpassad rot om egenskapen **Visa rotmeny** är inställd på **True**.</span><span class="sxs-lookup"><span data-stu-id="9e859-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="9e859-147">Följande illustration visar ett exempel på en kategoribild som visas på navigeringsmenyn för webbplatsen Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="9e859-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="9e859-148">![Exempel på en navigeringsmodul med kategoribilder](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="9e859-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="9e859-149">Lägg till en modul för navigeringsmeny i en sidhuvudmodul</span><span class="sxs-lookup"><span data-stu-id="9e859-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="9e859-150">Mer information om hur du lägger till en modul för navigeringsmeny i en sidhuvudmodul finns i [sidhuvudmodulen](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="9e859-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e859-151">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9e859-151">Additional resources</span></span>

[<span data-ttu-id="9e859-152">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="9e859-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9e859-153">Modul för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="9e859-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="9e859-154">Modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="9e859-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="9e859-155">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="9e859-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9e859-156">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="9e859-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="9e859-157">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="9e859-157">Header module</span></span>](author-header-module.md)
