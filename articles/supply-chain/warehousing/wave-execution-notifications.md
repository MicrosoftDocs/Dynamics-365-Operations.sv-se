---
title: Meddelanden för påfyllnadskörning
description: Det här ämnet beskriver meddelande om påfyllnadskörning och förklarar hur du ställer in det.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 47f270b5fff37e8e231d8a9c4a011172df3d9385
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271387"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="ec59f-103">Meddelanden för påfyllnadskörning</span><span class="sxs-lookup"><span data-stu-id="ec59f-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec59f-104">Funktionen *Meddelande påfyllnadskörning* använder affärshändelser och åtgärdscenter för att leverera meddelanden som är relaterade till påfyllnadskörning.</span><span class="sxs-lookup"><span data-stu-id="ec59f-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="ec59f-105">Där kan du ange vilka typer av händelser som genererar meddelanden, vilka lagerställen som genererar dem och vilka användare som tar emot dem.</span><span class="sxs-lookup"><span data-stu-id="ec59f-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="ec59f-106">Knappen **Visa meddelanden** (klocksymbol) till höger om navigeringsfältet anger när ett åtgärdscenter meddelande är tillgängligt för den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="ec59f-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="ec59f-107">Användaren kan välja knappen **Visa meddelanden** om du vill öppna Åtgärdscentret och granska meddelandena.</span><span class="sxs-lookup"><span data-stu-id="ec59f-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="ec59f-108">Affärshändelser inträffar när affärsprocesser körs.</span><span class="sxs-lookup"><span data-stu-id="ec59f-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="ec59f-109">Affärsprocesser består av uppgifter.</span><span class="sxs-lookup"><span data-stu-id="ec59f-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="ec59f-110">Under en affärsprocess utför de användare som deltar i den affärsåtgärder för att slutföra dessa uppgifter.</span><span class="sxs-lookup"><span data-stu-id="ec59f-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="ec59f-111">Affärshändelser innehåller en mekanism som gör att externa system kan ta emot meddelanden från Finance and Operations-program.</span><span class="sxs-lookup"><span data-stu-id="ec59f-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="ec59f-112">På det här sättet kan systemen utföra affärsåtgärder som svar på affärshändelser.</span><span class="sxs-lookup"><span data-stu-id="ec59f-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="ec59f-113">Mer information finns i [Översikt över affärshändelser](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="ec59f-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="ec59f-114">Aktivera funktionen meddelande om påfyllnadskörning</span><span class="sxs-lookup"><span data-stu-id="ec59f-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="ec59f-115">Innan du kan använda funktionen *meddelande om påfyllnadskörning* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="ec59f-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="ec59f-116">Administratörer kan använda arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ec59f-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ec59f-117">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ec59f-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ec59f-118">**Modul:** *Warehouse management*</span><span class="sxs-lookup"><span data-stu-id="ec59f-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ec59f-119">**Funktionsnamn:** *meddelande om påfyllnadskörning*</span><span class="sxs-lookup"><span data-stu-id="ec59f-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="ec59f-120">Scenario: Skicka meddelanden för batchkörning för påfyllnad till åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="ec59f-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="ec59f-121">I det här scenariot visas det kompletta flödet för utskick av meddelanden om körningsfel för påfyllnadsbatchen till en viss roll via Åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="ec59f-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="ec59f-122">Gör demodata tillgängliga</span><span class="sxs-lookup"><span data-stu-id="ec59f-122">Make demo data available</span></span>

<span data-ttu-id="ec59f-123">För att följa detta scenario måste du ha demonstrationsdata installerad och du måste välja juridiska personen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="ec59f-124">Kontrollera att påfyllnader körs i batchläge</span><span class="sxs-lookup"><span data-stu-id="ec59f-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="ec59f-125">Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="ec59f-126">På snabbfliken **Påfyllnadsbearbetning**, ange alternativet **Behandla påfyllnader i batch** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="ec59f-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="ec59f-127">Om du vill inaktivera meddelanden om exekvering av påfyllnadsbatch, ställ in **Inaktivera batchmeddelanden för påfyllnadsbehandling** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="ec59f-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="ec59f-128">Konfigurera en policy för påfyllnadsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="ec59f-128">Configure a wave notification policy</span></span>

<span data-ttu-id="ec59f-129">Policyer för påfyllnadsmeddelanden definierar vilka typer av meddelanden som skickas och vilka användare som meddelas.</span><span class="sxs-lookup"><span data-stu-id="ec59f-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="ec59f-130">Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Policyer för påfyllnadsmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="ec59f-131">Skapa en post med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ec59f-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="ec59f-132">**Policy påfyllnadsmeddelanden:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="ec59f-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="ec59f-133">**Beskrivning:** *Batchfel för lagerställe 24*</span><span class="sxs-lookup"><span data-stu-id="ec59f-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="ec59f-134">**Skicka meddelande om:** *Endast fel*</span><span class="sxs-lookup"><span data-stu-id="ec59f-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="ec59f-135">**Till rollen:** *Systemadministratör*</span><span class="sxs-lookup"><span data-stu-id="ec59f-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="ec59f-136">Eftersom detta scenario använder demodata väljs rollen *Systemadministratör* för enkelhetens skull.</span><span class="sxs-lookup"><span data-stu-id="ec59f-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="ec59f-137">Eftersom du är inloggad som systemadministratör får du därför meddelandena.</span><span class="sxs-lookup"><span data-stu-id="ec59f-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="ec59f-138">I praktiken bör du dock vanligtvis välja en mer specifik roll för att meddela om körningsfel för påfyllnadsbatchen, t.ex. *Warehouse management*.</span><span class="sxs-lookup"><span data-stu-id="ec59f-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="ec59f-139">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ec59f-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="ec59f-140">Konfigurera en påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="ec59f-140">Configure a wave template</span></span>

<span data-ttu-id="ec59f-141">Med påfyllnadsmallar kan du länka specifika förekomster av påfyllnadsmetoder till en motsvarande påfyllnadsetikettsmallar.</span><span class="sxs-lookup"><span data-stu-id="ec59f-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="ec59f-142">Gå till **Warehouse management \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="ec59f-143">I listrutan, ange fältet **Malltyp för påfyllnad** till *Leverans* och väljer sedan påfyllnadsmallen *24 leveransstandard* för lagerställe 24.</span><span class="sxs-lookup"><span data-stu-id="ec59f-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="ec59f-144">På snabbfliken **Allmänt** ställer du in fältet **Policy påfyllnadsmeddelanden** till *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="ec59f-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="ec59f-145">Konfigurera en arbetsmall</span><span class="sxs-lookup"><span data-stu-id="ec59f-145">Configure a work template</span></span>

<span data-ttu-id="ec59f-146">Arbetsmallar används under påfyllnadskörningen för att generera arbete.</span><span class="sxs-lookup"><span data-stu-id="ec59f-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="ec59f-147">I det här scenariot ska ett fel utlösas av påfyllnadskörningen.</span><span class="sxs-lookup"><span data-stu-id="ec59f-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="ec59f-148">Genom att ställa in arbetsmallfrågan till att använda ett lagerställe som inte finns, ser du till att påfyllnadskörningen misslyckas och skickar därför ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="ec59f-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="ec59f-149">Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsmallar**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="ec59f-150">I listrutan, ange fältet **Malltyp för arbete** till *Försäljningsorder* och väljer sedan arbetsmallen *24 SO steg* för lagerställe 24.</span><span class="sxs-lookup"><span data-stu-id="ec59f-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="ec59f-151">I åtgärdsfönstret väljer du **Redigera fråga**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="ec59f-152">I dialogrutan för frågeredigeraren, på fliken **Intervall** redigera följande rad (eller lägg till det om det inte finns):</span><span class="sxs-lookup"><span data-stu-id="ec59f-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="ec59f-153">**Tabell:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="ec59f-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="ec59f-154">**Härlett register:** *Tillfälliga arbetstransaktioner*</span><span class="sxs-lookup"><span data-stu-id="ec59f-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="ec59f-155">**Fält:** *lagerställe*</span><span class="sxs-lookup"><span data-stu-id="ec59f-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="ec59f-156">**Kriterier:** Ändra värdet från *24* till *Fel*.</span><span class="sxs-lookup"><span data-stu-id="ec59f-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="ec59f-157">Välj **OK** och bekräfta ändringen.</span><span class="sxs-lookup"><span data-stu-id="ec59f-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="ec59f-158">Skapa en försäljningsorder och släpp den på lagerstället</span><span class="sxs-lookup"><span data-stu-id="ec59f-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="ec59f-159">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="ec59f-160">Skapa en försäljningsorder med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ec59f-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="ec59f-161">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="ec59f-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="ec59f-162">**Lagerställe:** *24*</span><span class="sxs-lookup"><span data-stu-id="ec59f-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="ec59f-163">På snabbfliken **försäljningsorderrader** lägger du till en försäljningsorderrad som har följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ec59f-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="ec59f-164">**Artikelnummer:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ec59f-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ec59f-165">**Kvantitet:** *10*</span><span class="sxs-lookup"><span data-stu-id="ec59f-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec59f-166">Dessa artiklar och kvantiteter är bara exempel.</span><span class="sxs-lookup"><span data-stu-id="ec59f-166">These items and quantities are only examples.</span></span> <span data-ttu-id="ec59f-167">De måste ha lager i det angivna lagerstället.</span><span class="sxs-lookup"><span data-stu-id="ec59f-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="ec59f-168">Medan den nya raden fortfarande är markerad på snabbfliken **Försäljningsorderrader**, välj **Lager \> Reservation** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="ec59f-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="ec59f-169">På sidan **Reservation** i åtgärdssfönstret väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="ec59f-170">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ec59f-170">Then close the page.</span></span>
1. <span data-ttu-id="ec59f-171">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="ec59f-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="ec59f-172">Meddelanden från körning av batchjobb för påfyllnad</span><span class="sxs-lookup"><span data-stu-id="ec59f-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="ec59f-173">Beroende på inställningarna för dina affärshändelser kommer du så småningom att få ett meddelande om fel vid påfyllnadskörningen.</span><span class="sxs-lookup"><span data-stu-id="ec59f-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="ec59f-174">Meddelandet i åtgärdscenter liknar följande exempel och innehåller en länk till den påfyllnaden som misslyckades.</span><span class="sxs-lookup"><span data-stu-id="ec59f-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="ec59f-175">**Fel under påfyllnadskörning**</span><span class="sxs-lookup"><span data-stu-id="ec59f-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="ec59f-176">Ett fel uppstod vid körning av påfyllnaden USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="ec59f-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="ec59f-177">De senaste meddelandena: Inget arbete skapades för påfyllnaden USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="ec59f-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="ec59f-178">**STATUS**</span><span class="sxs-lookup"><span data-stu-id="ec59f-178">**STATUS**</span></span>  
> <span data-ttu-id="ec59f-179">Aktiva</span><span class="sxs-lookup"><span data-stu-id="ec59f-179">Active</span></span>
>
> <span data-ttu-id="ec59f-180">Öppna påfyllnadsinformation</span><span class="sxs-lookup"><span data-stu-id="ec59f-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
