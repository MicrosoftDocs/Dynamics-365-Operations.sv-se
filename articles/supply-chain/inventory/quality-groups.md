---
title: Kvalitetsgrupper för artiklar
description: I detta ämne beskrivs hur du använder och skapar artikelkvalitetsgrupper för att logiskt gruppera produkter så att dessa kan tilldelas kvalitetsassociationer för automatisk generering av kvalitetsorder.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3074a6a8cc054be045bf593b509e76a1043af0b7
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956830"
---
# <a name="item-quality-groups"></a><span data-ttu-id="5a30b-103">Kvalitetsgrupper för artiklar</span><span class="sxs-lookup"><span data-stu-id="5a30b-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a30b-104">En kvalitetsgrupp representerar gemensamma testbehov för artiklar.</span><span class="sxs-lookup"><span data-stu-id="5a30b-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="5a30b-105">I detta ämne beskrivs hur du använder och skapar artikelkvalitetsgrupper för att logiskt gruppera produkter så att dessa kan tilldelas kvalitetsassociationer för automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="5a30b-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="5a30b-106">Gå till **Lagerhantering \> Inställningar \> Kvalitetsgrupper** om du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel.</span><span class="sxs-lookup"><span data-stu-id="5a30b-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="5a30b-107">När du har definierat testkraven på sidan **Testgrupper** kan du definiera reglerna för automatisk generering av kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="5a30b-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="5a30b-108">För att förenkla processen definierar du inte regler för enskilda artiklar.</span><span class="sxs-lookup"><span data-stu-id="5a30b-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="5a30b-109">I stället kan du definiera regler för en kvalitetsgrupp på sidan **Kvalitetsassociationer**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="5a30b-110">Exempel på en kvalitetsgrupp för artiklar</span><span class="sxs-lookup"><span data-stu-id="5a30b-110">Example of an item quality group</span></span>

<span data-ttu-id="5a30b-111">Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion.</span><span class="sxs-lookup"><span data-stu-id="5a30b-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="5a30b-112">Företaget definierar därför en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen.</span><span class="sxs-lookup"><span data-stu-id="5a30b-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="5a30b-113">Senare köper företaget en ny typ av råmaterial som har samma testbehov.</span><span class="sxs-lookup"><span data-stu-id="5a30b-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="5a30b-114">I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="5a30b-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="5a30b-115">Samma företag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans.</span><span class="sxs-lookup"><span data-stu-id="5a30b-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="5a30b-116">Företaget definierar därför två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till respektive grupp.</span><span class="sxs-lookup"><span data-stu-id="5a30b-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="5a30b-117">Skapa en kvalitetsgrupp</span><span class="sxs-lookup"><span data-stu-id="5a30b-117">Create a quality group</span></span>

<span data-ttu-id="5a30b-118">Gör så här om du vill skapa en kvalitetsgrupp:</span><span class="sxs-lookup"><span data-stu-id="5a30b-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="5a30b-119">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="5a30b-120">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5a30b-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5a30b-121">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="5a30b-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="5a30b-122">**Kvalitetsgrupp** – Ange ett unikt ID eller namn för kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="5a30b-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="5a30b-123">**Beskrivning** – Ange en detaljerad beskrivning av kvalitetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="5a30b-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="5a30b-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5a30b-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="5a30b-125">Lägg till artiklar i en kvalitetsgrupp manuellt</span><span class="sxs-lookup"><span data-stu-id="5a30b-125">Manually add items to a quality group</span></span>

<span data-ttu-id="5a30b-126">Följ de här stegen om du vill lägga till artiklar manuellt i en kvalitetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5a30b-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="5a30b-127">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="5a30b-128">Välj den kvalitetsgrupp som du vill lägga till artiklar i.</span><span class="sxs-lookup"><span data-stu-id="5a30b-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="5a30b-129">Klicka på **Artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5a30b-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="5a30b-130">Ppå sidan **Artiklar i kvalitetsgrupper** väljer du **Ny** i åtgärdsfönstret om du vill lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5a30b-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5a30b-131">Ange sedan fältet **Artikelnummer** för den nya raden som det artikelnummer du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="5a30b-132">Upprepa föregående steg för varje ytterligare artikel som måste läggas till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="5a30b-133">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="5a30b-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="5a30b-134">Lägg till flera artiklar i en kvalitetsgrupp</span><span class="sxs-lookup"><span data-stu-id="5a30b-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="5a30b-135">Följ de här stegen om du vill lägga till flera artiklar i en kvalitetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5a30b-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="5a30b-136">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Kvalitetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="5a30b-137">Skapa eller välj den kvalitetsgrupp som du vill lägga till artiklar i.</span><span class="sxs-lookup"><span data-stu-id="5a30b-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="5a30b-138">Klicka på **Lägg till artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5a30b-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="5a30b-139">I dlialogrutan **Förfrågan** anger du filterkriterier för de artiklar som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="5a30b-140">Du kan till exempel filtrera för alla artiklar i en viss artikelgrupp.</span><span class="sxs-lookup"><span data-stu-id="5a30b-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="5a30b-141">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-141">Select **OK**.</span></span>
1. <span data-ttu-id="5a30b-142">I dialogrutan **Lägg till objekt** visar ett rutnät alla objekt som matchar frågan.</span><span class="sxs-lookup"><span data-stu-id="5a30b-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="5a30b-143">Granska resultaten.</span><span class="sxs-lookup"><span data-stu-id="5a30b-143">Review the results.</span></span>

    <span data-ttu-id="5a30b-144">Om du behöver genomföra ändringar väljer du **Välj** för att återgå till dialogrutan **Förfrågan**, och justerar sedan din fråga.</span><span class="sxs-lookup"><span data-stu-id="5a30b-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="5a30b-145">När resultatet inkluderar alla artiklar som du vill lägga till väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="5a30b-146">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5a30b-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="5a30b-147">Associera en artikel med en kvalitetsgrupp manuellt</span><span class="sxs-lookup"><span data-stu-id="5a30b-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="5a30b-148">Följ de här stegen om du vill lägga till artiklar manuellt i en kvalitetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5a30b-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="5a30b-149">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Artikelkvalitetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="5a30b-150">I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5a30b-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5a30b-151">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="5a30b-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="5a30b-152">**Artikelnummer** – Välj det artikelnummer som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="5a30b-153">**Kvalitetsgrupp** – Välj den kvalitetsgrupp som ska tilldelas artikeln.</span><span class="sxs-lookup"><span data-stu-id="5a30b-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="5a30b-154">Upprepa föregående steg för varje ytterligare kombination av en artikel och en kvalitetsgrupp som måste läggas till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="5a30b-155">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="5a30b-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="5a30b-156">Lägga till en kvalitetsgrupp manuellt från sidan Frisläppta produkter</span><span class="sxs-lookup"><span data-stu-id="5a30b-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="5a30b-157">Följ dessa steg om du vill lägga till en kvalitetsgrupp från sidan **Frisläppta produkter** manuellt.</span><span class="sxs-lookup"><span data-stu-id="5a30b-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="5a30b-158">Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="5a30b-159">Välj den produkt som du vill tilldela en kvalitetsgrupp till.</span><span class="sxs-lookup"><span data-stu-id="5a30b-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="5a30b-160">På fliken **Hantera lager** i åtgärdsfönstret, i gruppen **Kvalitet**, väljer du **Artikelkvalitetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="5a30b-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="5a30b-161">Ppå sidan **Artiklar i kvalitetsgrupper** väljer du **Ny** i åtgärdsfönstret om du vill lägga till en ny rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="5a30b-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="5a30b-162">Ange sedan fältet **Kvalitetsgrupp** för den nya raden som den kvalitetsgrupp du vill tilldela produkten.</span><span class="sxs-lookup"><span data-stu-id="5a30b-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="5a30b-163">Upprepa föregående steg för varje ytterligare kvalitetsgrupp som du vill tilldela produkten.</span><span class="sxs-lookup"><span data-stu-id="5a30b-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="5a30b-164">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="5a30b-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a30b-165">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5a30b-165">Additional resources</span></span>

- [<span data-ttu-id="5a30b-166">Testinstrument för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="5a30b-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="5a30b-167">Kvalitetshanteringstester</span><span class="sxs-lookup"><span data-stu-id="5a30b-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="5a30b-168">Testgrupper för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="5a30b-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="5a30b-169">Testvariabler för kvalitetshantering</span><span class="sxs-lookup"><span data-stu-id="5a30b-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="5a30b-170">Kvalitetsassociationer</span><span class="sxs-lookup"><span data-stu-id="5a30b-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
