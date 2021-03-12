---
title: Åtgärdssökning
description: I artikeln beskrivs funktionen åtgärdssökning. Funktionen för åtgärdssökning hjälper dig att hitta och köra åtgärder på en sida.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd9962451e8b72677e1a006dd9c1b8b8b268c93e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798657"
---
# <a name="action-search"></a><span data-ttu-id="08ea6-104">Åtgärdssökning</span><span class="sxs-lookup"><span data-stu-id="08ea6-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08ea6-105">I artikeln beskrivs funktionen åtgärdssökning.</span><span class="sxs-lookup"><span data-stu-id="08ea6-105">This article describes the action search functionality.</span></span> <span data-ttu-id="08ea6-106">Funktionen för åtgärdssökning hjälper dig att hitta och köra åtgärder på en sida.</span><span class="sxs-lookup"><span data-stu-id="08ea6-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="08ea6-107">Introduktion</span><span class="sxs-lookup"><span data-stu-id="08ea6-107">Introduction</span></span>

<span data-ttu-id="08ea6-108">Sidorna visar främst kommandon i åtgärdsfönster, både det vanliga åtgärdsfönstret som visas högst upp på en sida och verktygsfälten som visas på olika delar av sidan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-108">Pages primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="08ea6-109">I tidigare versioner fanns funktionen Tangenttips, som snabbt gav dig åtkomst till valfri knapp i ett åtgärdsfönster genom att trycka på ALT och en serie bokstäver.</span><span class="sxs-lookup"><span data-stu-id="08ea6-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="08ea6-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="08ea6-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="08ea6-111">Åtgärden sökningsfunktionen ersätter tangenttips, som inte längre är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="08ea6-111">The action search feature replaces Key Tips, which are no longer available.</span></span> <span data-ttu-id="08ea6-112">Den här nya funktionen kan du snabbt söka efter och kör en knapp från synliga rutan Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="08ea6-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="08ea6-113">Med hjälp av action sök</span><span class="sxs-lookup"><span data-stu-id="08ea6-113">Using action search</span></span>

<span data-ttu-id="08ea6-114">För att använda åtgärden sökfunktionen, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="08ea6-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="08ea6-115">I åtgärdsrutan, klicka i **sökfältet** .</span><span class="sxs-lookup"><span data-stu-id="08ea6-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="08ea6-116">( **åtgärden sökfältet** innehåller en förstoringsglaset).</span><span class="sxs-lookup"><span data-stu-id="08ea6-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="08ea6-117">Skriv hela eller en del av namnet på den knapp som du vill köra.</span><span class="sxs-lookup"><span data-stu-id="08ea6-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="08ea6-118">Du kan också söka genom att använda ord från knappens "sökväg".</span><span class="sxs-lookup"><span data-stu-id="08ea6-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="08ea6-119">(Mer information finns i nästa avsnitt i den här artikeln.) Vanligtvis visas en knapp längst upp i resultatlistan när du har skrivit två till fyra tecken.</span><span class="sxs-lookup"><span data-stu-id="08ea6-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="08ea6-120">Hitta och köra i resultatlistan (genom att använda din mus eller tangentbord).</span><span class="sxs-lookup"><span data-stu-id="08ea6-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="08ea6-121">När du kör, fokus återgår till din senaste position på sidan, så att du kan fortsätta att arbeta.</span><span class="sxs-lookup"><span data-stu-id="08ea6-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="08ea6-122">[![fält-för-åtgärdssökning](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="08ea6-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="08ea6-123">Du kan också starta åtgärden sökning, genom att pressa Ctrl+/- eller Alt+Q.</span><span class="sxs-lookup"><span data-stu-id="08ea6-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="08ea6-124">Tryck på kortkommandot igen för att återgå till din senaste position på sidan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="08ea6-125">Förstå resultaten förteckning</span><span class="sxs-lookup"><span data-stu-id="08ea6-125">Understanding the results list</span></span>

<span data-ttu-id="08ea6-126">Du måste ofta veta både på plats och samband för en knapp för att förstå syftet med den.</span><span class="sxs-lookup"><span data-stu-id="08ea6-126">Often, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="08ea6-127">Därför visas ytterligare information för som hjälper dig att förstå exakt vilka knappar som visas i listan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-127">Therefore, the results list shows additional information to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="08ea6-128">I synnerhet "sökväg" på knappen visas.</span><span class="sxs-lookup"><span data-stu-id="08ea6-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="08ea6-129">Den här sökvägen kan inkludera etiketter av följande UI-beståndsdelar:</span><span class="sxs-lookup"><span data-stu-id="08ea6-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="08ea6-130">Rutan åtgärd flik</span><span class="sxs-lookup"><span data-stu-id="08ea6-130">Action Pane tab</span></span>
- <span data-ttu-id="08ea6-131">Knappgrupp</span><span class="sxs-lookup"><span data-stu-id="08ea6-131">Button group</span></span>
- <span data-ttu-id="08ea6-132">Knappen meny (om knappen är placerad inuti en meny-knapp)</span><span class="sxs-lookup"><span data-stu-id="08ea6-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="08ea6-133">Menyn separator (om knappen är placerad inuti en namngiven grupp inuti en meny-knapp)</span><span class="sxs-lookup"><span data-stu-id="08ea6-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="08ea6-134">Grupp eller flik på sidan (t.ex. namnet på en snabbfliken)</span><span class="sxs-lookup"><span data-stu-id="08ea6-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="08ea6-135">Exempelvis du maskinskrev **tot** i **sökfältet** och granskar nu resultat listan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="08ea6-136">Den första posten, för en knapp vid namn **Summor**, markeras.</span><span class="sxs-lookup"><span data-stu-id="08ea6-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="08ea6-137">Knappsökvägen för **Försäljningsorder** &gt; **Visa** visas också.</span><span class="sxs-lookup"><span data-stu-id="08ea6-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="08ea6-138">**Försäljningsorder**-delen av sökvägen motsvarar fliken **Försäljningsorder** i åtgärdsfönstret, och **Visa**-delen i sökvägen motsvarar **Visa** gruppen på fliken. Dessutom informerar sökvägen till knappen **Totalrabatt** (**Sälj** &gt; **Beräkna**) dig om att den här knappen finns i gruppen **Beräkna** på fliken **Sälj** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="08ea6-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="08ea6-139">Därför kan den här informationen hjälpa dig att förstå exakt vilken knapp som utlöses av sökåtgärden (om du väljer knappen i resultatlistan).</span><span class="sxs-lookup"><span data-stu-id="08ea6-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="08ea6-140">[![fält-för-åtgärdssökning-med-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="08ea6-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="08ea6-141">I föregående exempel visade åtgärdsökningen resultat från det vanliga åtgärdsfönstret överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="08ea6-142">Men action sök visar också resultaten från synligt verktygsfält som finns på andra ställen på sidan.</span><span class="sxs-lookup"><span data-stu-id="08ea6-142">However, action search also shows results from visible toolbars that are in other places on the page.</span></span> <span data-ttu-id="08ea6-143">Låt oss till exempel säga att du söker efter knappen **Lagerbehållning** som finns på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="08ea6-143">For example, you're searching for the **On-hand inventory** button that is on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="08ea6-144">I det här fallet kommer knappsökvägen i resultatlistan (**Försäljningsorderrader** &gt; **Lager** &gt; **Visa**) att informera dig om att den här knappen finns under rubriken **Visa** på menyknappen **Lager** på snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="08ea6-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="08ea6-145">[![lagerbehållning](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="08ea6-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

> [!NOTE]
> <span data-ttu-id="08ea6-146">Det finns vissa knappar som inte visas vid åtgärdssökning.</span><span class="sxs-lookup"><span data-stu-id="08ea6-146">There are some buttons that do not show up in Action search.</span></span> <span data-ttu-id="08ea6-147">Dessa inkluderar nedrullningsbara dialogknappar och knappar från underformulär.</span><span class="sxs-lookup"><span data-stu-id="08ea6-147">These include drop dialog buttons and buttons from subforms.</span></span> 

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="08ea6-148">Åtgärd söka vs. navigation sökningen</span><span class="sxs-lookup"><span data-stu-id="08ea6-148">Action search vs. Navigation search</span></span>

<span data-ttu-id="08ea6-149">Medan åtgärdssökningen är avsedd att hitta och köra åtgärder på en sida, finns en separat sökmekanism för att söka och navigera till sidor.</span><span class="sxs-lookup"><span data-stu-id="08ea6-149">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages.</span></span> <span data-ttu-id="08ea6-150">Mer information om funktionen finns i artikeln [Navigeringssökning](navigation-search.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-150">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>
