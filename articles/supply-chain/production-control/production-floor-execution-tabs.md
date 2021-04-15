---
title: Designa körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du utformar innehållet i användargränssnittet för varje konfiguration.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 4e2b3746e690623e347e0319ab1b55f2645a5e23
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814690"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="04048-103">Designa körningsgränssnittet för produktionsgolvet</span><span class="sxs-lookup"><span data-stu-id="04048-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04048-104">Du kan utforma innehållet i användargränssnittet för varje konfiguration som används i gränssnittet för körning av produktionsstyrning.</span><span class="sxs-lookup"><span data-stu-id="04048-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="04048-105">Arbetstagarna i en arbetsgrupp kan t.ex. behöva öppna jobbinstruktioner på produktionsgolvet, medan det i en annan arbetsgrupp inte behövs.</span><span class="sxs-lookup"><span data-stu-id="04048-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="04048-106">I det fallet ska två konfigurationer skapas, en med en knapp för att öppna dokumentbilagor och en utan den här knappen.</span><span class="sxs-lookup"><span data-stu-id="04048-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="04048-107">Utforma en flik</span><span class="sxs-lookup"><span data-stu-id="04048-107">Design a tab</span></span>

<span data-ttu-id="04048-108">På sidan **Konfigurera körning av produktionsgolv** kan du skapa och konfigurera flikar genom att välja **Designa flikar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="04048-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="04048-109">Varje flik är uppdelad i fyra delar, som visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="04048-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="04048-110">![Fliklayout](media/pfe-tab-layout.png "Fliklayout")</span><span class="sxs-lookup"><span data-stu-id="04048-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="04048-111">Följande element visas i bilden:</span><span class="sxs-lookup"><span data-stu-id="04048-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="04048-112">Primärt verktygsfält</span><span class="sxs-lookup"><span data-stu-id="04048-112">Primary toolbar</span></span>
1. <span data-ttu-id="04048-113">Sekundärt verktygsfält</span><span class="sxs-lookup"><span data-stu-id="04048-113">Secondary toolbar</span></span>
1. <span data-ttu-id="04048-114">Huvudvy</span><span class="sxs-lookup"><span data-stu-id="04048-114">Main view</span></span>
1. <span data-ttu-id="04048-115">Detaljerad visning</span><span class="sxs-lookup"><span data-stu-id="04048-115">Detailed view</span></span>

<span data-ttu-id="04048-116">Följ stegen nedan om du vill skapa och konfigurera en ny flik:</span><span class="sxs-lookup"><span data-stu-id="04048-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="04048-117">Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.</span><span class="sxs-lookup"><span data-stu-id="04048-117">Go to **Production control \> Setup \> Manufacturing execution \> Configure production floor execution**.</span></span>

1. <span data-ttu-id="04048-118">Välj **Designa flikar** i åtgärdsfönstret för att **Designa flikar**.</span><span class="sxs-lookup"><span data-stu-id="04048-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="04048-119">![Sidan designa flikar](media/pfe-design-tabs.png "Sidan designa flikar")</span><span class="sxs-lookup"><span data-stu-id="04048-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="04048-120">Välj **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="04048-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="04048-121">Gör följande inställningar i sidans rubrik:</span><span class="sxs-lookup"><span data-stu-id="04048-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="04048-122">**Fliknamn** - Ange ett namn på fliken.</span><span class="sxs-lookup"><span data-stu-id="04048-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="04048-123">**Huvudvisning** - Välj mellan de två fördefinierade jobblistorna (*aktiva jobb*, *alla jobb* eller *min maskin*).</span><span class="sxs-lookup"><span data-stu-id="04048-123">**Main view** - Select between the two pre-defined job lists (*Active jobs*, *All jobs*, or *My machine*).</span></span>
    - <span data-ttu-id="04048-124">**Detaljvy** - Välj mellan ett tomt värde eller **jobbinformation**.</span><span class="sxs-lookup"><span data-stu-id="04048-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="04048-125">Om du väljer det tomma värdet visas ingen detaljerad vy på fliken. Om du väljer **jobbdetaljer** kommer den detaljerade vyn att innehålla en detaljerad beskrivning av det jobb som valts i jobblistan i huvudvyn.</span><span class="sxs-lookup"><span data-stu-id="04048-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="04048-126">I avsnittet för det **primära verktygsfältet** väljer du vilka knappar som ska vara tillgängliga i det primära verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="04048-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="04048-127">I kolumnen **tillgängliga åtgärder** visas en lista över alla knappar som kan läggas till.</span><span class="sxs-lookup"><span data-stu-id="04048-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="04048-128">I kolumnerna **Valda åtgärderna** visas en lista över alla knappar som ingår i den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="04048-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="04048-129">Använd knapparna mellan kolumnerna för att flytta de markerade objekten mellan de kolumner som behövs.</span><span class="sxs-lookup"><span data-stu-id="04048-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="04048-130">Använd knapparna upp och ned bredvid kolumnen **Valda åtgärder** om du vill styra i vilken ordning knapparna visas i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="04048-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="04048-131">I avsnittet för det **sekundära** **verktygsfältet** väljer du vilka knappar som ska vara tillgängliga i det sekundära verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="04048-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="04048-132">I kolumnen **tillgängliga åtgärder** visas en lista över alla knappar som kan läggas till.</span><span class="sxs-lookup"><span data-stu-id="04048-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="04048-133">I kolumnerna **Valda åtgärderna** visas en lista över alla knappar som ingår i den aktuella konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="04048-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="04048-134">Använd knapparna mellan kolumnerna för att flytta de markerade objekten mellan de kolumner som behövs.</span><span class="sxs-lookup"><span data-stu-id="04048-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="04048-135">Använd knapparna upp och ned bredvid kolumnen **Valda åtgärder** om du vill styra i vilken ordning knapparna visas i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="04048-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="04048-136">Associera en flik med en konfiguration</span><span class="sxs-lookup"><span data-stu-id="04048-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="04048-137">När du har skapat alla flikar du behöver kan du koppla dem till en konfiguration.</span><span class="sxs-lookup"><span data-stu-id="04048-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="04048-138">Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.</span><span class="sxs-lookup"><span data-stu-id="04048-138">Go to **Production control \> Setup \> Manufacturing execution \> Configure production floor execution**.</span></span>

    <span data-ttu-id="04048-139">![Konfigurera körning på produktionsgolv](media/pfe-config-prod-floor-execution.png "Konfigurera körning på produktionsgolv")</span><span class="sxs-lookup"><span data-stu-id="04048-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="04048-140">På snabbfliken **Val av flik** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04048-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="04048-141">En ny rad läggs till i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="04048-141">A new row is added to the grid.</span></span> <span data-ttu-id="04048-142">Markera namnet på en flik som du vill lägga till i konfigurationen för den nya raden.</span><span class="sxs-lookup"><span data-stu-id="04048-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="04048-143">Fortsätt att lägga till ytterligare flikar om det behövs.</span><span class="sxs-lookup"><span data-stu-id="04048-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="04048-144">Använd knapparna **Flytta upp** och **Flytta ned** i verktygsfältet om du vill ordna flikarna efter behov.</span><span class="sxs-lookup"><span data-stu-id="04048-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="04048-145">Flikarna visas från vänster till höger i den ordning som visas i ovanstående skärmdump (fliken längst upp visas till vänster).</span><span class="sxs-lookup"><span data-stu-id="04048-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]