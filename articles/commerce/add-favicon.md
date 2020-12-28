---
title: Lägg till en favicon
description: I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 262e478d426fd913130b21a3434331c7d27b54b2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415766"
---
# <a name="add-a-favicon"></a><span data-ttu-id="59ee3-103">Lägg till en favicon</span><span class="sxs-lookup"><span data-stu-id="59ee3-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="59ee3-104">I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="59ee3-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="59ee3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="59ee3-105">Overview</span></span>

<span data-ttu-id="59ee3-106">En favicon är en liten grafisk fil som visas på en flik i webbläsaren, i adressfältet, i webbhistoriken och i bokmärken eller favoriter, bland annat.</span><span class="sxs-lookup"><span data-stu-id="59ee3-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="59ee3-107">Vi rekommenderar att du lägger till en favicon på din webbplats, eftersom den representerar och stärker ditt varumärke och hjälper till att skilja din webbplats från andra webbplatser som dina kunder besöker.</span><span class="sxs-lookup"><span data-stu-id="59ee3-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="59ee3-108">Även om du kan lägga till flera favicons av olika storlekar och filtyper på din webbplats, visar det här avsnittet hur du lägger till en enskild favicon.</span><span class="sxs-lookup"><span data-stu-id="59ee3-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="59ee3-109">Samma process och plats används dock för att lägga till fler favicons.</span><span class="sxs-lookup"><span data-stu-id="59ee3-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="59ee3-110">Överför en favicon till webbplatsens tillgångssamling</span><span class="sxs-lookup"><span data-stu-id="59ee3-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="59ee3-111">Överför en favicon till webbplatsens tillgångssamling genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="59ee3-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="59ee3-112">I vänstra navigeringsfönstret, välj **mediebibliotek**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-112">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="59ee3-113">I kommandofältet, välj **Överför \> Överför medieartiklar**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-113">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="59ee3-114">I fönstret Utforskaren bläddrar du till avbildningsfilen favicon som du vill överföra, markerar den och väljer sedan **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-114">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="59ee3-115">I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.</span><span class="sxs-lookup"><span data-stu-id="59ee3-115">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="59ee3-116">Om du vill publicera bilden omedelbart efter överföring markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-116">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59ee3-117">Om du inte markerar kryssrutan **Publicera medieobjekt efter överföring** måste du gå tillbaka till sidan **Medieobjekt** och publicera favicon manuellt senare.</span><span class="sxs-lookup"><span data-stu-id="59ee3-117">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="59ee3-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-118">Select **OK**.</span></span>
1. <span data-ttu-id="59ee3-119">Kopiera den offentliga URL:en för favicon i egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="59ee3-119">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="59ee3-120">Du kommer att använda denna URL senare.</span><span class="sxs-lookup"><span data-stu-id="59ee3-120">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="59ee3-121">Skapa HTML för din favicon</span><span class="sxs-lookup"><span data-stu-id="59ee3-121">Create the HTML for your favicon</span></span>

<span data-ttu-id="59ee3-122">Om du vill skapa HTML för favicon använder du följande HTML-sträng.</span><span class="sxs-lookup"><span data-stu-id="59ee3-122">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="59ee3-123">För attributet **href**, ersätt **Public\_URL\_for\_your\_favicon** med den offentliga URL som du kopierade tidigare.</span><span class="sxs-lookup"><span data-stu-id="59ee3-123">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="59ee3-124">Skapa ett fragment som innehåller en metatagg för din favicon</span><span class="sxs-lookup"><span data-stu-id="59ee3-124">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="59ee3-125">För att skapa ett fragment som innehåller en metatagg för din favicon ska du följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="59ee3-125">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="59ee3-126">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-126">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="59ee3-127">I dialogrutan **Nytt fragment** markerar du **Metataggar** som modulen fragment är baserat på.</span><span class="sxs-lookup"><span data-stu-id="59ee3-127">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="59ee3-128">Ange ett namn på fragment och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-128">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="59ee3-129">I trädet för fragmentets hierarki väljer du underordnade **Standard metataggar**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-129">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="59ee3-130">I det högra fönstret, under **Metataggar**, väljer du **Lägg till** och anger sedan den HTML-sträng som du skapade tidigare för favicon.</span><span class="sxs-lookup"><span data-stu-id="59ee3-130">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="59ee3-131">Välj **Slutför redigering** och välj sedan **Publicera** för att publicera fragment.</span><span class="sxs-lookup"><span data-stu-id="59ee3-131">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="59ee3-132">Lägg till fragment med metatagg i HTML-huvudet på dina sidor</span><span class="sxs-lookup"><span data-stu-id="59ee3-132">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="59ee3-133">För att lägga till fragment med metatagg i HTML-**huvudet** på dina sidor ska du följa dessa steg</span><span class="sxs-lookup"><span data-stu-id="59ee3-133">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="59ee3-134">Gå till **Mallar** och öppna mallen för sidorna som du vill lägga till din favicon i och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-134">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="59ee3-135">I trädet för mallhierarkin väljer du ellipsknappen (**...**) till höger om behållaren för **HTML-huvud** och väljer **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-135">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="59ee3-136">I dialogrutan **Välj fragment** väljer du det metatagfragment som du skapade tidigare och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="59ee3-136">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="59ee3-137">Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.</span><span class="sxs-lookup"><span data-stu-id="59ee3-137">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="59ee3-138">Om mer än en mall används på webbplatsen måste du lägga till metatagfragmentet på alla.</span><span class="sxs-lookup"><span data-stu-id="59ee3-138">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="59ee3-139">När du förhandsgranskar sidor baserade på den mall som du har lagt till metatagfragmentet till ska du nu se favicon på fliken i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="59ee3-139">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59ee3-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="59ee3-140">Additional resources</span></span>

[<span data-ttu-id="59ee3-141">Lägga till en logotyp</span><span class="sxs-lookup"><span data-stu-id="59ee3-141">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="59ee3-142">Välja ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="59ee3-142">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="59ee3-143">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="59ee3-143">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="59ee3-144">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="59ee3-144">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="59ee3-145">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="59ee3-145">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="59ee3-146">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="59ee3-146">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="59ee3-147">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="59ee3-147">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

