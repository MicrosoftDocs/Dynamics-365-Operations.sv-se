---
title: Konfigurera ett menyalternativ för mobila enheter för att visa en översikt över plockrader
description: I det här avsnittet beskrivs hur du definierar när en lista med alla arbetsrader ska visas för lagerarbetare som bearbetar lagerarbetet på en mobil enhet. Den här funktionen kan vara användbar för lagerarbetare som ofta kräver en översikt över plockningsraderna i en arbetsorder så att de kan optimera sina plockserier.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 22e724b60ec5cc8bf39a520022f43784d3a328eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232921"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a><span data-ttu-id="341cb-104">Konfigurera ett menyalternativ för mobila enheter för att visa en översikt över plockrader</span><span class="sxs-lookup"><span data-stu-id="341cb-104">Set up a mobile device menu item to provide a pick line overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="341cb-105">I det här avsnittet beskrivs hur du konfigurerar alternativ som är relaterade till översikten över plockningsraden för menyalternativ för mobila enheter som används för att bearbeta plockningsarbete.</span><span class="sxs-lookup"><span data-stu-id="341cb-105">This topic explains how to configure options that are related to the pick line overview for mobile device menu items that are used to process picking work.</span></span> <span data-ttu-id="341cb-106">Plockningsradens översikt låter oss visa lagerarbetare och välja från en lista med alla arbetsrader som är kopplade till deras aktuella uppgift.</span><span class="sxs-lookup"><span data-stu-id="341cb-106">The pick line overview lets warehouse workers view and select from a list of all the work lines that are related to their current task.</span></span> <span data-ttu-id="341cb-107">Den här funktionen kan hjälpa arbetare att optimera sin plockserie.</span><span class="sxs-lookup"><span data-stu-id="341cb-107">This capability can help workers optimize their picking sequence.</span></span> <span data-ttu-id="341cb-108">Funktionen innehåller alternativ som ersätter standardknappen **Hoppa över** som gör att arbetarna går igenom raderna en i taget, i en fast ordning.</span><span class="sxs-lookup"><span data-stu-id="341cb-108">The feature provides options that replace the standard **Skip** button that lets workers cycle through the lines one at a time, in a fixed order.</span></span> <span data-ttu-id="341cb-109">(Alternativet att använda knappen är dock fortfarande tillgängligt.)</span><span class="sxs-lookup"><span data-stu-id="341cb-109">(However, the option to use that button is still available.)</span></span>

<span data-ttu-id="341cb-110">Administratörer kan konfigurera varje menyalternativ enskilt för att styra hur, när och var lagerstället ska visa översikten över plockningsraden.</span><span class="sxs-lookup"><span data-stu-id="341cb-110">Admins can configure each menu item individually to control how, when, and where the warehouse app presents the pick line overview.</span></span>

## <a name="turn-on-the-work-pick-line-overview-feature"></a><span data-ttu-id="341cb-111">Aktivera funktionen översikt över arbetsraddetaljer</span><span class="sxs-lookup"><span data-stu-id="341cb-111">Turn on the Work pick line overview feature</span></span>

<span data-ttu-id="341cb-112">Innan du kan använda den här funktionen den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="341cb-112">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="341cb-113">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="341cb-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="341cb-114">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="341cb-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="341cb-115">**Modul:** _Lagerstyrning_</span><span class="sxs-lookup"><span data-stu-id="341cb-115">**Module:** _Warehouse management_</span></span>
- <span data-ttu-id="341cb-116">**Funktionsnamn:** _Översikt över arbetsraddetaljer_</span><span class="sxs-lookup"><span data-stu-id="341cb-116">**Feature name:** _Work pick line overview_</span></span>

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a><span data-ttu-id="341cb-117">Konfigurera menyalternativ för att visa en lista över alla arbetsrader</span><span class="sxs-lookup"><span data-stu-id="341cb-117">Configure menu items to show a list of all work lines</span></span>

<span data-ttu-id="341cb-118">För att konfigurera ett menyalternativ för mobila enheter för att visa en översikt följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="341cb-118">To set up a mobile device menu item to provide a pick line overview, follow these steps.</span></span>

1. <span data-ttu-id="341cb-119">Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.</span><span class="sxs-lookup"><span data-stu-id="341cb-119">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="341cb-120">Välj eller skapa ett menyalternativ som är relaterat till plockningsarbete och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="341cb-120">Select or create a menu item that is related to picking work, and set the following values:</span></span>

    - <span data-ttu-id="341cb-121">**Läge:** *arbete*</span><span class="sxs-lookup"><span data-stu-id="341cb-121">**Mode:** *Work*</span></span>
    - <span data-ttu-id="341cb-122">**Använd befintligt arbete:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="341cb-122">**Use existing work:** *Yes*</span></span>
    - <span data-ttu-id="341cb-123">**Dirigeras av:** *Användardirigerad* eller *Systemdirigerad*</span><span class="sxs-lookup"><span data-stu-id="341cb-123">**Directed by:** *User directed* or *System directed*</span></span>

    <span data-ttu-id="341cb-124">Mer information om hur du skapar menyalternativ och använder de olika inställningar som finns på sidan **Menyalternativ på mobil enhet** finns i [Ställa in mobila enheter för lagerställe](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="341cb-124">For more information about how to create menu items and use the various settings that are available on the **Mobile device menu items** page, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>

1. <span data-ttu-id="341cb-125">På snabbfliken **Allmänt** konfigurerar du funktionen genom att ställa in fältet **Visa arbetsradlista** på något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="341cb-125">On the **General** FastTab, configure the feature by setting the **Show work line list** field to one of the following values:</span></span>

    - <span data-ttu-id="341cb-126">**Visa endast på begäran** – arbetare kan välja att visa listan över plockrader genom att välja knappen **Hoppa till** i modulen distributionslagerappen.</span><span class="sxs-lookup"><span data-stu-id="341cb-126">**Show only upon request** – Workers can choose to view the pick line list by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="341cb-127">**Visa i början av varje plockning** – arbetare ser listan varje gång de startar eller slutför en plockningsrad.</span><span class="sxs-lookup"><span data-stu-id="341cb-127">**Show at the start of every pick** – Workers see the list every time that they start or finish a pick line.</span></span> <span data-ttu-id="341cb-128">De kan också visa listan igen genom att välja knappen **Hoppa till** i modulen lagerställe.</span><span class="sxs-lookup"><span data-stu-id="341cb-128">They can also view the list again by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="341cb-129">**Visa endast i början av första plockningen** – Arbetare ser listan varje gång de påbörjar nytt plockningsarbete, men inte efter varje rad.</span><span class="sxs-lookup"><span data-stu-id="341cb-129">**Show at the start of the first pick only** – Workers see the list every time that they start new picking work, but not after each line.</span></span> <span data-ttu-id="341cb-130">De kan också visa listan igen genom att välja knappen **Hoppa till** i modulen lagerställe.</span><span class="sxs-lookup"><span data-stu-id="341cb-130">They can also view the list again by selecting the **Skip to** button in the warehouse app.</span></span>
    - <span data-ttu-id="341cb-131">**Visa aldrig** – standardknappen **Hoppa över** visas i distributionslagerappen och visningen av arbetsradlistan är inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="341cb-131">**Never show** – The standard **Skip** button appears in the warehouse app, and display of the work line list is turned off.</span></span> <span data-ttu-id="341cb-132">Knappen **Hoppa över** låter arbetarna gå igenom raderna en i taget, i en fast ordning.</span><span class="sxs-lookup"><span data-stu-id="341cb-132">The **Skip** button lets workers cycle through the lines one at a time, in a fixed order.</span></span> <span data-ttu-id="341cb-133">De kan också gå igenom listan så många gånger de behöver, tills alla rader har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="341cb-133">They can also cycle through the list as many times as they require, until all lines have been processed.</span></span>

1. <span data-ttu-id="341cb-134">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="341cb-134">On the Action Pane, select **Save**.</span></span>

    <span data-ttu-id="341cb-135">Om du ställer in fältet **Visa arbetsradlista** till ett värde utom *Visa aldrig* blir knappen **Fältlista** i åtgärdsfönstret tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="341cb-135">If you set the **Show work line list** field to any value except *Never show*, the **Field list** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="341cb-136">Klicka på **Fältlista** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="341cb-136">On the Action Pane, select **Field list**.</span></span>
1. <span data-ttu-id="341cb-137">På sidan **Fältlista** konfigurerar du den information som ska visas för varje rad i listan för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="341cb-137">On the **Field list** page, configure the information that the warehouse app shows for each line in the list.</span></span>

    - <span data-ttu-id="341cb-138">Fältet **primära kontroll** är alltid inställt på *LineNum*.</span><span class="sxs-lookup"><span data-stu-id="341cb-138">The **Primary control** field is always set to *LineNum*.</span></span> <span data-ttu-id="341cb-139">Därför börjar varje rad i listan med ett radnummer.</span><span class="sxs-lookup"><span data-stu-id="341cb-139">Therefore, each row in the list begins with a line number.</span></span>
    - <span data-ttu-id="341cb-140">Använd de återstående fälten **Visa fält** för att lägga till upp till sju ytterligare visningsfält efter behov.</span><span class="sxs-lookup"><span data-stu-id="341cb-140">Use the remaining **Display field** fields to add up to seven additional display fields, as you require.</span></span> <span data-ttu-id="341cb-141">I varje fält **Visningsfält** väljer du namnet på ett fält i arbetsraden.</span><span class="sxs-lookup"><span data-stu-id="341cb-141">In each **Display field** field, select the name of a work line field.</span></span> <span data-ttu-id="341cb-142">På varje rad visas sedan ett värde för det fältet.</span><span class="sxs-lookup"><span data-stu-id="341cb-142">Each line will then show a value for that field.</span></span> <span data-ttu-id="341cb-143">Värdena kommer att visas i den ordning du väljer här.</span><span class="sxs-lookup"><span data-stu-id="341cb-143">The values will be shown in the order that you select here.</span></span> <span data-ttu-id="341cb-144">Du kan lämna några av fälten **Visningsfält** tomma om du inte behöver alla sju värden.</span><span class="sxs-lookup"><span data-stu-id="341cb-144">You can leave some of the **Display field** fields blank if you don't require all seven values.</span></span>

1. <span data-ttu-id="341cb-145">I åtgärdsfönstret, välj **Spara** och stäng sedan sidan **Fältlista**.</span><span class="sxs-lookup"><span data-stu-id="341cb-145">On the Action Pane, select **Save**, and then close the **Field list** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]