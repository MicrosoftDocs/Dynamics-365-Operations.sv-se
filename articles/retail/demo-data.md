---
title: "Demonstrationsdataskärmens layout i MOPS/CPOS"
description: "Det här avsnittet innehåller information om skärmlayouterna som medföljer datauppsättningsdemo för butikupplevelser i Microsoft Dynamics 365 for Retail."
author: zlinster
manager: AnnBe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: zlinster
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 75b77ff633161acf39370a7c0cf522446b3a374a
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="demo-data-screen-layouts-in-mposcpos"></a><span data-ttu-id="4b559-103">Demonstrationsdataskärmens layout i MOPS/CPOS</span><span class="sxs-lookup"><span data-stu-id="4b559-103">Demo data screen layouts in MPOS/CPOS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b559-104">Det här avsnittet innehåller information om skärmlayouterna som medföljer datauppsättningsdemo för butikupplevelser i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="4b559-104">This topic provides information about the screen layouts that are included with the demo data set for the point of sale (POS) experiences in Microsoft Dynamics 365 for Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="4b559-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4b559-105">Overview</span></span>

<span data-ttu-id="4b559-106">Exempel på de skärmlayouter som medföljer Retail demodata ger innehåll som är optimerat för olika butikssegment, lagerarbetarroller och enheter.</span><span class="sxs-lookup"><span data-stu-id="4b559-106">The sample screen layouts that are included with Retail demo data provide content that is optimized for various retail segments, store worker roles, and devices.</span></span> <span data-ttu-id="4b559-107">En enkel layout kan innehålla flera layoutstorlekar och kombinationer av knappsatser som säkerställer täckning som lagerarbetare flyttar mellan enheter och stationer.</span><span class="sxs-lookup"><span data-stu-id="4b559-107">A single layout can contain several layout sizes and combinations of button grids, to help ensure coverage as store workers move between devices and stations.</span></span> <span data-ttu-id="4b559-108">Det här avsnittet beskriver skillnaderna mellan dessa layouter, operationer de tillhandahåller och de övergripande erfarenheter som de kan ge.</span><span class="sxs-lookup"><span data-stu-id="4b559-108">This topic highlights the differences between these layouts, the operations that they provide, and the overall experiences that they deliver.</span></span>

![Demodatalayouter mellan enheter](../retail/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a><span data-ttu-id="4b559-110">Beskrivning av en skärmlayout-ID</span><span class="sxs-lookup"><span data-stu-id="4b559-110">Anatomy of a screen layout ID</span></span>

<span data-ttu-id="4b559-111">För att hitta skärmlayouter i Retail, gå till **Butik** > **Kanalinställning** > **Butiksinställning** > **Butik** > **Skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="4b559-111">To find screen layouts in Retail, go to **Retail** > **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>

![Sidan skärmlayouter i Retail](../retail/media/demo-screen-layouts-fig-2-1.png)

<span data-ttu-id="4b559-113">Skärmlayout-ID kan ha upp till 10 tecken.</span><span class="sxs-lookup"><span data-stu-id="4b559-113">Screen layout IDs can have a maximum of 10 characters.</span></span> <span data-ttu-id="4b559-114">ID är en sträng som består av tre delar med information i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="4b559-114">The ID is a string that consists of three pieces of information, in this order:</span></span>

1. <span data-ttu-id="4b559-115">Företag</span><span class="sxs-lookup"><span data-stu-id="4b559-115">Company</span></span>
2. <span data-ttu-id="4b559-116">Layoutversion</span><span class="sxs-lookup"><span data-stu-id="4b559-116">Layout version</span></span>
3. <span data-ttu-id="4b559-117">Person</span><span class="sxs-lookup"><span data-stu-id="4b559-117">Persona</span></span>

### <a name="company"></a><span data-ttu-id="4b559-118">Företag</span><span class="sxs-lookup"><span data-stu-id="4b559-118">Company</span></span>

| <span data-ttu-id="4b559-119">Brev</span><span class="sxs-lookup"><span data-stu-id="4b559-119">Letter</span></span> | <span data-ttu-id="4b559-120">Företag</span><span class="sxs-lookup"><span data-stu-id="4b559-120">Company</span></span>         |
|--------|-----------------|
| <span data-ttu-id="4b559-121">A</span><span class="sxs-lookup"><span data-stu-id="4b559-121">A</span></span>      | <span data-ttu-id="4b559-122">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-122">Adventure Works</span></span> |
| <span data-ttu-id="4b559-123">F</span><span class="sxs-lookup"><span data-stu-id="4b559-123">F</span></span>      | <span data-ttu-id="4b559-124">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-124">Fabrikam</span></span>        |
| <span data-ttu-id="4b559-125">C</span><span class="sxs-lookup"><span data-stu-id="4b559-125">C</span></span>      | <span data-ttu-id="4b559-126">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-126">Contoso</span></span>         |

### <a name="layout-version"></a><span data-ttu-id="4b559-127">Layoutversion</span><span class="sxs-lookup"><span data-stu-id="4b559-127">Layout version</span></span>

| <span data-ttu-id="4b559-128">Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="4b559-128">Version number</span></span> | <span data-ttu-id="4b559-129">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4b559-129">Description</span></span>                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| <span data-ttu-id="4b559-130">3</span><span class="sxs-lookup"><span data-stu-id="4b559-130">3</span></span>              | <span data-ttu-id="4b559-131">Grundläggande version som stöder flera olika skärmstorlekar för olika enheter och förhållandet mellan bredd och höjd</span><span class="sxs-lookup"><span data-stu-id="4b559-131">The base version that supports multiple screen sizes for various devices and aspect ratios</span></span> |
| <span data-ttu-id="4b559-132">3.1</span><span class="sxs-lookup"><span data-stu-id="4b559-132">3.1</span></span>            | <span data-ttu-id="4b559-133">Grundläggande version som har stöd för ytterligare språk för panelen **Rekommenderade produkter**</span><span class="sxs-lookup"><span data-stu-id="4b559-133">The base version that has additional support for the **Recommended products** panel</span></span>        |

### <a name="persona"></a><span data-ttu-id="4b559-134">Person</span><span class="sxs-lookup"><span data-stu-id="4b559-134">Persona</span></span>

| <span data-ttu-id="4b559-135">Förkortning</span><span class="sxs-lookup"><span data-stu-id="4b559-135">Abbreviation</span></span> | <span data-ttu-id="4b559-136">Person</span><span class="sxs-lookup"><span data-stu-id="4b559-136">Persona</span></span>       | <span data-ttu-id="4b559-137">Innehåll</span><span class="sxs-lookup"><span data-stu-id="4b559-137">Contents</span></span> |
|--------------|---------------|----------|
| <span data-ttu-id="4b559-138">CSH</span><span class="sxs-lookup"><span data-stu-id="4b559-138">CSH</span></span>          | <span data-ttu-id="4b559-139">Kassör</span><span class="sxs-lookup"><span data-stu-id="4b559-139">Cashier</span></span>       | <span data-ttu-id="4b559-140">Kassörlayouter inkluderar alla transaktionsrelaterade operationer, t.ex. kundorder, returer, rabatter, annulleringar och presentkort.</span><span class="sxs-lookup"><span data-stu-id="4b559-140">Cashier layouts include all transaction-related operations, such as customer orders, returns, discounts, voids, and gift cards.</span></span> <span data-ttu-id="4b559-141">Dessa layouter kan också innehålla dagliga uppgifter för lagerhantering som t.ex. priskontroller, lagersökningar och lagerinventeringar.</span><span class="sxs-lookup"><span data-stu-id="4b559-141">These layouts also include daily tasks for inventory management, such price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="4b559-142">Grundläggande hantering av skift finns också för startbelopp, skjuta upp skift och tidsklocka.</span><span class="sxs-lookup"><span data-stu-id="4b559-142">Basic shift management is also provided for start amounts, suspending shifts, and time clock.</span></span> |
| <span data-ttu-id="4b559-143">MGR</span><span class="sxs-lookup"><span data-stu-id="4b559-143">MGR</span></span>          | <span data-ttu-id="4b559-144">Butikschef</span><span class="sxs-lookup"><span data-stu-id="4b559-144">Store Manager</span></span> | <span data-ttu-id="4b559-145">Butikscheflayouter inkluderar alla transaktionsrelaterade operationer som finns i kassalayouterna men innehåller också momsåsidosättningar.</span><span class="sxs-lookup"><span data-stu-id="4b559-145">Store Manager layouts include all transaction-related operations that are found in the Cashier layouts but also include tax overrides.</span></span> <span data-ttu-id="4b559-146">Dessa layouter kan också innehålla dagliga uppgifter för lagerhantering som t.ex. priskontroller, lagersökningar och lagerinventeringar.</span><span class="sxs-lookup"><span data-stu-id="4b559-146">These layouts also include daily tasks for inventory management, such as price checks, inventory lookups, and stock counts.</span></span> <span data-ttu-id="4b559-147">Hantering av skift tillhandahålls för att starta, skjuta upp och stänga skift.</span><span class="sxs-lookup"><span data-stu-id="4b559-147">Shift management is provided for starting, suspending, and closing shifts.</span></span> <span data-ttu-id="4b559-148">Dessutom innehåller layouterna kassaaktiviteter för registreringar, uttag, kassaavstämningar och kassaskåp och bankinsättningar.</span><span class="sxs-lookup"><span data-stu-id="4b559-148">Additionally, the layouts include drawer operations for entries, removals, tender declarations, and safe and bank drops.</span></span> <span data-ttu-id="4b559-149">Slutligen innehåller dessa layouter tillgång till prestandarapporter och aktivera X- och Z-rapporter som ska skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="4b559-149">Finally, these layouts include access to performance reports, and enable X and Z reports to be printed.</span></span> |
| <span data-ttu-id="4b559-150">STK</span><span class="sxs-lookup"><span data-stu-id="4b559-150">STK</span></span>          | <span data-ttu-id="4b559-151">Ansvarig för lager</span><span class="sxs-lookup"><span data-stu-id="4b559-151">Stock Clerk</span></span>   | <span data-ttu-id="4b559-152">Ansvarig för lager-layouter optimeras för lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="4b559-152">Stock Clerk layouts are optimized for inventory management.</span></span> <span data-ttu-id="4b559-153">De innehåller tillgång till dagliga uppgifter för prischeckar, lagersökningar, plockning och mottagning, lagerinventeringar och paketuppdelning.</span><span class="sxs-lookup"><span data-stu-id="4b559-153">They include access to daily tasks for price checks, inventory lookups, picking and receiving, stock counts, and kit disassembly.</span></span> <span data-ttu-id="4b559-154">Dessa layouter innehåller också grundläggande skiftoperationer för klocka och skjuta upp skift.</span><span class="sxs-lookup"><span data-stu-id="4b559-154">These layouts also provide basic shift operations for time clock and suspending shifts.</span></span> <span data-ttu-id="4b559-155">Även om dessa layouter huvudsakligen är avsedda för back office-uppgifter, har lagerarbetare samma operationer som kassörerna för transaktionsskärmar.</span><span class="sxs-lookup"><span data-stu-id="4b559-155">Although these layouts are intended mainly for back-office tasks, stock clerks have the same operations as cashiers for transaction screens.</span></span> |

### <a name="example-layout"></a><span data-ttu-id="4b559-156">Exempel på layout</span><span class="sxs-lookup"><span data-stu-id="4b559-156">Example layout</span></span>

<span data-ttu-id="4b559-157">Här följer ett exempel på en skärmlayout-ID för företaget Fabrikam, layoutversion 3 och butikschefen:</span><span class="sxs-lookup"><span data-stu-id="4b559-157">Here is an example of a screen layout ID for the Fabrikam company, layout version 3, and the Store Manager persona:</span></span>

<span data-ttu-id="4b559-158">F3MGR</span><span class="sxs-lookup"><span data-stu-id="4b559-158">F3MGR</span></span>

<span data-ttu-id="4b559-159">Följande illustration visar ett exempel på välkomstskärmen för Fabrikam butikschefen.</span><span class="sxs-lookup"><span data-stu-id="4b559-159">The following illustration shows an example of the Welcome screen for a Fabrikam store manager.</span></span>

![Välkomstskärm för butikschefen Fabrikam](../retail/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a><span data-ttu-id="4b559-161">Layoutstorlekar</span><span class="sxs-lookup"><span data-stu-id="4b559-161">Layout sizes</span></span>

### <a name="full-vs-compact-layouts"></a><span data-ttu-id="4b559-162">Fullständig jämfört med kompakt layout</span><span class="sxs-lookup"><span data-stu-id="4b559-162">Full vs. compact layouts</span></span>

<span data-ttu-id="4b559-163">En skärmlayout kan ha konfigurationer för både fullstora och kompakta enheter.</span><span class="sxs-lookup"><span data-stu-id="4b559-163">A screen layout can have configurations for both full devices and compact devices.</span></span> <span data-ttu-id="4b559-164">Därför kan en användare tilldelas till en enda skärmlayout som fungerar för olika storlekar och formfaktorer i butiken.</span><span class="sxs-lookup"><span data-stu-id="4b559-164">Therefore, a user can be assigned to a single screen layout that will work across various sizes and form factors in the store.</span></span>

- <span data-ttu-id="4b559-165">**Modern POS - fullständig** - Vanligtvis används fullständiga layouter bäst till större skärmar, till exempel datorskärmar eller surfplattor.</span><span class="sxs-lookup"><span data-stu-id="4b559-165">**Modern POS - Full** – Typically, full layouts are best used for larger displays, such as desktop computer monitors or tablets.</span></span> <span data-ttu-id="4b559-166">Användare kan markera de UI-element som layouten innehåller, ange storlek och placering av elementen och konfigurera de detaljerade egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="4b559-166">Users can select the UI elements that the layout includes, specify the size and placement of those elements, and configure their detailed properties.</span></span> <span data-ttu-id="4b559-167">Fullständiga layouter stöder både stående och liggande konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="4b559-167">Full layouts support both portrait and landscape configurations.</span></span>
- <span data-ttu-id="4b559-168">**Modern POS - komprimerad** - Vanligtvis är komprimerad layout bäst för telefoner eller små surfplattor.</span><span class="sxs-lookup"><span data-stu-id="4b559-168">**Modern POS - Compact** – Typically, compact layouts are best used for phones or small tablets.</span></span> <span data-ttu-id="4b559-169">Designmöjligheter är begränsade för kompakta enheter.</span><span class="sxs-lookup"><span data-stu-id="4b559-169">Design possibilities are limited for compact devices.</span></span> <span data-ttu-id="4b559-170">Användare kan konfigurera kolumner och fält för kvitto- och summarfönster.</span><span class="sxs-lookup"><span data-stu-id="4b559-170">Users can configure the columns and fields for the receipt pane and the totals pane.</span></span>

### <a name="screen-resolutions-that-are-provided"></a><span data-ttu-id="4b559-171">Skärmupplösning som tillhandahålls</span><span class="sxs-lookup"><span data-stu-id="4b559-171">Screen resolutions that are provided</span></span>

<span data-ttu-id="4b559-172">Följande tabell visar layoutstorlek för normal skärmupplösning.</span><span class="sxs-lookup"><span data-stu-id="4b559-172">The following table shows the layout sizes that are provided for typical screen resolutions.</span></span>

| <span data-ttu-id="4b559-173">Layouttyp</span><span class="sxs-lookup"><span data-stu-id="4b559-173">Layout type</span></span> | <span data-ttu-id="4b559-174">Upplösning</span><span class="sxs-lookup"><span data-stu-id="4b559-174">Resolution</span></span> | <span data-ttu-id="4b559-175">Förhållandet mellan bredd och höjd</span><span class="sxs-lookup"><span data-stu-id="4b559-175">Aspect ratio</span></span> | <span data-ttu-id="4b559-176">Måldisplay</span><span class="sxs-lookup"><span data-stu-id="4b559-176">Target display</span></span>          |
|-------------|------------|--------------|-------------------------|
| <span data-ttu-id="4b559-177">Komprimera\*</span><span class="sxs-lookup"><span data-stu-id="4b559-177">Compact\*</span></span>   | <span data-ttu-id="4b559-178">480 × 853</span><span class="sxs-lookup"><span data-stu-id="4b559-178">480 × 853</span></span>  | <span data-ttu-id="4b559-179">16:9</span><span class="sxs-lookup"><span data-stu-id="4b559-179">16:9</span></span>         | <span data-ttu-id="4b559-180">Telefon</span><span class="sxs-lookup"><span data-stu-id="4b559-180">Phones</span></span>                  |
| <span data-ttu-id="4b559-181">Fullständig</span><span class="sxs-lookup"><span data-stu-id="4b559-181">Full</span></span>        | <span data-ttu-id="4b559-182">1024 × 768</span><span class="sxs-lookup"><span data-stu-id="4b559-182">1024 × 768</span></span> | <span data-ttu-id="4b559-183">4:3</span><span class="sxs-lookup"><span data-stu-id="4b559-183">4:3</span></span>          | <span data-ttu-id="4b559-184">Surfplatta</span><span class="sxs-lookup"><span data-stu-id="4b559-184">Tablets</span></span>                 |
| <span data-ttu-id="4b559-185">Fullständig\*</span><span class="sxs-lookup"><span data-stu-id="4b559-185">Full\*</span></span>      | <span data-ttu-id="4b559-186">1280 × 720</span><span class="sxs-lookup"><span data-stu-id="4b559-186">1280 × 720</span></span> | <span data-ttu-id="4b559-187">16:9</span><span class="sxs-lookup"><span data-stu-id="4b559-187">16:9</span></span>         | <span data-ttu-id="4b559-188">Surfplatta</span><span class="sxs-lookup"><span data-stu-id="4b559-188">Tablets</span></span>                 |
| <span data-ttu-id="4b559-189">Fullständig</span><span class="sxs-lookup"><span data-stu-id="4b559-189">Full</span></span>        | <span data-ttu-id="4b559-190">1366 × 768</span><span class="sxs-lookup"><span data-stu-id="4b559-190">1366 × 768</span></span> | <span data-ttu-id="4b559-191">16:9</span><span class="sxs-lookup"><span data-stu-id="4b559-191">16:9</span></span>         | <span data-ttu-id="4b559-192">Surfplattor, större skärmar</span><span class="sxs-lookup"><span data-stu-id="4b559-192">Tablets, larger screens</span></span> |
| <span data-ttu-id="4b559-193">Fullständig</span><span class="sxs-lookup"><span data-stu-id="4b559-193">Full</span></span>        | <span data-ttu-id="4b559-194">1440 × 960</span><span class="sxs-lookup"><span data-stu-id="4b559-194">1440 × 960</span></span> | <span data-ttu-id="4b559-195">3:2</span><span class="sxs-lookup"><span data-stu-id="4b559-195">3:2</span></span>          | <span data-ttu-id="4b559-196">Surfplattor, större skärmar</span><span class="sxs-lookup"><span data-stu-id="4b559-196">Tablets, larger screens</span></span> |

<span data-ttu-id="4b559-197">\*Dessa ytterligare layoutstorlekar är bara tillgängliga i Adventure Works och Fabrikam layouter.</span><span class="sxs-lookup"><span data-stu-id="4b559-197">\* These additional layout sizes are available only in Adventure Works and Fabrikam layouts.</span></span>


>[!TIP]
> <span data-ttu-id="4b559-198">Kassan väljer automatiskt layoutstorlekar, baserat på närmaste storleken för skärmupplösningen för det aktuella appfönstret.</span><span class="sxs-lookup"><span data-stu-id="4b559-198">POS automatically selects layout sizes, based on the closest size that is available for the screen resolution of the current app window.</span></span> <span data-ttu-id="4b559-199">Öppna den layout-ID och layoutskärmupplösning som för närvarande används i Retail Modern POS (MOPS) eller Retail Cloud POS (CPOS), öppna sidan **inställningar** och titta i avsnittet **sessionsinformation**.</span><span class="sxs-lookup"><span data-stu-id="4b559-199">To find the screen layout ID and layout resolution that are currently used, in Retail Modern POS (MPOS) or Retail Cloud POS (CPOS), open the **Settings** page, and look in the **Session information** section.</span></span> <span data-ttu-id="4b559-200">Du kan också hitta den aktuella upplösningen för fönster för ditt aktuella program eller webbläsarram.</span><span class="sxs-lookup"><span data-stu-id="4b559-200">You can also see the actual window resolution for your current application or browser frame.</span></span> <span data-ttu-id="4b559-201">När du har den här informationen hittar du källan för layoutinnehållet i Retail genom att gå till **kanalinställning** > **kassainställningar** > **kassa** > **skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="4b559-201">After you have this information, you can find the source of the layout content in Retail by going to **Channel setup** > **POS setup** > **POS** > **Screen layouts**.</span></span>


![Skärmlayouter och layoutlösningar/storlekar i Retail och kassa](../retail/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a><span data-ttu-id="4b559-203">Företag och varumärken</span><span class="sxs-lookup"><span data-stu-id="4b559-203">Companies and brands</span></span>

<span data-ttu-id="4b559-204">Varje fiktivt företag är avsett för ett annat butikssegment och innehåller produktkataloger som är anpassade för företagets marknad.</span><span class="sxs-lookup"><span data-stu-id="4b559-204">Each fictitious company is targeted to a different retail segment and includes product catalogs that are tuned for the company's market.</span></span> <span data-ttu-id="4b559-205">Varje företag har ett unikt visuellt varumärke som medföljer produkter.</span><span class="sxs-lookup"><span data-stu-id="4b559-205">Each company has a unique visual brand that accompanies its products.</span></span> <span data-ttu-id="4b559-206">Varumärkesanpassade element omfattar tilläggsfärg, mörkt eller ljust tema och medföljande fotografier som ger realistiska upplevelser.</span><span class="sxs-lookup"><span data-stu-id="4b559-206">Branding elements include the accent color, dark or light theme, and accompanying photographs that provide realistic experiences.</span></span>

### <a name="company-segment-and-visual-characteristics"></a><span data-ttu-id="4b559-207">Företagssegment och visuella komponenter</span><span class="sxs-lookup"><span data-stu-id="4b559-207">Company segment and visual characteristics</span></span>

| <span data-ttu-id="4b559-208">Företag</span><span class="sxs-lookup"><span data-stu-id="4b559-208">Company</span></span>         | <span data-ttu-id="4b559-209">Plats</span><span class="sxs-lookup"><span data-stu-id="4b559-209">Location</span></span> | <span data-ttu-id="4b559-210">Segment</span><span class="sxs-lookup"><span data-stu-id="4b559-210">Segment</span></span>        | <span data-ttu-id="4b559-211">Accent</span><span class="sxs-lookup"><span data-stu-id="4b559-211">Accent</span></span> | <span data-ttu-id="4b559-212">Tema</span><span class="sxs-lookup"><span data-stu-id="4b559-212">Theme</span></span> |
|-----------------|----------|----------------|--------|-------|
| <span data-ttu-id="4b559-213">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-213">Adventure Works</span></span> | <span data-ttu-id="4b559-214">Seattle</span><span class="sxs-lookup"><span data-stu-id="4b559-214">Seattle</span></span>  | <span data-ttu-id="4b559-215">Sportutrustning</span><span class="sxs-lookup"><span data-stu-id="4b559-215">Sporting Goods</span></span> | <span data-ttu-id="4b559-216">Blått</span><span class="sxs-lookup"><span data-stu-id="4b559-216">Blue</span></span>   | <span data-ttu-id="4b559-217">Mörk</span><span class="sxs-lookup"><span data-stu-id="4b559-217">Dark</span></span>  |
| <span data-ttu-id="4b559-218">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-218">Fabrikam</span></span>        | <span data-ttu-id="4b559-219">Houston</span><span class="sxs-lookup"><span data-stu-id="4b559-219">Houston</span></span>  | <span data-ttu-id="4b559-220">Mode</span><span class="sxs-lookup"><span data-stu-id="4b559-220">Fashion</span></span>        | <span data-ttu-id="4b559-221">Grönt</span><span class="sxs-lookup"><span data-stu-id="4b559-221">Green</span></span>  | <span data-ttu-id="4b559-222">Ljus</span><span class="sxs-lookup"><span data-stu-id="4b559-222">Light</span></span> |
| <span data-ttu-id="4b559-223">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-223">Contoso</span></span>         | <span data-ttu-id="4b559-224">Boston</span><span class="sxs-lookup"><span data-stu-id="4b559-224">Boston</span></span>   | <span data-ttu-id="4b559-225">Elektronik</span><span class="sxs-lookup"><span data-stu-id="4b559-225">Electronics</span></span>    | <span data-ttu-id="4b559-226">Röd</span><span class="sxs-lookup"><span data-stu-id="4b559-226">Red</span></span>    | <span data-ttu-id="4b559-227">Mörk</span><span class="sxs-lookup"><span data-stu-id="4b559-227">Dark</span></span>  |


>[!NOTE]
> <span data-ttu-id="4b559-228">Adventure Works och Fabrikam är två framstående varumärken.</span><span class="sxs-lookup"><span data-stu-id="4b559-228">Adventure Works and Fabrikam are the two flagship brands.</span></span> <span data-ttu-id="4b559-229">Contoso finns tillgänglig, men alla layouter har inte tillhandahållits.</span><span class="sxs-lookup"><span data-stu-id="4b559-229">Contoso is available, but not all layouts have been provided.</span></span>


<span data-ttu-id="4b559-230">I följande illustrationer visas exempel på välkomstsidan och transaktionssidan för de tre fiktiva företagen.</span><span class="sxs-lookup"><span data-stu-id="4b559-230">The following illustrations show examples of the welcome page and transaction page for the three fictitious companies.</span></span>

### <a name="adventure-works"></a><span data-ttu-id="4b559-231">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-231">Adventure Works</span></span>

![Demodata välkomstsida för Adventure Works](../retail/media/demo-screen-layouts-fig-4-1a.png)

![Demodata transaktionssida för Adventure Works](../retail/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a><span data-ttu-id="4b559-234">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-234">Fabrikam</span></span>

![Demodata välkomstsida för Fabrikam](../retail/media/demo-screen-layouts-fig-4-2a.png)

![Demodata transaktionssida för Fabrikam](../retail/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a><span data-ttu-id="4b559-237">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-237">Contoso</span></span>

![Layouter för Contoso-demo](../retail/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a><span data-ttu-id="4b559-239">Matris för användarinloggning</span><span class="sxs-lookup"><span data-stu-id="4b559-239">User sign in matrix</span></span>

<span data-ttu-id="4b559-240">Användare har angetts för de olika layouterna för skärmen.</span><span class="sxs-lookup"><span data-stu-id="4b559-240">Users have been provided for the various screen layouts.</span></span> <span data-ttu-id="4b559-241">Med hjälp av tabellen nedan kan vara du få tillgång till skärmarna.</span><span class="sxs-lookup"><span data-stu-id="4b559-241">By using the following table, you should be able to access any of the screens.</span></span> <span data-ttu-id="4b559-242">Logga bara in med lämpligt operatörs-ID.</span><span class="sxs-lookup"><span data-stu-id="4b559-242">Just sign in by using an appropriate operator ID.</span></span>

| <span data-ttu-id="4b559-243">Företag</span><span class="sxs-lookup"><span data-stu-id="4b559-243">Company</span></span>         | <span data-ttu-id="4b559-244">Skärmlayout-id</span><span class="sxs-lookup"><span data-stu-id="4b559-244">Screen layout ID</span></span> | <span data-ttu-id="4b559-245">Person</span><span class="sxs-lookup"><span data-stu-id="4b559-245">Persona</span></span>          | <span data-ttu-id="4b559-246">Operatörs-ID</span><span class="sxs-lookup"><span data-stu-id="4b559-246">Operator IDs</span></span>           |
|-----------------|------------------|---------------   |------------------------|
| <span data-ttu-id="4b559-247">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-247">Adventure Works</span></span> | <span data-ttu-id="4b559-248">A3MGR</span><span class="sxs-lookup"><span data-stu-id="4b559-248">A3MGR</span></span>            | <span data-ttu-id="4b559-249">Butikschef</span><span class="sxs-lookup"><span data-stu-id="4b559-249">Store Manager</span></span>    | <span data-ttu-id="4b559-250">000154, 000137, 000073</span><span class="sxs-lookup"><span data-stu-id="4b559-250">000154, 000137, 000073</span></span> |
| <span data-ttu-id="4b559-251">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-251">Adventure Works</span></span> | <span data-ttu-id="4b559-252">A3CSH</span><span class="sxs-lookup"><span data-stu-id="4b559-252">A3CSH</span></span>            | <span data-ttu-id="4b559-253">Kassör</span><span class="sxs-lookup"><span data-stu-id="4b559-253">Cashier</span></span>          | <span data-ttu-id="4b559-254">000150, 000175, 000165</span><span class="sxs-lookup"><span data-stu-id="4b559-254">000150, 000175, 000165</span></span> |
| <span data-ttu-id="4b559-255">Adventure Works</span><span class="sxs-lookup"><span data-stu-id="4b559-255">Adventure Works</span></span> | <span data-ttu-id="4b559-256">A3STK</span><span class="sxs-lookup"><span data-stu-id="4b559-256">A3STK</span></span>            | <span data-ttu-id="4b559-257">Ansvarig för lager</span><span class="sxs-lookup"><span data-stu-id="4b559-257">Stock Clerk</span></span>      | <span data-ttu-id="4b559-258">000155, 000181, 000152</span><span class="sxs-lookup"><span data-stu-id="4b559-258">000155, 000181, 000152</span></span> |
| <span data-ttu-id="4b559-259">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-259">Fabrikam</span></span>        | <span data-ttu-id="4b559-260">F3MGR</span><span class="sxs-lookup"><span data-stu-id="4b559-260">F3MGR</span></span>            | <span data-ttu-id="4b559-261">Butikschef</span><span class="sxs-lookup"><span data-stu-id="4b559-261">Store Manager</span></span>    | <span data-ttu-id="4b559-262">000160, 000168, 000163</span><span class="sxs-lookup"><span data-stu-id="4b559-262">000160, 000168, 000163</span></span> |
| <span data-ttu-id="4b559-263">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-263">Fabrikam</span></span>        | <span data-ttu-id="4b559-264">F3CSH</span><span class="sxs-lookup"><span data-stu-id="4b559-264">F3CSH</span></span>            | <span data-ttu-id="4b559-265">Kassör</span><span class="sxs-lookup"><span data-stu-id="4b559-265">Cashier</span></span>          | <span data-ttu-id="4b559-266">000161, 000113, 000114</span><span class="sxs-lookup"><span data-stu-id="4b559-266">000161, 000113, 000114</span></span> |
| <span data-ttu-id="4b559-267">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="4b559-267">Fabrikam</span></span>        | <span data-ttu-id="4b559-268">F3STK</span><span class="sxs-lookup"><span data-stu-id="4b559-268">F3STK</span></span>            | <span data-ttu-id="4b559-269">Ansvarig för lager</span><span class="sxs-lookup"><span data-stu-id="4b559-269">Stock Clerk</span></span>      | <span data-ttu-id="4b559-270">000164, 000112, 000123</span><span class="sxs-lookup"><span data-stu-id="4b559-270">000164, 000112, 000123</span></span> |
| <span data-ttu-id="4b559-271">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-271">Contoso</span></span>         | <span data-ttu-id="4b559-272">C3MGR</span><span class="sxs-lookup"><span data-stu-id="4b559-272">C3MGR</span></span>            | <span data-ttu-id="4b559-273">Butikschef</span><span class="sxs-lookup"><span data-stu-id="4b559-273">Store Manager</span></span>    | <span data-ttu-id="4b559-274">000100, 000111</span><span class="sxs-lookup"><span data-stu-id="4b559-274">000100, 000111</span></span>         |
| <span data-ttu-id="4b559-275">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-275">Contoso</span></span>         | <span data-ttu-id="4b559-276">C3CSH</span><span class="sxs-lookup"><span data-stu-id="4b559-276">C3CSH</span></span>            | <span data-ttu-id="4b559-277">Kassör</span><span class="sxs-lookup"><span data-stu-id="4b559-277">Cashier</span></span>          | <span data-ttu-id="4b559-278">000110, 000120</span><span class="sxs-lookup"><span data-stu-id="4b559-278">000110, 000120</span></span>         |
| <span data-ttu-id="4b559-279">Contoso</span><span class="sxs-lookup"><span data-stu-id="4b559-279">Contoso</span></span>         | <span data-ttu-id="4b559-280">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4b559-280">Not applicable</span></span>   | <span data-ttu-id="4b559-281">Ansvarig för lager</span><span class="sxs-lookup"><span data-stu-id="4b559-281">Stock Clerk</span></span>      | <span data-ttu-id="4b559-282">Inte tillämpligt</span><span class="sxs-lookup"><span data-stu-id="4b559-282">Not applicable</span></span>         |


>[!TIP]
> <span data-ttu-id="4b559-283">För bästa resultat, aktivera ett register i motsvarande lagringsplats och ange vilket företag för den person som du tänker använda när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="4b559-283">For best results, activate a register in the corresponding store location, and set the company to the company of the persona that you plan to use when you sign in.</span></span> <span data-ttu-id="4b559-284">På så sätt kan du garantera den visuella profilen och varumärkesanpassade bilder är justerade genom erfarenheten.</span><span class="sxs-lookup"><span data-stu-id="4b559-284">In this way, you help guarantee that the visual profile and branding images are aligned across the experience.</span></span> <span data-ttu-id="4b559-285">Om du till exempel vill visa Fabrikam-layouten Fabrikam för en kassör, bör du aktivera en kassa i Houston-butiken.</span><span class="sxs-lookup"><span data-stu-id="4b559-285">For example, if you're interested in seeing a Fabrikam layout for a cashier, you should activate a register in the Houston store.</span></span>


<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail > Channel setup > POS setup > POS > Images**. -->

<!-- ![Images in Dynamics 365 for Retail](../retail/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../retail/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->

