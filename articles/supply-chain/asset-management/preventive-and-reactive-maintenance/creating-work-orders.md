---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836744"
---
# <a name="creating-work-orders"></a><span data-ttu-id="ca375-103">Skapa arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ca375-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca375-104">När du har schemalagt förebyggande underhållsjobb är nästa steg att skapa arbetsorder för jobben.</span><span class="sxs-lookup"><span data-stu-id="ca375-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="ca375-105">Du kan genomföra det här steget genom att använda ett av underhållsschemana.</span><span class="sxs-lookup"><span data-stu-id="ca375-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="ca375-106">De schemalagda jobben i ett underhållsschema kan ha olika referenstyper som beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="ca375-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="ca375-107">Referenstyp</span><span class="sxs-lookup"><span data-stu-id="ca375-107">Reference type</span></span> | <span data-ttu-id="ca375-108">beskrivning</span><span class="sxs-lookup"><span data-stu-id="ca375-108">Description</span></span> |
|---|---|
| <span data-ttu-id="ca375-109">Underhållsplaner</span><span class="sxs-lookup"><span data-stu-id="ca375-109">Maintenance plans</span></span> | <span data-ttu-id="ca375-110">Förebyggande underhållsjobb baserade på underhållsplanens typer *Tid* eller *Räknare*.</span><span class="sxs-lookup"><span data-stu-id="ca375-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="ca375-111">Underhållsomgångar</span><span class="sxs-lookup"><span data-stu-id="ca375-111">Maintenance rounds</span></span> | <span data-ttu-id="ca375-112">Förebyggande underhållsjobb som innehåller flera tillgångar som kräver en liknande typ av underhåll.</span><span class="sxs-lookup"><span data-stu-id="ca375-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="ca375-113">Underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="ca375-113">Maintenance request</span></span> | <span data-ttu-id="ca375-114">En manuellt skapad begäran om underhåll eller reparation av en tillgång.</span><span class="sxs-lookup"><span data-stu-id="ca375-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="ca375-115">Denna begäran kan konverteras till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="ca375-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="ca375-116">Skapa arbetsorder baserat på din underhållsplan</span><span class="sxs-lookup"><span data-stu-id="ca375-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="ca375-117">Skapa arbetsorder som baseras på din underhållsplan genom att följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="ca375-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="ca375-118">Öppna någon av följande sidor, beroende på hur du vill välja tidsplaner uppgifter för dina arbetsorder:</span><span class="sxs-lookup"><span data-stu-id="ca375-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="ca375-119">Alla underhållsscheman (**Hantering av tillgångar \> Hanteringsschema \> Alla underhållsscheman**)</span><span class="sxs-lookup"><span data-stu-id="ca375-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="ca375-120">Öppna underhållsschemarader (**Hantering av tillgångar \> Hanteringsschema \> Öppna underhållsschemarader**)</span><span class="sxs-lookup"><span data-stu-id="ca375-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="ca375-121">Öppna underhållsschemapooler (**Hantering av tillgångar \> Hanteringsschema \> Öppna underhållsschemapooler**)</span><span class="sxs-lookup"><span data-stu-id="ca375-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="ca375-122">Markera kryssrutan i rutnätet för varje planerat underhållsjobb som du vill skapa en arbetsorder för.</span><span class="sxs-lookup"><span data-stu-id="ca375-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="ca375-123">Välj **Arbetsorder** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ca375-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="ca375-124">Dialogrutan **Skapa arbetsorder** visas.</span><span class="sxs-lookup"><span data-stu-id="ca375-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="ca375-125">Det totala antalet prognostimmar för de valda raderna visas i fältet **Prognostimmar för underhåll**.</span><span class="sxs-lookup"><span data-stu-id="ca375-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Dialogrutan Skapa arbetsorder](media/18-preventive-maintenance.png)

1. <span data-ttu-id="ca375-127">I avsnittet **Parametrar** ange antalet arbetsorder som ska skapas.</span><span class="sxs-lookup"><span data-stu-id="ca375-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="ca375-128">Välj ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="ca375-128">Select one of the following options:</span></span>

    - <span data-ttu-id="ca375-129">**En arbetsorder per rad** – Skapa en arbetsorder per underhållsplansrad.</span><span class="sxs-lookup"><span data-stu-id="ca375-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="ca375-130">**En arbetsorder per** – Skapa arbetsorder som grupperas enligt inställningarna för de andra alternativen som blir tillgängliga när du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ca375-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="ca375-131">Välj vilken arbetsordertyp som ska användas för alla arbetsorder som du skapar i fältet **Typ av arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="ca375-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="ca375-132">Välj **OK** för att skapa arbetsorder i enlighet med dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="ca375-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="ca375-133">Gruppera arbetsorderrader som skapas automatiskt när en underhållsplan körs</span><span class="sxs-lookup"><span data-stu-id="ca375-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

<span data-ttu-id="ca375-134">Med hjälp av den här funktionen kan du definiera regler för gruppering av arbetsorderrader under en enskild arbetsorder när systemet är inställt på att generera arbetsorder automatiskt, baserat på en underhållsplan.</span><span class="sxs-lookup"><span data-stu-id="ca375-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="ca375-135">Tidigare kunde automatiskt genererade arbetsorder bara innehålla en rad.</span><span class="sxs-lookup"><span data-stu-id="ca375-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="ca375-136">Du kan nu dock gruppera arbetsorder efter till exempel tillgång, tillgångstyp eller funktionell plats.</span><span class="sxs-lookup"><span data-stu-id="ca375-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="ca375-137">(Manuellt genererade arbetsorder kan redan grupperas på det här sättet, på det sätt som beskrivs i det föregående avsnittet av det här avsnittet.)</span><span class="sxs-lookup"><span data-stu-id="ca375-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="ca375-138">Aktivera gruppering för automatiskt genererade arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ca375-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="ca375-139">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="ca375-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="ca375-140">Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den.</span><span class="sxs-lookup"><span data-stu-id="ca375-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="ca375-141">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ca375-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ca375-142">**Modul:** *Tillgångshantering*</span><span class="sxs-lookup"><span data-stu-id="ca375-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="ca375-143">**Funktionens namn:** *Använd regler för att gruppera arbetsorder när du kör en underhållsplan*</span><span class="sxs-lookup"><span data-stu-id="ca375-143">**Feature name:** *Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="ca375-144">Ange gruppering för automatiskt genererade arbetsorder</span><span class="sxs-lookup"><span data-stu-id="ca375-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="ca375-145">Ange gruppering för automatiskt genererade arbetsorder med följande steg.</span><span class="sxs-lookup"><span data-stu-id="ca375-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="ca375-146">Gå till **Tillgångshantering \> Inställning \> Förebyggande underhåll \> Underhållsplaner**.</span><span class="sxs-lookup"><span data-stu-id="ca375-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="ca375-147">Följ de här stegen för varje plan där du vill generera grupperade arbetsorder:</span><span class="sxs-lookup"><span data-stu-id="ca375-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="ca375-148">Välj planen i listfönstret.</span><span class="sxs-lookup"><span data-stu-id="ca375-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="ca375-149">På snabbflikarna **Rader** kontrollerar du att kryssrutan **Skapa automatiskt** har markerats på varje rad.</span><span class="sxs-lookup"><span data-stu-id="ca375-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="ca375-150">Gå till **Tillgångshantering \> Periodisk \> Förebyggande underhåll \> Schemalägg underhållsplaner**.</span><span class="sxs-lookup"><span data-stu-id="ca375-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="ca375-151">Ange tidshorisont för planen i dialogrutan **Schemaunderhållsplaner** i avsnittet **Period** (hur långt du kan se framåt när du söker efter planerade underhållsjobb som genererar arbete).</span><span class="sxs-lookup"><span data-stu-id="ca375-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="ca375-152">Ställ in alternativet **Skapa arbetsorder automatiskt från schema** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="ca375-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="ca375-153">Välj ett av följande alternativ i området **Arbetsorder**:</span><span class="sxs-lookup"><span data-stu-id="ca375-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="ca375-154">**En arbetsorder per rad** – Skapa en arbetsorder per underhållsplansrad.</span><span class="sxs-lookup"><span data-stu-id="ca375-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="ca375-155">(Det här alternativet ger samma funktion som är tillgänglig när funktionen *Använd regler för att gruppera arbetsorder när du kör en underhållsplan* är avaktiverad.)</span><span class="sxs-lookup"><span data-stu-id="ca375-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="ca375-156">**En arbetsorder per** – Skapa arbetsorder som grupperas enligt inställningarna för de andra alternativen som blir tillgängliga när du väljer det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="ca375-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="ca375-157">Om du vill att alternativen ska gälla när du bara kör några av dina underhållsplaner, på snabbfliken **Poster att inkludera** lägg till filter du vill ha som med andra batchjobb i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca375-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="ca375-158">På snabbfliken **Kör i bakgrunden** ställer du in alternativ för batch och tidsplanering efter behov, på samma sätt som du kan göra för andra batchjobb i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ca375-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="ca375-159">Välj **OK** för att köra och/eller planera de valda underhållsplanerna.</span><span class="sxs-lookup"><span data-stu-id="ca375-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]