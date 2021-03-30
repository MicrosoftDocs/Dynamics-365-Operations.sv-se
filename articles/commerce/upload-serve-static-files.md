---
title: Ladda upp och hantera statiska filer
description: I det här avsnittet beskrivs hur du överför en statisk fil till webbplatsskaparen för Microsoft Dynamics 365 Commerce, samt hur du skapar en anpassad URL och ett filnamn som kan användas för att begära den filen.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: aba9dde2ed9d5fa09e92fcdd784a53f208930eda
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211029"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="903c9-103">Ladda upp och hantera statiska filer</span><span class="sxs-lookup"><span data-stu-id="903c9-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="903c9-104">I det här avsnittet beskrivs hur du överför en statisk fil till webbplatsskaparen för Microsoft Dynamics 365 Commerce, samt hur du skapar en anpassad URL och ett filnamn som kan användas för att begära den filen.</span><span class="sxs-lookup"><span data-stu-id="903c9-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="903c9-105">Vissa anslutningar från tredje part kräver att en fil hanteras och servas från näthandelssajten.</span><span class="sxs-lookup"><span data-stu-id="903c9-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="903c9-106">Dessa anslutningsprogram förväntar sig att filen ska returneras av begäranden till en viss URL-sökväg och ett visst filnamn för motringning.</span><span class="sxs-lookup"><span data-stu-id="903c9-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="903c9-107">Därför förklarar det här avsnittet hur du överför och betjänar en statisk fil som har en användardefinierbar URL och ett fil namn på en Dynamics 365 Commerce-näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="903c9-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="903c9-108">Skapa en webbplats-URL som returnerar en statisk fil</span><span class="sxs-lookup"><span data-stu-id="903c9-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="903c9-109">Om du vill skapa en webbplats-URL som returnerar en statisk fil i Commerce-webbplatsbyggaren följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="903c9-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="903c9-110">Gå till mediebiblioteket för din webbplats och överför filen som ska betjänas av begäranden till den URL som du ska definiera.</span><span class="sxs-lookup"><span data-stu-id="903c9-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="903c9-111">Om du redan har överfört filen kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="903c9-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="903c9-112">Gå till **URL:er** för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="903c9-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="903c9-113">Välj **Nytt \> Ny URL**.</span><span class="sxs-lookup"><span data-stu-id="903c9-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="903c9-114">I dialogrutan **Ny URL** väljer du **Mediebibliotekstillgång**.</span><span class="sxs-lookup"><span data-stu-id="903c9-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="903c9-115">I fältet **URL-sökväg** anger du URL:en på nytt.</span><span class="sxs-lookup"><span data-stu-id="903c9-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="903c9-116">Inkludera filnamnet i sökvägen.</span><span class="sxs-lookup"><span data-stu-id="903c9-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="903c9-117">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="903c9-117">Select **Next**.</span></span> <span data-ttu-id="903c9-118">Mediebiblioteket öppnas och visar alla medietillgångar tillhörande den **dokument** typ som har överförts.</span><span class="sxs-lookup"><span data-stu-id="903c9-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="903c9-119">Markera den fil som ska betjänas för begäranden till den URL som du definierade i steg 5.</span><span class="sxs-lookup"><span data-stu-id="903c9-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="903c9-120">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="903c9-120">Select **Save**.</span></span>

<span data-ttu-id="903c9-121">I det här läget har den URL som du skapade statusen "utkast".</span><span class="sxs-lookup"><span data-stu-id="903c9-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="903c9-122">Filen som URL:en pekar mot kommer inte att returneras förrän URL:en publiceras.</span><span class="sxs-lookup"><span data-stu-id="903c9-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="903c9-123">Innan du publicerar URL:en kan du validera att den returnerar rätt data.</span><span class="sxs-lookup"><span data-stu-id="903c9-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="903c9-124">Validera och publicera en URL</span><span class="sxs-lookup"><span data-stu-id="903c9-124">Validate and publish a URL</span></span>

<span data-ttu-id="903c9-125">Följ dessa steg om du vill validera en URL innan du publicerar den.</span><span class="sxs-lookup"><span data-stu-id="903c9-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="903c9-126">Gå till **URL:er** för webbplatsen och välj den URL som ska förhandsgranskas.</span><span class="sxs-lookup"><span data-stu-id="903c9-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="903c9-127">I egenskapsfönstret till höger, under knappen **Redigera**, väljer du korrekt URL-länk.</span><span class="sxs-lookup"><span data-stu-id="903c9-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="903c9-128">Ett nytt webbläsarfönster öppnas och felmeddelandet 404 visas.</span><span class="sxs-lookup"><span data-stu-id="903c9-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="903c9-129">Lägg till frågesträngen **?preview=inprogress** i URL:en (t. ex. `https://yoursite.com/callback.html?preview=inprogress`) och läs in sidan igen.</span><span class="sxs-lookup"><span data-stu-id="903c9-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="903c9-130">Filen som du överförde till mediebiblioteket ska returneras i svaret.</span><span class="sxs-lookup"><span data-stu-id="903c9-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="903c9-131">När du har validerat URL:en kan du publicera den.</span><span class="sxs-lookup"><span data-stu-id="903c9-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="903c9-132">Gå till **URL:er** för webbplatsen och välj URL:en.</span><span class="sxs-lookup"><span data-stu-id="903c9-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="903c9-133">Välj **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="903c9-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="903c9-134">Uppdatera filen som en URL pekar mot</span><span class="sxs-lookup"><span data-stu-id="903c9-134">Update the file that a URL points to</span></span>

<span data-ttu-id="903c9-135">När en URL publiceras kan du uppdatera den så att den pekar mot en annan fil.</span><span class="sxs-lookup"><span data-stu-id="903c9-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="903c9-136">Du kan också uppdatera URL:en så att den pekar mot en annan typ av resurs, enligt beskrivningen i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="903c9-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="903c9-137">Du kan till exempel rikta URL:en mot en intern sida eller en omdirigering.</span><span class="sxs-lookup"><span data-stu-id="903c9-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="903c9-138">Om du vill uppdatera filen som en URL pekar mot följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="903c9-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="903c9-139">Gå till **URL:er** för din webbplats och välj den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="903c9-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="903c9-140">I egenskapsrutan till höger, välj egenskapen **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="903c9-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="903c9-141">Under **URL-tilldelning** markerar du rutan **Steg 2** och väljer sedan ett nytt dokument i mediebiblioteket.</span><span class="sxs-lookup"><span data-stu-id="903c9-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="903c9-142">Välj **Tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="903c9-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="903c9-143">Uppdatera den tillgångstyp som en URL pekar mot</span><span class="sxs-lookup"><span data-stu-id="903c9-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="903c9-144">Du kan också uppdatera en URL så att den pekar mot en annan typ av tillgång (resurs), t. ex. en intern sida eller en omdirigering.</span><span class="sxs-lookup"><span data-stu-id="903c9-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="903c9-145">Om du vill uppdatera tillgångstypen som en URL pekar mot följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="903c9-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="903c9-146">Gå till **URL:er** för din webbplats och välj den URL som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="903c9-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="903c9-147">I egenskapsrutan till höger, välj egenskapen **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="903c9-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="903c9-148">Under **URL-tilldelning** väljer du ett annat tillgångsnamn under **Steg 1**.</span><span class="sxs-lookup"><span data-stu-id="903c9-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="903c9-149">Markera rutan **Steg 2** och välj sedan den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="903c9-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="903c9-150">Välj **Tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="903c9-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="903c9-151">Ändra URL-sökvägen</span><span class="sxs-lookup"><span data-stu-id="903c9-151">Change the URL path</span></span>

<span data-ttu-id="903c9-152">När en URL har skapats kan dess sökväg inte ändras.</span><span class="sxs-lookup"><span data-stu-id="903c9-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="903c9-153">Om du måste ändra URL-sökvägen som används för en fil eller någon annan typ av resurs måste du skapa en ny URL, mappa den till den befintliga filen eller en annan resurs och sedan ta bort publiceringen samt den gamla URL:en.</span><span class="sxs-lookup"><span data-stu-id="903c9-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="903c9-154">För att ändra URL-sökväg, följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="903c9-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="903c9-155">Om du vill skapa en ny URL och mappa den till den befintliga filen eller en annan resurs följer du instruktionerna i avsnittet [Skapa en webbplats-URL som returnerar en statisk fil](#create-a-site-url-that-returns-a-static-file) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="903c9-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="903c9-156">Markera den nya URL:en och välj **Publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="903c9-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="903c9-157">Den nya URL:en publiceras.</span><span class="sxs-lookup"><span data-stu-id="903c9-157">The new URL is published.</span></span>
1. <span data-ttu-id="903c9-158">Om du vill ta bort den gamla URL:en markerar du den och väljer sedan **Ta bort** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="903c9-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="903c9-159">Du kan nu ta bort den gamla URL:en om du vill.</span><span class="sxs-lookup"><span data-stu-id="903c9-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="903c9-160">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="903c9-160">Additional resources</span></span>

[<span data-ttu-id="903c9-161">Översikt av digital tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="903c9-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="903c9-162">Överför bilder</span><span class="sxs-lookup"><span data-stu-id="903c9-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="903c9-163">Överför videor</span><span class="sxs-lookup"><span data-stu-id="903c9-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="903c9-164">Överför andra filer än bilder och videor</span><span class="sxs-lookup"><span data-stu-id="903c9-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="903c9-165">Beskär bilder</span><span class="sxs-lookup"><span data-stu-id="903c9-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="903c9-166">Anpassa bildens fokuspunkter</span><span class="sxs-lookup"><span data-stu-id="903c9-166">Customize image focal points</span></span>](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]