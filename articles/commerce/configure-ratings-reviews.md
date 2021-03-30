---
title: Konfigurera omdömen och recensioner
description: I det här avsnittet beskrivs hur du konfigurerar din näthandelssajt så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 130c80c1d68c7fb207a4fa073fe2b0476cbdd409
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220544"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="6f626-103">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="6f626-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f626-104">I det här avsnittet beskrivs hur du konfigurerar din näthandelssajt så att du kan visa kundomdömen och recensioner i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f626-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6f626-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="6f626-105">Overview</span></span>

<span data-ttu-id="6f626-106">Omdömen och recensioner på webbplatser för näthandel hjälper kunder lära sig mer om produkter innan de fattar ett inköpsbeslut, genom att visa vad andra kunder tycker om dessa produkter.</span><span class="sxs-lookup"><span data-stu-id="6f626-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="6f626-107">För näthandelssajter är omdömen och recensioner också en mekanism för att samla in kundernas feedback om produkter.</span><span class="sxs-lookup"><span data-stu-id="6f626-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="6f626-108">Konfigurera en webbplats att visa omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="6f626-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="6f626-109">Konfigurationsvärden för omdömen och recensioner, till exempel innehavar-ID, granska textlängd och granska rubriklängd, konfigureras på webbplatsnivå.</span><span class="sxs-lookup"><span data-stu-id="6f626-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="6f626-110">Konfigurera en webbplats för visning av värderingar och recensioner enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="6f626-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="6f626-111">Gå till **Start \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="6f626-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="6f626-112">Välj namnet på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6f626-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="6f626-113">Gå till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="6f626-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="6f626-114">I fältet **granska textens maxlängd** anger du det maximala antalet tecken som ska granska text kan ha (t.ex. **1000**).</span><span class="sxs-lookup"><span data-stu-id="6f626-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="6f626-115">I fältet **granska rubrikens maxlängd** anger du det maximala antalet tecken som ska granska rubriker kan ha (t.ex. **55**).</span><span class="sxs-lookup"><span data-stu-id="6f626-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="6f626-116">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="6f626-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="6f626-117">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f626-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurera en webbplats att visa omdömen och recensioner](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="6f626-119">Länka en produktvärdering till avsnittet recensioner i ett PDP</span><span class="sxs-lookup"><span data-stu-id="6f626-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="6f626-120">En produktvärdering visas under produktrubriken högst upp i PDP.</span><span class="sxs-lookup"><span data-stu-id="6f626-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="6f626-121">Produktvärderingen kan konfigureras så att den länkas till avsnittet **recensioner** i samma PDP.</span><span class="sxs-lookup"><span data-stu-id="6f626-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="6f626-122">Om du vill länka en produktvärdering avsnittet **recensioner** i PDP följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="6f626-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="6f626-123">Öppna PDP-mallen.</span><span class="sxs-lookup"><span data-stu-id="6f626-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="6f626-124">Gå till **Inställningar för behållarmodulen inköpsruta**.</span><span class="sxs-lookup"><span data-stu-id="6f626-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="6f626-125">Under **inköpsruta**, välj **produktvärderingar** och sedan väljer du kryssrutan **Länka klicka till modulen för fullständig recension**.</span><span class="sxs-lookup"><span data-stu-id="6f626-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="6f626-126">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f626-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Länka en produktvärdering till avsnittet recensioner i ett PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="6f626-128">Konfigurera länken till sidan sekretess och policy</span><span class="sxs-lookup"><span data-stu-id="6f626-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="6f626-129">Konfigurera länken till sidan sekretess och policy genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6f626-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="6f626-130">Gå till **Start \> Webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="6f626-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="6f626-131">Välj namnet på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="6f626-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="6f626-132">Gå till **Webbplatsinställningar \> Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="6f626-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="6f626-133">På sidan **Flöden**, under **RNR sekretess och policy**, välj **Lägg till en länk**.</span><span class="sxs-lookup"><span data-stu-id="6f626-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="6f626-134">Om en länk redan har angivits och du vill ersätta den markerar du länken.</span><span class="sxs-lookup"><span data-stu-id="6f626-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="6f626-135">I dialogrutan **Lägg till en länk** väljer du länken för sidan om sekretess och policy och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f626-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="6f626-136">Välj **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="6f626-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="6f626-137">Följande bild visar hur den här konfigurationen ser ut i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f626-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurera länken till sidan sekretess och policy](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="6f626-139">Konfigurera klassificeringar och recensioner av moduler på produktinformationssidor</span><span class="sxs-lookup"><span data-stu-id="6f626-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="6f626-140">Information om hur du konfigurerar modulen värderingar och recensioner på produktinformationssidor finns [Moduler för omdömen och moduler](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="6f626-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f626-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="6f626-141">Additional resources</span></span>

[<span data-ttu-id="6f626-142">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="6f626-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="6f626-143">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="6f626-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="6f626-144">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="6f626-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="6f626-145">Konfigurera klassificeringar och recensioner av moduler på produktinformationssidor</span><span class="sxs-lookup"><span data-stu-id="6f626-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="6f626-146">Synkronisera produktklassificeringar i Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="6f626-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]