---
title: Kartmodul
description: Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "3647050"
---
# <a name="map-module"></a><span data-ttu-id="53e3f-103">Kartmodul</span><span class="sxs-lookup"><span data-stu-id="53e3f-103">Map module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="53e3f-104">Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="53e3f-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="53e3f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="53e3f-105">Overview</span></span>

<span data-ttu-id="53e3f-106">En kartmodul visar platserna för butikerna i en interaktiv karta som återges med hjälp av [Bing Maps-V8 webbkontroll](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="53e3f-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="53e3f-107">En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="53e3f-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="53e3f-108">I kartmoduler finns olika vyer, till exempel väg, flyg och gata som användarna kan välja för att visa kartplatser.</span><span class="sxs-lookup"><span data-stu-id="53e3f-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="53e3f-109">De tillåter också interaktioner som att zooma in och använda användarens plats.</span><span class="sxs-lookup"><span data-stu-id="53e3f-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="53e3f-110">En kartmodul arbetar tillsammans med modulen butiksväljare för att fastställa geografiska platser för butiker som måste återges på en karta.</span><span class="sxs-lookup"><span data-stu-id="53e3f-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="53e3f-111">Butiksväljare och kartmoduler interagerar när en användare väljer en butik i en av dessa moduler på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="53e3f-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="53e3f-112">Kartmoduler kan utökas för andra scenarier, förutom interaktion med modulerna för butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="53e3f-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="53e3f-113">Det krävs emellertid att modulen anpassas.</span><span class="sxs-lookup"><span data-stu-id="53e3f-113">However, module customization is required.</span></span>

<span data-ttu-id="53e3f-114">Kartmodulen introducerades i Commerce version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="53e3f-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="53e3f-115">Följande bild visar ett exempel på en kartmodul som används på en sida för butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="53e3f-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exempel på en modul för butiksväljare](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="53e3f-117">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="53e3f-117">Module properties</span></span>

| <span data-ttu-id="53e3f-118">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="53e3f-118">Property name</span></span>             | <span data-ttu-id="53e3f-119">Värde</span><span class="sxs-lookup"><span data-stu-id="53e3f-119">Value</span></span>                 | <span data-ttu-id="53e3f-120">beskrivning</span><span class="sxs-lookup"><span data-stu-id="53e3f-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="53e3f-121">Rubrik</span><span class="sxs-lookup"><span data-stu-id="53e3f-121">Heading</span></span> | <span data-ttu-id="53e3f-122">Text</span><span class="sxs-lookup"><span data-stu-id="53e3f-122">Text</span></span> | <span data-ttu-id="53e3f-123">Rubriken för modulen.</span><span class="sxs-lookup"><span data-stu-id="53e3f-123">The heading for the module.</span></span> |
| <span data-ttu-id="53e3f-124">Kartnålsalternativ: standardikon</span><span class="sxs-lookup"><span data-stu-id="53e3f-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="53e3f-125">Bild</span><span class="sxs-lookup"><span data-stu-id="53e3f-125">Image</span></span> | <span data-ttu-id="53e3f-126">Symbolbilden för kartnål som används för butiker som visas på en karta.</span><span class="sxs-lookup"><span data-stu-id="53e3f-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="53e3f-127">Kartnålsalternativ: aktiv ikon</span><span class="sxs-lookup"><span data-stu-id="53e3f-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="53e3f-128">Bild</span><span class="sxs-lookup"><span data-stu-id="53e3f-128">Image</span></span> | <span data-ttu-id="53e3f-129">Symbolbilden för kartnål som används för butiker som väljs på en karta.</span><span class="sxs-lookup"><span data-stu-id="53e3f-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="53e3f-130">Kartnålsalternativ: färg på standardikon</span><span class="sxs-lookup"><span data-stu-id="53e3f-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="53e3f-131">Teckensträng</span><span class="sxs-lookup"><span data-stu-id="53e3f-131">Character string</span></span> | <span data-ttu-id="53e3f-132">Texten eller det hexadecimala värdet för färgen på kartnålssymboler på en karta.</span><span class="sxs-lookup"><span data-stu-id="53e3f-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="53e3f-133">Kartnålsalternativ: färg aktiv ikon</span><span class="sxs-lookup"><span data-stu-id="53e3f-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="53e3f-134">Teckensträng</span><span class="sxs-lookup"><span data-stu-id="53e3f-134">Character string</span></span> | <span data-ttu-id="53e3f-135">Texten eller det hexadecimala värdet för färgen på den valda kartnålssymboler på en karta.</span><span class="sxs-lookup"><span data-stu-id="53e3f-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="53e3f-136">Visa index</span><span class="sxs-lookup"><span data-stu-id="53e3f-136">Show index</span></span> | <span data-ttu-id="53e3f-137">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="53e3f-137">**True** or **False**</span></span> | <span data-ttu-id="53e3f-138">Om den här egenskapen har värdet **sant** visas ett index för varje kartnål som anger att en butik ska visa ett index.</span><span class="sxs-lookup"><span data-stu-id="53e3f-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="53e3f-139">Det här indexet matchar indexet i listvyn som visas i modulen butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="53e3f-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="53e3f-140">Lägg till tillåtna mappnings-URL:er till direktiven för webbplatsinnehållets säkerhetsprincip</span><span class="sxs-lookup"><span data-stu-id="53e3f-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="53e3f-141">För att kartmodulen ska samverka med Bing Maps måste du se till att följande mappnings-URL:er tillåts (kallas också "vitlistade") per webbplatsinnehållets säkerhetsprincip (CSP).</span><span class="sxs-lookup"><span data-stu-id="53e3f-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="53e3f-142">Den här inställningen görs i Commerce webbplatsskapare genom att lägga till tillåtna URL:er till olika webbplatsers CSP-direktiv (till exempel **img-src**).</span><span class="sxs-lookup"><span data-stu-id="53e3f-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="53e3f-143">Mer information finns i [säkerhetsprinciper för innehåll](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="53e3f-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="53e3f-144">Till direktivet **connect-src** lägger du till **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="53e3f-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="53e3f-145">Till direktivet **img-src** lägger du till **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="53e3f-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="53e3f-146">Till direktivet **script-src** lägger du till **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="53e3f-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="53e3f-147">Till direktivet **script style-src** lägger du till **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="53e3f-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="53e3f-148">Lägg till en kartmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="53e3f-148">Add a map module to a page</span></span>

<span data-ttu-id="53e3f-149">Mer information om hur du konfigurerar en kartmodul på en sida finns i [modulen butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="53e3f-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="53e3f-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="53e3f-150">Additional resources</span></span>

[<span data-ttu-id="53e3f-151">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="53e3f-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="53e3f-152">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="53e3f-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="53e3f-153">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="53e3f-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="53e3f-154">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="53e3f-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="53e3f-155">Hantera Bing-kartor för din organisation</span><span class="sxs-lookup"><span data-stu-id="53e3f-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="53e3f-156">Bing Maps V8 webbkontroll</span><span class="sxs-lookup"><span data-stu-id="53e3f-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
