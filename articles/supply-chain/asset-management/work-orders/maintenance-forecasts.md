---
title: Underhållsprognoser
description: I det här avsnittet beskrivs underhållsprognoser i Tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dd652af3100f8de59e06490443baeebca58a4dd3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838548"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="6cd83-103">Underhållsprognoser</span><span class="sxs-lookup"><span data-stu-id="6cd83-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="6cd83-104">När du skapar en arbetsorder skapar du arbetsorderjobb med relaterade tillgångar och underhållsjobbtyper.</span><span class="sxs-lookup"><span data-stu-id="6cd83-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="6cd83-105">När du väljer en underhållsjobbtyp som innehåller underhållsprognoser, kopieras prognoserna automatiskt till arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="6cd83-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="6cd83-106">Du kanske kan lägga till prognosrader till en arbetsorder eller ta bort dem från en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6cd83-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="6cd83-107">Inställningen av en livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera prognosrader.</span><span class="sxs-lookup"><span data-stu-id="6cd83-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="6cd83-108">Mer information om livscykeltillstånd för arbetsorder och relaterade projektfaser finns i [Prognoser, arbetsorder och projekt](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="6cd83-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="6cd83-109">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6cd83-110">Välj arbetsorder i listan och sedan i åtgärdsfönstret på fliken > **Arbetsorder** > i gruppen **Projekt** väljer du **Prognos**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="6cd83-111">På sidan **Underhållsprognos för arbetsorder** visas prognosrader från den typ av underhållsjobb som valts i arbetsorderjobbet.</span><span class="sxs-lookup"><span data-stu-id="6cd83-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="6cd83-112">Lägga till timprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="6cd83-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="6cd83-113">På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.</span><span class="sxs-lookup"><span data-stu-id="6cd83-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="6cd83-114">På snabbfliken **Timmar**, klicka på **Lägg till** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="6cd83-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="6cd83-115">Välj en kategori i fältet **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="6cd83-116">Infoga antal prognostiserade timmar i fältet **Timmar**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="6cd83-117">I fältet **Radegenskap** väljer du den typ av tillägg som ska användas på raden.</span><span class="sxs-lookup"><span data-stu-id="6cd83-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="6cd83-118">Lägga till artikelprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="6cd83-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="6cd83-119">Det finns tre sätt att lägga till artiklar i en underhållsprognos för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6cd83-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="6cd83-120">Du kan skapa rader för artiklar (reservdelar) som inte ingår i reservdelslistan eller tillgångsstrukturen, du kan välja reservdelar från listan med godkända reservdelar, och du kan välja artiklar från tillgångsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="6cd83-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="6cd83-121">På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.</span><span class="sxs-lookup"><span data-stu-id="6cd83-121">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

- <span data-ttu-id="6cd83-122">På snabbfliken **artiklar** lägg till artiklar i underhållsprognosen med hjälp av lämplig metod.</span><span class="sxs-lookup"><span data-stu-id="6cd83-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="6cd83-123">För att skapa en ny rad för en reservdel som inte finns med i reservdelslistan eller tillgångsstrukturlistan, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="6cd83-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="6cd83-124">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-124">Select **Add**.</span></span>
2. <span data-ttu-id="6cd83-125">Välj en artikel i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="6cd83-126">I fältet **Försäljningskvantitet** anger du kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6cd83-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="6cd83-127">Välj måttenhet för kvantiteten i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="6cd83-128">I fälten **Självkostnad** och **Valuta** anger du lämpliga värden.</span><span class="sxs-lookup"><span data-stu-id="6cd83-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="6cd83-129">I fältet **radegenskap** väljer du en rad egenskap.</span><span class="sxs-lookup"><span data-stu-id="6cd83-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="6cd83-130">Om du vill ändra listan över de dimensioner som visas på artikelraderna väljer du **Lager** > **Visa dimensioner**, väljer dimensioner och anger sedan alternativet **Spara inställningar** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="6cd83-131">Så här lägger du till en reservdel från en godkänd reservdelslista:</span><span class="sxs-lookup"><span data-stu-id="6cd83-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="6cd83-132">Välj **Lägg till reservdelar**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="6cd83-133">Välj reservdelen och redigera den relaterade informationen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="6cd83-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="6cd83-134">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-134">Select **OK**.</span></span>

<span data-ttu-id="6cd83-135">Gör så här om du vill lägga till en artikel från tillgångsstrukturen:</span><span class="sxs-lookup"><span data-stu-id="6cd83-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="6cd83-136">Välj **Lägg till strukturlisteartiklar**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="6cd83-137">Välj artikeln och redigera den relaterade informationen som du behöver.</span><span class="sxs-lookup"><span data-stu-id="6cd83-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="6cd83-138">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-138">Select **OK**.</span></span>

<span data-ttu-id="6cd83-139">Om du vill få en översikt som visar var artikeln på den valda raden används, i relation till tillgångar, underhållsjobbtypstandarder, reservdelar och arbetsorder i tillgångshantering väljer du **artikel där den används**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="6cd83-140">Mer information om översikten finns i [Artikel där den används](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="6cd83-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="6cd83-141">Lägga till utgiftsprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="6cd83-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="6cd83-142">På sidan **Underhållsprognos för arbetsorder** väljer du arbetsorder jobbet som du vill lägga till en prognos i.</span><span class="sxs-lookup"><span data-stu-id="6cd83-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="6cd83-143">På snabbfliken **Utgift**, klicka på **Lägg till** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="6cd83-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="6cd83-144">Välj en kategori i fältet **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="6cd83-145">I fältet **Kvantitet** anger du kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="6cd83-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="6cd83-146">I fälten **självkostnad**, **försäljningsvaluta** och **försäljningspris** anger du lämpliga värden.</span><span class="sxs-lookup"><span data-stu-id="6cd83-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="6cd83-147">I fältet **Radegenskap** väljer du den typ av tillägg som ska användas på raden.</span><span class="sxs-lookup"><span data-stu-id="6cd83-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="6cd83-148">Snabbfliken **Underhållsprognossummor** visar en översikt över antalet rader som har skapats för det valda arbetsorderjobbet och för arbetsordern på varje snabbfliken.</span><span class="sxs-lookup"><span data-stu-id="6cd83-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="6cd83-149">Den visar också visa en summa för prognostiserad arbetstid för arbetsorderjobbet och för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="6cd83-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="6cd83-150">I bilden nedan visas ett exempel på sidan **Underhållsprognos för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Figur 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="6cd83-152">Automatisk uppdatering av arbetsorderprognoser</span><span class="sxs-lookup"><span data-stu-id="6cd83-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="6cd83-153">Om timkostnader, artikelkostnader och utgifter uppdateras i andra moduler i Microsoft Dynamics 365 for Finance and Operations kan arbetsorderprognoser i Tillgångshantering uppdateras automatiskt för att återspegla dessa förändringar.</span><span class="sxs-lookup"><span data-stu-id="6cd83-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="6cd83-154">Denna kunskap hjälper till att garantera att de senaste självkostnaderna alltid används i dina arbetsorderprognoser.</span><span class="sxs-lookup"><span data-stu-id="6cd83-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="6cd83-155">Du kan också göra liknande uppdateringar för [prognoser för underhållsjobbtyper](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="6cd83-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="6cd83-156">Klicka på **Tillgångshantering** > **Periodiskt** > **Prognos** > **Uppdatera arbetsorderprognos**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="6cd83-157">I dialogrutan **Uppdatera arbetsorderprognos** på snabbfliken **Poster som ska ingå** kan du lägga till urval för specifika arbetsorder eller arbetsorderjobb om det behövs.</span><span class="sxs-lookup"><span data-stu-id="6cd83-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="6cd83-158">Välj **filter** och gör relevanta val.</span><span class="sxs-lookup"><span data-stu-id="6cd83-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="6cd83-159">På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.</span><span class="sxs-lookup"><span data-stu-id="6cd83-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="6cd83-160">Starta prognosuppdateringen genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="6cd83-161">I bilden nedan visas ett exempel på sidan dialogrutan **Uppdatera arbetsorderprognos**.</span><span class="sxs-lookup"><span data-stu-id="6cd83-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Figur 2](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]