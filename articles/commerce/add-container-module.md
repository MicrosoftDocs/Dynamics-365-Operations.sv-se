---
title: Behållaremodul
description: Det här avsnittet handlar om behållarmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 22a09b61fbe3bd1cca96011d3fb81a12ef1bc844
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697070"
---
# <a name="container-module"></a><span data-ttu-id="0d9d3-103">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-103">Container module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0d9d3-104">Det här avsnittet handlar om behållarmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-104">This topic covers container modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0d9d3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0d9d3-105">Overview</span></span>

<span data-ttu-id="0d9d3-106">En behållarmodul är en modul som är värd för andra moduler inne i den.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-106">A container module is a module that hosts other modules inside it.</span></span> <span data-ttu-id="0d9d3-107">Det är den mest allmänna behållaren som används i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-107">It's the most generic container that is used in Dynamics 365 Commerce.</span></span> <span data-ttu-id="0d9d3-108">Det primära syftet med en behållare är att definiera, via de egenskaper som är inställda för den, layouten för modulerna inne i den.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-108">The primary purpose of a container module is to define, through the properties that are set for it, the layout of the modules that are inside.</span></span> <span data-ttu-id="0d9d3-109">Dessa moduler kan till exempel visas sida vid sida i en layout med två kolumner, tre kolumner, fyra kolumner och sex kolumner.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-109">For example, those modules can appear side by side in a two-column, three-column, four-column, or six-column layout.</span></span> <span data-ttu-id="0d9d3-110">De kan också begränsas till behållarens bredd, eller så att de fyller skärmen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-110">They can also be limited to width of the container, or they can fill the screen.</span></span> <span data-ttu-id="0d9d3-111">En rubrik kan också läggas till i varje behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-111">A heading can also be added to every container module.</span></span>

<span data-ttu-id="0d9d3-112">Det finns tre standard typer av behållarmoduler: behållare, behållare med 2 platser och behållare med 3 platser.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-112">There are three standard types of container modules: container, container with 2-slots, and container with 3-slots.</span></span> <span data-ttu-id="0d9d3-113">Moduler av valfri typ av modul kan placeras i dessa behållare.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-113">Modules of any type of module can be put inside these containers.</span></span> <span data-ttu-id="0d9d3-114">Det finns också särskilda typer av moduler för behållare, t.ex. karusell, innehållsrika block, innehållsplacering, korg, utcheckning, inköpsruta, sidhuvud och sidfot.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-114">There are also special types of container modules, such as carousel, content rich block, content placement, cart, checkout, buy box, header, and footer.</span></span> <span data-ttu-id="0d9d3-115">Dessa behållare har särskilda syfte och endast specifika typer av moduler som stöds kan placeras inuti dem.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-115">These containers have specific purposes, and only specific supported types of modules can be put inside them.</span></span>

<span data-ttu-id="0d9d3-116">Vi rekommenderar att du placerar moduler inuti en behållare så att de kan begränsas till behållarens bredd.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-116">We recommend that you put modules inside a container, so that they can be limited to the width of the container.</span></span>

## <a name="examples-of-container-modules-in-e-commerce"></a><span data-ttu-id="0d9d3-117">Exempel på behållarmoduler i e-handel</span><span class="sxs-lookup"><span data-stu-id="0d9d3-117">Examples of container modules in e-Commerce</span></span>

- <span data-ttu-id="0d9d3-118">En webbplatsförfattare vill ha en layout med tre kolumner, där tre moduler visas sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-118">A site author wants a three-column layout, where three modules appear side by side.</span></span> <span data-ttu-id="0d9d3-119">Därför använder webbplatsförfattaren en behållarmodul med typen 3 platser.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-119">Therefore, the site author uses a container module of the container with 3-slots type.</span></span>
- <span data-ttu-id="0d9d3-120">En webbplatsförfattare vill ha en layout med sex kolumner, där sex moduler visas sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-120">A site author wants a six-column layout, where six modules appear side by side.</span></span> <span data-ttu-id="0d9d3-121">Därför använder webbplatsförfattaren en behållare som innehåller sex kolumner.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-121">Therefore, the site author uses a container of the contain type that has six columns inside it.</span></span>
- <span data-ttu-id="0d9d3-122">En webbplatsförfattare vill placera en modul på en sida men vill inte att den ska fylla skärmen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-122">A site author wants to put a module on a page but doesn't want it to fill the screen.</span></span> <span data-ttu-id="0d9d3-123">Därför lägger webbplatsförfattaren till modulen i en behållarmodul och anger behållarens egenskap **bredd** till **anpassad behållare**.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-123">Therefore, the site author adds the module to a container module and sets the container's **Width** property to **Fit container**.</span></span>

## <a name="container-module-properties"></a><span data-ttu-id="0d9d3-124">Egenskaper för behållarmoduler</span><span class="sxs-lookup"><span data-stu-id="0d9d3-124">Container module properties</span></span>

| <span data-ttu-id="0d9d3-125">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="0d9d3-125">Property name</span></span>     | <span data-ttu-id="0d9d3-126">Värden</span><span class="sxs-lookup"><span data-stu-id="0d9d3-126">Values</span></span> | <span data-ttu-id="0d9d3-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0d9d3-127">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="0d9d3-128">Rubrik</span><span class="sxs-lookup"><span data-stu-id="0d9d3-128">Heading</span></span>           | <span data-ttu-id="0d9d3-129">Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**)</span><span class="sxs-lookup"><span data-stu-id="0d9d3-129">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="0d9d3-130">En valfri rubrik kan anges för behållaren.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-130">An optional heading can be provided for the container.</span></span> <span data-ttu-id="0d9d3-131">Som standard används rubriktaggen **H2** för rubriken.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-131">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="0d9d3-132">Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-132">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="0d9d3-133">Bredd</span><span class="sxs-lookup"><span data-stu-id="0d9d3-133">Width</span></span>             | <span data-ttu-id="0d9d3-134">**Passa behållare** eller **Fyll skärm**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-134">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="0d9d3-135">Om värdet är inställt på att **Fylla behållare** (standardvärdet) modulerna inne i behållaren begränsas till behållarens bredd.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-135">If the value is set to **Fit container** (the default value), the modules inside the container are limited to the width of the container.</span></span> <span data-ttu-id="0d9d3-136">Om värdet är inställt på **Fyll skärm** begränsas modulerna inte till behållarens bredd utan kan fylla skärmen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-136">If the value is set to **Fill screen**, the modules aren't limited to the container width but can fill the screen.</span></span> |
| <span data-ttu-id="0d9d3-137">Antal kolumner</span><span class="sxs-lookup"><span data-stu-id="0d9d3-137">Number of columns</span></span> | <span data-ttu-id="0d9d3-138">**1**, **2**, **3**, **4**, **6** eller **12**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-138">**1**, **2**, **3**, **4**, **6**, or **12**</span></span> | <span data-ttu-id="0d9d3-139">Den här egenskapen definierar antalet kolumner i behållaren.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-139">This property defines the number of columns in the container.</span></span> <span data-ttu-id="0d9d3-140">En behållare kan ha upp till 12 kolumner.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-140">A container can have up to 12 columns.</span></span> |

## <a name="container-with-2-slots"></a><span data-ttu-id="0d9d3-141">Behållare med två platser</span><span class="sxs-lookup"><span data-stu-id="0d9d3-141">Container with 2-slots</span></span>

<span data-ttu-id="0d9d3-142">Behållaren av typen 2 platser är optimerad för en layout med två kolumner.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-142">The container with 2-slots type is optimized for a two-column layout.</span></span> <span data-ttu-id="0d9d3-143">Den här typen av behållare har två platser som du kan använda för att visa modulerna bredvid varandra.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-143">This type of container has two slots to allow for a side-by-side view of the modules that are inside.</span></span>

<span data-ttu-id="0d9d3-144">Ytterligare egenskaper kan användas för att optimera layouten för olika visningsportar (mobila enheter, surfplattor, datorer och så vidare).</span><span class="sxs-lookup"><span data-stu-id="0d9d3-144">Additional properties can be used to optimize the layout for different view ports (mobile devices, tablets, computers, and so on).</span></span> <span data-ttu-id="0d9d3-145">För varje visningsport kan bredden på varje kolumn definieras.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-145">For every view port, the width of each column can be defined.</span></span> <span data-ttu-id="0d9d3-146">Följande inställningar av kolumnbredd är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="0d9d3-146">The following column width settings are available:</span></span>

- <span data-ttu-id="0d9d3-147">**75 %/25 %** – den första modulen har kolumnbredden 75 procent och den andra modulen har kolumnbredden 25 procent.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-147">**75%/25%** – The first module has a column width of 75 percent, and the second module has a column width of 25 percent.</span></span> <span data-ttu-id="0d9d3-148">Alternativet **25 %/75 %** är också tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-148">A **25%/75%** option is also available.</span></span>
- <span data-ttu-id="0d9d3-149">**50 %/50 %** – båda modulerna har samma kolumnbredd.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-149">**50%/50%** – Both modules have equal column width.</span></span>
- <span data-ttu-id="0d9d3-150">**67 %/33 %** – den första modulen har kolumnbredden 67 procent och den andra modulen har kolumnbredden 33 procent.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-150">**67%/33%** – The first module has a column width of 67 percent, and the second module has a column width of 33 percent.</span></span> <span data-ttu-id="0d9d3-151">Alternativet **33 %/67 %** är också tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-151">A **33%/67%** option is also available.</span></span>
- <span data-ttu-id="0d9d3-152">**100 %** – båda modulerna har en fullständig kolumnbredd.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-152">**100%** – Both modules have a full-column width.</span></span> <span data-ttu-id="0d9d3-153">Därför staplas modulerna lodrätt i en enda kolumn.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-153">Therefore, the modules are vertically stacked in a single column.</span></span> <span data-ttu-id="0d9d3-154">Även om den här layouten för en kolumn ska placeras i förhållande till behållaren med två platser, kan det vara bättre att använda vissa visningsportar (t.ex. extra små vyer som t.ex. mobila enheter).</span><span class="sxs-lookup"><span data-stu-id="0d9d3-154">Although this single-column layout goes against intent of the container with 2-slots type, it might be preferable for some view ports (for example, extra-small view ports such as mobile devices).</span></span>

### <a name="container-with-2-slots-properties"></a><span data-ttu-id="0d9d3-155">Behållare med egenskaper för 2 platser</span><span class="sxs-lookup"><span data-stu-id="0d9d3-155">Container with 2-slots properties</span></span>

| <span data-ttu-id="0d9d3-156">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="0d9d3-156">Property name</span></span>                   | <span data-ttu-id="0d9d3-157">Värden</span><span class="sxs-lookup"><span data-stu-id="0d9d3-157">Values</span></span> | <span data-ttu-id="0d9d3-158">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0d9d3-158">Description</span></span> |
|---------------------------------|--------|-------------|
| <span data-ttu-id="0d9d3-159">Rubrik</span><span class="sxs-lookup"><span data-stu-id="0d9d3-159">Heading</span></span>                         | <span data-ttu-id="0d9d3-160">Rubriktext och rubriktagg</span><span class="sxs-lookup"><span data-stu-id="0d9d3-160">Heading text and heading tag</span></span> | <span data-ttu-id="0d9d3-161">En valfri kan anges för behållaren.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-161">An optional can be provided for the container.</span></span> |
| <span data-ttu-id="0d9d3-162">Konfiguration av extra liten visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-162">X-Small view port configuration</span></span> | <span data-ttu-id="0d9d3-163">**25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-163">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="0d9d3-164">Den här egenskapen definierar layouten för extra små visningsportar.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-164">This property defines the layout for extra-small view ports.</span></span> |
| <span data-ttu-id="0d9d3-165">Konfiguration av liten visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-165">Small view port configuration</span></span>   | <span data-ttu-id="0d9d3-166">**25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-166">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="0d9d3-167">Den här egenskapen definierar layouten för små visningsportar, t.ex. mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-167">This property defines the layout for small view ports, such as mobile devices.</span></span> |
| <span data-ttu-id="0d9d3-168">Konfiguration av medelstor visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-168">Medium view port configuration</span></span>  | <span data-ttu-id="0d9d3-169">**25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-169">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="0d9d3-170">Den här egenskapen definierar layouten för medelstora visningsportar, t.ex. surfplattor.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-170">This property defines the layout for medium view ports, such as tablets.</span></span> |
| <span data-ttu-id="0d9d3-171">Konfiguration av stor visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-171">Large view port configuration</span></span>   | <span data-ttu-id="0d9d3-172">**25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-172">**25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%**, or **100%**</span></span> | <span data-ttu-id="0d9d3-173">Den här egenskapen definierar layouten för stora visningsportar, t.ex. datorer.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-173">This property defines the layout for large view ports, such as computers.</span></span> |

## <a name="container-with-3-slots"></a><span data-ttu-id="0d9d3-174">Behållare med tre platser</span><span class="sxs-lookup"><span data-stu-id="0d9d3-174">Container with 3-slots</span></span>

<span data-ttu-id="0d9d3-175">Behållaren av typen 3 platsmoduler är optimerad för en layout med tre kolumner.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-175">The container with 3-slots modules type is optimized for a three-column layout.</span></span>

<span data-ttu-id="0d9d3-176">Ytterligare egenskaper kan användas för att optimera layouten för olika visningsportar.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-176">Additional properties can be used to optimize the layout for different view ports.</span></span> <span data-ttu-id="0d9d3-177">För varje visningsport kan bredden på varje kolumn definieras.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-177">For every view port, the width of each column can be defined.</span></span> <span data-ttu-id="0d9d3-178">Följande inställningar av kolumnbredd är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="0d9d3-178">The following column width settings are available:</span></span>

- <span data-ttu-id="0d9d3-179">**33 %/33 %/33 %** – Alla tre modulerna har samma kolumnbredd.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-179">**33%/33%/33%** – All three modules have equal column width.</span></span>
- <span data-ttu-id="0d9d3-180">**50 %/25 %/25 %** – den första modulen har kolumnbredden 50 procent och var och en av de återstående två modulerna har kolumnbredden 25 procent.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-180">**50%/25%/25%** – The first module has a column width of 50 percent, and each of the remaining two modules has a column width of 25 percent.</span></span> <span data-ttu-id="0d9d3-181">Alternativen **25 %/50 %/25 %** och **25%/25%/50%** är också tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-181">**25%/50%/25%** and **25%/25%/50%** options are also available.</span></span>
- <span data-ttu-id="0d9d3-182">**16 %/16 %/67 %** – Var och en av de första två modulerna har kolumnbredden 16 procent och den tredje modulen har kolumnbredden 67 procent.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-182">**16%/16%/67%** – Each of the first two modules has a column width of 16 percent, and the third module has a column width of 67 percent.</span></span> <span data-ttu-id="0d9d3-183">Alternativen **16 %/67 %/16 %** och **67%/16%/16%** är också tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-183">**16%/67%/16%** and **67%/16%/16%** options are also available.</span></span>

### <a name="container-with-3-slots-properties"></a><span data-ttu-id="0d9d3-184">Behållare med egenskaper för 3 platser</span><span class="sxs-lookup"><span data-stu-id="0d9d3-184">Container with 3-slots properties</span></span>

| <span data-ttu-id="0d9d3-185">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="0d9d3-185">Property name</span></span>                   | <span data-ttu-id="0d9d3-186">Värden</span><span class="sxs-lookup"><span data-stu-id="0d9d3-186">Values</span></span> | <span data-ttu-id="0d9d3-187">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0d9d3-187">Description</span></span> |
|---------------------------------|--------|-------------|
| <span data-ttu-id="0d9d3-188">Rubrik</span><span class="sxs-lookup"><span data-stu-id="0d9d3-188">Heading</span></span>                         | <span data-ttu-id="0d9d3-189">Rubriktext och rubriktagg</span><span class="sxs-lookup"><span data-stu-id="0d9d3-189">Heading text and heading tag</span></span> | <span data-ttu-id="0d9d3-190">En valfri rubrik kan läggas till behållaren.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-190">An optional heading can be added to the container.</span></span> |
| <span data-ttu-id="0d9d3-191">Konfiguration av extra liten visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-191">X-Small view port configuration</span></span> | <span data-ttu-id="0d9d3-192">**33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-192">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="0d9d3-193">Den här egenskapen definierar layouten för extra små visningsportar.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-193">This property defines the layout for extra-small view ports.</span></span> |
| <span data-ttu-id="0d9d3-194">Konfiguration av liten visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-194">Small view port configuration</span></span>   | <span data-ttu-id="0d9d3-195">**33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-195">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="0d9d3-196">Den här egenskapen definierar layouten för små visningsportar, t.ex. mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-196">This property defines the layout for small view ports, such as mobile devices.</span></span> |
| <span data-ttu-id="0d9d3-197">Konfiguration av medelstor visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-197">Medium view port configuration</span></span>  | <span data-ttu-id="0d9d3-198">**33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-198">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="0d9d3-199">Den här egenskapen definierar layouten för medelstora visningsportar, t.ex. surfplattor.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-199">This property defines the layout for medium view ports, such as tablets.</span></span> |
| <span data-ttu-id="0d9d3-200">Konfiguration av stor visningsport</span><span class="sxs-lookup"><span data-stu-id="0d9d3-200">Large view port configuration</span></span>   | <span data-ttu-id="0d9d3-201">**33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %**</span><span class="sxs-lookup"><span data-stu-id="0d9d3-201">**33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%**, or **67%/16%/16%**</span></span> | <span data-ttu-id="0d9d3-202">Den här egenskapen definierar layouten för stora visningsportar, t.ex. datorer.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-202">This property defines the layout for large view ports, such as computers.</span></span> |

## <a name="add-a-container-module-to-a-page"></a><span data-ttu-id="0d9d3-203">Lägg till en behållarmodul på en sida</span><span class="sxs-lookup"><span data-stu-id="0d9d3-203">Add a container module to a page</span></span>

<span data-ttu-id="0d9d3-204">Om du vill lägga till en modul för behållarspelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-204">To add a container player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="0d9d3-205">Skapa en sidmall som har namnet **behållarmall**.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-205">Create a page template that is named **container template**.</span></span>
1. <span data-ttu-id="0d9d3-206">Lägg till platsen **Huvud** på standardsida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-206">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="0d9d3-207">I behållarmodulen, lägg till en funktionsmodul.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-207">In the container module, add a feature module.</span></span>
1. <span data-ttu-id="0d9d3-208">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-208">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="0d9d3-209">Använd den behållarmall som du just skapade för att skapa en sida med namnet **behållarsida**.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-209">Use the container template that you just created to create a page that is named **container page**.</span></span>
1. <span data-ttu-id="0d9d3-210">Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-210">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="0d9d3-211">I egenskapsrutan för behållarmodulen anger du egenskapen **antalet kolumner** till **1** och egenskapen **bredd** till **passa behållare**.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-211">In the property pane for the container module, set the **Number of columns** property to **1** and the **Width** property to **Fit container**.</span></span>
1. <span data-ttu-id="0d9d3-212">I behållarmodulen, lägg till en funktionsmodul.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-212">In the container module, add a feature module.</span></span>
1. <span data-ttu-id="0d9d3-213">Konfigurera en rubrik i egenskapsfönstret för funktionsmodulen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-213">In the property pane for the feature module, configure a heading.</span></span>
1. <span data-ttu-id="0d9d3-214">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-214">Save and preview the page.</span></span> <span data-ttu-id="0d9d3-215">Du bör se en modul som får plats inom samma bredd som behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-215">You should see one feature module that fits within the width of the container module.</span></span>
1. <span data-ttu-id="0d9d3-216">I behållarmodulens egenskapsfönster, ändra värdet för **Antal kolumner** till **3**.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-216">In the property pane for the container module, change the the value of the **Number of columns** property to **3**.</span></span>
1. <span data-ttu-id="0d9d3-217">Lägg till två fler funktionsmoduler till behållarmodulen.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-217">Add two more feature modules to the container module.</span></span>
1. <span data-ttu-id="0d9d3-218">Spara och förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-218">Save and preview the page.</span></span> <span data-ttu-id="0d9d3-219">Nu ska du se tre funktionsmoduler som visas sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-219">You should now see three feature modules that appear side by side.</span></span>
1. <span data-ttu-id="0d9d3-220">När du har uppnått layouten du vill ha, checkar du in sidan och publicerar den.</span><span class="sxs-lookup"><span data-stu-id="0d9d3-220">After you've achieved the layout that you want, check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d9d3-221">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0d9d3-221">Additional resources</span></span>

[<span data-ttu-id="0d9d3-222">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="0d9d3-222">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0d9d3-223">Karusellmodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-223">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="0d9d3-224">Innehållsrik blockmodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-224">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="0d9d3-225">Modul för innehållsplacering</span><span class="sxs-lookup"><span data-stu-id="0d9d3-225">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="0d9d3-226">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="0d9d3-226">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0d9d3-227">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-227">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0d9d3-228">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-228">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0d9d3-229">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="0d9d3-229">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0d9d3-230">Sidfotmodul</span><span class="sxs-lookup"><span data-stu-id="0d9d3-230">Footer module</span></span>](author-footer-module.md)