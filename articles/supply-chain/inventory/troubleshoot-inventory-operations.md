---
title: Felsöka lageråtgärder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med lageråtgärder.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: ee1bfbf1b5aa736e1ee5bd38403b6c94c2bd036b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225012"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="f0d16-103">Felsöka lageråtgärder</span><span class="sxs-lookup"><span data-stu-id="f0d16-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0d16-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med lageråtgärder.</span><span class="sxs-lookup"><span data-stu-id="f0d16-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="f0d16-105">Jag hittar inte listrutan "Arbetsflöde" för lagerjournaler.</span><span class="sxs-lookup"><span data-stu-id="f0d16-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-106">Issue description</span></span>

<span data-ttu-id="f0d16-107">Du hittar inte listrutan **Arbetsflöde** på journalsidan, eller att relaterade arbetsflödesåtgärder inte är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="f0d16-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="f0d16-108">Det här problemet kan uppstå av tre orsaker, som beskrivs i följande underavsnitt.</span><span class="sxs-lookup"><span data-stu-id="f0d16-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="f0d16-109">Problemlösning 1</span><span class="sxs-lookup"><span data-stu-id="f0d16-109">Issue resolution 1</span></span>

<span data-ttu-id="f0d16-110">Om problemet gäller för alla användare kan det bero på att arbetsflödet för godkännande inte har tilldelats journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="f0d16-111">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="f0d16-112">Gå till **Lagerhantering &gt; Inställningar &gt; Journalnamn &gt; Lager**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="f0d16-113">Välj ett journalnamn i listfönstret för att öppna inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f0d16-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="f0d16-114">På snabbfliken **allmänt** anger du alternativet **Godkännandearbetsflöde** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="f0d16-115">Om du uppmanas att bekräfta ändringen väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="f0d16-116">I fältet **Arbetsflöde** välj det arbetsflöde du vill använda för det valda journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="f0d16-117">Problemlösning 2</span><span class="sxs-lookup"><span data-stu-id="f0d16-117">Issue resolution 2</span></span>

<span data-ttu-id="f0d16-118">Om det används anpassad kod i arbetsflödet kan problem uppstå när du har uppgraderat systemet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="f0d16-119">I journalarbetsflödet kan till exempel knappen **Skicka** vara gråtonad så att du inte kan välja den för att godkänna en överföring.</span><span class="sxs-lookup"><span data-stu-id="f0d16-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="f0d16-120">Om knappen **Skicka** är gråtonad kanske arbetsflödet har anpassats, vilket innebär att metoden för arbetsflödet, `canSubmitToWorkflow()` i `FormDataUtil`, utökats.</span><span class="sxs-lookup"><span data-stu-id="f0d16-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="f0d16-121">Du åtgärdar problemet genom att ändra sättet som du utökar metoden för `canSubmitToWorkflow()` för att använda strukturen i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="f0d16-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="f0d16-122">Problemlösning 3</span><span class="sxs-lookup"><span data-stu-id="f0d16-122">Issue resolution 3</span></span>

<span data-ttu-id="f0d16-123">Om problemet endast gäller ett fåtal specifika användare kanske dessa användare inte har de säkerhetsprivilegier som krävs för att köra arbetsflödesåtgärder på lagerjournaler.</span><span class="sxs-lookup"><span data-stu-id="f0d16-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="f0d16-124">Kontrollera att varje berörd användare har säkerhetsprivilegiet *Underhåll arbetsflöde för lagerjournal*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="f0d16-125">Som standard tilldelas det här privilegiet ett uppdrag som har samma namn och uppdraget tillämpas rollerna *Lagerarbetare* och *Lagerchef*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="f0d16-126">Min lagerjournal förblir i systemlåst status och batchjobbet för arbetsflödet fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="f0d16-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-127">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-127">Issue description</span></span>

<span data-ttu-id="f0d16-128">En av dina lagerjournaler är låst av någon operation och släpps inte.</span><span class="sxs-lookup"><span data-stu-id="f0d16-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="f0d16-129">Om ett okänt fel till exempel inträffar under bokföringen (vilket är en systemlåsoperation) kan journalen finnas kvar i systemlåst status.</span><span class="sxs-lookup"><span data-stu-id="f0d16-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="f0d16-130">I det här fallet arbetsflödet arbetsobjekt hanterare kommer att kasta ett fel medan den gör låsvalidering.</span><span class="sxs-lookup"><span data-stu-id="f0d16-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f0d16-131">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-131">Issue resolution</span></span>

<span data-ttu-id="f0d16-132">Logga in på SQL Server-instansen för Supply Chain Management, och kontrollera om **InventJournalTable.SystemBlocked** är inställt på *1*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="f0d16-133">Om det är det, se till att journalen inte ska vara i låst status och återställ sedan **InventJournalTable.SystemBlocked** till *0*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="f0d16-134">Mitt arbetsflöde för lagerjournalen har aldrig slutförts och journalen kan inte redigeras eller bokföras.</span><span class="sxs-lookup"><span data-stu-id="f0d16-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-135">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-135">Issue description</span></span>

<span data-ttu-id="f0d16-136">När du har skickat ett arbetsflöde för godkännande av journaler slutar arbetsflödesbearbetningen att svara och du kan inte redigera eller bearbeta dina journaler.</span><span class="sxs-lookup"><span data-stu-id="f0d16-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f0d16-137">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-137">Issue resolution</span></span>

<span data-ttu-id="f0d16-138">Det finns flera orsaker till att arbetsflödesbearbetningen kanske inte har slutförts.</span><span class="sxs-lookup"><span data-stu-id="f0d16-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="f0d16-139">Kontrollera om följande problem:</span><span class="sxs-lookup"><span data-stu-id="f0d16-139">Check for the following issues:</span></span>

- <span data-ttu-id="f0d16-140">Gå till **Lagerhantering &gt; Inställningar &gt; Arbetsflöden för lagerhantering** och granska konfigurationen av det berörda arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="f0d16-141">Mer information finns i [Godkännandearbetsflöden för lagerjournal](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f0d16-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="f0d16-142">Arbetsflödet kanske stöter på ett undantag eller ett fel.</span><span class="sxs-lookup"><span data-stu-id="f0d16-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="f0d16-143">Granska arbetsobjektshistoriken för det berörda arbetsflödet för att se om det inkluderar ett programfel som avslutar arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="f0d16-144">Lagerjournalen kan bara uppdateras eller redigeras om den är godkänd.</span><span class="sxs-lookup"><span data-stu-id="f0d16-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="f0d16-145">Om återkallande är aktivt kan du försöka återkalla journalen.</span><span class="sxs-lookup"><span data-stu-id="f0d16-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="f0d16-146">Körning av batchjobbet för arbetsflöde kanske stängs av på grund av flera skäl.</span><span class="sxs-lookup"><span data-stu-id="f0d16-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="f0d16-147">Vissa av dessa orsaker kan bero på problemet med arbetsflödesramverket.</span><span class="sxs-lookup"><span data-stu-id="f0d16-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="f0d16-148">Arbetsflödesvillkor för lagerjournal gäller endast på journalnivå, inte på radnivå</span><span class="sxs-lookup"><span data-stu-id="f0d16-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-149">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-149">Issue description</span></span>

<span data-ttu-id="f0d16-150">Det här problemet kan du uppleva om du till exempel försöker ställa in ett arbetsflödesvillkor för lagerjournal på kostnadsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="f0d16-151">Du ställer in villkoret så att steg 1 endast körs när kostnadsbeloppet är mindre än 100.</span><span class="sxs-lookup"><span data-stu-id="f0d16-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="f0d16-152">Du ställer in ett annat villkor så att steg 2 endast körs när kostnadsbeloppet är mer än eller lika med 100.</span><span class="sxs-lookup"><span data-stu-id="f0d16-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="f0d16-153">När arbetsflödet körs visar sedan arbetsflödeshistoriken bara en rad, och det första villkoret utvärderas alltid som *sant*, oavsett vilket värde som skickas.</span><span class="sxs-lookup"><span data-stu-id="f0d16-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="f0d16-154">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-154">Issue workaround</span></span>

<span data-ttu-id="f0d16-155">I aktuella versionen gäller endast arbetsflödesvillkor för lagerjournal på journalnivå, inte på radnivå.</span><span class="sxs-lookup"><span data-stu-id="f0d16-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="f0d16-156">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f0d16-156">This behavior is by design.</span></span> <span data-ttu-id="f0d16-157">Vi rekommenderar att du anger dina villkor endast på journalnivåattribut.</span><span class="sxs-lookup"><span data-stu-id="f0d16-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="f0d16-158">Filterfönstret på sidan Behållningslista filtrerar inte resultat som jag förväntar mig.</span><span class="sxs-lookup"><span data-stu-id="f0d16-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-159">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-159">Issue description</span></span>

<span data-ttu-id="f0d16-160">Filter i filterfönstret på sidan **Behållningslista** filtrerar inte resultat som du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="f0d16-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f0d16-161">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-161">Issue resolution</span></span>

<span data-ttu-id="f0d16-162">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="f0d16-162">This behavior is by design.</span></span>

<span data-ttu-id="f0d16-163">Sidan  **Behållningslista** är monterad i en detaljerad lagerbehållning som inkluderar alla tillgängliga dimensioner.</span><span class="sxs-lookup"><span data-stu-id="f0d16-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="f0d16-164">Listan på den här sidan är dock en sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="f0d16-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="f0d16-165">Därför kan det hända att rader kombineras från källtabellen genom att värdena aggregeras enligt de dimensioner som visas.</span><span class="sxs-lookup"><span data-stu-id="f0d16-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="f0d16-166">Filtren som anges i filterfönstret gäller för källtabellen, inte den aggregerade listan.</span><span class="sxs-lookup"><span data-stu-id="f0d16-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="f0d16-167">Det här beteendet kan ibland ge oväntade resultat, vilket visas i [dessa exempel](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="f0d16-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="f0d16-168">Men [filtren som finns i rutnätet](inventory-on-hand-list.md#grid-filters) *gäller* för den aggregerade listan.</span><span class="sxs-lookup"><span data-stu-id="f0d16-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="f0d16-169">Dessa filter inkluderar både snabbfilter överst i rutnätet och filtret för varje kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="f0d16-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="f0d16-170">Enhets- och enhetskvantiteten fungerar inte korrekt i lagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="f0d16-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-171">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-171">Issue description</span></span>

<span data-ttu-id="f0d16-172">Du kanske stöter på ett eller båda av följande problem när du arbetar med enheter och kvantiteter i en lagerjournal:</span><span class="sxs-lookup"><span data-stu-id="f0d16-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="f0d16-173">Du ser inte enheter eller enhetskvantiteter i lagerjournalen medan en enhet med konvertering ställs in för den frisläppta produkten och du kan inte ändra enheten i lagerjournalen.</span><span class="sxs-lookup"><span data-stu-id="f0d16-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="f0d16-174">Du ser fälten **Antal** och **Enhet** i lagerjournalen, men du ser inte fältet **enhetskvantitet**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="f0d16-175">Om du ändrar enheten, anger ett antal och bokför journalen, visar journalen fortfarande den ursprungliga måttenheten för den kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="f0d16-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f0d16-176">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-176">Issue resolution</span></span>

<span data-ttu-id="f0d16-177">Gör så här om du vill åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="f0d16-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="f0d16-178">I arbetsytan **Funktionshantering** se till att funktionen *Använda måttenhet och kvantitet i lagerjournaler* är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="f0d16-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="f0d16-179">Den här funktionen lägger till fälten **Enhet** och **Enhetskvantitet** i journalen.</span><span class="sxs-lookup"><span data-stu-id="f0d16-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="f0d16-180">När funktionen har aktiverats använder du fälten **Antal**, **Enhetskvantitet** och **Enhet** på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="f0d16-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="f0d16-181">**Antal** – Ange kvantiteten med hjälp av standardenheten som har definierats för den frisläppta produkten.</span><span class="sxs-lookup"><span data-stu-id="f0d16-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="f0d16-182">Standardenheten i sig visas dock inte här.</span><span class="sxs-lookup"><span data-stu-id="f0d16-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="f0d16-183">Om en konvertering ställs in mellan standardenheten och den enhet som är markerad i fältet **Enhet** uppdateras fältet **Antal** automatiskt, baserat på valen i fälten **Enhetskvantitet** och **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="f0d16-184">**Enhetskvantitet** – Ange mängden i den enhet som har valts i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="f0d16-185">**Enhet** – Välj den enhet som ska kopplas till värdet i fältet **Enhetskvantitet**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="f0d16-186">Följande felmeddelande visas: "Maximalt antal decimaler för lagerhållningsenheten är 0."</span><span class="sxs-lookup"><span data-stu-id="f0d16-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="f0d16-187">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d16-187">Issue description</span></span>

<span data-ttu-id="f0d16-188">När du försöker bokföra en lagertransaktion eller en lagerreservation visas följande felmeddelande: "Maximalt antal decimaler för lagerhållningsenheten är 0."</span><span class="sxs-lookup"><span data-stu-id="f0d16-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="f0d16-189">Det här problemet uppstår när lagertransaktionskvantiteten anges som ett decimalvärde som är under den nivå av precision som fältet stöder.</span><span class="sxs-lookup"><span data-stu-id="f0d16-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="f0d16-190">En kvantitet på *0,5* har till exempel angetts för en lagertransaktion, men endast heltalskvantiteter stöds.</span><span class="sxs-lookup"><span data-stu-id="f0d16-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="f0d16-191">Därför bör värdet vara *1* i stället för *0,5*.</span><span class="sxs-lookup"><span data-stu-id="f0d16-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f0d16-192">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="f0d16-192">Issue resolution</span></span>

1. <span data-ttu-id="f0d16-193">Kör följande skript på din SQL Server-instans för att avrunda kvantiteter i lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="f0d16-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="f0d16-194">Det här skriptet kommer att korrigera värden i tabellen **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="f0d16-195">Kör en konsekvenskontroll där alternativet **åtgärda fel** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="f0d16-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="f0d16-196">Denna kontroll kommer att korrigera värden i tabellen **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="f0d16-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0d16-197">Vi rekommenderar starkt att du noggrant redigerar skriptet som krävs för din miljö, testar den i en testmiljö och sedan kontrollerar resulterande data innan du kör skriptet i en produktionsmiljö.</span><span class="sxs-lookup"><span data-stu-id="f0d16-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]