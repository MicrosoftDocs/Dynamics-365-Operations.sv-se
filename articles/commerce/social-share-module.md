---
title: Modul för social delning
description: Det här avsnittet handlar om modul för social delning och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 0a5ad1f4a9bb317e128ad14f21a4e6c48cab8a72
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985546"
---
# <a name="social-share-module"></a><span data-ttu-id="8b294-103">Modul för social delning</span><span class="sxs-lookup"><span data-stu-id="8b294-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8b294-104">Det här avsnittet handlar om modul för social delning och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b294-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8b294-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="8b294-105">Overview</span></span>

<span data-ttu-id="8b294-106">Med hjälp av modul för social delning kan användarna dela webbadresser för näthandelssajter på sociala medier som exempelvis Facebook, Twitter, Pinterest och LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="8b294-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="8b294-107">Webbadresser till webbplatssidan kan också delas via e-post.</span><span class="sxs-lookup"><span data-stu-id="8b294-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="8b294-108">Moduler för social delning används ofta på produktinformationssidor (PDP) för att hjälpa användarna att dela produktinformation.</span><span class="sxs-lookup"><span data-stu-id="8b294-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="8b294-109">Varje modul för social delning är en behållare för artikelmoduler för social delning.</span><span class="sxs-lookup"><span data-stu-id="8b294-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="8b294-110">Varje artikelmodul för social delning kan konfigureras så att den pekar mot en specifik plats för sociala medier.</span><span class="sxs-lookup"><span data-stu-id="8b294-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="8b294-111">Integrering med Facebook, Twitter, Pinterest, LinkedIn och e-post stöds i kartongen.</span><span class="sxs-lookup"><span data-stu-id="8b294-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="8b294-112">När en webbplats användare väljer en symbol för sociala medier, startas en HTML iFrame för respektive socialt medieplats.</span><span class="sxs-lookup"><span data-stu-id="8b294-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="8b294-113">I iFrame kan användaren logga in och bokföra det sidinnehåll som de visade.</span><span class="sxs-lookup"><span data-stu-id="8b294-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="8b294-114">Varje plattform för sociala medier kan spåra cookies, så den här modulen kräver att webbplats användarna accepterar meddelandet om att ett meddelande ska skickas till en cookie.</span><span class="sxs-lookup"><span data-stu-id="8b294-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="8b294-115">När cookie-tillstånd inte godkänns, döljs modulen på sidan.</span><span class="sxs-lookup"><span data-stu-id="8b294-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="8b294-116">Mer information finns i [kompatibilitet med cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="8b294-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="8b294-117">Följande bild visar ett exempel på en modul för social delning som används på en produktinformationssida.</span><span class="sxs-lookup"><span data-stu-id="8b294-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exempel på en modul för social delning](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="8b294-119">Egenskaper för modul för social delning</span><span class="sxs-lookup"><span data-stu-id="8b294-119">Social share module properties</span></span>

| <span data-ttu-id="8b294-120">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="8b294-120">Property name</span></span>             | <span data-ttu-id="8b294-121">Värde</span><span class="sxs-lookup"><span data-stu-id="8b294-121">Value</span></span>                 | <span data-ttu-id="8b294-122">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b294-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="8b294-123">Rubrik</span><span class="sxs-lookup"><span data-stu-id="8b294-123">Caption</span></span>                  | <span data-ttu-id="8b294-124">Text</span><span class="sxs-lookup"><span data-stu-id="8b294-124">Text</span></span> | <span data-ttu-id="8b294-125">Den här egenskapen anger en rubrik för modulen.</span><span class="sxs-lookup"><span data-stu-id="8b294-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="8b294-126">Orientering</span><span class="sxs-lookup"><span data-stu-id="8b294-126">Orientation</span></span> | <span data-ttu-id="8b294-127">**Horisontell** eller **Vertikal**</span><span class="sxs-lookup"><span data-stu-id="8b294-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="8b294-128">Den här egenskapen definierar orienteringen för de sociala medieartiklarna.</span><span class="sxs-lookup"><span data-stu-id="8b294-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="8b294-129">Egenskaper för artikelmodul för social delning</span><span class="sxs-lookup"><span data-stu-id="8b294-129">Social share item module properties</span></span>
| <span data-ttu-id="8b294-130">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="8b294-130">Property name</span></span>             | <span data-ttu-id="8b294-131">Värde</span><span class="sxs-lookup"><span data-stu-id="8b294-131">Value</span></span>                 | <span data-ttu-id="8b294-132">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8b294-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="8b294-133">Sociala medier</span><span class="sxs-lookup"><span data-stu-id="8b294-133">Social media</span></span>              | <span data-ttu-id="8b294-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **post**</span><span class="sxs-lookup"><span data-stu-id="8b294-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="8b294-135">En nedrullningsbar meny med en lista över sociala medieplattformar.</span><span class="sxs-lookup"><span data-stu-id="8b294-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="8b294-136">Ikon</span><span class="sxs-lookup"><span data-stu-id="8b294-136">Icon</span></span> |<span data-ttu-id="8b294-137">Bild</span><span class="sxs-lookup"><span data-stu-id="8b294-137">Image</span></span>    | <span data-ttu-id="8b294-138">Detta är den bild som kommer att visas för respektive socialt media.</span><span class="sxs-lookup"><span data-stu-id="8b294-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="8b294-139">Du bör läsa den sociala medieplattformens SDK för den rekommenderade bilden som ska användas för varje plattform.</span><span class="sxs-lookup"><span data-stu-id="8b294-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="8b294-140">Lägg till en modul för social delning för en modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="8b294-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="8b294-141">Följ dessa steg för att lägga till en social delningsmodul till en köpboxmodul.</span><span class="sxs-lookup"><span data-stu-id="8b294-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="8b294-142">På webbplatsen Fabrikam väljer du **sidor** och väljer sedan sidan **DefaultPDP** för att öppna sidan produktinformation.</span><span class="sxs-lookup"><span data-stu-id="8b294-142">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="8b294-143">I facket **inköpsruta (krävs)** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b294-143">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b294-144">I dialogrutan **Lägg till modul**, välj modulen **social delning** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b294-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b294-145">I facket **social delning** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b294-145">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b294-146">I dialogrutan **Lägg till modul**, välj modulen **social delning** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b294-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b294-147">I egenskapsfönstret i modulen **social delning**, under **orientering** välj **horisontell**.</span><span class="sxs-lookup"><span data-stu-id="8b294-147">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="8b294-148">Lägg till en undertext efter behov.</span><span class="sxs-lookup"><span data-stu-id="8b294-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="8b294-149">I facket **social delning** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8b294-149">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8b294-150">I dialogrutan **Lägg till modul**, välj modulen **social delningsartikel** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b294-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="8b294-151">I egenskapsfönstret i modulen **social delningsartikel**, under **sociala medier** välj **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="8b294-151">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="8b294-152">I egenskapsfönstret i modulen **social delningsartikel**, under **Ikon** välj **+ Lägg till en bild**.</span><span class="sxs-lookup"><span data-stu-id="8b294-152">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="8b294-153">I dialogrutan **Mediaväljare** välj modulen Facebook-logotyp och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b294-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="8b294-154">Om det inte finns någon Facebook logotypbild kan du välja **överför ny medieartikel** för att ladda upp ett.</span><span class="sxs-lookup"><span data-stu-id="8b294-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="8b294-155">Lägg till och konfigurera ytterligare moduler för **social delningsartikel** efter behov.</span><span class="sxs-lookup"><span data-stu-id="8b294-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="8b294-156">Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.</span><span class="sxs-lookup"><span data-stu-id="8b294-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="8b294-157">På sidan visas modulen för modul för social delning.</span><span class="sxs-lookup"><span data-stu-id="8b294-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="8b294-158">Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="8b294-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b294-159">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8b294-159">Additional resources</span></span>

[<span data-ttu-id="8b294-160">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="8b294-160">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8b294-161">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="8b294-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8b294-162">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="8b294-162">Cookie compliance</span></span>](cookie-compliance.md)
