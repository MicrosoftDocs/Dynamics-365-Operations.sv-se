---
title: Modulen för navigeringssökväg
description: Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.openlocfilehash: 05e8614f53db2593ade92fdb42dc0dfe869e9407
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055414"
---
# <a name="breadcrumb-module"></a><span data-ttu-id="02a51-103">Modulen för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="02a51-103">Breadcrumb module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02a51-104">Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02a51-104">This topic covers breadcrumb modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="02a51-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="02a51-105">Overview</span></span>

<span data-ttu-id="02a51-106">Med hjälp av moduler för navigeringssökväg navigering kan du navigera på webbplatssidorna.</span><span class="sxs-lookup"><span data-stu-id="02a51-106">Breadcrumb modules are used to provide secondary navigation on site pages.</span></span> <span data-ttu-id="02a51-107">De visas vanligtvis längst upp på sidan, under rubriken.</span><span class="sxs-lookup"><span data-stu-id="02a51-107">They are typically shown at the top of a page, below the header.</span></span> <span data-ttu-id="02a51-108">Även om det går att lägga till moduler för navigeringssökväg på en sida, används de oftast på produktinformationssidor (PDP), för att visa produktkategorihierarki och ett snabbt sätt att flytta runt på en webbplats.</span><span class="sxs-lookup"><span data-stu-id="02a51-108">Although breadcrumb modules can be added to any page, they are most often used on product details pages (PDPs), to show the product category hierarchy and provide a quick way to move around a site.</span></span> <span data-ttu-id="02a51-109">En modul för navigeringssökväg kan också användas för att visa länken "tillbaka till resultat" när användaren öppnar ett PDP från en sökning eller en listsida.</span><span class="sxs-lookup"><span data-stu-id="02a51-109">A breadcrumb module can also be used to show a "Back to results" link when users open a PDP from a search or list page.</span></span> <span data-ttu-id="02a51-110">På så sätt kan användarna snabbt gå tillbaka till deras filtrerade listsidor och fortsätta handla.</span><span class="sxs-lookup"><span data-stu-id="02a51-110">In this way, users can quickly return to their filtered list page to continue shopping.</span></span>

<span data-ttu-id="02a51-111">På sidor som har produktkategorikontext, t.ex. PDP och kategorisidor, visar modulerna för navigeringssökväg kategorihierarkin.</span><span class="sxs-lookup"><span data-stu-id="02a51-111">On pages that have product category context, such as PDPs and category pages, breadcrumb modules show the category hierarchy.</span></span> <span data-ttu-id="02a51-112">På sidor som inte har kategorikontext visar moduler för navigeringssökväg **&lt;webbplatsens rot&gt; / &lt;aktuell sida&gt;** som standard.</span><span class="sxs-lookup"><span data-stu-id="02a51-112">On pages that don't have category context, breadcrumb modules show **&lt;Site root&gt; / &lt;Current page&gt;** by default.</span></span> <span data-ttu-id="02a51-113">Moduler för navigeringssökväg kan också konfigureras manuellt på andra typer av webbplatssidor för att visa länkar till specifika sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="02a51-113">Breadcrumb modules can also be manually configured on other types of site pages to show links to specific pages on the site.</span></span>

> [!NOTE]
> <span data-ttu-id="02a51-114">Den dynamiska modulen är tillgänglig i Dynamics 365 Commerce 10.0.12-versionen.</span><span class="sxs-lookup"><span data-stu-id="02a51-114">The breadcrumb module is available in the Dynamics 365 Commerce 10.0.12 release.</span></span>

<span data-ttu-id="02a51-115">Följande bild visar ett exempel på en modul för navigeringssökväg som visar kategorihierarkin på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="02a51-115">The following image shows an example of a breadcrumb module that shows the category hierarchy on a PDP.</span></span>

![Exempel på en modulen för navigeringssökväg](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a><span data-ttu-id="02a51-117">Inställningar för moduler för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="02a51-117">Breadcrumb module settings</span></span>

<span data-ttu-id="02a51-118">Modulen för navigeringssökväg är beroende av inställningen **navigeringssökväg displaytyp på PDP** som definieras i **Webbplatsinställningar \> Tillägg** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="02a51-118">The breadcrumb module relies on the **Breadcrumb display type on PDP** setting, which is defined at **Site Settings \> Extensions** in site builder.</span></span> <span data-ttu-id="02a51-119">Den här inställningen har tre möjliga värden:</span><span class="sxs-lookup"><span data-stu-id="02a51-119">This setting has three possible values:</span></span>

- <span data-ttu-id="02a51-120">**Visa kategorihierarki** – när det här värdet väljs visar den fullständiga kategorihierarkin för produkten som visas på PDP i modulen för dynamiska länkar.</span><span class="sxs-lookup"><span data-stu-id="02a51-120">**Show category hierarchy** – When this value is selected, the breadcrumb module will show the full category hierarchy of the product that is viewed on the PDP.</span></span>
- <span data-ttu-id="02a51-121">**Visa tillbaka till resultat** – när det här värdet väljs visas länken "tillbaka till resultat" på ett PDP om användaren har öppnat PDP från en modul där det går att använda länken "tillbaka till resultat".</span><span class="sxs-lookup"><span data-stu-id="02a51-121">**Show back to results** – When this value is selected, the breadcrumb module will show a "Back to results" link on a PDP if the user opened the PDP from a module that allows for a "Back to results" link.</span></span> <span data-ttu-id="02a51-122">Den här funktionen är tillgänglig när användare navigerar på sidorna kategori, sökning, lista och rekommendationslistor.</span><span class="sxs-lookup"><span data-stu-id="02a51-122">This functionality is available when users navigate from category, search, list, and recommendation lists pages.</span></span> <span data-ttu-id="02a51-123">För att stödja den här funktionen har modulerna för produktsamling och sökresultat en egenskap med namnet **Tillåt tillbaka till resultaten på PDP**.</span><span class="sxs-lookup"><span data-stu-id="02a51-123">To support this functionality, product collection and search results modules have a property that is named **Allow back to results on PDP**.</span></span> <span data-ttu-id="02a51-124">Den här egenskapen ger dig flexibiliteten att definiera vilka moduler som ska stödja länkfunktionen "tillbaka till resultat" i PDP.</span><span class="sxs-lookup"><span data-stu-id="02a51-124">This property gives you the flexibility to define which modules should support the "Back to results" link functionality on the PDP.</span></span> <span data-ttu-id="02a51-125">Till exempel när **Visa tillbaka till resultat** har valts som inställning på **navigeringssökväg displaytyp på PDP** i modulen för navigeringssökväg och **Tillåt tillbaka till resultat på PDP** är vald för sökresultatmodulen för sökningssidan, en "Tillbaka till resultat"-länk visas när användare navigerar från söksidan till en PDP.</span><span class="sxs-lookup"><span data-stu-id="02a51-125">For example, when **Show back to results** is selected for the **Breadcrumb display type on PDP** setting of the breadcrumb module, and **Allow back to results on PDP** is selected for the search page search results module, a "Back to results" link will be shown when users navigate from the search page to a PDP.</span></span>
- <span data-ttu-id="02a51-126">**Visa kategorihierarki och tillbaka till resultat** – detta värde är en kombination av de föregående två.</span><span class="sxs-lookup"><span data-stu-id="02a51-126">**Show category hierarchy and back to results** – This value is a combination of the previous two.</span></span> <span data-ttu-id="02a51-127">När det här värdet väljs visas både den fullständiga kategorihierarkin och länken "tillbaka till resultat" (om den har konfigurerats) på ett PDP.</span><span class="sxs-lookup"><span data-stu-id="02a51-127">When this value is selected, the breadcrumb module will show both the full category hierarchy and a "Back to results" link (if it's configured) on a PDP.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02a51-128">Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen.</span><span class="sxs-lookup"><span data-stu-id="02a51-128">These settings are available in the Dynamics 365 Commerce 10.0.12 release.</span></span> <span data-ttu-id="02a51-129">Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt.</span><span class="sxs-lookup"><span data-stu-id="02a51-129">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="02a51-130">Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="02a51-130">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span>

## <a name="breadcrumb-module-properties"></a><span data-ttu-id="02a51-131">Egenskaper för modulen för navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="02a51-131">Breadcrumb module properties</span></span>

| <span data-ttu-id="02a51-132">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="02a51-132">Property name</span></span> | <span data-ttu-id="02a51-133">Värden</span><span class="sxs-lookup"><span data-stu-id="02a51-133">Values</span></span> | <span data-ttu-id="02a51-134">beskrivning</span><span class="sxs-lookup"><span data-stu-id="02a51-134">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="02a51-135">Rot</span><span class="sxs-lookup"><span data-stu-id="02a51-135">Root</span></span> | <span data-ttu-id="02a51-136">Text eller länk</span><span class="sxs-lookup"><span data-stu-id="02a51-136">Text or link</span></span>| <span data-ttu-id="02a51-137">Den här valfria egenskapen anger länktext och ett länkmål för navigeringssökvägens webbplatsrot.</span><span class="sxs-lookup"><span data-stu-id="02a51-137">This optional property specifies link text and a link target for the breadcrumb site root.</span></span> <span data-ttu-id="02a51-138">Om den här egenskapen inte har konfigurerats kommer ingen rot att definieras.</span><span class="sxs-lookup"><span data-stu-id="02a51-138">If this property isn't configured, no root will be defined.</span></span> |
| <span data-ttu-id="02a51-139">Länk till navigeringssökväg</span><span class="sxs-lookup"><span data-stu-id="02a51-139">Breadcrumb link</span></span> | <span data-ttu-id="02a51-140">Länka</span><span class="sxs-lookup"><span data-stu-id="02a51-140">Link</span></span> | <span data-ttu-id="02a51-141">Den här valfria egenskapen anger länkar för en manuellt konfigurerad dynamiska länk, om dessa länkar behövs.</span><span class="sxs-lookup"><span data-stu-id="02a51-141">This optional property specifies links for a manually configured breadcrumb, if these links are required.</span></span> <span data-ttu-id="02a51-142">Länkarna visas i angiven ordning i.</span><span class="sxs-lookup"><span data-stu-id="02a51-142">Links appear in the order that they are listed in.</span></span> |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a><span data-ttu-id="02a51-143">Lägg till en modul för navigeringssökväg på en ny sida</span><span class="sxs-lookup"><span data-stu-id="02a51-143">Add a breadcrumb module to a new page</span></span>

<span data-ttu-id="02a51-144">Om du vill lägga till en modul för navigeringssökväg till en PDP och ställa in de obligatoriska egenskaperna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02a51-144">To add a breadcrumb module to a PDP and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="02a51-145">Gå till **webbplatsinställningar /> tillägg** och för den **navigeringssökväg displaytyp på PDP** -inställningen väljer du **Visa kategorihierarki**.</span><span class="sxs-lookup"><span data-stu-id="02a51-145">Go to **Site Settings /> Extensions** , and then, for the **Breadcrumb display type on PDP** setting, select **Show category hierarchy**.</span></span>
1. <span data-ttu-id="02a51-146">Gå till **mallar** och välj PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="02a51-146">Go to **Templates** , and select the PDP template.</span></span>
1. <span data-ttu-id="02a51-147">I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen ( **...** ) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="02a51-147">In the **Container** slot that contains the buy box module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="02a51-148">I dialogrutan **Lägg till modul** , välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a51-148">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="02a51-149">Välj **Spara** , välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="02a51-149">Select **Save** , select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="02a51-150">Gå till **sidor** och öppna en PDP som använder PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="02a51-150">Go to **Pages** , and open a PDP that uses the PDP template.</span></span> <span data-ttu-id="02a51-151">Om det ännu inte finns något PDP skapar du ett.</span><span class="sxs-lookup"><span data-stu-id="02a51-151">If a PDP doesn't yet exist, create one.</span></span>
1. <span data-ttu-id="02a51-152">I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen ( **...** ) och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="02a51-152">In the **Container** slot that contains the buy box module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="02a51-153">I dialogrutan **Lägg till modul** , välj modulen **navigeringssökväg** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a51-153">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="02a51-154">I egenskapsrutan för platsen **Navigeringssökväg** , under **Rot** , välj **Länktext**.</span><span class="sxs-lookup"><span data-stu-id="02a51-154">In the properties pane of the **Breadcrumb** slot, under **Root** , select **Link text**.</span></span>
1. <span data-ttu-id="02a51-155">I dialogrutan **Länktext** ange **Start** och sedan under **Länkmål** , välj **Lägg till en länk**.</span><span class="sxs-lookup"><span data-stu-id="02a51-155">In the **Link text** dialog box, enter **Home** , and then, under **Link target** , select **Add a link**.</span></span>
1. <span data-ttu-id="02a51-156">I dialogrutan **Lägg till en länk** väljer du länken för roten för navigeringssökväg och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a51-156">In the **Add a link** dialog box, select a link for the breadcrumb root, and then select **OK**.</span></span>
1. <span data-ttu-id="02a51-157">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="02a51-157">Select **Save** , and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="02a51-158">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="02a51-158">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02a51-159">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="02a51-159">Additional resources</span></span>

[<span data-ttu-id="02a51-160">Modulbibliotek – översikt</span><span class="sxs-lookup"><span data-stu-id="02a51-160">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="02a51-161">Modul för navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="02a51-161">Navigation menu module</span></span>](nav-menu-module.md)

[<span data-ttu-id="02a51-162">Modul för webbplatsväljare</span><span class="sxs-lookup"><span data-stu-id="02a51-162">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="02a51-163">Översikt över standardkategorilandningssida och sida för sökresultat</span><span class="sxs-lookup"><span data-stu-id="02a51-163">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="02a51-164">Produktsamlingsmoduler</span><span class="sxs-lookup"><span data-stu-id="02a51-164">Product collection modules</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="02a51-165">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="02a51-165">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="02a51-166">Uppdateringar av SDK och modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="02a51-166">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)
