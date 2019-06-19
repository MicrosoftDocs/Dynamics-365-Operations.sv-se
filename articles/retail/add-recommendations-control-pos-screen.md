---
title: Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter
description: Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
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
ms.openlocfilehash: f17da3db6fbc19548544a0c6c090a0b6db093673
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606859"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="7b99d-103">Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter</span><span class="sxs-lookup"><span data-stu-id="7b99d-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="7b99d-104">Vi tar bort den nuvarande versionen av tjänsten produktrekommendation eftersom vi designar om funktionen med en bättre algoritm och nya butiksorienterade funktioner.</span><span class="sxs-lookup"><span data-stu-id="7b99d-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="7b99d-105">Mer information finns i beskrivningen av [borttagna eller gamla funktioner](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="7b99d-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span>

<span data-ttu-id="7b99d-106">Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7b99d-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="7b99d-107">Du kan visa produktrekommendationer på din kassaenhet när du använder Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7b99d-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="7b99d-108">*Rekommendationer* är artiklar som dina kunder kan vara intresserade av baserat på sina tidigare inköp, artiklar i sina önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="7b99d-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="7b99d-109">Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="7b99d-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="7b99d-110">Öppna layoutdesignern</span><span class="sxs-lookup"><span data-stu-id="7b99d-110">Open Layout designer</span></span>

1. <span data-ttu-id="7b99d-111">Navigera till **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="7b99d-112">Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i.</span><span class="sxs-lookup"><span data-stu-id="7b99d-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="7b99d-113">Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-113">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="7b99d-114">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="7b99d-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="7b99d-115">Markera exempelvis **Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-115">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="7b99d-116">Klicka på **Layoutdesigner**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-116">Click **Layout designer**.</span></span>
5. <span data-ttu-id="7b99d-117">Följ instruktionerna för att starta layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="7b99d-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="7b99d-118">När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="7b99d-119">När du loggar in visas en sida som liknar den nedanstående.</span><span class="sxs-lookup"><span data-stu-id="7b99d-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="7b99d-120">Layouten är olika beroende på de anpassningar som gjorts för din butik.</span><span class="sxs-lookup"><span data-stu-id="7b99d-120">The layout will be different depending on the customizations that were made for your store.</span></span>

    <span data-ttu-id="7b99d-121">[![Layoutdesigner](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="7b99d-121">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="7b99d-122">Välj ett visningsalternativ</span><span class="sxs-lookup"><span data-stu-id="7b99d-122">Choose a display option</span></span>

<span data-ttu-id="7b99d-123">Det finns två konfigurationsalternativ tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="7b99d-123">There are two configurations options available.</span></span> <span data-ttu-id="7b99d-124">Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna.</span><span class="sxs-lookup"><span data-stu-id="7b99d-124">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="7b99d-125">De två alternativen är:</span><span class="sxs-lookup"><span data-stu-id="7b99d-125">The two options are:</span></span>

- <span data-ttu-id="7b99d-126">Rekommendationer visas alltid.</span><span class="sxs-lookup"><span data-stu-id="7b99d-126">Recommendations are always visible.</span></span>
- <span data-ttu-id="7b99d-127">Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="7b99d-127">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="7b99d-128">Gör så att rekommendationer alltid visas</span><span class="sxs-lookup"><span data-stu-id="7b99d-128">Make recommendations always visible</span></span>

1. <span data-ttu-id="7b99d-129">Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.</span><span class="sxs-lookup"><span data-stu-id="7b99d-129">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>

    <span data-ttu-id="7b99d-130">[![Höjden på detaljområdet för transaktionsrader har reducerats](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="7b99d-130">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="7b99d-131">Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="7b99d-131">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="7b99d-132">Ändra storlek på kontrollen så att den passar in i utrymmet.</span><span class="sxs-lookup"><span data-stu-id="7b99d-132">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="7b99d-133">[![Rekommendationskontroll som läggs till i layouten](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="7b99d-133">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>

3. <span data-ttu-id="7b99d-134">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="7b99d-134">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="7b99d-135">I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-135">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="7b99d-136">I listan väljer du  **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-136">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="7b99d-137">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-137">Click **Run now**.</span></span>

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="7b99d-138">Lägg till en rekommendationsflik i knappsatsen till höger på skärmen</span><span class="sxs-lookup"><span data-stu-id="7b99d-138">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="7b99d-139">Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="7b99d-139">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2. <span data-ttu-id="7b99d-140">Klicka på **anpassa**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-140">Click **Customize**.</span></span>

    <span data-ttu-id="7b99d-141">[![Anpassning - dialogrutan flikkontroll](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="7b99d-141">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="7b99d-142">Klicka på **Ny flik**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-142">Click **New tab**.</span></span>
4. <span data-ttu-id="7b99d-143">Hitta den nya fliken som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="7b99d-143">Find the new tab that you just added.</span></span> <span data-ttu-id="7b99d-144">Du kan behöva rulla nedåt.</span><span class="sxs-lookup"><span data-stu-id="7b99d-144">You may need to scroll down.</span></span>
5. <span data-ttu-id="7b99d-145">I listrutan **Innehåll** väljer du **Rekommenderade produkter**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-145">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="7b99d-146">[![Välja rekommenderade produkter i fältet Innehåll](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="7b99d-146">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="7b99d-147">I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.</span><span class="sxs-lookup"><span data-stu-id="7b99d-147">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="7b99d-148">I fältet **Bild** väljer du den bild du vill visa i fliken.</span><span class="sxs-lookup"><span data-stu-id="7b99d-148">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="7b99d-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-149">Click **OK**.</span></span> <span data-ttu-id="7b99d-150">Den nya fliken visas i knappsatsen.</span><span class="sxs-lookup"><span data-stu-id="7b99d-150">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="7b99d-151">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="7b99d-151">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="7b99d-152">I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-152">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="7b99d-153">I listan väljer du  **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-153">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="7b99d-154">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="7b99d-154">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b99d-155">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7b99d-155">Additional resources</span></span>

[<span data-ttu-id="7b99d-156">Översikt över anpassade produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="7b99d-156">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)
