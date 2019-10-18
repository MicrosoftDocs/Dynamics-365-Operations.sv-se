---
title: Underhållsprognoser
description: I det här avsnittet beskrivs underhållsprognoser i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024509"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="a2174-103">Underhållsprognoser</span><span class="sxs-lookup"><span data-stu-id="a2174-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="a2174-104">När du skapar en arbetsorder skapar du arbetsorderjobb med relaterade tillgångar och underhållsjobbtyper.</span><span class="sxs-lookup"><span data-stu-id="a2174-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="a2174-105">När du väljer en underhållsjobbtyp som innehåller underhållsprognoser, kopieras prognoserna automatiskt till arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="a2174-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="a2174-106">Du kanske kan lägga till eller ta bort prognosrader på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a2174-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="a2174-107">Inställningen av ett livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera prognosrader.</span><span class="sxs-lookup"><span data-stu-id="a2174-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="a2174-108">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="a2174-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="a2174-109">Välj arbetsorder i listan och klicka på **Prognos**.</span><span class="sxs-lookup"><span data-stu-id="a2174-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="a2174-110">I **Underhållsprognos för arbetsorder** visas prognosrader från den typ av underhållsjobb som valts i arbetsorderjobbet.</span><span class="sxs-lookup"><span data-stu-id="a2174-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="a2174-111">Lägga till timprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2174-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="a2174-112">Välj det arbetsorderjobb som du vill lägga till en prognos för.</span><span class="sxs-lookup"><span data-stu-id="a2174-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a2174-113">På snabbfliken **Timmar**, klicka på **Lägg till** för att skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="a2174-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="a2174-114">Välj en kategori i fältet **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="a2174-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="a2174-115">Infoga antal prognostiserade timmar i fältet **Timmar**.</span><span class="sxs-lookup"><span data-stu-id="a2174-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="a2174-116">I fältet **Radegenskap** väljer du den kostnadstyp som ska användas på raden.</span><span class="sxs-lookup"><span data-stu-id="a2174-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="a2174-117">Lägga till artikelprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2174-117">Add items forecast to a work order</span></span>

<span data-ttu-id="a2174-118">Det finns tre sätt att lägga till artiklar i en underhållsprognos för arbetsorder: du kan skapa rader för artiklar (reservdelar) som inte ingår i reservdelslistan eller tillgångsstrukturen, du kan välja reservdelar från listan med godkända reservdelar, och du kan välja artiklar från tillgångsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="a2174-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="a2174-119">Välj det arbetsorderjobb som du vill lägga till en prognos för.</span><span class="sxs-lookup"><span data-stu-id="a2174-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a2174-120">Välj på snabbfliken **Artiklar**.</span><span class="sxs-lookup"><span data-stu-id="a2174-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="a2174-121">Klicka på **Lägg till** om du vill skapa en ny rad för en reservdel som inte finns med i reservdelslistan eller tillgångsstrukturlistan.</span><span class="sxs-lookup"><span data-stu-id="a2174-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="a2174-122">Välj artikeln i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="a2174-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="a2174-123">Infoga kvantitet i fältet **Försäljningskvantitet** och välj en kvantitetsenhet i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="a2174-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="a2174-124">Infoga självkostnad och valuta i de relevanta fälten och välj en **Radegenskap**.</span><span class="sxs-lookup"><span data-stu-id="a2174-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="a2174-125">Om du vill ändra listan över de dimensioner som visas på artikelraderna klickar du på **Lager** > **Visa dimensioner**, väljer dimensioner och väljer sedan "Ja" på växlingsknappen **Spara inställningar** .</span><span class="sxs-lookup"><span data-stu-id="a2174-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="a2174-126">Om du vill lägga till en godkänd reservdel i underhållsprognosen klickar du på **Lägg till reservdelar**, väljer reservdelen, redigerar relaterad informationen om det behövs och klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2174-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="a2174-127">Om du vill lägga till tillgångsstrukturartiklar i prognosen klickar du på **Lägg till strukturlisteartiklar**, väljer den aktuella artikeln, redigerar relaterad information klickar på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2174-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="a2174-128">Klicka på **Artikel där den används** om du vill få en översikt över var artikeln på den valda raden används i Tillgångshantering, i relation till tillgångar, standardvärden för underhållsjobbtyper, reservdelar och arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a2174-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="a2174-129">Lägga till utgiftsprognos i en arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2174-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="a2174-130">I det här avsnittet beskrivs hur du lägger till en utgiftsprognos till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="a2174-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="a2174-131">På vänstra sidan av formuläret väljer du det arbetsorderjobb som du vill lägga till en prognos för.</span><span class="sxs-lookup"><span data-stu-id="a2174-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="a2174-132">Välj snabbfliken **Utgift**.</span><span class="sxs-lookup"><span data-stu-id="a2174-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="a2174-133">Klicka på **Lägg till** om du vill skapa en ny rad.</span><span class="sxs-lookup"><span data-stu-id="a2174-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="a2174-134">Välj en kategori i fältet **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="a2174-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="a2174-135">I fältet **Kvantitet** anger du kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="a2174-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="a2174-136">Infoga självkostnad, försäljningsvaluta och försäljningspris i de relevanta fälten.</span><span class="sxs-lookup"><span data-stu-id="a2174-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="a2174-137">I fältet **Radegenskap** väljer du den kostnadstyp som ska användas på raden.</span><span class="sxs-lookup"><span data-stu-id="a2174-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="a2174-138">På snabbfliken **Underhållsprognossummor** visas en översikt över antalet rader som har skapats på varje flik, för det valda arbetsorderjobbet och för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="a2174-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="a2174-139">Du kan också visa en summa för prognostiserad arbetstid för arbetsorderjobbet och för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="a2174-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Figur 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="a2174-141">Automatisk uppdatering av arbetsorderprognoser</span><span class="sxs-lookup"><span data-stu-id="a2174-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="a2174-142">I Tillgångshantering kan du automatiskt uppdatera alla ändringar av arbetsorderprognoser för timkostnader, artikelkostnader och utgifter som har uppdaterats i andra moduler.</span><span class="sxs-lookup"><span data-stu-id="a2174-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules.</span></span> <span data-ttu-id="a2174-143">Detta görs för att se till att de senaste självkostnaderna alltid används i dina arbetsorderprognoser.</span><span class="sxs-lookup"><span data-stu-id="a2174-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="a2174-144">Det går också att göra liknande uppdateringar för [prognoser för underhållsjobbtyper](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="a2174-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="a2174-145">Klicka på **Tillgångshantering** > **Periodiskt** > **Prognos** > **Uppdatera arbetsorderprognos**.</span><span class="sxs-lookup"><span data-stu-id="a2174-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="a2174-146">I den nedrullningsbara dialogrutan **Uppdatera arbetsorderprognos** kan du lägga till urval för specifika arbetsorder eller arbetsorderjobb om det behövs.</span><span class="sxs-lookup"><span data-stu-id="a2174-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="a2174-147">Klicka på **Filter** för att göra urvalen.</span><span class="sxs-lookup"><span data-stu-id="a2174-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="a2174-148">På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.</span><span class="sxs-lookup"><span data-stu-id="a2174-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="a2174-149">Klicka på **OK** för att starta progonosuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="a2174-149">Click **OK** to start the forecast update.</span></span>


![Figur 2](media/07-work-orders.png)

