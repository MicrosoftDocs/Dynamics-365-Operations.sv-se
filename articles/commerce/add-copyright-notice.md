---
title: Lägg till copyrightmeddelande
description: I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelssajt.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 54d9ccbb56131333159cdf8858dfca23b75b61fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980466"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="7537c-103">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="7537c-103">Add a copyright notice</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7537c-104">I det här avsnittet beskrivs hur du lägger till ett copyrightmeddelande till din näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="7537c-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7537c-105">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="7537c-105">Prerequisites</span></span>

<span data-ttu-id="7537c-106">Innan du kan lägga till copyrightinformation till webbplatsen måste du ha följande objekt:</span><span class="sxs-lookup"><span data-stu-id="7537c-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="7537c-107">En mall som innehåller ett avsnitt för delad sidfot.</span><span class="sxs-lookup"><span data-stu-id="7537c-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="7537c-108">En sida som använder den mallen.</span><span class="sxs-lookup"><span data-stu-id="7537c-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="7537c-109">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="7537c-109">Add a copyright notice</span></span>

<span data-ttu-id="7537c-110">Om du vill lägga till copyrightinformation längst ned på varje sida som använder en viss mall följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7537c-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="7537c-111">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="7537c-111">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="7537c-112">I dialogrutan **Nytt fragment**, välj modulen **Sidfot** och namnge fragmentet.</span><span class="sxs-lookup"><span data-stu-id="7537c-112">In the **New fragment** dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="7537c-113">Du kan t.ex. ange **Sidfot-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="7537c-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="7537c-114">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7537c-114">Select **OK**.</span></span>
1. <span data-ttu-id="7537c-115">I navigeringsfönstret väljer du ellipsknappen (**...**) bredvid **sidfot** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="7537c-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="7537c-116">I dialogrutan, välj **Sidfotskategori** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7537c-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="7537c-117">I navigeringsfönstret väljer du ellipsknappen bredvid **sidfotskategori** och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="7537c-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="7537c-118">I dialogrutan, välj **Textblock** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="7537c-118">In the dialog box, select **Text block**, and then select **OK**.</span></span>
1. <span data-ttu-id="7537c-119">Välj **textblock** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7537c-119">In the navigation pane, select **Text block**.</span></span>
1. <span data-ttu-id="7537c-120">I det här egenskapsfönstret till höger, i fältet **stycke** lägger du till ditt copyright-meddelande.</span><span class="sxs-lookup"><span data-stu-id="7537c-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="7537c-121">Ange till exempel **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="7537c-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="7537c-122">Välj **Spara**, välj **Slutför redigering** och sedan **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="7537c-122">Select **Save**, select **Finish editing**, and then select **Publish**.</span></span>
1. <span data-ttu-id="7537c-123">Gå till **mallar**, markera mallen och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7537c-123">Go to **Templates**, select the template, and then select **Edit**.</span></span>
1. <span data-ttu-id="7537c-124">Under **Siddisposition**, utöka **Brödtext** och utöka sedan **Standardsidan**.</span><span class="sxs-lookup"><span data-stu-id="7537c-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="7537c-125">Markera knappen med punkter för platsen **Sidfotsplats** och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="7537c-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="7537c-126">Markera det fragment som du skapade tidigare och välj sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="7537c-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="7537c-127">Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.</span><span class="sxs-lookup"><span data-stu-id="7537c-127">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="7537c-128">Sidfoten som innehåller copyrightinformationen visas automatiskt längst ner på alla sidor som använder den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="7537c-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7537c-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7537c-129">Additional resources</span></span>

[<span data-ttu-id="7537c-130">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="7537c-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="7537c-131">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7537c-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="7537c-132">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="7537c-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="7537c-133">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="7537c-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="7537c-134">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="7537c-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="7537c-135">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="7537c-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="7537c-136">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="7537c-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

