---
title: Lägg till rekommendationer på transaktionsskärmen
description: Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6085a69132a4687455282a908d613aa98d2e7a8d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209261"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="9fc1c-103">Lägg till rekommendationer på transaktionsskärmen</span><span class="sxs-lookup"><span data-stu-id="9fc1c-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="9fc1c-104">Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="9fc1c-105">Mer information om produktrekommendationer finns i [produktrekommendationerna i kassadokumentationen](product.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1c-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="9fc1c-106">Du kan visa produktrekommendationer på din kassaenhet när du använder Commerce .</span><span class="sxs-lookup"><span data-stu-id="9fc1c-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="9fc1c-107">Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="9fc1c-108">Öppna layoutdesignern</span><span class="sxs-lookup"><span data-stu-id="9fc1c-108">Open Layout designer</span></span>

1. <span data-ttu-id="9fc1c-109">Navigera till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="9fc1c-110">Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="9fc1c-111">Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="9fc1c-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="9fc1c-113">Markera exempelvis **Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="9fc1c-114">Klicka på **Layoutdesigner**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="9fc1c-115">Följ instruktionerna för att starta layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="9fc1c-116">När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="9fc1c-117">När du loggar in visas en sida som liknar den nedanstående.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="9fc1c-118">Layouten är olika beroende på de anpassningar som gjorts för din butik.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="9fc1c-119">[![Layoutdesigner](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="9fc1c-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="9fc1c-120">Välj ett visningsalternativ</span><span class="sxs-lookup"><span data-stu-id="9fc1c-120">Choose a display option</span></span>

<span data-ttu-id="9fc1c-121">Det finns två konfigurationsalternativ tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-121">There are two configurations options available.</span></span> <span data-ttu-id="9fc1c-122">Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="9fc1c-123">De två alternativen är:</span><span class="sxs-lookup"><span data-stu-id="9fc1c-123">The two options are:</span></span>

- <span data-ttu-id="9fc1c-124">Rekommendationer visas alltid.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="9fc1c-125">Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="9fc1c-126">Gör så att rekommendationer alltid visas</span><span class="sxs-lookup"><span data-stu-id="9fc1c-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="9fc1c-127">Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="9fc1c-128">[![Höjden på detaljområdet för transaktionsrader har reducerats](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="9fc1c-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="9fc1c-129">Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="9fc1c-130">Ändra storlek på kontrollen så att den passar in i utrymmet.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="9fc1c-131">[![Rekommendationskontroll som läggs till i layouten](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="9fc1c-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="9fc1c-132">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="9fc1c-133">I Commerce, gå till **Butik och handel** &gt; **Butiks- och handels-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="9fc1c-134">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="9fc1c-135">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="9fc1c-136">Lägg till en rekommendationsflik i knappsatsen till höger på skärmen</span><span class="sxs-lookup"><span data-stu-id="9fc1c-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="9fc1c-137">Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="9fc1c-138">Klicka på **anpassa**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-138">Click **Customize**.</span></span>

    <span data-ttu-id="9fc1c-139">[![Anpassning – dialogrutan flikkontroll](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="9fc1c-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="9fc1c-140">Klicka på **Ny flik**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-140">Click **New tab**.</span></span>
4. <span data-ttu-id="9fc1c-141">Hitta den nya fliken som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-141">Find the new tab that you just added.</span></span> <span data-ttu-id="9fc1c-142">Du kan behöva rulla nedåt.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="9fc1c-143">I listrutan **Innehåll** väljer du **Rekommenderade produkter**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="9fc1c-144">[![Välja rekommenderade produkter i fältet Innehåll](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="9fc1c-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="9fc1c-145">I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="9fc1c-146">I fältet **Bild** väljer du den bild du vill visa i fliken.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="9fc1c-147">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-147">Click **OK**.</span></span> <span data-ttu-id="9fc1c-148">Den nya fliken visas i knappsatsen.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="9fc1c-149">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="9fc1c-150">I Commerce, gå till **Butik och handel** &gt; **Butiks- och handels-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="9fc1c-151">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="9fc1c-152">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="9fc1c-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9fc1c-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9fc1c-153">Additional resources</span></span>

[<span data-ttu-id="9fc1c-154">Översikt av produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="9fc1c-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="9fc1c-155">Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="9fc1c-155">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="9fc1c-156">Aktivera produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="9fc1c-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="9fc1c-157">Aktivera anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="9fc1c-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="9fc1c-158">Avanmäl anpassade rekommendationer</span><span class="sxs-lookup"><span data-stu-id="9fc1c-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="9fc1c-159">Aktivera rekommendationer för "köp liknande produkter"</span><span class="sxs-lookup"><span data-stu-id="9fc1c-159">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="9fc1c-160">Lägga till produktrekommendationer i POS</span><span class="sxs-lookup"><span data-stu-id="9fc1c-160">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="9fc1c-161">Justera rekommendationsresultat från AI-ML</span><span class="sxs-lookup"><span data-stu-id="9fc1c-161">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="9fc1c-162">Skapa granskade rekommendationer manuellt</span><span class="sxs-lookup"><span data-stu-id="9fc1c-162">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="9fc1c-163">Skapa rekommendationer med demodata</span><span class="sxs-lookup"><span data-stu-id="9fc1c-163">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="9fc1c-164">Vanliga frågor om produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="9fc1c-164">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]