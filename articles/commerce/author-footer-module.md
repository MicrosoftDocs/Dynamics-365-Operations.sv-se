---
title: Modul för sidfot
description: Det här avsnittet innehåller moduler för sidfot och hur du redigerar dem i Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 04/14/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 51f8d26d6223dcd1f6961058cd9d772a67c69670
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269646"
---
# <a name="footer-module"></a><span data-ttu-id="7be28-103">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="7be28-103">Footer module</span></span>  


[!include [banner](includes/banner.md)]

<span data-ttu-id="7be28-104">Det här avsnittet handlar om moduler för sidfot och beskriver hur du skapar dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7be28-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7be28-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="7be28-105">Overview</span></span>

<span data-ttu-id="7be28-106">Modulen för sidfot är en särskild behållare som används som värd för modulerna som visas i sidfoten.</span><span class="sxs-lookup"><span data-stu-id="7be28-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="7be28-107">Den kan till exempel innehålla länkar till olika sidor på webbplatsen, t.ex. sidorna **Kontakta oss** och **Butikspolicyer**.</span><span class="sxs-lookup"><span data-stu-id="7be28-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="7be28-108">Egenskaper för moduler för sidfot</span><span class="sxs-lookup"><span data-stu-id="7be28-108">Footer module properties</span></span> 

<span data-ttu-id="7be28-109">Precis som i de flesta behållare har en modul för sidfot stöd för egenskaper för rubriker och bredd.</span><span class="sxs-lookup"><span data-stu-id="7be28-109">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="7be28-110">Den stöder också att du lägger till flera kategorimoduler för sidfötter.</span><span class="sxs-lookup"><span data-stu-id="7be28-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="7be28-111">Varje kategorimodul för sidfot som läggs till återges som en kolumn i modulen sidfot.</span><span class="sxs-lookup"><span data-stu-id="7be28-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="7be28-112">Moduler tillgängliga i en modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="7be28-112">Modules available in a footer module</span></span>

<span data-ttu-id="7be28-113">**Sidfotsobjekt** – en modul för sidfotsobjekt kan innehålla en rubrik, en bild och en länk.</span><span class="sxs-lookup"><span data-stu-id="7be28-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="7be28-114">Rubriken kan antingen användas separat eller tillsammans med en bild och en länk.</span><span class="sxs-lookup"><span data-stu-id="7be28-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="7be28-115">Varje länk i sidfoten kan konfigureras så att den bara har text (t.ex. "kontakta oss" och "sekretess") eller så att den har både text och bild (t.ex. sociala medielänkar).</span><span class="sxs-lookup"><span data-stu-id="7be28-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="7be28-116">**Tillbaka till början** – modulen Tillbaka till början innehåller en länk för snabb navigering till sidans övre del.</span><span class="sxs-lookup"><span data-stu-id="7be28-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="7be28-117">En destination måste anges.</span><span class="sxs-lookup"><span data-stu-id="7be28-117">A destination is required.</span></span> <span data-ttu-id="7be28-118">Standarddestinationen är #, vilket innebär att användaren kommer högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="7be28-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="7be28-119">Skriva en sidfotsmodul</span><span class="sxs-lookup"><span data-stu-id="7be28-119">Author a footer module</span></span>

1. <span data-ttu-id="7be28-120">I navigeringsfönstret, välj **fragment** och välj sedan **Nytt sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="7be28-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="7be28-121">I dialogrutan **Nytt sidfragment** väljer du modul för sidfot, anger ett namn på sidan och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7be28-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="7be28-122">I dispositionsträdet till vänster väljer du ellipsknappen (**...**) för modulen för sidfot och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="7be28-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="7be28-123">I dialogrutan **Lägg till modul**, välj modulen sidfotskategori och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7be28-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="7be28-124">I dispositionsträdet väljer du ellipsknappen (...) för modulen för sidfotskategori och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="7be28-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="7be28-125">I dialogrutan **Lägg till modul**, välj modulen sidfotsartikel och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7be28-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="7be28-126">Välj modul för sidfotsartikel i dispositionsträdet.</span><span class="sxs-lookup"><span data-stu-id="7be28-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="7be28-127">I egenskapsrutan till höger konfigurerar du rubrik, länk och länktext och bilden efter behov.</span><span class="sxs-lookup"><span data-stu-id="7be28-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="7be28-128">Upprepa steg 5 till 7 om du vill lägga till fler sidfotsartiklar.</span><span class="sxs-lookup"><span data-stu-id="7be28-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="7be28-129">Om du vill lägga till länken "Tillbaka till början" väljer du ellipsknappen (...) för modulen för sidfotskategori och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="7be28-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="7be28-130">I dialogrutan **Lägg till modul**, välj modulen Tillbaka till början och sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7be28-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="7be28-131">Välj modul för Tillbaka till början i dispositionsträdet.</span><span class="sxs-lookup"><span data-stu-id="7be28-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="7be28-132">Konfigurera sedan tillbaka till modulen Tillbaka till början i egenskapsfönstret till höger efter behov.</span><span class="sxs-lookup"><span data-stu-id="7be28-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="7be28-133">Välj **Spara**, välj **Slutför redigering** för att checka in sidfragmentet och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="7be28-133">Select **Save**, select **Finish editing** to check in the page fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="7be28-134">Gör följande för varje sidmall som har skapats för webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="7be28-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="7be28-135">Lägg till platsen **Huvud** för standardsidan i modulen för sidfot, lägg till det sidfotsfragment som du skapade.</span><span class="sxs-lookup"><span data-stu-id="7be28-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="7be28-136">Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="7be28-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="7be28-137">Genom att lägga till sidfragment i sidmallar kan du säkerställa att sidfoten återges på varje sida.</span><span class="sxs-lookup"><span data-stu-id="7be28-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7be28-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7be28-138">Additional resources</span></span>

[<span data-ttu-id="7be28-139">Översikt över startpaket</span><span class="sxs-lookup"><span data-stu-id="7be28-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="7be28-140">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="7be28-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="7be28-141">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="7be28-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="7be28-142">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="7be28-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7be28-143">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="7be28-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="7be28-144">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="7be28-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="7be28-145">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="7be28-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="7be28-146">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="7be28-146">Footer module</span></span>](author-footer-module.md)
