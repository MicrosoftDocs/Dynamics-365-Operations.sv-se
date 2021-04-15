---
title: Modul för social delning
description: Det här avsnittet handlar om modul för social delning och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c34410a8c817de9fed350bf2cd2dd918a37c230f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795367"
---
# <a name="social-share-module"></a><span data-ttu-id="f0e5e-103">Modul för delning på sociala nätverk</span><span class="sxs-lookup"><span data-stu-id="f0e5e-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0e5e-104">Det här avsnittet handlar om modul för social delning och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f0e5e-105">Med hjälp av modul för social delning kan användarna dela webbadresser för näthandelssajter på sociala medier som exempelvis Facebook, Twitter, Pinterest och LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="f0e5e-106">Webbadresser till webbplatssidan kan också delas via e-post.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="f0e5e-107">Moduler för social delning används ofta på produktinformationssidor (PDP) för att hjälpa användarna att dela produktinformation.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="f0e5e-108">Varje modul för social delning är en behållare för artikelmoduler för social delning.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="f0e5e-109">Varje artikelmodul för social delning kan konfigureras så att den pekar mot en specifik plats för sociala medier.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="f0e5e-110">Integrering med Facebook, Twitter, Pinterest, LinkedIn och e-post stöds i kartongen.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="f0e5e-111">När en webbplats användare väljer en symbol för sociala medier, startas en HTML iFrame för respektive socialt medieplats.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="f0e5e-112">I iFrame kan användaren logga in och bokföra det sidinnehåll som de visade.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="f0e5e-113">Varje plattform för sociala medier kan spåra cookies, så den här modulen kräver att webbplats användarna accepterar meddelandet om att ett meddelande ska skickas till en cookie.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="f0e5e-114">När cookie-tillstånd inte godkänns, döljs modulen på sidan.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="f0e5e-115">Mer information finns i [kompatibilitet med cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="f0e5e-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="f0e5e-116">Följande bild visar ett exempel på en modul för social delning som används på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exempel på en modul för social delning](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="f0e5e-118">Egenskaper för modul för social delning</span><span class="sxs-lookup"><span data-stu-id="f0e5e-118">Social share module properties</span></span>

| <span data-ttu-id="f0e5e-119">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="f0e5e-119">Property name</span></span>             | <span data-ttu-id="f0e5e-120">Värde</span><span class="sxs-lookup"><span data-stu-id="f0e5e-120">Value</span></span>                 | <span data-ttu-id="f0e5e-121">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f0e5e-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="f0e5e-122">Rubrik</span><span class="sxs-lookup"><span data-stu-id="f0e5e-122">Caption</span></span>                  | <span data-ttu-id="f0e5e-123">Text</span><span class="sxs-lookup"><span data-stu-id="f0e5e-123">Text</span></span> | <span data-ttu-id="f0e5e-124">Den här egenskapen anger en rubrik för modulen.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="f0e5e-125">Orientering</span><span class="sxs-lookup"><span data-stu-id="f0e5e-125">Orientation</span></span> | <span data-ttu-id="f0e5e-126">**Horisontell** eller **Vertikal**</span><span class="sxs-lookup"><span data-stu-id="f0e5e-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="f0e5e-127">Den här egenskapen definierar orienteringen för de sociala medieartiklarna.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="f0e5e-128">Egenskaper för artikelmodul för social delning</span><span class="sxs-lookup"><span data-stu-id="f0e5e-128">Social share item module properties</span></span>
| <span data-ttu-id="f0e5e-129">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="f0e5e-129">Property name</span></span>             | <span data-ttu-id="f0e5e-130">Värde</span><span class="sxs-lookup"><span data-stu-id="f0e5e-130">Value</span></span>                 | <span data-ttu-id="f0e5e-131">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f0e5e-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="f0e5e-132">Sociala medier</span><span class="sxs-lookup"><span data-stu-id="f0e5e-132">Social media</span></span>              | <span data-ttu-id="f0e5e-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **post**</span><span class="sxs-lookup"><span data-stu-id="f0e5e-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="f0e5e-134">En nedrullningsbar meny med en lista över sociala medieplattformar.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="f0e5e-135">Ikon</span><span class="sxs-lookup"><span data-stu-id="f0e5e-135">Icon</span></span> |<span data-ttu-id="f0e5e-136">Bild</span><span class="sxs-lookup"><span data-stu-id="f0e5e-136">Image</span></span>    | <span data-ttu-id="f0e5e-137">Detta är den bild som kommer att visas för respektive socialt media.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="f0e5e-138">Du bör läsa den sociala medieplattformens SDK för den rekommenderade bilden som ska användas för varje plattform.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="f0e5e-139">Lägg till en modul för social delning för en modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="f0e5e-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="f0e5e-140">Följ dessa steg för att lägga till en social delningsmodul till en köpboxmodul.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="f0e5e-141">På webbplatsen Fabrikam väljer du **sidor** och väljer sedan sidan **DefaultPDP** för att öppna sidan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="f0e5e-142">I facket **inköpsruta (krävs)** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f0e5e-143">I dialogrutan **Lägg till modul**, välj modulen **social delning** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f0e5e-144">I facket **social delning** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f0e5e-145">I dialogrutan **Lägg till modul**, välj modulen **social delning** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f0e5e-146">I egenskapsfönstret i modulen **social delning**, under **orientering** välj **horisontell**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="f0e5e-147">Lägg till en undertext efter behov.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="f0e5e-148">I facket **social delning** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f0e5e-149">I dialogrutan **Lägg till modul**, välj modulen **social delningsartikel** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f0e5e-150">I egenskapsfönstret i modulen **social delningsartikel**, under **sociala medier** välj **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="f0e5e-151">I egenskapsfönstret i modulen **social delningsartikel**, under **Ikon** välj **+ Lägg till en bild**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="f0e5e-152">I dialogrutan **Mediaväljare** välj modulen Facebook-logotyp och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="f0e5e-153">Om det inte finns någon Facebook logotypbild kan du välja **överför ny medieartikel** för att ladda upp ett.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="f0e5e-154">Lägg till och konfigurera ytterligare moduler för **social delningsartikel** efter behov.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="f0e5e-155">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="f0e5e-156">På sidan visas modulen för modul för social delning.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="f0e5e-157">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="f0e5e-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0e5e-158">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f0e5e-158">Additional resources</span></span>

[<span data-ttu-id="f0e5e-159">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="f0e5e-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f0e5e-160">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="f0e5e-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f0e5e-161">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="f0e5e-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]