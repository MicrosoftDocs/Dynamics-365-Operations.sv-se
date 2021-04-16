---
title: Lagerpåfyllnad över platskapacitet
description: Det här avsnittet innehåller information om funktionen påfyllnad över lagerställekapacitet. Den här funktionen gör att allt påfyllningsarbete som krävs för dagen skapas och kan användas för att se till att plockplatsen varken hamnar utanför lagret eller går över kapacitet.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 309df56671bf258e1669ae6d5393de01e2b500f0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823249"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="1f27a-104">Lagerpåfyllnad över platskapacitet</span><span class="sxs-lookup"><span data-stu-id="1f27a-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f27a-105">Vissa lagerställen med hög volym eller begränsat utrymme måste leverera mer kvantitet av en artikel på en dag än vad som får plats på plockplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="1f27a-106">Funktionen *påfyllnad över lagerställekapacitey* gör att allt påfyllningsarbete som krävs för dagen skapas och kan användas för att se till att plockplatsen varken hamnar utanför lagret eller går över kapacitet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="1f27a-107">Funktionen gör det möjligt att skapa mer återanskaffningsarbete än vad som får plats på en plats och det blockerar påfyllningsarbetet från att slutföras när platsen är full.</span><span class="sxs-lookup"><span data-stu-id="1f27a-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="1f27a-108">När lagret på plockplatsen sjunker under ett konfigurerbart tröskelvärde görs mer återanskaffningsarbete tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="1f27a-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="1f27a-109">Aktivera funktionen påfyllnad över lagerställekapacitet</span><span class="sxs-lookup"><span data-stu-id="1f27a-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="1f27a-110">Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:</span><span class="sxs-lookup"><span data-stu-id="1f27a-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="1f27a-111">Arbetsspärr för hela organisationen</span><span class="sxs-lookup"><span data-stu-id="1f27a-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="1f27a-112">Lagerpåfyllnad över platskapacitet</span><span class="sxs-lookup"><span data-stu-id="1f27a-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="1f27a-113">Ställ in funktionen för det här exempelscenariot</span><span class="sxs-lookup"><span data-stu-id="1f27a-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="1f27a-114">Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du ställer in den här funktionen och förbereder exempeldata för scenariot som ges senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="1f27a-115">Aktivera exempeldata</span><span class="sxs-lookup"><span data-stu-id="1f27a-115">Enable sample data</span></span>

<span data-ttu-id="1f27a-116">Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats.</span><span class="sxs-lookup"><span data-stu-id="1f27a-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="1f27a-117">Dessutom måste du välja den **USMF** juridiska personen innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="1f27a-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="1f27a-118">Platsprofiler</span><span class="sxs-lookup"><span data-stu-id="1f27a-118">Location profile</span></span>

<span data-ttu-id="1f27a-119">Aktivera funktionen för påfyllning över kapacitet på platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="1f27a-120">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="1f27a-121">Markera **PICK-06** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="1f27a-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="1f27a-122">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1f27a-123">Ange följande värden på snabbfliken **lagerpåfyllnad**:</span><span class="sxs-lookup"><span data-stu-id="1f27a-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="1f27a-124">**Överskriden kapacitet för plats:** *ja*</span><span class="sxs-lookup"><span data-stu-id="1f27a-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="1f27a-125">När den aktiveras blir platsens maxkapacitet tillåten att överskridas med påfyllnadsarbete.</span><span class="sxs-lookup"><span data-stu-id="1f27a-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="1f27a-126">Detta aktiverar även andra fält på snabbfliken **lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="1f27a-127">**Tröskeltyp för arbetstillgänglighet:** *kvantitet*</span><span class="sxs-lookup"><span data-stu-id="1f27a-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="1f27a-128">I det här fältet anges den metod som används för att bestämma när mer arbete ska frisläppas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="1f27a-129">Du kan släppa antingen kvantitet eller procent:</span><span class="sxs-lookup"><span data-stu-id="1f27a-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="1f27a-130">*Procent* – Välj det här alternativet om du vill använda procentkapacitet som baseras på lagergränser eller volymmetriker.</span><span class="sxs-lookup"><span data-stu-id="1f27a-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="1f27a-131">Om du väljer det här alternativet aktiveras fältet **Överfyllnadsprocent** och inaktiverar de två kvantitetsrelaterade fälten,  **Överfyllnadskvantitet** och **Överfyllnadsenhet**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="1f27a-132">Du kan använda det här alternativet om plockplatserna använder volymmetriker.</span><span class="sxs-lookup"><span data-stu-id="1f27a-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="1f27a-133">Om det här alternativet är markerat ställer du in **Överfyllnadsprocent** för den procentsats som ytterligare påfyllningsarbete kommer att göras tillgängligt för.</span><span class="sxs-lookup"><span data-stu-id="1f27a-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="1f27a-134">*Kvantitet* – Välj det här alternativet om du vill använda ett specifikt värde för kvantitet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="1f27a-135">Om du väljer det här alternativet inaktiveras fältet **Överfyllnadsprocent** och aktiverar fälten **Överfyllnadskvantitet** och **Överfyllnadsenhet**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="1f27a-136">Använd det här alternativet om du inte använder volymmetriker för de platser som ska fyllas på, eller när du har enhetliga kvantiteter som du vill att mer lager ska skickas till.</span><span class="sxs-lookup"><span data-stu-id="1f27a-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="1f27a-137">Om det här alternativet är markerat ställer du in fälten **Överfyllnadskvantitet** och **Överfyllnadsenhet** till kvantitet och enhet där mer påfyllningsarbete kommer att göras tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="1f27a-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="1f27a-138">**Överfyllnadskvantitet:** *0.65*</span><span class="sxs-lookup"><span data-stu-id="1f27a-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="1f27a-139">Det här fältet anger den kvantitet där vilken platsen överfylls.</span><span class="sxs-lookup"><span data-stu-id="1f27a-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="1f27a-140">Arbetet kommer att finnas tillgängligt när summan av den tillgängliga kvantiteten på platsen och arbetskvantiteten ligger under detta värde.</span><span class="sxs-lookup"><span data-stu-id="1f27a-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="1f27a-141">Eventuell kvantitet för påfyllningsarbete som är över detta värde spärras och måste avblockeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="1f27a-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="1f27a-142">Platslagergränser beaktas när arbetskvantiteten beräknas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="1f27a-143">**Överfyllnadsenhet:** *PL*</span><span class="sxs-lookup"><span data-stu-id="1f27a-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="1f27a-144">Det här fältet definierar den enhet som är kopplad till överfyllnadskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1f27a-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="1f27a-145">I det här fallet görs mer lagerpåfyllnadsarbete när platsen kommer ner till 0,65 lastpall (PL).</span><span class="sxs-lookup"><span data-stu-id="1f27a-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="1f27a-146">**Överfyllnad i procent**</span><span class="sxs-lookup"><span data-stu-id="1f27a-146">**Overflow percentage**</span></span>

        <span data-ttu-id="1f27a-147">Det här fältet anger den procentsats där platsen överfylls.</span><span class="sxs-lookup"><span data-stu-id="1f27a-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="1f27a-148">Arbetet kommer att finnas tillgängligt när summan av den tillgängliga kvantiteten på platsen och arbetskvantiteten ligger under denna procentsats.</span><span class="sxs-lookup"><span data-stu-id="1f27a-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="1f27a-149">Eventuell kvantitet för påfyllningsarbete som är procentsats över detta värde spärras och måste avblockeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="1f27a-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="1f27a-150">Platslagergränser beaktas när arbetskvantitetens procentsats beräknas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="1f27a-151">Om inga platslagringsgränser anges beräknas den procentuella kvantiteten av volym om volymbegränsningar definieras i platsprofilen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f27a-152">Om du använder demodata för juridiska personen **USMF** och tidigare aktiverat funktionen för positionering av funktionen *Placering för plats-ID-nummer* måste du stänga inställningen **Aktivera plats för positionering av ID-nummer** för platsprofilen **BULK-06** för att slutföra de mobila stegen i exempelscenariot.</span><span class="sxs-lookup"><span data-stu-id="1f27a-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="1f27a-153">Kod för påfyllnadssteg</span><span class="sxs-lookup"><span data-stu-id="1f27a-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="1f27a-154">Om du vill ställa in en påfyllnadskod som beskrivs här, kanske du först måste använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen med namnet *Påfyllnadsstegkod för hela organisationen*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="1f27a-155">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Koder för påfyllnadssteg**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="1f27a-156">Välj **ny** och ange sedan följande värden:</span><span class="sxs-lookup"><span data-stu-id="1f27a-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="1f27a-157">**Kod för påfyllnadssteg:** *lagerp*</span><span class="sxs-lookup"><span data-stu-id="1f27a-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="1f27a-158">**Beskrivning för påfyllnadssteg:** *lagerpåfyllnad*</span><span class="sxs-lookup"><span data-stu-id="1f27a-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="1f27a-159">**Typ av påfyllnadssteg:** *lagerpåfyllnad*</span><span class="sxs-lookup"><span data-stu-id="1f27a-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="1f27a-160">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="1f27a-161">Mall för lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="1f27a-161">Replenishment template</span></span>

<span data-ttu-id="1f27a-162">Mallar för lagerpåfyllnad är en uppsättning regler som kontrollerar hur en plats fylls på.</span><span class="sxs-lookup"><span data-stu-id="1f27a-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="1f27a-163">Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mall för lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="1f27a-164">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1f27a-165">I avsnittet **Översikt** väljer du den rad där fältet **Lagerpåfyllnadsmall** anges till *Efterfrågan av lagerpåfyllnad*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="1f27a-166">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="1f27a-166">Set the following values:</span></span>

    - <span data-ttu-id="1f27a-167">**Kod för påfyllnadssteg:** *lagerp*</span><span class="sxs-lookup"><span data-stu-id="1f27a-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="1f27a-168">**Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** *Ja*</span><span class="sxs-lookup"><span data-stu-id="1f27a-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="1f27a-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="1f27a-170">Påfyllnadsmall</span><span class="sxs-lookup"><span data-stu-id="1f27a-170">Wave template</span></span>

1. <span data-ttu-id="1f27a-171">Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="1f27a-172">I vänster ruta ange fältet **Malltyp för påfyllnad** till *Leverans*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="1f27a-173">Välj mallen **61 leverans** i listan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="1f27a-174">I åtgärdsfönstret väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="1f27a-175">På snabbfliken **Allmänt** ställer du in alternativet **Automatisera frisläppning av lagerpåfyllnadsarbete** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="1f27a-176">Ange det här alternativet till *Ja* om du vill skapa efterfrågebaserat återanskaffningsarbete och frisläppa det automatiskt.</span><span class="sxs-lookup"><span data-stu-id="1f27a-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="1f27a-177">Du måste lägga till påfyllnadsmetoden i påfyllnadsmallen och skapa en återanskaffningsmall av typen **Påfyllnadsefterfrågan**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="1f27a-178">Ställ in en påfyllnadsmall på sidan för **Återanskaffningmallar**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="1f27a-179">Om du vill skapa en påfyllningsmall måste du lägga till metoden för påfyllnadsmall.</span><span class="sxs-lookup"><span data-stu-id="1f27a-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="1f27a-180">På snabbfliken **Metoder** i kolumnen **Valda metoder** hittar du följande rad:</span><span class="sxs-lookup"><span data-stu-id="1f27a-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="1f27a-181">**Metodnamn:** *fylla på*</span><span class="sxs-lookup"><span data-stu-id="1f27a-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="1f27a-182">**Namn:** *lagerpåfyllnad*</span><span class="sxs-lookup"><span data-stu-id="1f27a-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="1f27a-183">Ställ in fältet **Kod för påfyllnadssteg** för den här raden till *lagerp*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="1f27a-184">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="1f27a-185">Exempelscenario</span><span class="sxs-lookup"><span data-stu-id="1f27a-185">Example scenario</span></span>

<span data-ttu-id="1f27a-186">När du har gjort alla exempel data som du redan har beskrivit och ställt in dem kan du arbeta i det här scenariot för att testa funktionen *Påfyllnad över lagerställekapacitet*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="1f27a-187">De värden som visas i det här scenariot förutsätter att du arbetar med standard demodata, att du har valt den juridiska personen **USMF** och att du har förberett exempelposterna som beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="1f27a-188">Det här scenariot fungerar även som ett exempel som visar hur funktionen kan användas i en produktionsinställning.</span><span class="sxs-lookup"><span data-stu-id="1f27a-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="1f27a-189">Skapa lagerpåfyllnadsarbete</span><span class="sxs-lookup"><span data-stu-id="1f27a-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="1f27a-190">Skapa försäljningsorder 1</span><span class="sxs-lookup"><span data-stu-id="1f27a-190">Create sales order 1</span></span>

1. <span data-ttu-id="1f27a-191">Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="1f27a-192">I åtgärdsfönstret välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1f27a-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="1f27a-193">Ange följande värden i dialogrutan:</span><span class="sxs-lookup"><span data-stu-id="1f27a-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="1f27a-194">**Kundkonto:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="1f27a-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="1f27a-195">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="1f27a-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="1f27a-196">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="1f27a-197">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-197">The new sales order is opened.</span></span> <span data-ttu-id="1f27a-198">Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="1f27a-199">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="1f27a-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="1f27a-200">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="1f27a-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="1f27a-201">**Kvantitet:** *40*</span><span class="sxs-lookup"><span data-stu-id="1f27a-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="1f27a-202">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="1f27a-203">På sidan **Reservation** väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="1f27a-204">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-204">Close the page.</span></span>
1. <span data-ttu-id="1f27a-205">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="1f27a-206">Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="1f27a-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="1f27a-207">En lagerpåfyllnad skapas också.</span><span class="sxs-lookup"><span data-stu-id="1f27a-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="1f27a-208">Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".</span><span class="sxs-lookup"><span data-stu-id="1f27a-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="1f27a-209">Skapa försäljningsorder 2</span><span class="sxs-lookup"><span data-stu-id="1f27a-209">Create sales order 2</span></span>

1. <span data-ttu-id="1f27a-210">På sidan **Alla försäljningsorder** i åtgärdsfönstret, välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1f27a-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="1f27a-211">Ange följande värde i dialogrutan:</span><span class="sxs-lookup"><span data-stu-id="1f27a-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="1f27a-212">**Kundkonto:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="1f27a-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="1f27a-213">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="1f27a-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="1f27a-214">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="1f27a-215">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-215">The new sales order is opened.</span></span> <span data-ttu-id="1f27a-216">Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="1f27a-217">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="1f27a-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="1f27a-218">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="1f27a-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="1f27a-219">**Kvantitet:** *60*</span><span class="sxs-lookup"><span data-stu-id="1f27a-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="1f27a-220">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="1f27a-221">På sidan **Reservation** väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="1f27a-222">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-222">Close the page.</span></span>
1. <span data-ttu-id="1f27a-223">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="1f27a-224">Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="1f27a-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="1f27a-225">En lagerpåfyllnad skapas också.</span><span class="sxs-lookup"><span data-stu-id="1f27a-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="1f27a-226">Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".</span><span class="sxs-lookup"><span data-stu-id="1f27a-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="1f27a-227">Skapa försäljningsorder 3</span><span class="sxs-lookup"><span data-stu-id="1f27a-227">Create sales order 3</span></span>

1. <span data-ttu-id="1f27a-228">På sidan **Alla försäljningsorder** i åtgärdsfönstret, välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1f27a-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="1f27a-229">Ange följande värden i dialogrutan:</span><span class="sxs-lookup"><span data-stu-id="1f27a-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="1f27a-230">**Kundkonto:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="1f27a-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="1f27a-231">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="1f27a-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="1f27a-232">Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="1f27a-233">Den nya försäljningsordern öppnas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-233">The new sales order is opened.</span></span> <span data-ttu-id="1f27a-234">Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="1f27a-235">Ställ in följande värden på denna rad:</span><span class="sxs-lookup"><span data-stu-id="1f27a-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="1f27a-236">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="1f27a-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="1f27a-237">**Kvantitet:** *30*</span><span class="sxs-lookup"><span data-stu-id="1f27a-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="1f27a-238">På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="1f27a-239">På sidan **Reservation** väljer du **Reservera parti**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="1f27a-240">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-240">Close the page.</span></span>
1. <span data-ttu-id="1f27a-241">I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="1f27a-242">Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades.</span><span class="sxs-lookup"><span data-stu-id="1f27a-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="1f27a-243">En lagerpåfyllnad skapas också.</span><span class="sxs-lookup"><span data-stu-id="1f27a-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="1f27a-244">Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".</span><span class="sxs-lookup"><span data-stu-id="1f27a-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="1f27a-245">Visa information om arbete</span><span class="sxs-lookup"><span data-stu-id="1f27a-245">View work details</span></span>

1. <span data-ttu-id="1f27a-246">Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="1f27a-247">I avsnittet **Översikt** filtrerar du kolumnen **Lagerställe** för lagerställe *61*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="1f27a-248">Du bör se att sju arbets-ID:n har skapats för de tre försäljningsorder som krävs.</span><span class="sxs-lookup"><span data-stu-id="1f27a-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="1f27a-249">Tre av de sju arbets-ID:na har värdet **Arbetsordertyp** av *Lagerpåfyllnad* och fyra har ett värde **Arbetsordertyp** av *Försäljningsorder*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="1f27a-250">Alla tre arbets-ID:n som har en **Arbetsordertyp** värdet för *Påfyllning* har samma *plockning* och *placering* i avsnittet **Rader**:</span><span class="sxs-lookup"><span data-stu-id="1f27a-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="1f27a-251">**Plocka:** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="1f27a-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="1f27a-252">**Placera:** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="1f27a-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="1f27a-253">Två arbets-ID:n skapades för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="1f27a-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="1f27a-254">Anteckna arbets-ID:t för försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1f27a-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="1f27a-255">Beroende på behållningskvantitet kan de skapade arbetskvantiteterna skilja sig något.</span><span class="sxs-lookup"><span data-stu-id="1f27a-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="1f27a-256">Men generellt bör de arbetsrubriker som skapas överensstämma med det här scenarioexemplet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="1f27a-257">ID-nummer för lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1f27a-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="1f27a-258">Senare i det här scenariot använder du mobilappen för distributionslagerhantering (eller en emulator), där du måste identifiera ID-numret för att slutföra scenarier med plockning och lagerpåfyllnad.</span><span class="sxs-lookup"><span data-stu-id="1f27a-258">Later in this scenario, you will use the Warehouse Management mobile app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="1f27a-259">Följ instruktionerna nedan för att hitta de ID-nummer som du kommer att behöva senare.</span><span class="sxs-lookup"><span data-stu-id="1f27a-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="1f27a-260">Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="1f27a-261">Välj knappen **Visa filter** om du vill öppna filterrutan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="1f27a-262">Ange följande filtreringskriterier för att hämta ID-nummer för scenariot.</span><span class="sxs-lookup"><span data-stu-id="1f27a-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="1f27a-263">Använd filtret *börjar med*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="1f27a-264">**Artikelnummer:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="1f27a-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="1f27a-265">**Lagerställe:** *61*</span><span class="sxs-lookup"><span data-stu-id="1f27a-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="1f27a-266">Välj **Tillämpa**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-266">Select **Apply**.</span></span>
1. <span data-ttu-id="1f27a-267">I åtgärdsfönstret, välj **Dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="1f27a-268">I dialogrutan **Dimensionsvisning** i avsnittet **Lagerdimensioner** väljer du alla värden.</span><span class="sxs-lookup"><span data-stu-id="1f27a-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="1f27a-269">I avsnittet **Transaktioner** väljer du **Artikelnummer** och **Kvantitet \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="1f27a-270">När du är klar klickar du på **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="1f27a-271">Rutnätet **Behållning** visar ID-nummer för artikel *T0100* på varje plats.</span><span class="sxs-lookup"><span data-stu-id="1f27a-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="1f27a-272">Anteckna vilket ID-nummer som finns på varje plats, eftersom du kommer att behöva dessa uppgifter vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="1f27a-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="1f27a-273">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1f27a-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="1f27a-274">Processteg</span><span class="sxs-lookup"><span data-stu-id="1f27a-274">Process steps</span></span>

<span data-ttu-id="1f27a-275">Du kommer att utföra återanskaffningen av distributionslagret för de första två arbets-ID:n.</span><span class="sxs-lookup"><span data-stu-id="1f27a-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="1f27a-276">Arbetet med det tredje påfyllnadsarbetet spärras tills lagernivån på plockplatsen sjunker under tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="1f27a-277">Lagerpåfyllnad</span><span class="sxs-lookup"><span data-stu-id="1f27a-277">Replenishment</span></span>

1. <span data-ttu-id="1f27a-278">Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *61*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-278">Sign in to the Warehouse Management mobile app as a user in warehouse *61*.</span></span> <span data-ttu-id="1f27a-279">(Ange *61* som användar-ID och *1* som lösenord.)</span><span class="sxs-lookup"><span data-stu-id="1f27a-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="1f27a-280">Gå till **Lager \> Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="1f27a-281">Du uppmanas att slutföra det första påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="1f27a-282">Artikelnummer, kvantitet och plats att plocka från visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="1f27a-283">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="1f27a-284">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="1f27a-285">Systemet genererar ett mål-ID-nummer för det nya ID-numret för den plockade artikeln.</span><span class="sxs-lookup"><span data-stu-id="1f27a-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="1f27a-286">Bekräfta värdet genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="1f27a-287">Infört arbete visas och instruerar användaren att placera mål-ID-numret på påfyllningsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="1f27a-288">*Placeringsplatsen* bör vara **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="1f27a-289">Bekräfta placeringsinformationen och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="1f27a-290">Meddelandet "arbete slutförd" visas och information om nästa uppgift med påfyllnadsplockning visas: artikelnummer, kvantitet och lagerställe att plocka från.</span><span class="sxs-lookup"><span data-stu-id="1f27a-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="1f27a-291">Plockningsplatsen kommer att vara densamma som den första lagerpåfyllnadsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="1f27a-292">Därför får ID-numret samma ID-nummer som användes för den första lagerpåfyllnadsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="1f27a-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="1f27a-293">Upprepa föregående steg för att slutföra lagerpåfyllnadsarbetet för den andra arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="1f27a-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="1f27a-294">Kvantiteten och ID-numret kommer att skilja sig från kvantiteten och mål-ID-numret för den första arbetsuppgiften.</span><span class="sxs-lookup"><span data-stu-id="1f27a-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="1f27a-295">När det andra lagerpåfyllnadsarbetet har slutförts visas meddelandet "färdigt arbete".</span><span class="sxs-lookup"><span data-stu-id="1f27a-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="1f27a-296">Den mobila enheten informerar också om att inget arbete är tillgängligt, även om en del av lagerpåfyllnadsarbetet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="1f27a-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="1f27a-297">Det här problemet beror på att en tillgänglighetsstatus har angetts för lagerpåfyllnadsarbetet *Hållen* och därför markeras det som **Spärrat**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="1f27a-298">Statusen *Hållen* utlöstes eftersom platsprofilen för plockningsplatsen som arbetet tilldelas till har ett värdet för **Överfyllnadskvantitet** på *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="1f27a-299">De två föregående påfyllningsarbetena fyller platsen i stort sett mot dess överfyllnadsgräns för artikel *T0100*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="1f27a-300">(Enhetskonverteringen för artikeln är *1 PL = 100 ea*.) Därför kommer det återstående påfyllningsarbetet att överskrida sin överfyllnadsgräns.</span><span class="sxs-lookup"><span data-stu-id="1f27a-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="1f27a-301">Tills tillräckligt med lager plockas från platsen för att få plats under tröskelvärdet för arbetsfrisläppning på menyalternativet mobil enhet förblir detta påfyllningsarbete spärrat.</span><span class="sxs-lookup"><span data-stu-id="1f27a-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="1f27a-302">Plockning av försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="1f27a-302">Sales order pick</span></span>

<span data-ttu-id="1f27a-303">Innan lagerpåfyllnadsarbetet kan slutföras måste plockningsplatsen vara tom för lagret till en nivå där det återstående påfyllningsarbetet kan avbrytas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="1f27a-304">Med andra ord kan summan av lagerbehållningen på platsen och den påfyllningskvantitet som anges inte överskrida värdet för **Överfyllnadskvantitet**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="1f27a-305">När den här summan är mindre än överfyllnadskvantitet, kommer det återstående lagerpåfyllnadsarbetet att spärras.</span><span class="sxs-lookup"><span data-stu-id="1f27a-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="1f27a-306">Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *61*.</span><span class="sxs-lookup"><span data-stu-id="1f27a-306">Sign in to the Warehouse Management mobile app as a user in warehouse *61*.</span></span> <span data-ttu-id="1f27a-307">(Ange *61* som användar-ID och *1* som lösenord.)</span><span class="sxs-lookup"><span data-stu-id="1f27a-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="1f27a-308">Gå till **Utgående \> Försäljningsplockning**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="1f27a-309">Ange det första arbets-ID:t för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="1f27a-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="1f27a-310">Se arbets-ID:n för försäljningsorder som du har gjort en anteckning för tidigare på sidan **arbetsuppgifter**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="1f27a-311">Det arbets-ID som du anger här kommer att generera ett plockningsarbete för en kvantitet på 10 ea från två separata platser.</span><span class="sxs-lookup"><span data-stu-id="1f27a-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="1f27a-312">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-312">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-313">Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från för den första platsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="1f27a-314">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="1f27a-315">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="1f27a-316">Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från för nästa plats.</span><span class="sxs-lookup"><span data-stu-id="1f27a-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="1f27a-317">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="1f27a-318">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="1f27a-319">Sidan **Försäljningsorder: placera** ger instruktioner om att både slutförda plockningar ska föras in på den utgående mellanlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="1f27a-320">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-320">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-321">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="1f27a-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="1f27a-322">Ange det andra arbets-ID:t för försäljningsorder 1.</span><span class="sxs-lookup"><span data-stu-id="1f27a-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="1f27a-323">Det finns bara en plockningsuppgift för detta arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="1f27a-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="1f27a-324">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-324">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-325">Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.</span><span class="sxs-lookup"><span data-stu-id="1f27a-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="1f27a-326">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="1f27a-327">Det ID-numret som du anger kommer att vara en av de systemgenererade ID-numren från uppgifterna för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="1f27a-328">Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1f27a-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="1f27a-329">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="1f27a-330">Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="1f27a-331">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-331">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-332">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="1f27a-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="1f27a-333">Försäljningsorder 2 spärras från plockning eftersom den lagerpåfyllnadsuppgift som den är kopplad till inte är slutförd.</span><span class="sxs-lookup"><span data-stu-id="1f27a-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="1f27a-334">För närvarande finns det fortfarande en kvantitet på 30 ea på plockningsplatsen och lagerpåfyllnadskvantitet för försäljningsorder 2 är 60 ea.</span><span class="sxs-lookup"><span data-stu-id="1f27a-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="1f27a-335">Summan av lagerbehållningen och det påfyllnings lagret (90 ea) överskrider överflödningskvantiteten på 0,65 PL (eller 65 ea).</span><span class="sxs-lookup"><span data-stu-id="1f27a-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="1f27a-336">Innan påfyllningsarbetet kan slutföras måste försäljningsorder 3 plockas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="1f27a-337">Ange arbets-ID:t för försäljningsorder 3.</span><span class="sxs-lookup"><span data-stu-id="1f27a-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="1f27a-338">Det finns bara en plockningsuppgift för detta arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="1f27a-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="1f27a-339">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-339">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-340">Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.</span><span class="sxs-lookup"><span data-stu-id="1f27a-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="1f27a-341">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="1f27a-342">Det ID-numret som du anger kommer att vara en av de systemgenererade ID-numren från uppgifterna för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="1f27a-343">Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1f27a-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="1f27a-344">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="1f27a-345">Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="1f27a-346">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-346">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-347">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="1f27a-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="1f27a-348">Så snart summan av lagerbehållningen på plockningsplatsen och lagerpåfyllnadskvantitet ligger under tröskeln kan du bearbeta det återstående påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="1f27a-349">Gå tillbaka till sidan **Arbetsinformation** och observera att lagerpåfyllnadsarbetet för sista lagerpåfyllnadsdelen (för försäljningsorder 2) är *Öppen*, eftersom det nu finns tillräckligt med utrymme på platsen för att acceptera påfyllnaden.</span><span class="sxs-lookup"><span data-stu-id="1f27a-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="1f27a-350">Du kan nu bearbeta påfyllningsarbetet via den mobila enheten.</span><span class="sxs-lookup"><span data-stu-id="1f27a-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="1f27a-351">Gå till **Lager \> Lagerpåfyllnad**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="1f27a-352">Du uppmanas att slutföra det återstående påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="1f27a-353">Artikelnummer, kvantitet och plats att plocka från visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="1f27a-354">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="1f27a-355">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="1f27a-356">Systemet genererar ett mål-ID-nummer för det nya ID-numret för den plockade artikeln.</span><span class="sxs-lookup"><span data-stu-id="1f27a-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="1f27a-357">Bekräfta värdet genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="1f27a-358">Infört arbete visas och instruerar användaren att placera mål-ID-numret på påfyllningsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="1f27a-359">*Placeringsplatsen* bör vara **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="1f27a-360">Bekräfta placeringsinformationen och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="1f27a-361">Meddelanden med "arbete slutfört" och "inget arbete tillgängligt" visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="1f27a-362">Du kan nu välja försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="1f27a-362">You can now pick sales order 2.</span></span> <span data-ttu-id="1f27a-363">Den blev spärrad när det påfyllningsarbete som har kopplats till försäljningsordern slutfördes.</span><span class="sxs-lookup"><span data-stu-id="1f27a-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="1f27a-364">Ange arbets-ID:t för försäljningsorder 2.</span><span class="sxs-lookup"><span data-stu-id="1f27a-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="1f27a-365">Det finns bara en plockningsuppgift för detta arbets-ID.</span><span class="sxs-lookup"><span data-stu-id="1f27a-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="1f27a-366">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-366">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-367">Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.</span><span class="sxs-lookup"><span data-stu-id="1f27a-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="1f27a-368">I fältet **LP** ange ID-nummer för den artikel på platsen som visas.</span><span class="sxs-lookup"><span data-stu-id="1f27a-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="1f27a-369">Det ID-numret som du anger kommer att vara det systemgenererade ID-numret från uppgiften för påfyllningsarbetet.</span><span class="sxs-lookup"><span data-stu-id="1f27a-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="1f27a-370">Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1f27a-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="1f27a-371">Välj **OK**-knappen (bockmarkeringssymbol).</span><span class="sxs-lookup"><span data-stu-id="1f27a-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="1f27a-372">Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="1f27a-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="1f27a-373">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f27a-373">Select **OK**.</span></span>

    <span data-ttu-id="1f27a-374">Du får ett meddelande arbetet är slutfört.</span><span class="sxs-lookup"><span data-stu-id="1f27a-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="1f27a-375">Anteckningar och tips</span><span class="sxs-lookup"><span data-stu-id="1f27a-375">Notes and tips</span></span>

- <span data-ttu-id="1f27a-376">Den här funktionen fungerar med alla typer av påfyllnad: påfyllnad av efterfrågan, min/max, lastefterfrågan och artikelplacering.</span><span class="sxs-lookup"><span data-stu-id="1f27a-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="1f27a-377">Du kan manuellt åsidosätta lagerpåfyllnadsarbetets tillgänglighet för varje arbetsrubrik från sidan **Arbetsinformation** om du vill.</span><span class="sxs-lookup"><span data-stu-id="1f27a-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="1f27a-378">När systemet ställer in tillgänglighet av lagerpåfyllnadsarbete beaktas alla lager som redan finns på platsen innan något arbete har slutförts</span><span class="sxs-lookup"><span data-stu-id="1f27a-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="1f27a-379">Varje exemplar av försäljningsorderarbete är kopplat till ett visst påfyllningsarbete.</span><span class="sxs-lookup"><span data-stu-id="1f27a-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="1f27a-380">Det finns ingen motsvarande funktion för tillgänglighet av försäljningsresurser.</span><span class="sxs-lookup"><span data-stu-id="1f27a-380">There is no corresponding sales work availability functionality.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]