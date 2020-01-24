---
title: Lägg till copyrightmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelsplats.
author: psimolin
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 58c2949057ef777f706d12cee2dd3341d1a3b7e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914591"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="9bad6-103">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="9bad6-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="9bad6-104">I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelsplats.</span><span class="sxs-lookup"><span data-stu-id="9bad6-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bad6-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="9bad6-105">Prerequisites</span></span>

<span data-ttu-id="9bad6-106">Innan du kan lägga till copyrightinformation till webbplatsen måste du ha följande objekt:</span><span class="sxs-lookup"><span data-stu-id="9bad6-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="9bad6-107">En mall som innehåller ett avsnitt för delad sidfot.</span><span class="sxs-lookup"><span data-stu-id="9bad6-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="9bad6-108">En sida som använder den mallen.</span><span class="sxs-lookup"><span data-stu-id="9bad6-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="9bad6-109">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="9bad6-109">Add a copyright notice</span></span>

<span data-ttu-id="9bad6-110">Om du vill lägga till copyrightinformation längst ned på varje sida som använder en viss mall följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="9bad6-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="9bad6-111">Gå till **fragment** och välj **nytt sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="9bad6-112">I dialog rutan väljer du modulen **sidfot** och namnger fragmentet.</span><span class="sxs-lookup"><span data-stu-id="9bad6-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="9bad6-113">Du kan t.ex. ange **Sidfot-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="9bad6-114">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-114">Select **OK**.</span></span>
1. <span data-ttu-id="9bad6-115">I navigeringsfönstret väljer du ellipsknappen (**...**) bredvid **sidfot** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9bad6-116">I dialogrutan, välj **Sidfotskategori** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="9bad6-117">I navigeringsfönstret väljer du ellipsknappen bredvid **sidfotskategori** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="9bad6-118">I dialogrutan, välj **innehållsrikt blockobjekt** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="9bad6-119">I navigeringsfönstret, välj **innehållsrika blockobjekt**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="9bad6-120">I det här egenskapsfönstret till höger, i fältet **stycke** lägger du till ditt copyright-meddelande.</span><span class="sxs-lookup"><span data-stu-id="9bad6-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="9bad6-121">Ange till exempel **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="9bad6-122">Välj **Spara**, välj **Checka in** och sedan **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="9bad6-123">Gå till **mallar**, markera mallen och välj sedan **Checka ut**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="9bad6-124">Under **Siddisposition**, utöka **Brödtext** och utöka sedan **Standardsidan**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="9bad6-125">Markera knappen med punkter för platsen **Sidfotsplats** och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="9bad6-126">Markera det fragment som du skapade tidigare och välj sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="9bad6-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="9bad6-127">Checka in mallen och publicera den.</span><span class="sxs-lookup"><span data-stu-id="9bad6-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="9bad6-128">Sidfoten som innehåller copyrightinformationen visas automatiskt längst ner på alla sidor som använder den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="9bad6-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9bad6-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9bad6-129">Additional resources</span></span>

[<span data-ttu-id="9bad6-130">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="9bad6-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="9bad6-131">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="9bad6-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="9bad6-132">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="9bad6-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="9bad6-133">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="9bad6-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="9bad6-134">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="9bad6-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="9bad6-135">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="9bad6-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="9bad6-136">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="9bad6-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
