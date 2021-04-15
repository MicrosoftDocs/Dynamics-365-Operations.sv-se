---
title: Modul för sidfot
description: Det här avsnittet innehåller moduler för sidfot och hur du redigerar dem i Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d6e7b0ad4fe0723575a0ec55a9b02d110568db58
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797243"
---
# <a name="footer-module"></a><span data-ttu-id="88d32-103">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="88d32-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="88d32-104">Det här avsnittet handlar om moduler för sidfot och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="88d32-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="88d32-105">Modulen för sidfot är en särskild behållare som används som värd för modulerna som visas i sidfoten.</span><span class="sxs-lookup"><span data-stu-id="88d32-105">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="88d32-106">Den kan till exempel innehålla länkar till olika sidor på webbplatsen, t.ex. sidorna **Kontakta oss** och **Butikspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="88d32-106">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="88d32-107">Följande bild visar ett exempel på en sidfotsmodul på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="88d32-107">The following image shows an example of a footer module on a site page.</span></span>

![Exempel på en sidfotsmodul](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties&quot;></a><span data-ttu-id=&quot;88d32-109&quot;>Egenskaper för moduler för sidfot</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-109&quot;>Footer module properties</span></span> 

<span data-ttu-id=&quot;88d32-110&quot;>Precis som i de flesta behållare har en modul för sidfot stöd för egenskaper för rubriker och bredd.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-110&quot;>Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id=&quot;88d32-111&quot;>Den stöder också att du lägger till flera kategorimoduler för sidfötter.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-111&quot;>It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id=&quot;88d32-112&quot;>Varje kategorimodul för sidfot som läggs till återges som en kolumn i modulen sidfot.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-112&quot;>Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name=&quot;modules-available-in-a-footer-module&quot;></a><span data-ttu-id=&quot;88d32-113&quot;>Moduler tillgängliga i en modul för sidfot</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-113&quot;>Modules available in a footer module</span></span>

<span data-ttu-id=&quot;88d32-114&quot;>**Sidfotsobjekt** – en modul för sidfotsobjekt kan innehålla en rubrik, en bild och en länk.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-114&quot;>**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id=&quot;88d32-115&quot;>Rubriken kan antingen användas separat eller tillsammans med en bild och en länk.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;88d32-115&quot;>The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id=&quot;88d32-116&quot;>Varje länk i sidfoten kan konfigureras så att den bara har text (t.ex. &quot;kontakta oss&quot; och &quot;sekretess") eller så att den har både text och bild (t.ex. sociala medielänkar).</span><span class="sxs-lookup"><span data-stu-id="88d32-116">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="88d32-117">**Tillbaka till början** – modulen Tillbaka till början innehåller en länk för snabb navigering till sidans övre del.</span><span class="sxs-lookup"><span data-stu-id="88d32-117">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="88d32-118">En destination måste anges.</span><span class="sxs-lookup"><span data-stu-id="88d32-118">A destination is required.</span></span> <span data-ttu-id="88d32-119">Standarddestinationen är \# vilket innebär att användaren kommer högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="88d32-119">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="88d32-120">Skapa en sidfotsmodul</span><span class="sxs-lookup"><span data-stu-id="88d32-120">Create a footer module</span></span>

1. <span data-ttu-id="88d32-121">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="88d32-121">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="88d32-122">I dialogrutan **Nytt fragment** väljer du modul för **Behållare**, anger ett namn på fragmentet och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d32-122">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="88d32-123">I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="88d32-123">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="88d32-124">I dialogrutan **Lägg till modul**, välj modulen **sidfotskategori** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d32-124">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="88d32-125">I facket **Sidfotskategori** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="88d32-125">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="88d32-126">I dialogrutan **Lägg till modul** välj modulen **sidfotsartikel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d32-126">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="88d32-127">Välj platsen **Sidfotskategori** och sedan i egenskapsrutan till höger konfigurerar du rubrik, länk och länktext och bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="88d32-127">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="88d32-128">Upprepa steg 5 till 7 om du vill lägga till fler sidfotsartiklar.</span><span class="sxs-lookup"><span data-stu-id="88d32-128">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="88d32-129">Om du vill lägga till länken "Tillbaka till början" väljer du ellipsknappen (**...**) i platsen **sidfotskategori** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="88d32-129">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="88d32-130">I dialogrutan **Lägg till modul**, välj modulen **Tillbaka till början** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d32-130">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="88d32-131">Välj platsen **Tillbaka till början** och sedan i egenskapsrutan till höger konfigurerar du text och andra modulegenskaper efter behov.</span><span class="sxs-lookup"><span data-stu-id="88d32-131">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="88d32-132">Välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera det.</span><span class="sxs-lookup"><span data-stu-id="88d32-132">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="88d32-133">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="88d32-133">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="88d32-134">På platsen **Sidfot** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.</span><span class="sxs-lookup"><span data-stu-id="88d32-134">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="88d32-135">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="88d32-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="88d32-136">Genom att lägga till fragment i sidmallar kan du säkerställa att sidfoten återges på varje sida.</span><span class="sxs-lookup"><span data-stu-id="88d32-136">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88d32-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88d32-137">Additional resources</span></span>

[<span data-ttu-id="88d32-138">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="88d32-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="88d32-139">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="88d32-139">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="88d32-140">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="88d32-140">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="88d32-141">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="88d32-141">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="88d32-142">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="88d32-142">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="88d32-143">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="88d32-143">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="88d32-144">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="88d32-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="88d32-145">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="88d32-145">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]