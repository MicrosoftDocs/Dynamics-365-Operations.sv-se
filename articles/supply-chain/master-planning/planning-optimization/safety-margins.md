---
title: Säkerhetsmarginaler
description: I det här avsnittet beskrivs hur säkerhetsmarginaler kan användas med tillägget planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management .
author: ChristianRytt
manager: tfehr
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-9-14
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 08bdcef865c1e4904f32ce01f2956ac7acf55bf1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987314"
---
# <a name="safety-margins"></a><span data-ttu-id="d7ed4-103">Säkerhetsmarginaler</span><span class="sxs-lookup"><span data-stu-id="d7ed4-103">Safety margins</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7ed4-104">I det här avsnittet beskrivs hur säkerhetsmarginaler kan användas med tillägget planeringsoptimering för Microsoft Dynamics 365 Supply Chain Management .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-104">This topic describes how safety margins can be used with the Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="safety-margins-overview"></a><span data-ttu-id="d7ed4-105">Säkerhetsmarginaler, översikt</span><span class="sxs-lookup"><span data-stu-id="d7ed4-105">Safety margins overview</span></span>

<span data-ttu-id="d7ed4-106">Syftet med säkerhetsmarginaler är att aktivera en inställning som ger en viss buffertlängd utöver normal produktionstid.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-106">The purpose of safety margins is to enable a setup that provides some buffer time beyond the normal lead time.</span></span> <span data-ttu-id="d7ed4-107">Om material till exempel måste vara uppackat eller inspekterat efter att det har inträffat från leverantören, kan du inte bara lägga till den extra tiden i inköpsproduktionstiden, eftersom den här metoden ger leverantören den extra buffertstorleken.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-107">For example, when material must be unpacked or inspected after it arrives from the vendor, you can't just add the extra time to the purchase lead time, because this approach will give the additional buffer time to the supplier.</span></span> <span data-ttu-id="d7ed4-108">I det här exemplet kan du använda kvittomarginalen för att se till att leverantören levereras tidigare.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-108">In this example, the receipt margin can be used to ensure that the supplier delivers earlier.</span></span> <span data-ttu-id="d7ed4-109">Den här metoden ger en buffertlängd så att varorna kan hanteras internt.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-109">This approach provides buffer time so that the goods can be handled internally.</span></span>

<span data-ttu-id="d7ed4-110">Det finns tre typer av säkerhetsmarginaler:</span><span class="sxs-lookup"><span data-stu-id="d7ed4-110">There are three types of safety margins:</span></span>

- <span data-ttu-id="d7ed4-111">**Beställningsmarginal** – bufferttid för att skicka leveransordern</span><span class="sxs-lookup"><span data-stu-id="d7ed4-111">**Reorder margin** – The buffer time for placing the supply order</span></span>
- <span data-ttu-id="d7ed4-112">**Kvittomarginal** – bufferttid för hantering av inkommande leveranser</span><span class="sxs-lookup"><span data-stu-id="d7ed4-112">**Receipt margin** – The buffer time for handling incoming supply</span></span>
- <span data-ttu-id="d7ed4-113">**Ärendemarginal** – buffertens tid för hantering av försändelser</span><span class="sxs-lookup"><span data-stu-id="d7ed4-113">**Issue margin** – The buffer time for handling shipments</span></span>

<span data-ttu-id="d7ed4-114">Följande bild visar hur dessa säkerhetsmarginaler gäller över tid.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-114">The following illustration shows how these safety margins apply over time.</span></span>

![Säkerhetsmarginaler](media/safety-margins-1.png)

<span data-ttu-id="d7ed4-116">Alla marginaler anges i dagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-116">All margins are defined in days.</span></span> <span data-ttu-id="d7ed4-117">Standardvärde *0* (noll), indikerar att ingen marginal tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-117">The default value, *0* (zero), indicates that no margin is applied.</span></span> <span data-ttu-id="d7ed4-118">Om du ställer in flera marginaler läggs de till den totala tiden från leveransens *orderdatum* till efterfrågans *behovsdatum* .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-118">If you set up multiple margins, they all add to the total time from the supply *order date* to the demand *requirement date*.</span></span> <span data-ttu-id="d7ed4-119">Till exempel har en inställning ingen produktionstid och alla tre marginaltyperna är inställda på en dag.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-119">For example, a setup has no lead time, and all three margin types are set to one day.</span></span> <span data-ttu-id="d7ed4-120">I det här fallet kommer det att finnas tre dagar mellan leveransorder datumet och behovsdatumet, så om orderdatumet är den 1 juli blir behovsdatumet den 4 juli.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-120">In this case, there will be three days between the supply order date and the demand requirement date, so if the order date is July 1, the requirement date would be July 4.</span></span>

### <a name="receipt-margin"></a><span data-ttu-id="d7ed4-121">Inleveransmarginal</span><span class="sxs-lookup"><span data-stu-id="d7ed4-121">Receipt margin</span></span>

<span data-ttu-id="d7ed4-122">Kvittomarginalen är antagligen den mest utnyttjade av de tre säkerhetsmarginalerna.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-122">The receipt margin is probably the most used of the three safety margins.</span></span> <span data-ttu-id="d7ed4-123">Den används på *leveransdatumet* och bakåt från *behovsdatum* .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-123">It's applied to the *delivery date* and backward from the *requirement date*.</span></span> <span data-ttu-id="d7ed4-124">Med andra ord bör produkterna tas emot det angivna antalet dagar för den mottagande marginalen innan de krävs.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-124">In other words, the products should be received the specified number of receipt margin days before they are required.</span></span>

<span data-ttu-id="d7ed4-125">På bilden nedan beskrivs kvittomarginalen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-125">The following illustration highlights the receipt margin.</span></span>

![Inleveransmarginal](media/safety-margins-2.png)

<span data-ttu-id="d7ed4-127">Kvittomarginalen används vanligtvis som buffert för att säkerställa tid för lagerregistrering eller andra tidskrävande processer som inte har registrerats som en del av den allmänna produktionstiden i systemet.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-127">The receipt margin is typically used as a buffer to ensure time for warehouse registration or other time-consuming processes that aren't captured as part of the general lead time in the system.</span></span> <span data-ttu-id="d7ed4-128">För inköp är en fördel att *leveransdatum* för inköpsordern flyttas framåt i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-128">For purchases, one benefit is that the *delivery date* of the purchase order is moved forward accordingly.</span></span> <span data-ttu-id="d7ed4-129">Om du ökar produktionstiden istället för att använda en säkerhetsmarginal, kommer leverantören fortfarande att bli ombedd att leverera den sista minuten.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-129">If you  increase the lead time instead of using a safety margin, the vendor will still be asked to deliver at the last minute.</span></span>

<span data-ttu-id="d7ed4-130">Observera att kvittomarginalen inte ändrar *leveransens behovsdatum* .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-130">Notice that the receipt margin doesn't change the *requirement date* of the supply.</span></span> <span data-ttu-id="d7ed4-131">Därför är kvittomarginalen inte direkt synlig när behovsdatum för efterfrågan och tillgången jämförs (t.ex. på sidan **nettobehov**).</span><span class="sxs-lookup"><span data-stu-id="d7ed4-131">Therefore, the receipt margin isn't directly visible when requirement dates for demand and supply are compared (for example, on the **Net requirements** page).</span></span> <span data-ttu-id="d7ed4-132">Till exempel, om inleveransmarginalen är inställd på fyra dagar och en inköpsorderrad planeras för mottagande den femtonde i månaden, beräknar huvudplaneringen det justerade mottagningsdatumet som den nittonde i månaden.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-132">For example, if the receipt margin is set to four days, and a purchase order line is planned for receipt on the fifteenth of the month, master planning calculates the adjusted receipt date as the nineteenth of the month.</span></span>

<span data-ttu-id="d7ed4-133">Observera att en inleveransmarginal inte används när lagerbehållning används som leverans.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-133">Note that a receipt margin isn't applied when on-hand inventory is used as the supply.</span></span> <span data-ttu-id="d7ed4-134">All lagerbehållning antas vara tillgänglig omedelbart, oberoende av när den faktiskt togs emot.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-134">All on-hand inventory is assumed to be available immediately, regardless of when it was actually received.</span></span>

### <a name="reorder-margin"></a><span data-ttu-id="d7ed4-135">Beställningsmarginal</span><span class="sxs-lookup"><span data-stu-id="d7ed4-135">Reorder margin</span></span>

> [!NOTE]
> <span data-ttu-id="d7ed4-136">**Kommer snart:** den här funktionen stöds inte ännu för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-136">**Coming soon:** This feature isn't yet supported for Planning Optimization.</span></span> <span data-ttu-id="d7ed4-137">Alla värden som anges för **Ändra ordning på marginal som lagts till i artikelledtiden** kommer att behandlas som *0* (noll) tills den stöds.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-137">Until it's supported, all values that are entered for **Reorder margin added to item lead time** will be treated as *0* (zero).</span></span>

<span data-ttu-id="d7ed4-138">På bilden nedan beskrivs beställningsmarginalen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-138">The following illustration highlights the reorder margin.</span></span>

![Beställningsmarginal](media/safety-margins-3.png)

<span data-ttu-id="d7ed4-140">Beställningsmarginalen läggs till före artikelns produktionstid för alla planerade order vid huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-140">The reorder margin is added before the item lead time for all planned orders during master planning.</span></span> <span data-ttu-id="d7ed4-141">Därför gör det det enklare att placera en leveransorder.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-141">Therefore, it ensures additional time for a supply order to be placed.</span></span> <span data-ttu-id="d7ed4-142">Den här marginalen används vanligtvis som buffert för att säkerställa tiden för godkännandeprocesser eller andra interna processer som krävs när leveransorder skapas.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-142">This margin is typically used as a buffer to ensure time for approval processes or other internal processes that are required during the creation of supply orders.</span></span> <span data-ttu-id="d7ed4-143">Beställningsmarginalen placeras mellan leverans *orderdatum* och *startdatum*.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-143">The reorder margin is put between the supply *order date* and *start date*.</span></span>

### <a name="issue-margin"></a><span data-ttu-id="d7ed4-144">Utleveransmarginal</span><span class="sxs-lookup"><span data-stu-id="d7ed4-144">Issue margin</span></span>

> [!NOTE]
> <span data-ttu-id="d7ed4-145">**Kommer snart:** den här funktionen stöds inte ännu för planeringsoptimering.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-145">**Coming soon:** This feature isn't yet supported for Planning Optimization.</span></span> <span data-ttu-id="d7ed4-146">Alla värden som anges för **Utleveransmarginal som dragits av från behovsdatum** kommer att behandlas som *0* (noll).</span><span class="sxs-lookup"><span data-stu-id="d7ed4-146">Until it's supported, all values that are entered for **Issue margin deducted from requirement date** will be treated as *0* (zero).</span></span>

<span data-ttu-id="d7ed4-147">På bilden nedan beskrivs utleveransmarginal.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-147">The following illustration highlights the issue margin.</span></span>

![Utleveransmarginal](media/safety-margins-4.png)

<span data-ttu-id="d7ed4-149">Utleveransmarginalen dras från behovsdatumet vid behov vid huvudplaneringen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-149">The issue margin is deducted from the demand requirement date during master planning.</span></span> <span data-ttu-id="d7ed4-150">Det säkerställer att du har tid att reagera på och leverera inkommande efterfrågeorder.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-150">It helps ensure that you have time to react to and ship incoming demand orders.</span></span> <span data-ttu-id="d7ed4-151">Den här marginalen används vanligtvis som buffert för att säkerställa tid för leverans och relaterade avgående lagerprocesser.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-151">This margin is typically used as a buffer to ensure time for shipment and related outbound warehouse processes.</span></span>

<span data-ttu-id="d7ed4-152">Observera att när en utleveransmarginal används matchar inte relaterade leverans- och efterfrågebehovsdatum.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-152">Notice that when an issue margin is applied, related supply and demand requirement dates don't match.</span></span> <span data-ttu-id="d7ed4-153">De skiljer sig i stället från utleveransmarginal, eftersom utleveransmarginal läggs till mellan leveransens *behovsdatum* och efterfrågans *behovsdatum* .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-153">Instead, they differ by the issue margin, because the issue margin is added between the supply *requirement date* and the demand *requirement date*.</span></span>

## <a name="set-up-safety-margins"></a><span data-ttu-id="d7ed4-154">Ställ in säkerhetsmarginaler</span><span class="sxs-lookup"><span data-stu-id="d7ed4-154">Set up safety margins</span></span>

### <a name="turn-on-safety-margins-in-feature-management"></a><span data-ttu-id="d7ed4-155">Aktivera säkerhetsmarginaler i funktionshantering</span><span class="sxs-lookup"><span data-stu-id="d7ed4-155">Turn on safety margins in Feature management</span></span>

<span data-ttu-id="d7ed4-156">Innan du kan använda den här funktionen med Planeringsoptimering måste den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-156">Before you can use this feature with Planning Optimization, it must be turned on in your system.</span></span> <span data-ttu-id="d7ed4-157">Administratörer kan använda arbetsytan [funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-157">Admins can use the [Feature management](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="d7ed4-158">Funktionen visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d7ed4-158">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="d7ed4-159">**Modul:** _huvudplanering_</span><span class="sxs-lookup"><span data-stu-id="d7ed4-159">**Module:** _Master planning_</span></span>
- <span data-ttu-id="d7ed4-160">**Funktionsnamn:** _marginaler för planeringsoptimering_</span><span class="sxs-lookup"><span data-stu-id="d7ed4-160">**Feature name:** _Margins for Planning Optimization_</span></span>

### <a name="define-safety-margins"></a><span data-ttu-id="d7ed4-161">Definiera säkerhetsmarginaler</span><span class="sxs-lookup"><span data-stu-id="d7ed4-161">Define safety margins</span></span>

<span data-ttu-id="d7ed4-162">Säkerhetsmarginalerna har en flexibel inställning.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-162">Safety margins have a flexible setup.</span></span> <span data-ttu-id="d7ed4-163">De kan ställas in både på *disponeringsgruppen* och i *huvudplanen* .</span><span class="sxs-lookup"><span data-stu-id="d7ed4-163">They can be set on both the *coverage group* and the *master plan*.</span></span> <span data-ttu-id="d7ed4-164">Det är viktigt att du förstår att marginalerna läggs till ovanpå varandra.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-164">It's important that you understand that the margins are added on top of each other.</span></span> <span data-ttu-id="d7ed4-165">En kvittomarginal på två dagar i disponeringsgruppen och tre dagar i huvudplanen kommer att skapa en giltig kvittomarginal på fem dagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-165">For example, a receipt margin of two days on the coverage group and three days on the master plan will produce an effective receipt margin of five days.</span></span>

<span data-ttu-id="d7ed4-166">Möjligheten att ställa in marginalen på huvudplanen kan vara användbar när du vill simulera längre produktionstider eller osäkerhet för ett specifikt plan, men utan att påverka den dagliga planeringen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-166">The ability to set the margin on the master plan can be useful when you want to simulate longer lead times or uncertainty for a specific plan, but without affecting the daily planning.</span></span>

#### <a name="coverage-group-safety-margins"></a><span data-ttu-id="d7ed4-167">Disponeringsgrupper med säkerhetsmarginal</span><span class="sxs-lookup"><span data-stu-id="d7ed4-167">Coverage group safety margins</span></span>

<span data-ttu-id="d7ed4-168">Följ de här stegen om du vill tillämpa en säkerhetsmarginal på en disponeringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-168">To apply a safety margin to a coverage group, follow these steps.</span></span>

1. <span data-ttu-id="d7ed4-169">Gå till **huvudplanering \> inställningar \> disponeringsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-169">Go to **Master planning \> Setup \> Coverage groups**.</span></span>
1. <span data-ttu-id="d7ed4-170">Välj önskad disponeringsgrupp i listrutan.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-170">In the list pane, select the desired coverage group.</span></span>
1. <span data-ttu-id="d7ed4-171">På snabbfliken **Övrig** i avsnittet **säkerhetsmarginaler på dagar** använd följande fält för att ange krävda säkerhetsmarginaler (i dagar):</span><span class="sxs-lookup"><span data-stu-id="d7ed4-171">On the **Other** FastTab, in the **Safety margins in days** section, use the following fields to set the required safety margins (in days):</span></span>

    - <span data-ttu-id="d7ed4-172">Inleveransmarginal som lagts till för behovsdatum</span><span class="sxs-lookup"><span data-stu-id="d7ed4-172">Receipt margin added to requirement date</span></span>
    - <span data-ttu-id="d7ed4-173">Utleveransmarginal som dragits av från behovsdatum</span><span class="sxs-lookup"><span data-stu-id="d7ed4-173">Issue margin deducted from requirement date</span></span>
    - <span data-ttu-id="d7ed4-174">Ändra ordning på marginal som lagts till i artikelledtiden</span><span class="sxs-lookup"><span data-stu-id="d7ed4-174">Reorder margin added to item lead time</span></span>

#### <a name="master-plan-safety-margins"></a><span data-ttu-id="d7ed4-175">Huvudplaner med säkerhetsmarginaler</span><span class="sxs-lookup"><span data-stu-id="d7ed4-175">Master plan safety margins</span></span>

<span data-ttu-id="d7ed4-176">Följ de här stegen om du vill tillämpa en säkerhetsmarginal på en huvudplan.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-176">To apply a safety margin to a master plan, follow these steps.</span></span>

1. <span data-ttu-id="d7ed4-177">Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-177">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="d7ed4-178">Välj önskad disponeringsgrupp i huvudplaner.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-178">In the list pane, select the desired master plan.</span></span>
1. <span data-ttu-id="d7ed4-179">På snabbfliken **säkerhetsmarginaler på dagar** använd följande fält för att ange krävda säkerhetsmarginaler (i dagar):</span><span class="sxs-lookup"><span data-stu-id="d7ed4-179">On the **Safety margins in days** FastTab, use the following fields to set the required safety margins (in days):</span></span>

    - <span data-ttu-id="d7ed4-180">Inleveransmarginal som lagts till för behovsdatum</span><span class="sxs-lookup"><span data-stu-id="d7ed4-180">Receipt margin added to requirement date</span></span>
    - <span data-ttu-id="d7ed4-181">Utleveransmarginal som dragits av från behovsdatum</span><span class="sxs-lookup"><span data-stu-id="d7ed4-181">Issue margin deducted from requirement date</span></span>
    - <span data-ttu-id="d7ed4-182">Ändra ordning på marginal som lagts till i artikelledtiden</span><span class="sxs-lookup"><span data-stu-id="d7ed4-182">Reorder margin added to item lead time</span></span>

### <a name="define-whether-calculations-are-based-on-calendar-days-or-work-days"></a><span data-ttu-id="d7ed4-183">Definiera om beräkningar ska baseras på kalenderdagar eller arbetsdagar</span><span class="sxs-lookup"><span data-stu-id="d7ed4-183">Define whether calculations are based on calendar days or work days</span></span>

<span data-ttu-id="d7ed4-184">Du kan ställa in alla säkerhetsmarginaler så att de beräknas utifrån antingen kalenderdagar eller arbetsdagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-184">You can set all safety margins so that they are calculated based on either calendar days or work days.</span></span>

1. <span data-ttu-id="d7ed4-185">Gå till **Huvudplanering \> Inställningar \> Huvudplaneringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-185">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
1. <span data-ttu-id="d7ed4-186">På fliken **Allmänt** i avsnittet **Säkerhetsmarginaler i dagar** ange alternativet **Arbetsdagar** till *Ja* om du vill beräkna marginaler baserat på arbetsdagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-186">On the **General** tab, in the **Safety margins in days** section, set the **Working days** option to *Yes* to calculate margins based on working days.</span></span> <span data-ttu-id="d7ed4-187">Ställ in alternativet på *Nej* om du vill beräkna marginaler baserat på kalenderdagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-187">Set the option to *No* to calculate margins based on calendar days.</span></span>

<span data-ttu-id="d7ed4-188">En kalender är till exempel öppen från måndag till fredag och stängs från lördag till söndag.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-188">For example, a calendar is open from Monday through Friday and closed from Saturday through Sunday.</span></span> <span data-ttu-id="d7ed4-189">Om det finns en kvittomarginal på en dag, ger ett behovsdatum på en måndag ett leveransdatum på föregående fredag eftersom lördag och söndag inte är arbetsdagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-189">If there is a receipt margin of one day, a requirement date on a Monday produces a delivery date on the previous Friday, because Saturday and Sunday aren't working days.</span></span>

<span data-ttu-id="d7ed4-190">Vilken kalender som används för att bestämma arbetsdagar beror på inställningarna och leveranstypen.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-190">The calendar that is used to determine the working days depends on the setup and the supply type.</span></span> <span data-ttu-id="d7ed4-191">Den kan styras av gruppens kalendrar, lagerstället och leverantören.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-191">It can be controlled by the calendars of the coverage group, the warehouse, and the vendor.</span></span>

> [!NOTE]
> <span data-ttu-id="d7ed4-192">Om *lagerstället* inte ingår i disponeringsdimension (d.v.s. planering endast baseras på *plats*), används inte lagerkalendern.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-192">If *warehouse* isn't part of the coverage dimension (in other words, planning is based only on *site*), the warehouse calendar isn't used.</span></span>

<span data-ttu-id="d7ed4-193">Systemet kan hantera en inställning där en eller flera kalendrar definieras.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-193">The system can handle a setup where one or more calendars are defined.</span></span> <span data-ttu-id="d7ed4-194">Följande underavsnitt beskriver de möjliga kombinationer som kan användas för att styra resultatet.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-194">The following subsections describe the possible combinations that can be used to control the result.</span></span>

#### <a name="calendar-that-is-used-for-the-duration"></a><span data-ttu-id="d7ed4-195">Kalender som används för varaktigheten</span><span class="sxs-lookup"><span data-stu-id="d7ed4-195">Calendar that is used for the duration</span></span>

<span data-ttu-id="d7ed4-196">I de definierade kalendrarna kontrolleras den faktiska totala produktions tiden i kalenderdagar, från leveransorderdatumet till behovsdatumet.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-196">The defined calendars control the actual total lead time in calendar days, from the supply order date to the demand requirement date.</span></span> <span data-ttu-id="d7ed4-197">Följande kalenderprioritering används:</span><span class="sxs-lookup"><span data-stu-id="d7ed4-197">The following calendar prioritization is used:</span></span>

- <span data-ttu-id="d7ed4-198">**Produktionstid** – endast disponeringsgruppens kalender beaktas.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-198">**Purchase lead time** – Only the coverage group calendar is considered.</span></span>
- <span data-ttu-id="d7ed4-199">**Kvittomarginal** – disponeringsgruppens kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-199">**Receipt margin** – The coverage group calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-200">Annars används kalendern för distributionslager.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-200">Otherwise, the warehouse calendar is used.</span></span>
- <span data-ttu-id="d7ed4-201">**Utleveransmarginal** – disponeringsgruppens kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-201">**Issue margin** – The coverage group calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-202">Annars används kalendern för distributionslager.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-202">Otherwise, the warehouse calendar is used.</span></span>
- <span data-ttu-id="d7ed4-203">**Ordermarginal** – endast disponeringsgruppens kalender beaktas.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-203">**Order margin** – Only the coverage group calendar is considered.</span></span>

#### <a name="calendar-that-is-used-for-the-final-date"></a><span data-ttu-id="d7ed4-204">Kalender som används för slutdatum</span><span class="sxs-lookup"><span data-stu-id="d7ed4-204">Calendar that is used for the final date</span></span>

<span data-ttu-id="d7ed4-205">Följande regler används för att avgöra om ett visst datum ska användas för planeringsmotorn för en viss datatyp:</span><span class="sxs-lookup"><span data-stu-id="d7ed4-205">The following rules are applied to determine whether the planning engine can use a given date for a given date type:</span></span>

- <span data-ttu-id="d7ed4-206">**Datum för inköpsinleverans** – leverantörskalendern används, om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-206">**Purchase receipt date** – The vendor calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-207">Annars kan disponeringsgruppens kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-207">Otherwise, the coverage group calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-208">Om ingen av dessa kalendrar definieras används lagerställekalendern.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-208">If neither of those calendars is defined, the warehouse calendar is used.</span></span>
- <span data-ttu-id="d7ed4-209">**Överföringsinleveransdatum** – disponeringsgruppens kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-209">**Transfer receipt date** – The coverage group calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-210">Annars används kalendern för distributionslager.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-210">Otherwise, the warehouse calendar is used.</span></span>
- <span data-ttu-id="d7ed4-211">**Produktionsinleveransdatum** – disponeringsgruppens kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-211">**Production receipt date** – The coverage group calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-212">Annars används kalendern för distributionslager.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-212">Otherwise, the warehouse calendar is used.</span></span>
- <span data-ttu-id="d7ed4-213">**Efterfrågan utleverans öppen dag** – lagerställekalendern kalender används om den har definierats.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-213">**Demand issue open day** – The warehouse calendar is used, if it's defined.</span></span> <span data-ttu-id="d7ed4-214">Annars kan disponeringsgruppens kalender används.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-214">Otherwise, the coverage group calendar is used.</span></span>
- <span data-ttu-id="d7ed4-215">**Order öppen dag** – en kombination (skärningspunkt) på gruppen för disponeringsgrupper och leverantörskalendern används.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-215">**Order open day** – A combination (intersection) of the coverage group calendar and the vendor calendar is used.</span></span> <span data-ttu-id="d7ed4-216">Båda kalendrarna måste vara öppna för att du ska kunna använda datumet.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-216">Both calendars must be open to use the date.</span></span> <span data-ttu-id="d7ed4-217">Om bara en av kalendrarna är definierade används den kalendern ensam.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-217">If only one of the calendars is defined, that calendar is used alone.</span></span>

#### <a name="calendar-setup-overview-matrix"></a><span data-ttu-id="d7ed4-218">Matris för översikt över kalenderinställningar</span><span class="sxs-lookup"><span data-stu-id="d7ed4-218">Calendar setup overview matrix</span></span>

<span data-ttu-id="d7ed4-219">Följande bild visar en matris som sammanfattar vilka kalendrar som gäller när säkerhetsmarginaler beräknas.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-219">The following illustration presents a matrix that summarizes which calendars apply when safety margins are calculated.</span></span> <span data-ttu-id="d7ed4-220">(Markera bilden om du vill öppna en högupplöst version av den.) Följande förkortningar och färger används för att ange var varje typ av kalender anges:</span><span class="sxs-lookup"><span data-stu-id="d7ed4-220">(Select the image to open a high-resolution version of it.) The following abbreviations and colors are used to indicate where each type of calendar is specified:</span></span>

- <span data-ttu-id="d7ed4-221">**Disponeringsgrupp (CG):** grön</span><span class="sxs-lookup"><span data-stu-id="d7ed4-221">**Coverage group (CG):** Green</span></span>
- <span data-ttu-id="d7ed4-222">**Lagerställe (WH):** gul</span><span class="sxs-lookup"><span data-stu-id="d7ed4-222">**Warehouse (WH):** Yellow</span></span>
- <span data-ttu-id="d7ed4-223">**Leverantör (V):** blå</span><span class="sxs-lookup"><span data-stu-id="d7ed4-223">**Vendor (V):** Blue</span></span>

<span data-ttu-id="d7ed4-224">[![Matris för översikt över kalenderinställningar](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)</span><span class="sxs-lookup"><span data-stu-id="d7ed4-224">[![Calendar setup overview matrix](media/safety-margins-calendar-matrix.png)](media/safety-margins-calendar-matrix-high.png)</span></span>

## <a name="calculating-delays"></a><span data-ttu-id="d7ed4-225">Beräkna fördröjningar</span><span class="sxs-lookup"><span data-stu-id="d7ed4-225">Calculating delays</span></span>

<span data-ttu-id="d7ed4-226">Alla tre typerna av säkerhetsmarginal tas med när systemet fastställer om en order är försenad.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-226">All three types of safety margins are included when the system determines whether an order is delayed.</span></span>

<span data-ttu-id="d7ed4-227">En artikel har t.ex. produktionstid på en dag och en kvittomarginal på tre dagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-227">For example, an item has lead time of one day and a receipt margin of three days.</span></span> <span data-ttu-id="d7ed4-228">En försäljningsorder för denna artikel ställs in efter behov i dag.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-228">A sales order for this item is set as required today.</span></span> <span data-ttu-id="d7ed4-229">I det här fallet beräknas förseningen som *produktionstiden* + *kvittomarginal* = fyra dagar.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-229">In this case, the delay is calculated as *lead time* + *receipt margin* = four days.</span></span> <span data-ttu-id="d7ed4-230">Om dagens datum är den 14 augusti skapas därför en leverans på 18 augusti för fyra dagars fördröjning.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-230">Therefore, if today is August 14, the four days of delay produces a delivery on August 18.</span></span> <span data-ttu-id="d7ed4-231">Illustrationen nedan visar ett exempel.</span><span class="sxs-lookup"><span data-stu-id="d7ed4-231">The following illustration shows this example.</span></span>

![Exempel på fördröjningsberäkning](media/safety-margins-delays.png)

## <a name="additional-resources"></a><span data-ttu-id="d7ed4-233">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d7ed4-233">Additional resources</span></span>

[<span data-ttu-id="d7ed4-234">Kom igång med planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="d7ed4-234">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="d7ed4-235">Bristanalys för planeringsoptimering</span><span class="sxs-lookup"><span data-stu-id="d7ed4-235">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
