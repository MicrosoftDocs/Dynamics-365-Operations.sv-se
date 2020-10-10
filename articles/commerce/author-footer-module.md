---
title: Modul för sidfot
description: Det här avsnittet innehåller moduler för sidfot och hur du redigerar dem i Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 42a71ea9498461febca80952acc3158517918332
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3816971"
---
# <a name="footer-module"></a><span data-ttu-id="344a4-103">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="344a4-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="344a4-104">Det här avsnittet handlar om moduler för sidfot och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="344a4-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="344a4-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="344a4-105">Overview</span></span>

<span data-ttu-id="344a4-106">Modulen för sidfot är en särskild behållare som används som värd för modulerna som visas i sidfoten.</span><span class="sxs-lookup"><span data-stu-id="344a4-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="344a4-107">Den kan till exempel innehålla länkar till olika sidor på webbplatsen, t.ex. sidorna **Kontakta oss** och **Butikspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="344a4-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="344a4-108">Följande bild visar ett exempel på en sidfotsmodul på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="344a4-108">The following image shows an example of a footer module on a site page.</span></span>

![Exempel på en sidfotsmodul](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="344a4-110">Egenskaper för moduler för sidfot</span><span class="sxs-lookup"><span data-stu-id="344a4-110">Footer module properties</span></span> 

<span data-ttu-id="344a4-111">Precis som i de flesta behållare har en modul för sidfot stöd för egenskaper för rubriker och bredd.</span><span class="sxs-lookup"><span data-stu-id="344a4-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="344a4-112">Den stöder också att du lägger till flera kategorimoduler för sidfötter.</span><span class="sxs-lookup"><span data-stu-id="344a4-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="344a4-113">Varje kategorimodul för sidfot som läggs till återges som en kolumn i modulen sidfot.</span><span class="sxs-lookup"><span data-stu-id="344a4-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="344a4-114">Moduler tillgängliga i en modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="344a4-114">Modules available in a footer module</span></span>

<span data-ttu-id="344a4-115">**Sidfotsobjekt** – en modul för sidfotsobjekt kan innehålla en rubrik, en bild och en länk.</span><span class="sxs-lookup"><span data-stu-id="344a4-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="344a4-116">Rubriken kan antingen användas separat eller tillsammans med en bild och en länk.</span><span class="sxs-lookup"><span data-stu-id="344a4-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="344a4-117">Varje länk i sidfoten kan konfigureras så att den bara har text (t.ex. "kontakta oss" och "sekretess") eller så att den har både text och bild (t.ex. sociala medielänkar).</span><span class="sxs-lookup"><span data-stu-id="344a4-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="344a4-118">**Tillbaka till början** – modulen Tillbaka till början innehåller en länk för snabb navigering till sidans övre del.</span><span class="sxs-lookup"><span data-stu-id="344a4-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="344a4-119">En destination måste anges.</span><span class="sxs-lookup"><span data-stu-id="344a4-119">A destination is required.</span></span> <span data-ttu-id="344a4-120">Standarddestinationen är \# vilket innebär att användaren kommer högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="344a4-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="344a4-121">Skapa en sidfotsmodul</span><span class="sxs-lookup"><span data-stu-id="344a4-121">Create a footer module</span></span>

1. <span data-ttu-id="344a4-122">Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="344a4-122">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="344a4-123">I dialogrutan **Nytt fragment** väljer du modul för **Behållare**, anger ett namn på fragmentet och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="344a4-123">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="344a4-124">I facket **Standardbehållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="344a4-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="344a4-125">I dialogrutan **Lägg till modul**, välj modulen **sidfotskategori** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="344a4-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="344a4-126">I facket **Sidfotskategori** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="344a4-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="344a4-127">I dialogrutan **Lägg till modul** välj modulen **sidfotsartikel** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="344a4-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="344a4-128">Välj platsen **Sidfotskategori** och sedan i egenskapsrutan till höger konfigurerar du rubrik, länk och länktext och bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="344a4-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="344a4-129">Upprepa steg 5 till 7 om du vill lägga till fler sidfotsartiklar.</span><span class="sxs-lookup"><span data-stu-id="344a4-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="344a4-130">Om du vill lägga till länken "Tillbaka till början" väljer du ellipsknappen (**...**) i platsen **sidfotskategori** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="344a4-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="344a4-131">I dialogrutan **Lägg till modul**, välj modulen **Tillbaka till början** och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="344a4-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="344a4-132">Välj platsen **Tillbaka till början** och sedan i egenskapsrutan till höger konfigurerar du text och andra modulegenskaper efter behov.</span><span class="sxs-lookup"><span data-stu-id="344a4-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="344a4-133">Välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera det.</span><span class="sxs-lookup"><span data-stu-id="344a4-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="344a4-134">Om du vill garantera att ett sidhuvud visas på varje sida följer du stegen nedan för varje sidmall som skapas för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="344a4-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="344a4-135">På platsen **Sidfot** i modulen **standardsida** lägg till det sidfotsfragment som du skapade.</span><span class="sxs-lookup"><span data-stu-id="344a4-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="344a4-136">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="344a4-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="344a4-137">Genom att lägga till fragment i sidmallar kan du säkerställa att sidfoten återges på varje sida.</span><span class="sxs-lookup"><span data-stu-id="344a4-137">By adding the fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="344a4-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="344a4-138">Additional resources</span></span>

[<span data-ttu-id="344a4-139">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="344a4-139">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="344a4-140">Behållarmodul</span><span class="sxs-lookup"><span data-stu-id="344a4-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="344a4-141">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="344a4-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="344a4-142">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="344a4-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="344a4-143">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="344a4-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="344a4-144">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="344a4-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="344a4-145">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="344a4-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="344a4-146">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="344a4-146">Footer module</span></span>](author-footer-module.md)
