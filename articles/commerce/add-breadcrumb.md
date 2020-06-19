---
title: Modulen för navigeringssökväg
description: Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1c6d846686e3214e976a55271694382d7c5973ed
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417402"
---
# <a name="breadcrumb-module"></a><span data-ttu-id="2558a-103">Modulen för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="2558a-103">Breadcrumb module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2558a-104">Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2558a-104">This topic covers breadcrumb modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2558a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="2558a-105">Overview</span></span>

<span data-ttu-id="2558a-106">Med hjälp av moduler för navigeringssökväg navigering kan du navigera på webbplatssidorna.</span><span class="sxs-lookup"><span data-stu-id="2558a-106">Breadcrumb modules are used to provide secondary navigation on site pages.</span></span> <span data-ttu-id="2558a-107">De visas vanligtvis längst upp på sidan, under rubriken.</span><span class="sxs-lookup"><span data-stu-id="2558a-107">They are typically shown at the top of a page, below the header.</span></span> <span data-ttu-id="2558a-108">Även om det går att lägga till moduler för navigeringssökväg på en sida, används de oftast på produktinformationssidor (PDP), för att visa produktkategorihierarki och ett snabbt sätt att flytta runt på en webbplats.</span><span class="sxs-lookup"><span data-stu-id="2558a-108">Although breadcrumb modules can be added to any page, they are most often used on product details pages (PDPs), to show the product category hierarchy and provide a quick way to move around a site.</span></span> <span data-ttu-id="2558a-109">En modul för navigeringssökväg kan också användas för att visa länken "tillbaka till resultat" när användaren öppnar ett PDP från en sökning eller en listsida.</span><span class="sxs-lookup"><span data-stu-id="2558a-109">A breadcrumb module can also be used to show a "Back to results" link when users open a PDP from a search or list page.</span></span> <span data-ttu-id="2558a-110">På så sätt kan användarna snabbt gå tillbaka till deras filtrerade listsidor och fortsätta handla.</span><span class="sxs-lookup"><span data-stu-id="2558a-110">In this way, users can quickly return to their filtered list page to continue shopping.</span></span>

<span data-ttu-id="2558a-111">På sidor som har produktkategorikontext, t.ex. PDP och kategorisidor, visar modulerna för navigeringssökväg kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="2558a-111">On pages that have product category context, such as PDPs and category pages, breadcrumb modules show the category hierarchy.</span></span> <span data-ttu-id="2558a-112">På sidor som inte har kategorikontext visar moduler för navigeringssökväg **&lt;webbplatsens rot&gt; / &lt;aktuell sida&gt;** som standard.</span><span class="sxs-lookup"><span data-stu-id="2558a-112">On pages that don't have category context, breadcrumb modules show **&lt;Site root&gt; / &lt;Current page&gt;** by default.</span></span> <span data-ttu-id="2558a-113">Moduler för navigeringssökväg kan också konfigureras manuellt på andra typer av webbplatssidor för att visa länkar till specifika sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2558a-113">Breadcrumb modules can also be manually configured on other types of site pages to show links to specific pages on the site.</span></span>

<span data-ttu-id="2558a-114">Följande bild visar ett exempel på en modul för navigeringssökväg som visar kategorihierarkin på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="2558a-114">The following image shows an example of a breadcrumb module that shows the category hierarchy on a PDP.</span></span>

![Exempel på en modulen för navigeringssökväg](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a><span data-ttu-id="2558a-116">Inställningar för moduler för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="2558a-116">Breadcrumb module settings</span></span>

<span data-ttu-id="2558a-117">Modulen för navigeringssökväg är beroende av inställningen **navigeringssökväg displaytyp på PDP** som definieras i **Webbplatsinställningar \> Tillägg** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="2558a-117">The breadcrumb module relies on the **Breadcrumb display type on PDP** setting, which is defined at **Site Settings \> Extensions** in site builder.</span></span> <span data-ttu-id="2558a-118">Den här inställningen har tre möjliga värden:</span><span class="sxs-lookup"><span data-stu-id="2558a-118">This setting has three possible values:</span></span>

- <span data-ttu-id="2558a-119">**Visa kategorihierarki** – när det här värdet väljs visar den fullständiga kategorihierarkin för produkten som visas på PDP i modulen för dynamiska länkar.</span><span class="sxs-lookup"><span data-stu-id="2558a-119">**Show category hierarchy** – When this value is selected, the breadcrumb module will show the full category hierarchy of the product that is viewed on the PDP.</span></span>
- <span data-ttu-id="2558a-120">**Visa tillbaka till resultat** – när det här värdet väljs visas länken "tillbaka till resultat" på ett PDP om användaren har öppnat PDP från en modul där det går att använda länken "tillbaka till resultat".</span><span class="sxs-lookup"><span data-stu-id="2558a-120">**Show back to results** – When this value is selected, the breadcrumb module will show a "Back to results" link on a PDP if the user opened the PDP from a module that allows for a "Back to results" link.</span></span> <span data-ttu-id="2558a-121">Den här funktionen är tillgänglig när användare navigerar på sidorna kategori, sökning, lista och rekommendationslistor.</span><span class="sxs-lookup"><span data-stu-id="2558a-121">This functionality is available when users navigate from category, search, list, and recommendation lists pages.</span></span> <span data-ttu-id="2558a-122">För att stödja den här funktionen har modulerna för produktsamling och sökresultat en egenskap med namnet **Tillåt tillbaka till resultaten på PDP**.</span><span class="sxs-lookup"><span data-stu-id="2558a-122">To support this functionality, product collection and search results modules have a property that is named **Allow back to results on PDP**.</span></span> <span data-ttu-id="2558a-123">Den här egenskapen ger dig flexibiliteten att definiera vilka moduler som ska stödja länkfunktionen "tillbaka till resultat" i PDP.</span><span class="sxs-lookup"><span data-stu-id="2558a-123">This property gives you the flexibility to define which modules should support the "Back to results" link functionality on the PDP.</span></span> <span data-ttu-id="2558a-124">Till exempel när **Visa tillbaka till resultat** har valts som inställning på **navigeringssökväg displaytyp på PDP** i modulen för navigeringssökväg och **Tillåt tillbaka till resultat på PDP** är vald för sökresultatmodulen för sökningssidan, en "Tillbaka till resultat"-länk visas när användare navigerar från söksidan till en PDP.</span><span class="sxs-lookup"><span data-stu-id="2558a-124">For example, when **Show back to results** is selected for the **Breadcrumb display type on PDP** setting of the breadcrumb module, and **Allow back to results on PDP** is selected for the search page search results module, a "Back to results" link will be shown when users navigate from the search page to a PDP.</span></span>
- <span data-ttu-id="2558a-125">**Visa kategorihierarki och tillbaka till resultat** – detta värde är en kombination av de föregående två.</span><span class="sxs-lookup"><span data-stu-id="2558a-125">**Show category hierarchy and back to results** – This value is a combination of the previous two.</span></span> <span data-ttu-id="2558a-126">När det här värdet väljs visas både den fullständiga kategorihierarkin och länken "tillbaka till resultat" (om den har konfigurerats) på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="2558a-126">When this value is selected, the breadcrumb module will show both the full category hierarchy and a "Back to results" link (if it's configured) on a PDP.</span></span>

## <a name="breadcrumb-module-properties"></a><span data-ttu-id="2558a-127">Egenskaper för modulen för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="2558a-127">Breadcrumb module properties</span></span>

| <span data-ttu-id="2558a-128">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="2558a-128">Property name</span></span> | <span data-ttu-id="2558a-129">Värden</span><span class="sxs-lookup"><span data-stu-id="2558a-129">Values</span></span> | <span data-ttu-id="2558a-130">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2558a-130">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="2558a-131">Rot</span><span class="sxs-lookup"><span data-stu-id="2558a-131">Root</span></span> | <span data-ttu-id="2558a-132">Text eller länk</span><span class="sxs-lookup"><span data-stu-id="2558a-132">Text or link</span></span>| <span data-ttu-id="2558a-133">Den här valfria egenskapen anger länktext och ett länkmål för navigeringssökvägens webbplatsrot.</span><span class="sxs-lookup"><span data-stu-id="2558a-133">This optional property specifies link text and a link target for the breadcrumb site root.</span></span> <span data-ttu-id="2558a-134">Om den här egenskapen inte har konfigurerats kommer ingen rot att definieras.</span><span class="sxs-lookup"><span data-stu-id="2558a-134">If this property isn't configured, no root will be defined.</span></span> |
| <span data-ttu-id="2558a-135">Länk till navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="2558a-135">Breadcrumb link</span></span> | <span data-ttu-id="2558a-136">Länka</span><span class="sxs-lookup"><span data-stu-id="2558a-136">Link</span></span> | <span data-ttu-id="2558a-137">Den här valfria egenskapen anger länkar för en manuellt konfigurerad dynamiska länk, om dessa länkar behövs.</span><span class="sxs-lookup"><span data-stu-id="2558a-137">This optional property specifies links for a manually configured breadcrumb, if these links are required.</span></span> <span data-ttu-id="2558a-138">Länkarna visas i angiven ordning i.</span><span class="sxs-lookup"><span data-stu-id="2558a-138">Links appear in the order that they are listed in.</span></span> |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a><span data-ttu-id="2558a-139">Lägg till en modul för navigeringssökväg på en ny sida</span><span class="sxs-lookup"><span data-stu-id="2558a-139">Add a breadcrumb module to a new page</span></span>

<span data-ttu-id="2558a-140">Om du vill lägga till en modul för navigeringssökväg till en PDP och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="2558a-140">To add a breadcrumb module to a PDP and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="2558a-141">Gå till **webbplatsinställningar /> tillägg** och för den **navigeringssökväg displaytyp på PDP**-inställningen väljer du **Visa kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="2558a-141">Go to **Site Settings /> Extensions**, and then, for the **Breadcrumb display type on PDP** setting, select **Show category hierarchy**.</span></span>
1. <span data-ttu-id="2558a-142">Gå till **mallar** och välj PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="2558a-142">Go to **Templates**, and select the PDP template.</span></span>
1. <span data-ttu-id="2558a-143">I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2558a-143">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2558a-144">I dialogrutan **Lägg till modul**, välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2558a-144">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2558a-145">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="2558a-145">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="2558a-146">Gå till **sidor** och öppna en PDP som använder PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="2558a-146">Go to **Pages**, and open a PDP that uses the PDP template.</span></span> <span data-ttu-id="2558a-147">Om det ännu inte finns något PDP skapar du ett.</span><span class="sxs-lookup"><span data-stu-id="2558a-147">If a PDP doesn't yet exist, create one.</span></span>
1. <span data-ttu-id="2558a-148">I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="2558a-148">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2558a-149">I dialogrutan **Lägg till modul**, välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="2558a-149">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2558a-150">I egenskapsrutan för platsen **Navigeringssökväg**, under **Rot**, välj **Länktext**.</span><span class="sxs-lookup"><span data-stu-id="2558a-150">In the properties pane of the **Breadcrumb** slot, under **Root**, select **Link text**.</span></span>
1. <span data-ttu-id="2558a-151">I dialogrutan **Länktext** ange **Start** och sedan under **Länkmål**, välj **Lägg till en länk**.</span><span class="sxs-lookup"><span data-stu-id="2558a-151">In the **Link text** dialog box, enter **Home**, and then, under **Link target**, select **Add a link**.</span></span>
1. <span data-ttu-id="2558a-152">I dialogrutan **Lägg till en länk** väljer du länken för roten för navigeringssökväg och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="2558a-152">In the **Add a link** dialog box, select a link for the breadcrumb root, and then select **OK**.</span></span>
1. <span data-ttu-id="2558a-153">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="2558a-153">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="2558a-154">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="2558a-154">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2558a-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2558a-155">Additional resources</span></span>

[<span data-ttu-id="2558a-156">Startpaket – översikt</span><span class="sxs-lookup"><span data-stu-id="2558a-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2558a-157">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="2558a-157">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="2558a-158">Produktsamlingsmoduler</span><span class="sxs-lookup"><span data-stu-id="2558a-158">Product collection modules</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="2558a-159">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="2558a-159">Buy box module</span></span>](add-buy-box.md)
