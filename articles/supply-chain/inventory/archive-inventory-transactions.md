---
title: Arkivera lagertransaktioner
description: I det här avsnittet beskrivs hur du arkiverar data för lagertransaktioner för att förbättra systemets prestanda.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b740da1a8a349f4a1a80b41bf717c388fd3db0c0
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881842"
---
# <a name="archive-inventory-transactions"></a><span data-ttu-id="c8038-103">Arkivera lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="c8038-103">Archive inventory transactions</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c8038-104">Med tiden fortsätter lagertransaktionsregistret (`InventTrans`) att växa och förbruka mer databasutrymme.</span><span class="sxs-lookup"><span data-stu-id="c8038-104">Over time, the inventory transactions table (`InventTrans`) will continue to grow and consume more database space.</span></span> <span data-ttu-id="c8038-105">Därför kommer frågeställningar som görs mot registret att gradvis bli besvarade.</span><span class="sxs-lookup"><span data-stu-id="c8038-105">Therefore, queries that are made against the table will gradually become slower.</span></span> <span data-ttu-id="c8038-106">Det här ämnet beskriver användning av funktionen *arkiv för lagertransaktioner* för att arkivera data om lagertransaktioner för att förbättra systemets prestanda.</span><span class="sxs-lookup"><span data-stu-id="c8038-106">This topic describes how you can use the *Inventory transactions archive* feature to archive data about inventory transactions to help improve system performance.</span></span>

> [!NOTE]
> <span data-ttu-id="c8038-107">Endast ekonomiskt uppdaterade lagertransaktioner kan arkiveras i en vald stängd redovisningsperiod.</span><span class="sxs-lookup"><span data-stu-id="c8038-107">Only financially updated inventory transactions can be archived in a selected closed ledger period.</span></span> <span data-ttu-id="c8038-108">För att kunna arkiveras måste ekonomiskt uppdaterade utgående lagertransaktioner ha utleveransstatus *Såld* och inkommande lagertransaktioner måste ha inleveransstatus *Inköpt* .</span><span class="sxs-lookup"><span data-stu-id="c8038-108">To be archived, financially updated outbound inventory transactions must have an issue status of *Sold*, and inbound inventory transactions must have a receipt status of *Purchased*.</span></span>

<span data-ttu-id="c8038-109">När du arkiverar lagertransaktioner flyttas alla relaterade transaktioner till `InventTransArchive` registret.</span><span class="sxs-lookup"><span data-stu-id="c8038-109">When you archive inventory transactions, all related transactions are moved to the `InventTransArchive` table.</span></span> <span data-ttu-id="c8038-110">Transaktioner för lagerutleverans och lagerinleverans arkiveras separat baserat på kombinationen av artikel-ID (`itemId`) och lagerdimension-ID (`inventDimId`) och de placeras i den sammanfattade utgåvan och de sammanfattade inleveranstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="c8038-110">Inventory issue transactions and inventory receipt transactions are archived separately, based on the combination of the item ID (`itemId`) and inventory dimension ID (`inventDimId`), and they are put into the summarized issue and summarized receipt transactions.</span></span>

<span data-ttu-id="c8038-111">Om en `itemId` och `inventDimId` kombinationen bara innehåller en inleverans- eller utleveranstransaktion arkiveras inte transaktionen.</span><span class="sxs-lookup"><span data-stu-id="c8038-111">If an `itemId` and `inventDimId` combination contains only one receipt or issue transaction, the transaction won't be archived.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="c8038-112">Aktivera funktionen i systemet</span><span class="sxs-lookup"><span data-stu-id="c8038-112">Turn on the feature in your system</span></span>

<span data-ttu-id="c8038-113">Om ditt system inte redan innehåller de funktioner som beskrivs i det här avsnittet, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera funktionen *arkiv för lagertransaktioner*.</span><span class="sxs-lookup"><span data-stu-id="c8038-113">If your system doesn't already include the features that is described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Inventory transactions archive* feature.</span></span> <span data-ttu-id="c8038-114">Observera att denna funktion inte kan inaktiveras när den väl har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="c8038-114">Note that this feature cannot be disabled once it has been enabled.</span></span>

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a><span data-ttu-id="c8038-115">Saker du bör tänka på innan du arkiverar lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="c8038-115">Things to consider before you archive inventory transactions</span></span>

<span data-ttu-id="c8038-116">Innan du arkiverar lagertransaktioner bör du tänka på följande affärsscenarier eftersom de påverkas av operationen:</span><span class="sxs-lookup"><span data-stu-id="c8038-116">Before you archive inventory transactions, you should consider the following business scenarios, because they will be affected by the operation:</span></span>

- <span data-ttu-id="c8038-117">När du granskar lagertransaktioner från relaterade dokument, till exempel inköpsorderrader, visas de som arkiverade.</span><span class="sxs-lookup"><span data-stu-id="c8038-117">When you audit inventory transactions from related documents, such as purchase order lines, they will be shown as archived.</span></span> <span data-ttu-id="c8038-118">För att granska de arkiverade transaktionerna måste du gå till **Lagerhantering \> Periodiska uppgifter \> Rensa \> Arkiv lagertransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="c8038-118">To review the archived transactions, you must go to **Inventory management \> Periodic tasks \> Clean up \> Inventory transactions archive**.</span></span>
- <span data-ttu-id="c8038-119">Lagerstängning kan inte annulleras för arkiverade perioder.</span><span class="sxs-lookup"><span data-stu-id="c8038-119">Inventory closing can't be canceled for archived periods.</span></span> <span data-ttu-id="c8038-120">Innan du kan annullera en lagerstängning måste du återföra lagertransaktionsarkivet för den relevanta perioden.</span><span class="sxs-lookup"><span data-stu-id="c8038-120">Before you can cancel an inventory closing, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="c8038-121">Standardkostnadskonvertering kan inte göras för arkiverade perioder.</span><span class="sxs-lookup"><span data-stu-id="c8038-121">Standard cost conversion can't be done for archived periods.</span></span> <span data-ttu-id="c8038-122">Innan du kan göra standardkostnadskonvertering måste du återföra lagertransaktionsarkivet för den relevanta perioden.</span><span class="sxs-lookup"><span data-stu-id="c8038-122">Before you can do standard cost conversion, you must reverse the inventory transaction archive for the relevant period.</span></span>
- <span data-ttu-id="c8038-123">Lagerrapporter som kommer från lagertransaktioner påverkas när du arkiverar lagertransaktioner.</span><span class="sxs-lookup"><span data-stu-id="c8038-123">Inventory reports that are sourced from inventory transactions will be affected when you archive inventory transactions.</span></span> <span data-ttu-id="c8038-124">Dessa rapporter omfattar rapporten för lager åldersfördelning och lagervärderapporter.</span><span class="sxs-lookup"><span data-stu-id="c8038-124">These reports include the inventory aging report and inventory value reports.</span></span>
- <span data-ttu-id="c8038-125">Lagerprognoser kan påverkas om de körs under tidshorisonten för arkiverade perioder.</span><span class="sxs-lookup"><span data-stu-id="c8038-125">Inventory forecasts might be affected if they are run during the time horizon of archived periods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8038-126">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c8038-126">Prerequisites</span></span>

<span data-ttu-id="c8038-127">Lagertransaktioner kan bara arkiveras under perioder där följande villkor uppfylls:</span><span class="sxs-lookup"><span data-stu-id="c8038-127">Inventory transactions can be archived only during periods where the following conditions are met:</span></span>

- <span data-ttu-id="c8038-128">Redovisningsperioden måste vara stängd.</span><span class="sxs-lookup"><span data-stu-id="c8038-128">The ledger period must be closed.</span></span>
- <span data-ttu-id="c8038-129">Lagerstängningen måste köras på eller efter till-perioddatumet för arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-129">Inventory closing must be run on or after the to-period date of the archive.</span></span>
- <span data-ttu-id="c8038-130">Perioden måste vara minst ett år före arkivets från-perioddatum.</span><span class="sxs-lookup"><span data-stu-id="c8038-130">The period must be at least one year before the from-period date of the archive.</span></span>
- <span data-ttu-id="c8038-131">Inga befintliga lageromberäkningar får finnas.</span><span class="sxs-lookup"><span data-stu-id="c8038-131">There must not be any existing inventory recalculations.</span></span>

## <a name="archive-inventory-transactions"></a><span data-ttu-id="c8038-132">Arkivera lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="c8038-132">Archive inventory transactions</span></span>

<span data-ttu-id="c8038-133">Följ dessa steg för att arkivera inventeringstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="c8038-133">To archive inventory transactions, follow these steps.</span></span>

1. <span data-ttu-id="c8038-134">Gå till **Lagerhantering** \> **Periodiska uppgifter** \> **Rensa** \> **Lagertransaktionsarkiv**.</span><span class="sxs-lookup"><span data-stu-id="c8038-134">Go to **Inventory management** \> **Periodic tasks** \> **Clean up** \> **Inventory transaction archive**.</span></span>

    <span data-ttu-id="c8038-135">Sidan **Lagertransaktionsarkiv** visas och visar en lista med arkiverade processposter.</span><span class="sxs-lookup"><span data-stu-id="c8038-135">The **Inventory transactions archive** page appears and shows a list of archived process records.</span></span>

    <span data-ttu-id="c8038-136">![Sidan lagertransaktionsarkiv](media/archive-inventory-empty.png "Sidan lagertransaktionsarkiv")</span><span class="sxs-lookup"><span data-stu-id="c8038-136">![Inventory transactions archive page](media/archive-inventory-empty.png "Inventory transactions archive page")</span></span>

1. <span data-ttu-id="c8038-137">I åtgärdsfönstret, välj **Lagertransaktionsarkiv** om du vill skapa ett lagertransaktionsarkiv.</span><span class="sxs-lookup"><span data-stu-id="c8038-137">On the Action Pane, select **Inventory transactions archive** to create an inventory transaction archive.</span></span>
1. <span data-ttu-id="c8038-138">I dialogrutan **Lagertransaktionsarkiv** på snabbfliken **Parametrar** ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="c8038-138">In the **Inventory transactions archive** dialog box, on the **Parameters** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="c8038-139">**Från datum i stängd redovisningsperiod** – Välj det tidigaste transaktionsdatumet som ska inkluderas i arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-139">**From date in closed ledger period** – Select the earliest transaction date to include in the archive.</span></span>
    - <span data-ttu-id="c8038-140">**Till datum i stängd redovisningsperiod** – Välj det senaste transaktionsdatumet som ska inkluderas i arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-140">**To date in closed ledger period** – Select the latest transaction date to include in the archive.</span></span>

    <span data-ttu-id="c8038-141">![Dialogrutan lagertransaktionsarkiv](media/archive-inventory-dates.png "Dialogrutan lagertransaktionsarkiv")</span><span class="sxs-lookup"><span data-stu-id="c8038-141">![Inventory transactions archive dialog box](media/archive-inventory-dates.png "Inventory transactions archive dialog box")</span></span>

    > [!NOTE]
    > <span data-ttu-id="c8038-142">Endast perioder som uppfyller [kraven](#prerequisites) är tillgängliga för val.</span><span class="sxs-lookup"><span data-stu-id="c8038-142">Only periods that meet the [prerequisites](#prerequisites) will be available for selection.</span></span>

1. <span data-ttu-id="c8038-143">På snabbfliken **Kör i bakgrunden** ställer du in batchbearbetningsinformation efter behov.</span><span class="sxs-lookup"><span data-stu-id="c8038-143">On the **Run in the background** FastTab, set up batch processing details as you require.</span></span> <span data-ttu-id="c8038-144">Följ de vanligaste stegen för batchjobb i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c8038-144">Follow the usual steps for batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="c8038-145">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8038-145">Select **OK**.</span></span>
1. <span data-ttu-id="c8038-146">Du får ett meddelande som uppmanar dig att bekräfta att du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="c8038-146">You receive a message that prompts you to confirm that you want to continue.</span></span> <span data-ttu-id="c8038-147">Läs meddelandet noggrant och välj sedan **Ja** om du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="c8038-147">Read the message carefully, and then select **Yes** if you want to continue.</span></span>

    <span data-ttu-id="c8038-148">Du får ett meddelande om att dina lagertransaktioner arkivjobb har lagts till i batchkön.</span><span class="sxs-lookup"><span data-stu-id="c8038-148">You receive a message that states that your inventory transactions archive job has been added to the batch queue.</span></span> <span data-ttu-id="c8038-149">Jobbet börjar nu att arkivera lagertransaktioner från den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="c8038-149">The job will now start to archive inventory transactions from the selected period.</span></span>

## <a name="view-archived-inventory-transactions"></a><span data-ttu-id="c8038-150">Visa arkiverade lagertransaktioner</span><span class="sxs-lookup"><span data-stu-id="c8038-150">View archived inventory transactions</span></span>

<span data-ttu-id="c8038-151">Sidan **lagertransaktionsarkiv** visar hela arkiveringshistoriken.</span><span class="sxs-lookup"><span data-stu-id="c8038-151">The **Inventory transactions archive** page shows your full archiving history.</span></span> <span data-ttu-id="c8038-152">Varje rad i rutnätet visar information som t.ex. datum då arkivet skapades, användaren som skapade det och dess status.</span><span class="sxs-lookup"><span data-stu-id="c8038-152">Each row in the grid shows information such as the date when the archive was created, the user who created it, and its status.</span></span>

<span data-ttu-id="c8038-153">![Arkiveringshistorik på sidan en lagertransaktionsarkiv](media/archive-inventory-full.png "Arkiveringshistorik på sidan en lagertransaktionsarkiv")</span><span class="sxs-lookup"><span data-stu-id="c8038-153">![Archiving history on the Inventory transactions archive page](media/archive-inventory-full.png "Archiving history on the Inventory transactions archive page")</span></span>

<span data-ttu-id="c8038-154">Välj ett av följande värden i listrutan högst upp på sidan för att filtrera de arkiv som visas i rutnätet:</span><span class="sxs-lookup"><span data-stu-id="c8038-154">In the drop-down list at the top of the page select one of the following values to filter the archives that are shown in the grid:</span></span>

- <span data-ttu-id="c8038-155">**Aktiv** – Visa endast aktiva arkiv, inte återförda arkiv.</span><span class="sxs-lookup"><span data-stu-id="c8038-155">**Active** – Show only active archives, not reversed archives.</span></span>
- <span data-ttu-id="c8038-156">**Alla** – Visa alla arkiv, både aktiva och återförda.</span><span class="sxs-lookup"><span data-stu-id="c8038-156">**All** – Show all archives, both active and reversed.</span></span>

<span data-ttu-id="c8038-157">För varje arkiv i rutnätet finns följande information:</span><span class="sxs-lookup"><span data-stu-id="c8038-157">For each archive in the grid, the following information is provided:</span></span>

- <span data-ttu-id="c8038-158">**Aktiv** – En bockmarkering anger att arkivet är aktivt.</span><span class="sxs-lookup"><span data-stu-id="c8038-158">**Active** – A check mark indicates that the archive is active.</span></span>
- <span data-ttu-id="c8038-159">**Från datum** – Datumet för den äldsta transaktionen som kan inkluderas i arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-159">**From date** – The date of the oldest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="c8038-160">**Till datum** – Datumet för den senaste transaktionen som kan inkluderas i arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-160">**To date** – The date of the latest transaction that can be included in the archive.</span></span>
- <span data-ttu-id="c8038-161">**Tidsplanerad av** – Användarkontot som skapade arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-161">**Scheduled by** – The user account that created the archive.</span></span>
- <span data-ttu-id="c8038-162">**Utförd** – Datum då arkivet skapades.</span><span class="sxs-lookup"><span data-stu-id="c8038-162">**Executed** – The date when the archive was created.</span></span>
- <span data-ttu-id="c8038-163">**Återför** – En bockmarkering indikerar att arkivet har återförts.</span><span class="sxs-lookup"><span data-stu-id="c8038-163">**Reverse** – A check mark indicates that the archive has been reversed.</span></span>
- <span data-ttu-id="c8038-164">**Stoppa aktuell uppdatering** – En bockmarkering anger att arkivet pågår, men att det har pausats.</span><span class="sxs-lookup"><span data-stu-id="c8038-164">**Stop current update** – A check mark indicates that the archive is in progress, but it has been paused.</span></span>
- <span data-ttu-id="c8038-165">**Tillstånd** – Arkivets bearbetningsstatus.</span><span class="sxs-lookup"><span data-stu-id="c8038-165">**State** – The processing status of the archive.</span></span> <span data-ttu-id="c8038-166">De möjliga värdena är *Väntar*, *Pågår* och *Slutförd*.</span><span class="sxs-lookup"><span data-stu-id="c8038-166">The possible values are *Waiting*, *In progress*, and *Finished*.</span></span>

<span data-ttu-id="c8038-167">Verktygsfältet ovanför rutnätet innehåller följande knappar som du använder när du arbetar med ett valt arkiv:</span><span class="sxs-lookup"><span data-stu-id="c8038-167">The toolbar above the grid provides the following buttons that you can use to work with a selected archive:</span></span>

- <span data-ttu-id="c8038-168">**Arkiverade transaktioner** – Visa fullständiga detaljer om det valda arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-168">**Archived transactions** – View the full details of the selected archive.</span></span> <span data-ttu-id="c8038-169">Sidan **Arkiverade transaktioner** visar alla transaktioner i arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-169">The **Archived transactions** page that appears shows all the transactions in the archive.</span></span>

    <span data-ttu-id="c8038-170">![Sidan Arkiverade transaktioner](media/archive-inventory-transactions.png "Sidan Arkiverade transaktioner")</span><span class="sxs-lookup"><span data-stu-id="c8038-170">![Archived transactions page](media/archive-inventory-transactions.png "Archived transactions page")</span></span>

    <span data-ttu-id="c8038-171">För att få mer information om en viss transaktion på sidan **Arkiverade transaktioner** markerar du den i rutnätet och väljer sedan **Information om arkiverade transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="c8038-171">To view more information about a specific transaction on the **Archived transactions** page, select it in the grid, and then, on the Action Pane, select **Archived transaction details**.</span></span> <span data-ttu-id="c8038-172">Sidan **Information om arkiverade transaktioner** som visas kommer att visa information som redovisningsbokföring, relaterade redovisningsreferenser och ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="c8038-172">The **Archived transaction details** page that appears shows information such as the ledger posting, related subledger references, and financial dimensions.</span></span>

- <span data-ttu-id="c8038-173">**Göra paus i arkivering** – Pausa ett valt arkiv som bearbetas just nu.</span><span class="sxs-lookup"><span data-stu-id="c8038-173">**Pause archiving** – Pause a selected archive that is currently being processed.</span></span> <span data-ttu-id="c8038-174">Pausen gäller bara efter det att arkiveringsuppgiften har genererats.</span><span class="sxs-lookup"><span data-stu-id="c8038-174">The pause takes effect only after the archiving task has been generated.</span></span> <span data-ttu-id="c8038-175">Därför kan det ta en kort tid innan pausen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="c8038-175">Therefore, there might be a short delay before the pause takes effect.</span></span> <span data-ttu-id="c8038-176">Om ett arkiv har pausats visas en bockmarkering i fältet **Stoppa aktuell uppdatering**.</span><span class="sxs-lookup"><span data-stu-id="c8038-176">If an archive has been paused, a check mark appears in its **Stop current update** field.</span></span>
- <span data-ttu-id="c8038-177">**Återuppta arkivering** – Återuppta bearbetning för ett valt arkiv som pausas just nu.</span><span class="sxs-lookup"><span data-stu-id="c8038-177">**Resume archiving** – Resume processing for a selected archive that is currently paused.</span></span>
- <span data-ttu-id="c8038-178">**Återför** – Återför det valda arkivet.</span><span class="sxs-lookup"><span data-stu-id="c8038-178">**Reverse** – Reverse the selected archive.</span></span> <span data-ttu-id="c8038-179">Du kan bara återföra ett arkiv om dess **Tillstånd** anges till *Slutförd*.</span><span class="sxs-lookup"><span data-stu-id="c8038-179">You can reverse an archive only if its **State** field is set to *Finished*.</span></span> <span data-ttu-id="c8038-180">Om ett arkiv har återställas visas en bockmarkering i fältet **återställa**.</span><span class="sxs-lookup"><span data-stu-id="c8038-180">If an archive has been reversed, a check mark appears in its **Reverse** field.</span></span>
