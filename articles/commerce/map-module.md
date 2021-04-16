---
title: Kartmodul
description: Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b8c3ab0653fd5e3561d0bfbe85624d912756e2be
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794197"
---
# <a name="map-module"></a><span data-ttu-id="57c5f-103">Kartmodul</span><span class="sxs-lookup"><span data-stu-id="57c5f-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="57c5f-104">Det här avsnittet mappar kartmoduler och beskriver hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="57c5f-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="57c5f-105">En kartmodul visar platserna för butikerna i en interaktiv karta som återges med hjälp av [Bing Maps-V8 webbkontroll](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="57c5f-105">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="57c5f-106">En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="57c5f-106">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="57c5f-107">I kartmoduler finns olika vyer, till exempel väg, flyg och gata som användarna kan välja för att visa kartplatser.</span><span class="sxs-lookup"><span data-stu-id="57c5f-107">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="57c5f-108">De tillåter också interaktioner som att zooma in och använda användarens plats.</span><span class="sxs-lookup"><span data-stu-id="57c5f-108">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="57c5f-109">En kartmodul arbetar tillsammans med modulen butiksväljare för att fastställa geografiska platser för butiker som måste återges på en karta.</span><span class="sxs-lookup"><span data-stu-id="57c5f-109">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="57c5f-110">Butiksväljare och kartmoduler interagerar när en användare väljer en butik i en av dessa moduler på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="57c5f-110">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="57c5f-111">Kartmoduler kan utökas för andra scenarier, förutom interaktion med modulerna för butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="57c5f-111">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="57c5f-112">Det krävs emellertid att modulen anpassas.</span><span class="sxs-lookup"><span data-stu-id="57c5f-112">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="57c5f-113">Mappningsmodulen är tillgänglig i Dynamics 365 Commerce 10.0.13-versionen.</span><span class="sxs-lookup"><span data-stu-id="57c5f-113">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="57c5f-114">Följande bild visar ett exempel på en kartmodul som används på en sida för butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="57c5f-114">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exempel på en modul för butiksväljare](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="57c5f-116">Modulegenskaper</span><span class="sxs-lookup"><span data-stu-id="57c5f-116">Module properties</span></span>

| <span data-ttu-id="57c5f-117">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="57c5f-117">Property name</span></span>             | <span data-ttu-id="57c5f-118">Värde</span><span class="sxs-lookup"><span data-stu-id="57c5f-118">Value</span></span>                 | <span data-ttu-id="57c5f-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="57c5f-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="57c5f-120">Rubrik</span><span class="sxs-lookup"><span data-stu-id="57c5f-120">Heading</span></span> | <span data-ttu-id="57c5f-121">Text</span><span class="sxs-lookup"><span data-stu-id="57c5f-121">Text</span></span> | <span data-ttu-id="57c5f-122">Rubriken för modulen.</span><span class="sxs-lookup"><span data-stu-id="57c5f-122">The heading for the module.</span></span> |
| <span data-ttu-id="57c5f-123">Kartnålsalternativ: standardikon</span><span class="sxs-lookup"><span data-stu-id="57c5f-123">Pushpin options: Default icon</span></span> | <span data-ttu-id="57c5f-124">Bild</span><span class="sxs-lookup"><span data-stu-id="57c5f-124">Image</span></span> | <span data-ttu-id="57c5f-125">Symbolbilden för kartnål som används för butiker som visas på en karta.</span><span class="sxs-lookup"><span data-stu-id="57c5f-125">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="57c5f-126">Kartnålsalternativ: aktiv ikon</span><span class="sxs-lookup"><span data-stu-id="57c5f-126">Pushpin options: Active icon</span></span> | <span data-ttu-id="57c5f-127">Bild</span><span class="sxs-lookup"><span data-stu-id="57c5f-127">Image</span></span> | <span data-ttu-id="57c5f-128">Symbolbilden för kartnål som används för butiker som väljs på en karta.</span><span class="sxs-lookup"><span data-stu-id="57c5f-128">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="57c5f-129">Kartnålsalternativ: färg på standardikon</span><span class="sxs-lookup"><span data-stu-id="57c5f-129">Pushpin options: Default icon color</span></span> | <span data-ttu-id="57c5f-130">Teckensträng</span><span class="sxs-lookup"><span data-stu-id="57c5f-130">Character string</span></span> | <span data-ttu-id="57c5f-131">Texten eller det hexadecimala värdet för färgen på kartnålssymboler på en karta.</span><span class="sxs-lookup"><span data-stu-id="57c5f-131">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="57c5f-132">Kartnålsalternativ: färg aktiv ikon</span><span class="sxs-lookup"><span data-stu-id="57c5f-132">Pushpin options: Active icon color</span></span> | <span data-ttu-id="57c5f-133">Teckensträng</span><span class="sxs-lookup"><span data-stu-id="57c5f-133">Character string</span></span> | <span data-ttu-id="57c5f-134">Texten eller det hexadecimala värdet för färgen på den valda kartnålssymboler på en karta.</span><span class="sxs-lookup"><span data-stu-id="57c5f-134">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="57c5f-135">Visa index</span><span class="sxs-lookup"><span data-stu-id="57c5f-135">Show index</span></span> | <span data-ttu-id="57c5f-136">**Sant** eller **falskt**</span><span class="sxs-lookup"><span data-stu-id="57c5f-136">**True** or **False**</span></span> | <span data-ttu-id="57c5f-137">Om den här egenskapen har värdet **sant** visas ett index för varje kartnål som anger att en butik ska visa ett index.</span><span class="sxs-lookup"><span data-stu-id="57c5f-137">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="57c5f-138">Det här indexet matchar indexet i listvyn som visas i modulen butiksväljare.</span><span class="sxs-lookup"><span data-stu-id="57c5f-138">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="57c5f-139">Lägg till tillåtna mappnings-URL:er till direktiven för webbplatsinnehållets säkerhetsprincip</span><span class="sxs-lookup"><span data-stu-id="57c5f-139">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="57c5f-140">För att kartmodulen ska kunna interagera med Bing Maps måste du se till att följande mappnings-URL:er tillåts i enlighet med webbplatsinnehållets säkerhetsprincip (CSP).</span><span class="sxs-lookup"><span data-stu-id="57c5f-140">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed per your site's content security policy (CSP).</span></span> <span data-ttu-id="57c5f-141">Den här inställningen görs i Commerce webbplatsskapare genom att lägga till tillåtna URL:er till olika webbplatsers CSP-direktiv (till exempel **img-src**).</span><span class="sxs-lookup"><span data-stu-id="57c5f-141">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="57c5f-142">Mer information finns i [säkerhetsprinciper för innehåll](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="57c5f-142">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="57c5f-143">Till direktivet **connect-src** lägger du till **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="57c5f-143">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="57c5f-144">Till direktivet **img-src** lägger du till **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="57c5f-144">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="57c5f-145">Till direktivet **script-src** lägger du till **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="57c5f-145">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="57c5f-146">Till direktivet **script style-src** lägger du till **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="57c5f-146">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="57c5f-147">Lägg till en kartmodul på en ny sida</span><span class="sxs-lookup"><span data-stu-id="57c5f-147">Add a map module to a page</span></span>

<span data-ttu-id="57c5f-148">Mer information om hur du konfigurerar en kartmodul på en sida finns i [modulen butiksväljare](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="57c5f-148">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="57c5f-149">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="57c5f-149">Additional resources</span></span>

[<span data-ttu-id="57c5f-150">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="57c5f-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="57c5f-151">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="57c5f-151">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="57c5f-152">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="57c5f-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="57c5f-153">Modul för butiksväljare</span><span class="sxs-lookup"><span data-stu-id="57c5f-153">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="57c5f-154">Hantera Bing-kartor för din organisation</span><span class="sxs-lookup"><span data-stu-id="57c5f-154">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="57c5f-155">Bing Maps V8 webbkontroll</span><span class="sxs-lookup"><span data-stu-id="57c5f-155">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]