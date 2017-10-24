---
title: "Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet"
description: "Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4cdfcbdcafdbbbab21c398ebc8002a45742e33e6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="49830-103">Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet</span><span class="sxs-lookup"><span data-stu-id="49830-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="49830-104">Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="49830-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="49830-105">Du kan visa produktrekommendationer på din kassaenhet när du använder Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="49830-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="49830-106">*Rekommendationer* är artiklar som dina kunder kan vara intresserade av baserat på sina tidigare inköp, artiklar i sina önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker.</span><span class="sxs-lookup"><span data-stu-id="49830-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="49830-107">Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="49830-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="49830-108">Öppna layoutdesignern</span><span class="sxs-lookup"><span data-stu-id="49830-108">Open Layout designer</span></span>
1.  <span data-ttu-id="49830-109">Navigera till **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="49830-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="49830-110">Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i.</span><span class="sxs-lookup"><span data-stu-id="49830-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="49830-111">Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet "F2CP16:9M".</span><span class="sxs-lookup"><span data-stu-id="49830-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="49830-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="49830-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="49830-113">Markera exempelvis "Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M".</span><span class="sxs-lookup"><span data-stu-id="49830-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="49830-114">Klicka på **Layoutdesigner**.</span><span class="sxs-lookup"><span data-stu-id="49830-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="49830-115">Följ instruktionerna för att starta layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="49830-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="49830-116">När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.</span><span class="sxs-lookup"><span data-stu-id="49830-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="49830-117">När du loggar in visas en sida som liknar den nedanstående.</span><span class="sxs-lookup"><span data-stu-id="49830-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="49830-118">Layouten är olika beroende på de anpassningar som gjorts för din butik.</span><span class="sxs-lookup"><span data-stu-id="49830-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="49830-119">[![skärmlayout-bild-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Välj ett visningsalternativ</span><span class="sxs-lookup"><span data-stu-id="49830-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="49830-120">Det finns två konfigurationsalternativ tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="49830-120">There are two configurations options available.</span></span> <span data-ttu-id="49830-121">Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna.</span><span class="sxs-lookup"><span data-stu-id="49830-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="49830-122">De två alternativen är:</span><span class="sxs-lookup"><span data-stu-id="49830-122">The two options are:</span></span>
-   <span data-ttu-id="49830-123">Rekommendationer visas alltid.</span><span class="sxs-lookup"><span data-stu-id="49830-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="49830-124">Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="49830-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="49830-125">För att alltid visa rekommendationer</span><span class="sxs-lookup"><span data-stu-id="49830-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="49830-126">Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.[](./media/pic-2.png)[![skärmlayout-bild-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="49830-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="49830-127">Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="49830-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="49830-128">Ändra storlek på kontrollen så att den passar in i utrymmet.[](./media/pic-3.png)[![bildlayout-bild-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="49830-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="49830-129">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="49830-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="49830-130">I Dynamics 365 for Retail, navigera till **Butik** &gt; **Butiks-IT** &gt; **Fördelningsscheman**.</span><span class="sxs-lookup"><span data-stu-id="49830-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="49830-131">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="49830-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="49830-132">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="49830-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="49830-133">För att lägga till en rekommendationsflik i knappsatsen till höger på skärmen</span><span class="sxs-lookup"><span data-stu-id="49830-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="49830-134">Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="49830-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="49830-135">Klicka på **Anpassa**.[![bild-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="49830-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="49830-136">Klicka på **Ny flik**.</span><span class="sxs-lookup"><span data-stu-id="49830-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="49830-137">Hitta den nya fliken som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="49830-137">Find the new tab that you just added.</span></span> <span data-ttu-id="49830-138">Du kan behöva rulla nedåt.</span><span class="sxs-lookup"><span data-stu-id="49830-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="49830-139">I listrutan **Innehåll** väljer du **Rekommenderade produkter**.</span><span class="sxs-lookup"><span data-stu-id="49830-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="49830-140">[![bild-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="49830-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="49830-141">I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.</span><span class="sxs-lookup"><span data-stu-id="49830-141">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="49830-142">I fältet **Bild** väljer du den bild du vill visa i fliken.</span><span class="sxs-lookup"><span data-stu-id="49830-142">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="49830-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="49830-143">Click **OK**.</span></span> <span data-ttu-id="49830-144">Den nya fliken visas i knappsatsen.</span><span class="sxs-lookup"><span data-stu-id="49830-144">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="49830-145">Klick på **X** för att spara och stänga layoutdesignern.</span><span class="sxs-lookup"><span data-stu-id="49830-145">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="49830-146">I Dynamics 365 for Retail, navigera till **Butik** &gt; **Butiks-IT** &gt; **Fördelningsscheman**.</span><span class="sxs-lookup"><span data-stu-id="49830-146">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="49830-147">I listan väljer du **1090 Registers**.</span><span class="sxs-lookup"><span data-stu-id="49830-147">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="49830-148">Klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="49830-148">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="49830-149">Se även</span><span class="sxs-lookup"><span data-stu-id="49830-149">See also</span></span>
--------

[<span data-ttu-id="49830-150">Översikt över anpassade produktrekommendationer</span><span class="sxs-lookup"><span data-stu-id="49830-150">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




