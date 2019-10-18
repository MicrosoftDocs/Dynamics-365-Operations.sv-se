---
title: Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter
description: Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d646c8ba559ba3e8d2175911e76c57d25eff02ca
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278139"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="3231d-103">Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="3231d-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="3231d-104">Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="3231d-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="3231d-105">Mer information om produktrekommendationer finns i [produktrekommendationerna i kassadokumentationen.](product.md)</span><span class="sxs-lookup"><span data-stu-id="3231d-105">For more information about product recommendations, read the  [product recommendations on POS documentation.](product.md)</span></span>


<span data-ttu-id="3231d-106">Du kan visa produktrekommendationer på din kassaenhet när du använder Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="3231d-106">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="3231d-107">Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="3231d-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="3231d-108">Öppna layoutdesignern</span><span class="sxs-lookup"><span data-stu-id="3231d-108">Open Layout designer</span></span>

1. <span data-ttu-id="3231d-109">Navigera till **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="3231d-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="3231d-110">Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i.</span><span class="sxs-lookup"><span data-stu-id="3231d-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="3231d-111">Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="3231d-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="3231d-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3231d-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="3231d-113">Markera exempelvis **Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="3231d-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="3231d-114">Klicka på **Layoutdesigner**.</span><span class="sxs-lookup"><span data-stu-id="3231d-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="3231d-115">Följ instruktionerna för att starta layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="3231d-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="3231d-116">När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="3231d-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="3231d-117">När du loggar in visas en sida som liknar den nedanstående.</span><span class="sxs-lookup"><span data-stu-id="3231d-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="3231d-118">Layouten är olika beroende på de anpassningar som gjorts för din butik.</span><span class="sxs-lookup"><span data-stu-id="3231d-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="3231d-119">[![Layoutdesigner](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="3231d-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="3231d-120">Välj ett visningsalternativ</span><span class="sxs-lookup"><span data-stu-id="3231d-120">Choose a display option</span></span>

<span data-ttu-id="3231d-121">Det finns två konfigurationsalternativ tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="3231d-121">There are two configurations options available.</span></span> <span data-ttu-id="3231d-122">Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna.</span><span class="sxs-lookup"><span data-stu-id="3231d-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="3231d-123">De två alternativen är:</span><span class="sxs-lookup"><span data-stu-id="3231d-123">The two options are:</span></span>

- <span data-ttu-id="3231d-124">Rekommendationer visas alltid.</span><span class="sxs-lookup"><span data-stu-id="3231d-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="3231d-125">Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="3231d-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="3231d-126">Gör så att rekommendationer alltid visas</span><span class="sxs-lookup"><span data-stu-id="3231d-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="3231d-127">Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.</span><span class="sxs-lookup"><span data-stu-id="3231d-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="3231d-128">[![Höjden på detaljområdet för transaktionsrader har reducerats](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="3231d-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="3231d-129">Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="3231d-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="3231d-130">Ändra storlek på kontrollen så att den passar in i utrymmet.</span><span class="sxs-lookup"><span data-stu-id="3231d-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="3231d-131">[![Rekommendationskontroll som läggs till i layouten](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="3231d-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="3231d-132">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="3231d-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="3231d-133">I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="3231d-133">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="3231d-134">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="3231d-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="3231d-135">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="3231d-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="3231d-136">Lägg till en rekommendationsflik i knappsatsen till höger på skärmen</span><span class="sxs-lookup"><span data-stu-id="3231d-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="3231d-137">Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="3231d-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="3231d-138">Klicka på **anpassa**.</span><span class="sxs-lookup"><span data-stu-id="3231d-138">Click **Customize**.</span></span>

    <span data-ttu-id="3231d-139">[![Anpassning - dialogrutan flikkontroll](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="3231d-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="3231d-140">Klicka på **Ny flik**.</span><span class="sxs-lookup"><span data-stu-id="3231d-140">Click **New tab**.</span></span>
4. <span data-ttu-id="3231d-141">Hitta den nya fliken som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="3231d-141">Find the new tab that you just added.</span></span> <span data-ttu-id="3231d-142">Du kan behöva rulla nedåt.</span><span class="sxs-lookup"><span data-stu-id="3231d-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="3231d-143">I listrutan **Innehåll** väljer du **Rekommenderade produkter**.</span><span class="sxs-lookup"><span data-stu-id="3231d-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="3231d-144">[![Välja rekommenderade produkter i fältet Innehåll](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="3231d-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="3231d-145">I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.</span><span class="sxs-lookup"><span data-stu-id="3231d-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="3231d-146">I fältet **Bild** väljer du den bild du vill visa i fliken.</span><span class="sxs-lookup"><span data-stu-id="3231d-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="3231d-147">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3231d-147">Click **OK**.</span></span> <span data-ttu-id="3231d-148">Den nya fliken visas i knappsatsen.</span><span class="sxs-lookup"><span data-stu-id="3231d-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="3231d-149">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="3231d-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="3231d-150">I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="3231d-150">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="3231d-151">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="3231d-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="3231d-152">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="3231d-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3231d-153">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3231d-153">Additional resources</span></span>

[<span data-ttu-id="3231d-154">produktrekommendationer i kassa</span><span class="sxs-lookup"><span data-stu-id="3231d-154">product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="3231d-155">översikt över produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="3231d-155">product recommendations overview</span></span>](../commerce/product-recommendations.md)
