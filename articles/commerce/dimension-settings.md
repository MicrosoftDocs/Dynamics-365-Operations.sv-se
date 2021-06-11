---
title: Använd visningsinställningar för produktdimensioner
description: I det här avsnittet beskrivs visningsinställningarna för produktdimensioner och hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117247"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="43ad4-103">Använd visningsinställningar för produktdimensioner</span><span class="sxs-lookup"><span data-stu-id="43ad4-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="43ad4-104">I det här avsnittet beskrivs visningsinställningarna för produktdimensioner och hur du använder dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43ad4-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="43ad4-105">Dynamics 365 Commerce stöder dimensioner för storlek, utförande och färg för att särskilja produktvarianter.</span><span class="sxs-lookup"><span data-stu-id="43ad4-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="43ad4-106">Dimensioner visas vanligtvis som textvärden, till exempel "Small", "Medium" och "Large" för storlekar, och "Svart" och "Brunt" för färger.</span><span class="sxs-lookup"><span data-stu-id="43ad4-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="43ad4-107">Om en produkt stöder många variationer kan det dock vara svårt att bläddra bland produktvarianter, eftersom flera val krävs för att visa bilden för varje variant.</span><span class="sxs-lookup"><span data-stu-id="43ad4-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="43ad4-108">För att göra det enklare att bläddra i produktvarianter kan version 10.0.20-versionen av Commerce använda bilder och hexadecimala (hex)-koder för att visa dimensioner som tum.</span><span class="sxs-lookup"><span data-stu-id="43ad4-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="43ad4-109">I Commerce-webbplatsskaparen, definieras inställningar på **Platsinställningar \> Tillägg \> Dimensionsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="43ad4-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="43ad4-110">I följande bild visas ett exempel på dimensionsinställningar i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="43ad4-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Exempel på siteinställningar i Commerce webbplatsskaparen](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="43ad4-112">Det finns två dimensionsinställningar:</span><span class="sxs-lookup"><span data-stu-id="43ad4-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="43ad4-113">**Dimensioner som ska visas som bild** – Ange vilka dimensioner som ska visas som färgrutor på sidor med e-handelswebbplatser, t.ex. produktinformationssidor (PDP) och listor med sökresultat.</span><span class="sxs-lookup"><span data-stu-id="43ad4-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="43ad4-114">Alla kombinationer av färg, storlek och stildimensioner kan visas som en färgruta.</span><span class="sxs-lookup"><span data-stu-id="43ad4-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="43ad4-115">Om en dimension har valts för visning som en färgruta, kommer återgivning av Commerce-modul att leta efter en tillgänglig konfiguration av en hexkodsfärg.</span><span class="sxs-lookup"><span data-stu-id="43ad4-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="43ad4-116">Om ingen hexkod konfigureras söker systemlogiken efter en konfiguration av en bild-URL konfiguration.</span><span class="sxs-lookup"><span data-stu-id="43ad4-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="43ad4-117">Text visas om varken en hexkod eller en URL för bilden har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="43ad4-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="43ad4-118">I följande bild visas ett exempel där en PDP på en e-handelswebbplats innehåller färg- och storleksrutor.</span><span class="sxs-lookup"><span data-stu-id="43ad4-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="43ad4-119">I det här exemplet konfigureras en hexkod för färgdimensionen.</span><span class="sxs-lookup"><span data-stu-id="43ad4-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="43ad4-120">Därför visas färgrutor som färger.</span><span class="sxs-lookup"><span data-stu-id="43ad4-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="43ad4-121">Det går dock att konfigurera varken en hexkod eller en bild-URL för storleksdimensionen.</span><span class="sxs-lookup"><span data-stu-id="43ad4-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="43ad4-122">Därför visas text.</span><span class="sxs-lookup"><span data-stu-id="43ad4-122">Therefore, text is shown.</span></span>

    ![Exempel på färgdimensionen som visas som tum på en detaljsida för e-handelprodukt](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="43ad4-124">**Dimensioner som ska visas på produktkort** – Ange vilka dimensioner som ska visas på produktkort som visas i listor och på listsidor.</span><span class="sxs-lookup"><span data-stu-id="43ad4-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="43ad4-125">Innan en dimension kan visas på ett produktkort måste den här inställningen vara aktiverad för den dimensionen.</span><span class="sxs-lookup"><span data-stu-id="43ad4-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="43ad4-126">Även inställningen **dimensionerna som ska visas som bild** bör vara aktiverade.</span><span class="sxs-lookup"><span data-stu-id="43ad4-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="43ad4-127">Urvalssättet för färgrutor för produktkort optimeras för färgdimensionen.</span><span class="sxs-lookup"><span data-stu-id="43ad4-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="43ad4-128">För andra dimensioner kan det krävas ett visningstillägg för att anpassa urvalsbeteendet.</span><span class="sxs-lookup"><span data-stu-id="43ad4-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="43ad4-129">I följande bild visas ett exempel där en listsida på en e-handelsplats innehåller produktkort som innehåller färgrutor.</span><span class="sxs-lookup"><span data-stu-id="43ad4-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Exempel på färgdimensionen som visas som tum på en listsida för e-handel](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="43ad4-131">Mer information om hur du konfigurerar produktdimensioner så att de visas som färgrutor på webbplatssidor finns i [Konfigurera produktdimensionsvärden så att de visas som färgrutor](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="43ad4-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43ad4-132">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="43ad4-132">Additional resources</span></span>

[<span data-ttu-id="43ad4-133">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="43ad4-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="43ad4-134">Sökresultatmodul</span><span class="sxs-lookup"><span data-stu-id="43ad4-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="43ad4-135">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="43ad4-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="43ad4-136">Konfigurera värden för produktdimensioner som ska visas som färgrutor</span><span class="sxs-lookup"><span data-stu-id="43ad4-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
