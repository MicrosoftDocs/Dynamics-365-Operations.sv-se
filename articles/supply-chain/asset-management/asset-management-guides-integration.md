---
title: Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides
description: Det här avsnittet innehåller information om hur du integrerar modulen för tillgångshantering i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides och drar nytta av guiderna för dagligt service- och underhållsarbete.
author: kamaybac
manager: tfehr
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f9ee7f1af8e88f56589c84bfaa063ea005aa353a
ms.sourcegitcommit: 88b4a9d19d16b0ef6543adf7c378a08bf0e07b3a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "3311791"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a><span data-ttu-id="b1564-103">Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="b1564-103">Integrate Dynamics 365 Supply Chain Management (Asset management) with Dynamics 365 Guides</span></span>

<span data-ttu-id="b1564-104">Du kan integrera modulen för **tillgångshantering** i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides och dra nytta av guiderna för dagligt service- och underhållsarbete.</span><span class="sxs-lookup"><span data-stu-id="b1564-104">You can integrate the **Asset management** module in Microsoft Dynamics 365 Supply Chain Management with Dynamics 365 Guides to take advantage of mixed-reality guides in your day-to-day service and maintenance workflows.</span></span> <span data-ttu-id="b1564-105">Om en guide är associerad till en arbetsorder för tillgångshantering kan en arbetare som öppnar arbetsorderns underhållschecklista i mobilappen Supply Chain Management (Dynamics 365) se att en guide är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b1564-105">If a guide is associated with an Asset Management work order, a worker who opens the work order's maintenance checklist in the Supply Chain Management (Dynamics 365) mobile app sees that a guide is available.</span></span> <span data-ttu-id="b1564-106">Arbetaren kan sedan hitta och öppna guiden i appen Dynamics 365 Guides HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b1564-106">The worker can then find and open the guide in the Dynamics 365 Guides HoloLens app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1564-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b1564-107">Prerequisites</span></span>

<span data-ttu-id="b1564-108">Innan du kan koppla guider till arbetsorder för tillgångshantering måste följande förutsättningar föreligga:</span><span class="sxs-lookup"><span data-stu-id="b1564-108">Before you can attach guides to Asset management work orders, you must complete these prerequisites:</span></span>

- <span data-ttu-id="b1564-109">[Ställ in Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 eller senare.</span><span class="sxs-lookup"><span data-stu-id="b1564-109">[Set up Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 or later.</span></span>
- <span data-ttu-id="b1564-110">[Aktivera dubbelriktad skrivning för Supply Chain Management-appar](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="b1564-110">[Turn on dual-write for Supply Chain Management apps](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).</span></span>
- <span data-ttu-id="b1564-111">[Aktivera flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) för funktionen **MRGuidesFeature**.</span><span class="sxs-lookup"><span data-stu-id="b1564-111">[Turn on flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) for the **MRGuidesFeature** feature.</span></span> <span data-ttu-id="b1564-112">(För produktionsmiljöer måste du först skicka in ett supportärende så att din klientorganisation läggs till i flightgruppen.)</span><span class="sxs-lookup"><span data-stu-id="b1564-112">(For production environments, you must first submit a support ticket to have your tenant added to the flighting group.)</span></span>
- <span data-ttu-id="b1564-113">[Aktivera följande konfigurationsnycklar](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) på sidan **Licenskonfiguration**:</span><span class="sxs-lookup"><span data-stu-id="b1564-113">[Turn on the following configuration keys](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) on the **License configuration** page:</span></span>

    - <span data-ttu-id="b1564-114">Tillgångshantering \> Tillgångshantering mixed reality</span><span class="sxs-lookup"><span data-stu-id="b1564-114">Asset management \> Asset management mixed reality</span></span>
    - <span data-ttu-id="b1564-115">Mixed reality \> Mixed reality-guide</span><span class="sxs-lookup"><span data-stu-id="b1564-115">Mixed reality \> Mixed reality guide</span></span>

- <span data-ttu-id="b1564-116">[Ställ in Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 eller senare.</span><span class="sxs-lookup"><span data-stu-id="b1564-116">[Set up Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 or later.</span></span>

## <a name="use-dynamics-365-guides-with-asset-management"></a><span data-ttu-id="b1564-117">Använd Dynamics 365 Guides med tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="b1564-117">Use Dynamics 365 Guides with Asset management</span></span>

<span data-ttu-id="b1564-118">Om du vill associera en guide använder du en underhållschecklistrad i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="b1564-118">To associate a guide, you use a maintenance checklist line in Asset management.</span></span> <span data-ttu-id="b1564-119">Du kan skapa associeringen via en mall för checklista för underhåll, en underhållsjobbtyp eller en arbetsorder, eftersom alla tre innehåller underhållschecklistrader.</span><span class="sxs-lookup"><span data-stu-id="b1564-119">You can create the association through a maintenance checklist template, a maintenance job type, or a work order, because all three contain maintenance checklist lines.</span></span> <span data-ttu-id="b1564-120">Du kan spara tid genom att använda en mall, eftersom en mall kan associeras till alla typer av underhållsjobb som använder den.</span><span class="sxs-lookup"><span data-stu-id="b1564-120">You can save time by using a template, because a template can be associated with all the maintenance job types that use it.</span></span> <span data-ttu-id="b1564-121">En guide som är associerad med en underhållsjobbtyp kopplas till exempel automatiskt till alla arbetsorder som anger den jobbtypen.</span><span class="sxs-lookup"><span data-stu-id="b1564-121">For example, a guide that is associated with a maintenance job type is automatically associated with all work orders that specify that job type.</span></span> <span data-ttu-id="b1564-122">Å andra sidan finns en guide som är associerad direkt till en arbetsorder enbart för den aktuella arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="b1564-122">On the other hand, a guide that is associated directly with a work order exists only for that work order.</span></span>

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a><span data-ttu-id="b1564-123">Associera en guide med en mall för underhållschecklista</span><span class="sxs-lookup"><span data-stu-id="b1564-123">Associate a guide with a maintenance checklist template</span></span>

<span data-ttu-id="b1564-124">För att associera en guide med en mall för underhållschecklista ska du följa dessa steg.</span><span class="sxs-lookup"><span data-stu-id="b1564-124">To associate a guide with a maintenance checklist template, follow these steps.</span></span>

1. <span data-ttu-id="b1564-125">Skapa en guide med Dynamics 365 Guides för dator och HoloLens-apparna.</span><span class="sxs-lookup"><span data-stu-id="b1564-125">Create a guide by using the Dynamics 365 Guides PC and HoloLens apps.</span></span> <span data-ttu-id="b1564-126">För information om hur du skapar en guide, se följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="b1564-126">For information about how to create a guide, see the following topics:</span></span>

    - [<span data-ttu-id="b1564-127">Skapa guiden med hjälp av datorappen</span><span class="sxs-lookup"><span data-stu-id="b1564-127">Use the PC app to create a guide</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/pc-app-overview)
    - [<span data-ttu-id="b1564-128">Använd HoloLens-appen för att placera dina hologram</span><span class="sxs-lookup"><span data-stu-id="b1564-128">Use the HoloLens app to place your holograms</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-overview)

1. <span data-ttu-id="b1564-129">I Supply Chain Management [skapar du en mall för underhållschecklista](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span><span class="sxs-lookup"><span data-stu-id="b1564-129">In Supply Chain Management, [create a maintenance checklist template](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).</span></span>
1. <span data-ttu-id="b1564-130">Associera guiden som du skapade med en underhållschecklistrad i den nya mallen för underhållschecklista:</span><span class="sxs-lookup"><span data-stu-id="b1564-130">Associate the guide that you created with a maintenance checklist line in the new maintenance checklist template:</span></span>

    1. <span data-ttu-id="b1564-131">På snabbfliken **Underhållschecklistrader** markerar du raden som du vill associera guiden till.</span><span class="sxs-lookup"><span data-stu-id="b1564-131">On the **Maintenance checklist lines** FastTab, select the line that you want to associate the guide with.</span></span>
    1. <span data-ttu-id="b1564-132">På snabbfliken **Associerade guider** väljer du **Lägg till guide**.</span><span class="sxs-lookup"><span data-stu-id="b1564-132">On the **Associated guides** FastTab, select **Add Guide**.</span></span>

        <span data-ttu-id="b1564-133">![Associera en guide med en mall för underhållschecklistrad](media/am-guides-integration-add-guide.png "Associera en guide med en mall för underhållschecklistrad")</span><span class="sxs-lookup"><span data-stu-id="b1564-133">![Associate a guide with a maintenance checklist line](media/am-guides-integration-add-guide.png "Associate a guide with a maintenance checklist line")</span></span>

    1. <span data-ttu-id="b1564-134">I fältet **Namn** väljer du en guide och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1564-134">In the **Name** field, select a guide, and then select **Save**.</span></span>

        <span data-ttu-id="b1564-135">![Välj guide i fältet Namn](media/am-guides-integration-select-guide.png "Välj guide i fältet Namn")</span><span class="sxs-lookup"><span data-stu-id="b1564-135">![Select a guide in the Name field](media/am-guides-integration-select-guide.png "Select a guide in the Name field")</span></span>

1. <span data-ttu-id="b1564-136">Associera en mall för underhållschecklista med en jobbtyp:</span><span class="sxs-lookup"><span data-stu-id="b1564-136">Associate the maintenance checklist template with a job type:</span></span>

    1. <span data-ttu-id="b1564-137">[Skapa en underhållsjobbtyp](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) eller välj en befintlig underhållsjobbtyp.</span><span class="sxs-lookup"><span data-stu-id="b1564-137">[Create a maintenance job type](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type), or select an existing maintenance job type.</span></span>
    1. <span data-ttu-id="b1564-138">I åtgärdsfönstret väljer du **Standardinställningar för underhållsjobbtyp**.</span><span class="sxs-lookup"><span data-stu-id="b1564-138">On the Action Pane, select **Maintenance job type defaults**.</span></span>

        <span data-ttu-id="b1564-139">![Knappen standardinställningar för underhållsjobbtyp](media/am-guides-integration-job-defaults.png "Knappen standardinställningar för underhållsjobbtyp")</span><span class="sxs-lookup"><span data-stu-id="b1564-139">![Maintenance job type defaults button](media/am-guides-integration-job-defaults.png "Maintenance job type defaults button")</span></span>

    1. <span data-ttu-id="b1564-140">Skapa en rad och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1564-140">Create a line, and then select **Save**.</span></span>

        <span data-ttu-id="b1564-141">![Skapa en rad](media/am-guides-integration-add-line.png "Skapa en rad")</span><span class="sxs-lookup"><span data-stu-id="b1564-141">![Create a line](media/am-guides-integration-add-line.png "Create a line")</span></span>

    1. <span data-ttu-id="b1564-142">I åtgärdsfönstret klickar du på **Underhållschecklista**.</span><span class="sxs-lookup"><span data-stu-id="b1564-142">On the Action Pane, select **Maintenance checklist**.</span></span>

        <span data-ttu-id="b1564-143">![Knapp för underhållschecklista](media/am-guides-integration-maintenance-checklist.png "Knapp för underhållschecklista")</span><span class="sxs-lookup"><span data-stu-id="b1564-143">![Maintenance checklist button](media/am-guides-integration-maintenance-checklist.png "Maintenance checklist button")</span></span>

    1. <span data-ttu-id="b1564-144">På snabbfliken **Underhållschecklistrader** lägger du till en rad och ändrar sedan värdet i fältet **Typ** till **Mall**.</span><span class="sxs-lookup"><span data-stu-id="b1564-144">On the **Maintenance checklist lines** FastTab, add a line, and then change the value of the **Type** field to **Template**.</span></span>

        <span data-ttu-id="b1564-145">![Ändra värdet Typ](media/am-guides-integration-checklist-lines.png "Ändra värdet Typ")</span><span class="sxs-lookup"><span data-stu-id="b1564-145">![Change the Type value](media/am-guides-integration-checklist-lines.png "Change the Type value")</span></span>

    1. <span data-ttu-id="b1564-146">På snabbfliken **Raddetaljer** i fältet **Mall** väljer du den mall som du associerade guiden till och väljer **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b1564-146">On the **Line details** FastTab, in the **Template** field, select the template that you associated the guide with, and then select **Save**.</span></span>

        <span data-ttu-id="b1564-147">![Välj mall](media/am-guides-integration-checklist-line-details.png "Välj mall")</span><span class="sxs-lookup"><span data-stu-id="b1564-147">![Select the template](media/am-guides-integration-checklist-line-details.png "Select the template")</span></span>

1. <span data-ttu-id="b1564-148">[Skapa en arbetsorder](work-orders/manually-created-workorders.md#create-work-order) och välj sedan underhållsjobbtyp som använder den mall för underhållschecklista som du associerade guiden till.</span><span class="sxs-lookup"><span data-stu-id="b1564-148">[Create a work order](work-orders/manually-created-workorders.md#create-work-order), and then select the maintenance job type that uses the maintenance checklist template that you associated the guide with.</span></span> <span data-ttu-id="b1564-149">Guiden associeras automatiskt till arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="b1564-149">The guide is automatically associated with the work order.</span></span>

    <span data-ttu-id="b1564-150">![Välj underhållsjobbtyp](media/am-guides-integration-create-work-order.png "Välj underhållsjobbtyp")</span><span class="sxs-lookup"><span data-stu-id="b1564-150">![Select a maintenance job type](media/am-guides-integration-create-work-order.png "Select a maintenance job type")</span></span>

1. <span data-ttu-id="b1564-151">Visa den guide som är associerad till arbetsordern och arbetarna:</span><span class="sxs-lookup"><span data-stu-id="b1564-151">View the guide that is associated with the work order and workers:</span></span>

    1. <span data-ttu-id="b1564-152">Öppna [Arbetsytan för tillgångshantering](asset-management-mobile-workspace.md) för att komma åt arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="b1564-152">Open the [Asset management mobile workspace](asset-management-mobile-workspace.md) to access the work order.</span></span>
    1. <span data-ttu-id="b1564-153">[Öppna underhållschecklistan](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) för arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="b1564-153">[Open the maintenance checklist](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) for the work order.</span></span>
    1. <span data-ttu-id="b1564-154">Välj en checklistrad för att se associerad guide.</span><span class="sxs-lookup"><span data-stu-id="b1564-154">Select a checklist line to see the associated guide.</span></span>

        <span data-ttu-id="b1564-155">![Guide associerad till checklistarad](media/am-guides-integration-show-guide.png "Guide associerad till checklistrad")</span><span class="sxs-lookup"><span data-stu-id="b1564-155">![Guide associated with a checklist line](media/am-guides-integration-show-guide.png "Guide associated with a checklist line")</span></span>

    1. <span data-ttu-id="b1564-156">Öppna guiden i HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b1564-156">Open the guide on HoloLens.</span></span>

        <span data-ttu-id="b1564-157">![Öppna guiden i HoloLens](media/am-guides-integration-hololens-select.png "Öppna guiden i HoloLens")</span><span class="sxs-lookup"><span data-stu-id="b1564-157">![Open the guide on HoloLens](media/am-guides-integration-hololens-select.png "Open the guide on HoloLens")</span></span>

> [!NOTE]
> <span data-ttu-id="b1564-158">Du kan även associera en guide direkt i underhållschecklistan för en arbetsorder eller jobbtyp.</span><span class="sxs-lookup"><span data-stu-id="b1564-158">You can also associate a guide directly in the maintenance checklist of a work order or a job type.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1564-159">Det finns ett känt problem när du associerar en mall för underhållschecklista med en standard underhållsjobbtyp. Då visas inte guiden som är associerad till mallen på snabbfliken **Associerade guider** på sidan **Standardinställningar för underhållsjobbtyp**.</span><span class="sxs-lookup"><span data-stu-id="b1564-159">There is a known issue where, when you associate a maintenance checklist template with a default maintenance job type, the guide that is linked to the template doesn't appear on the **Associated guides** FastTab of the **Maintenance job type defaults** page.</span></span> <span data-ttu-id="b1564-160">Guiden visas dock när jobbtypen har tillämpats på en arbetsorder på snabbfliken **Associerade guider**.</span><span class="sxs-lookup"><span data-stu-id="b1564-160">However, the guide will appear after that job type is applied to a work order on the **Associated guides** FastTab.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1564-161">Se även</span><span class="sxs-lookup"><span data-stu-id="b1564-161">See also</span></span>

- [<span data-ttu-id="b1564-162">Översikt över dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="b1564-162">Dual-write overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [<span data-ttu-id="b1564-163">Översikt av tillgångshantering</span><span class="sxs-lookup"><span data-stu-id="b1564-163">Asset management overview</span></span>](index.md)
