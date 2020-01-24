---
title: Lägg till en favicon
description: I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: 18e12cbe46650fcf024a56b6de9a8cb2903d2bf8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914594"
---
# <a name="add-a-favicon"></a><span data-ttu-id="46ffc-103">Lägg till en favicon</span><span class="sxs-lookup"><span data-stu-id="46ffc-103">Add a favicon</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="46ffc-104">I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="46ffc-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="46ffc-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="46ffc-105">Overview</span></span>

<span data-ttu-id="46ffc-106">En favicon är en liten grafisk fil som visas på en flik i webbläsaren, i adressfältet, i webbhistoriken och i bokmärken eller favoriter, bland annat.</span><span class="sxs-lookup"><span data-stu-id="46ffc-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="46ffc-107">Vi rekommenderar att du lägger till en favicon på din webbplats, eftersom den representerar och stärker ditt varumärke och hjälper till att skilja din webbplats från andra webbplatser som dina kunder besöker.</span><span class="sxs-lookup"><span data-stu-id="46ffc-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="46ffc-108">Även om du kan lägga till flera favicons av olika storlekar och filtyper på din webbplats, visar det här avsnittet hur du lägger till en enskild favicon.</span><span class="sxs-lookup"><span data-stu-id="46ffc-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="46ffc-109">Samma process och plats används dock för att lägga till fler favicons.</span><span class="sxs-lookup"><span data-stu-id="46ffc-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="46ffc-110">Överför en favicon till webbplatsens tillgångssamling</span><span class="sxs-lookup"><span data-stu-id="46ffc-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="46ffc-111">Överför en favicon till webbplatsens tillgångssamling genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="46ffc-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="46ffc-112">Gå till **Tillgångar \> Överför \> Överför tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="46ffc-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="46ffc-113">Hitta och markera favicon i det lokala filsystemet.</span><span class="sxs-lookup"><span data-stu-id="46ffc-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="46ffc-114">Ange en rubrik och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="46ffc-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="46ffc-115">Kopiera den offentliga URL:en för favicon i egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="46ffc-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="46ffc-116">Om du inte markerar alternativet **publicera resurser efter överföring** måste du gå tillbaka till sidan **tillgångar** och publicera favicon manuellt senare.</span><span class="sxs-lookup"><span data-stu-id="46ffc-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="46ffc-117">Skapa HTML för favicon</span><span class="sxs-lookup"><span data-stu-id="46ffc-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="46ffc-118">Om du vill skapa HTML för favicon använder du följande HTML-kodfragment.</span><span class="sxs-lookup"><span data-stu-id="46ffc-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="46ffc-119">För attributet **href**, ersätt **"Public\_URL\_for\_your\_favicon"** med den offentliga URL som du kopierade tidigare.</span><span class="sxs-lookup"><span data-stu-id="46ffc-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="46ffc-120">Lägga till HTML-koden för favicon till elementet \<head\> på sidorna</span><span class="sxs-lookup"><span data-stu-id="46ffc-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="46ffc-121">Om du vill lägga till en favicon på webbplatsen använder du samma procedur som för att lägga till alla typer av HTML och skript till elementet **\<head\>** på webbplatssidorna.</span><span class="sxs-lookup"><span data-stu-id="46ffc-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46ffc-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="46ffc-122">Additional resources</span></span>

[<span data-ttu-id="46ffc-123">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="46ffc-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="46ffc-124">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="46ffc-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="46ffc-125">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="46ffc-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="46ffc-126">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="46ffc-126">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="46ffc-127">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="46ffc-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="46ffc-128">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="46ffc-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="46ffc-129">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="46ffc-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

