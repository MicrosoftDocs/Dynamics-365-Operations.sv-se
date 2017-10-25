---
title: "Parametrar för utläggshantering"
description: "Följande parametrar styr beteendet i utgiftshanteringen."
author: KimANelson
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8ca9e80d6d2b87fcdd10ebb9d32bd0a2b2d15614
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-parameters"></a><span data-ttu-id="67bc0-103">Parametrar för utläggshantering</span><span class="sxs-lookup"><span data-stu-id="67bc0-103">Expense management parameters</span></span>
-----------------------------

<span data-ttu-id="67bc0-104">Följande parametrar styr det allmänna beteendet i utgiftshanteringen.</span><span class="sxs-lookup"><span data-stu-id="67bc0-104">The parameters control the general behavior in Expense management.</span></span>

### <a name="general"></a><span data-ttu-id="67bc0-105">Allmänt</span><span class="sxs-lookup"><span data-stu-id="67bc0-105">General</span></span>

| <span data-ttu-id="67bc0-106">**Fält**</span><span class="sxs-lookup"><span data-stu-id="67bc0-106">**Field**</span></span>                                                | <span data-ttu-id="67bc0-107">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-107">**Description**</span></span>                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| <span data-ttu-id="67bc0-108">**Standardtariff för milersättning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-108">**Standard rate of mileage**</span></span>                             | <span data-ttu-id="67bc0-109">Ange vilken tariff för milersättning.</span><span class="sxs-lookup"><span data-stu-id="67bc0-109">Enter the reimbursement rate for mileage expenses.</span></span> <span data-ttu-id="67bc0-110">Satsen ska multipliceras med den körsträcka som angetts för att beräkna beloppet återbetalas för reseutgifter utgiften.</span><span class="sxs-lookup"><span data-stu-id="67bc0-110">The rate will be multiplied by the mileage entered on the expense to calculate the amount reimbursed for the travel expense.</span></span>                       |
|<span data-ttu-id="67bc0-111">**Privata utgifter betalas av**</span><span class="sxs-lookup"><span data-stu-id="67bc0-111">**Personal expenses paid by**</span></span>                             | <span data-ttu-id="67bc0-112">Välj vem som är ansvarig för att betala alla kreditkortstransaktionsbelopp som kategoriseras som personliga.</span><span class="sxs-lookup"><span data-stu-id="67bc0-112">Select who is responsible for paying any credit card transaction amounts categorized as personal.</span></span>                                                                                                     |
|<span data-ttu-id="67bc0-113">**Visa hela utgiftsrapporten vid vidaresökning bakåt**</span><span class="sxs-lookup"><span data-stu-id="67bc0-113">**Display entire expense report on drillback**</span></span>               | <span data-ttu-id="67bc0-114">Välj detta alternativ om du vill visa alla utgifter för en utgiftsrapport när du visar informationen i det ursprungliga dokumentet för en viss verifikation som skapades när utgiftsrapporten bokförs.</span><span class="sxs-lookup"><span data-stu-id="67bc0-114">Select this option to display all expenses for an expense report when viewing the details of the original document for a specific voucher that was generated when the expense report was posted.</span></span>              |
|<span data-ttu-id="67bc0-115">**Förauktorisering för resa är obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="67bc0-115">**Pre-authorization of travel is mandatory**</span></span>                 | <span data-ttu-id="67bc0-116">Välj detta alternativ om du vill att en reserekvisition överlämnas och godkänns innan en medarbetare kan skicka en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-116">Select this option to require that a travel requisition be submitted and approved before an employee can submit an expense report.</span></span>                                                                    |
|<span data-ttu-id="67bc0-117">**Tillåt redigering av fördelningar före bokföring**</span><span class="sxs-lookup"><span data-stu-id="67bc0-117">**Allow editing of distributions before posting**</span></span>            | <span data-ttu-id="67bc0-118">Välj om distribution av en utgiftsrapport kan ändras före bokföring.</span><span class="sxs-lookup"><span data-stu-id="67bc0-118">Select whether the distributions of an expense report can be edited prior to posting.</span></span>                                                                                                                 |
|<span data-ttu-id="67bc0-119">**Utvärdera policyer för utläggshantering**</span><span class="sxs-lookup"><span data-stu-id="67bc0-119">**Evaluate expense management policies**</span></span>                     | <span data-ttu-id="67bc0-120">Välj när utgifter utvärderas för att avgöra om en utgiftspolicy har överträtts.</span><span class="sxs-lookup"><span data-stu-id="67bc0-120">Select when expenses are evaluated to determine if an expense policy has been violated.</span></span> <span data-ttu-id="67bc0-121">Utgifter kan kontrolleras för brott när utgiftsposten anges och sparas eller när utgifterna har skickats för godkännande.</span><span class="sxs-lookup"><span data-stu-id="67bc0-121">Expenses can be checked for violations when the expense entry is entered and saved or when the expense is submitted for approval.</span></span> <span data-ttu-id="67bc0-122">Policyregler för kvitton som krävs kontrolleras när utgiftsraden har sparats.</span><span class="sxs-lookup"><span data-stu-id="67bc0-122">The policy rules for receipts required will be checked when the expense line is saved.</span></span>                   |
|<span data-ttu-id="67bc0-123">**Tillåt koncerninterna utgiftsrader**</span><span class="sxs-lookup"><span data-stu-id="67bc0-123">**Allow intercompany expense lines**</span></span>                         | <span data-ttu-id="67bc0-124">Välj om du vill tillåta inmatning av utgifter för andra juridiska personer i en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-124">Select whether to allow entry of expenses for other legal entities within an expense report.</span></span>                                                                                                          |
|<span data-ttu-id="67bc0-125">**Tillåt redigering av valutakursen för kreditkortsutgifter**</span><span class="sxs-lookup"><span data-stu-id="67bc0-125">**Allow editing the exchange rate for credit card expenses**</span></span> | <span data-ttu-id="67bc0-126">Välj detta alternativ om du vill tillåta användaren att redigera växelkursen för importerade kreditkortutgifter.</span><span class="sxs-lookup"><span data-stu-id="67bc0-126">Select this option to allow the user to edit the exchange rate for imported credit card expenses.</span></span>                                                                        |
|<span data-ttu-id="67bc0-127">**Flera hierarkinivåfält att visa**</span><span class="sxs-lookup"><span data-stu-id="67bc0-127">**Multi-level hierarchy fields to display**</span></span>                  | <span data-ttu-id="67bc0-128">Välj vilket godkännarfält som visas när tilldelningstypen för utgiftsrapportarbetsflödet anges till hierarki och alternativet hierarki är konfigurerat att använda godkännandehierarki på flera nivåer för utgift.</span><span class="sxs-lookup"><span data-stu-id="67bc0-128">Select which approver fields to display when the expense report workflow assignment type is set to be hierarchy and the hierarchy selection is set to use the Expense multi-level approval hierarchy.</span></span> <span data-ttu-id="67bc0-129">När godkännandehierarkin på flera nivåer används för arbetsflöde visas och redigeras de markerade fälten i utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="67bc0-129">When the multi-level approval hierarchy is used for workflow, the selected fields will be displayed and editable in the Expense report.</span></span> |
|<span data-ttu-id="67bc0-130">**Ange medarbetarens kreditkortsnummer (uppdatering juli 2017)**</span><span class="sxs-lookup"><span data-stu-id="67bc0-130">**Enter employee credit card number (July 2017 update)**</span></span>     | <span data-ttu-id="67bc0-131">Välj om ett 15 eller 16 teckens nummer anges och sparas i fältet **kort-ID** på sidan **kreditkort** för en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="67bc0-131">Select whether a 15-or 16-character number can be entered and saved in the **Card ID** field in the **Credit cards** page for an employee.</span></span>                                                                          |

### <a name="financial"></a><span data-ttu-id="67bc0-132">Ekonomi</span><span class="sxs-lookup"><span data-stu-id="67bc0-132">Financial</span></span>

| <span data-ttu-id="67bc0-133">**Fält**</span><span class="sxs-lookup"><span data-stu-id="67bc0-133">**Field**</span></span>                                                            | <span data-ttu-id="67bc0-134">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-134">**Description**</span></span>     |
|----------------------------------------------------------------------|------------------------------------|
|<span data-ttu-id="67bc0-135">**Namn på dagboksjournal i redovisning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-135">**Ledger daily journal name**</span></span>                                         | <span data-ttu-id="67bc0-136">Välj vilket namn på redovisningsjournal som godkända utgiftsrapporter ska bokföras i.</span><span class="sxs-lookup"><span data-stu-id="67bc0-136">Select the name of the ledger journal that approved expense reports are posted to.</span></span>            |
|<span data-ttu-id="67bc0-137">**Aktivera momsåterbetalning från utgifter**</span><span class="sxs-lookup"><span data-stu-id="67bc0-137">**Enable tax recovery from expenses**</span></span>                                  | <span data-ttu-id="67bc0-138">Välj detta alternativ om du vill aktivera momsåterbetalning för berättigade utgifter.</span><span class="sxs-lookup"><span data-stu-id="67bc0-138">Select this option to enable expense tax recovery for eligible expenses.</span></span> <span data-ttu-id="67bc0-139">Det här alternativet kan inte aktiveras om amerikansk moms och använda skatteregler har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="67bc0-139">This option cannot be enabled if US sales tax and use tax rules are enabled.</span></span>      |
|<span data-ttu-id="67bc0-140">**Bokför förskott omedelbart**</span><span class="sxs-lookup"><span data-stu-id="67bc0-140">**Post cash advances immediately**</span></span>                                     | <span data-ttu-id="67bc0-141">Välj det här alternativet om du vill bokföra ett godkänt förskott när processen att betala och överföra har slutförts.</span><span class="sxs-lookup"><span data-stu-id="67bc0-141">Select this option to post an approved cash advance when the process to Pay and transfer is completed.</span></span> <span data-ttu-id="67bc0-142">Om alternativet inte är markerat genererat processen Betala och överför en ej bokförd redovisningsjournal.</span><span class="sxs-lookup"><span data-stu-id="67bc0-142">If this option is not selected, the Pay and transfer process will generate an unposted general journal.</span></span> |
|<span data-ttu-id="67bc0-143">**Korrekt redovisningsdatum under bokföring**</span><span class="sxs-lookup"><span data-stu-id="67bc0-143">**Correct accounting date during posting**</span></span>                             | <span data-ttu-id="67bc0-144">Välj detta alternativ om du vill uppdatera redovisningsdatumet när utgifter bokförs om den aktuella perioden är spärrad eller stängd.</span><span class="sxs-lookup"><span data-stu-id="67bc0-144">Select this option to update the accounting date when posting expenses if the current period is on hold or closed.</span></span> <span data-ttu-id="67bc0-145">Redovisningsdatumet anges till nästa öppna period.</span><span class="sxs-lookup"><span data-stu-id="67bc0-145">The accounting date will be set to the next open period.</span></span>   |
|<span data-ttu-id="67bc0-146">**Tillåt gruppering av transaktioner baserade på motkonto angivet i betalningsmetoden**</span><span class="sxs-lookup"><span data-stu-id="67bc0-146">**Allow grouping of transactions based on offset account specified in payment method**</span></span>      | <span data-ttu-id="67bc0-147">Välj detta alternativ om du vill summera utgiftstransaktioner för utgiftsrapporter som baseras på motkontot enligt betalningsmetoden för utgifterna.</span><span class="sxs-lookup"><span data-stu-id="67bc0-147">Select this option to summarize the expense transactions for an expense report, based on the offset account specified in the payment method for the expenses.</span></span>   
|<span data-ttu-id="67bc0-148">**Inklusive skatt**</span><span class="sxs-lookup"><span data-stu-id="67bc0-148">**Tax included**</span></span>                                                   | <span data-ttu-id="67bc0-149">Välj det här alternativet för att inkludera moms i utgiftsbeloppet som standard.</span><span class="sxs-lookup"><span data-stu-id="67bc0-149">Select this option to include sales tax in the expense amount by default.</span></span>             |
|<span data-ttu-id="67bc0-150">**Frisläpp inteckningar vid stängning av reserekvisitioner**</span><span class="sxs-lookup"><span data-stu-id="67bc0-150">**Release encumbrances on closing travel requisitions**</span></span>            | <span data-ttu-id="67bc0-151">Välj detta alternativ för att frisläppa intecknade medel när en godkänd reserekvisition stängs.</span><span class="sxs-lookup"><span data-stu-id="67bc0-151">Select this option to release encumbered funds when an approved travel requisition is closed.</span></span>                                                                                   |
|<span data-ttu-id="67bc0-152">**Tillåt att reserekvisition skickas vid budgetöverskridningar för budgetregister och projektbudget**</span><span class="sxs-lookup"><span data-stu-id="67bc0-152">**Allow travel requisition submit on budget overrun for budget register and project budget**</span></span> | <span data-ttu-id="67bc0-153">Välj detta alternativ om du vill tillåta att medarbetare skickar reserekvisitioner för godkännande som antingen överstiger tillåten budget som har angetts i budgetregistret eller tillåten budget för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="67bc0-153">Select this option to allow employees to submit travel requisitions for approval that exceed either the allowed budget that is set in the budget register or the allowed budget for a project.</span></span>            |
|<span data-ttu-id="67bc0-154">**Tillåt att utgiftsrapport skickas vid budgetöverskridningar för budgetregister och projektbudget**</span><span class="sxs-lookup"><span data-stu-id="67bc0-154">**Allow expense report submit on budget overrun for budget register and project budget**</span></span>    | <span data-ttu-id="67bc0-155">Välj detta alternativ om du vill tillåta att medarbetare skickar utgiftsrapporter för godkännande som antingen överstiger tillåten budget som har angetts i budgetregistret eller tillåten budget för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="67bc0-155">Select this option to allow employees to submit expense reports for approval that exceed either the allowed budget that is set in the budget register or the allowed budget for a project.</span></span>                |
|<span data-ttu-id="67bc0-156">**Tillåt godkännande av utgiftsrapport vid budgetöverskridningar endast för budgetregister**</span><span class="sxs-lookup"><span data-stu-id="67bc0-156">**Allow expense report approval on budget overrun for budget register only**</span></span>                | <span data-ttu-id="67bc0-157">Välj detta alternativ om du vill tillåta godkännare att godkänna utgiftsrapporter som överskrider den tillåtna budget som anges i budgetregistret.</span><span class="sxs-lookup"><span data-stu-id="67bc0-157">Select this option to allow approvers to approve expense reports that exceed the allowed budget that is set in the budget register.</span></span>                                                                       |

### <a name="per-diem"></a><span data-ttu-id="67bc0-158">Traktamente</span><span class="sxs-lookup"><span data-stu-id="67bc0-158">Per diem</span></span>

| <span data-ttu-id="67bc0-159">**Fält**</span><span class="sxs-lookup"><span data-stu-id="67bc0-159">**Field**</span></span>                             | <span data-ttu-id="67bc0-160">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-160">**Description**</span></span>             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|<span data-ttu-id="67bc0-161">**Lägsta antal timmar för dagtraktamente**</span><span class="sxs-lookup"><span data-stu-id="67bc0-161">**Minimum hours for per diem**</span></span>           | <span data-ttu-id="67bc0-162">Ange lägsta standardantal timmar som en medarbetare måste arbeta per dag för att vara berättigad till traktamente för reserelaterade utgifter.</span><span class="sxs-lookup"><span data-stu-id="67bc0-162">Enter the default minimum number of hours that an employee must work in a day to be eligible to receive a per diem for travel-related expenses.</span></span>  <span data-ttu-id="67bc0-163">Detta värde används endast som ett standardvärde för fältet för lägsta antal timmar på traktamenteprisnivåer.</span><span class="sxs-lookup"><span data-stu-id="67bc0-163">This value is only used as a default value for the Minimum hours field on per diem rate tiers.</span></span>                                                                                      |
|<span data-ttu-id="67bc0-164">**Måltidsprocent**</span><span class="sxs-lookup"><span data-stu-id="67bc0-164">**Meal percent**</span></span>                          | <span data-ttu-id="67bc0-165">Ange en standardprocentsats för traktamentet för måltider som används på den första och sista dagen i den reserelaterade utgiften när fältet **beräkna måltidsavdrag genom** anges till antingen **Måltidstyp per dag** eller **Antal måltider per dag**.</span><span class="sxs-lookup"><span data-stu-id="67bc0-165">Enter the default percentage of the per diem for meals that is used on the first and last days of the travel-related expense when the **Calculate meal reduction by** field is set to either **Meal type per day** or **Number of meals per day**.</span></span> <span data-ttu-id="67bc0-166">Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag.</span><span class="sxs-lookup"><span data-stu-id="67bc0-166">The work day on the first and last days may be shorter than a standard work day.</span></span> <span data-ttu-id="67bc0-167">Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet.</span><span class="sxs-lookup"><span data-stu-id="67bc0-167">Therefore, the amount of the per diem on these days may differ from the standard amount.</span></span> <span data-ttu-id="67bc0-168">Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00.</span><span class="sxs-lookup"><span data-stu-id="67bc0-168">If the percent is set to 0, then the first and last day deductions will be 0.00.</span></span> |
|<span data-ttu-id="67bc0-169">**Hotellprocent**</span><span class="sxs-lookup"><span data-stu-id="67bc0-169">**Hotel percent**</span></span>                        | <span data-ttu-id="67bc0-170">Ange en standardprocentsats för traktamentet för hotell som används på de första och sista dagarna för den reserelaterade utgiften.</span><span class="sxs-lookup"><span data-stu-id="67bc0-170">Enter the default percentage of the per diem for hotels that is used on the first and last days of the travel-related expense.</span></span> <span data-ttu-id="67bc0-171">Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag.</span><span class="sxs-lookup"><span data-stu-id="67bc0-171">The work day on the first and last days may be shorter than a standard work day.</span></span> <span data-ttu-id="67bc0-172">Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet.</span><span class="sxs-lookup"><span data-stu-id="67bc0-172">Therefore, the amount of the per diem on these days may differ from the standard amount.</span></span> <span data-ttu-id="67bc0-173">Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00.</span><span class="sxs-lookup"><span data-stu-id="67bc0-173">If the percent is set to 0, then the first and last day deductions will be 0.00.</span></span>                                              |
|<span data-ttu-id="67bc0-174">**Annan procent**</span><span class="sxs-lookup"><span data-stu-id="67bc0-174">**Other percent**</span></span>                        | <span data-ttu-id="67bc0-175">Ange en standardprocentsats för traktamentet för diverse utgifter som används på de första och sista dagarna för den reserelaterade utgiften.</span><span class="sxs-lookup"><span data-stu-id="67bc0-175">Enter the default percentage of the per diem for miscellaneous expenses that is used on the first and last days of the travel-related expense.</span></span> <span data-ttu-id="67bc0-176">Arbetsdagen den första och sista dagen, kan vara kortare än en standardarbetsdag.</span><span class="sxs-lookup"><span data-stu-id="67bc0-176">The work day on the first and last days may be shorter than a standard work day.</span></span> <span data-ttu-id="67bc0-177">Därför kan beloppet för dagtraktamente dessa dagar skilja sig från standardbeloppet.</span><span class="sxs-lookup"><span data-stu-id="67bc0-177">Therefore, the amount of the per diem on these days may differ from the standard amount.</span></span> <span data-ttu-id="67bc0-178">Om procenttalet ställs in på 0, kommer de första och sista dagsavdragen vara 0,00.</span><span class="sxs-lookup"><span data-stu-id="67bc0-178">If the percent is set to 0, then the first and last day deductions will be 0.00.</span></span>                                                                                                     |
|<span data-ttu-id="67bc0-179">**Reducering (procentandel) för frukost**</span><span class="sxs-lookup"><span data-stu-id="67bc0-179">**Reduction in percentage for breakfast**</span></span> | <span data-ttu-id="67bc0-180">Ange beloppet som dagtraktamentet minskar för frukost.</span><span class="sxs-lookup"><span data-stu-id="67bc0-180">Enter the amount that the per diem is reduced for breakfast.</span></span> <span data-ttu-id="67bc0-181">Om medarbetaren till exempel får gratis frukost kan du välja att sänka beloppet för dagtraktamentet med 10 procent.</span><span class="sxs-lookup"><span data-stu-id="67bc0-181">For example, if an employee receives a complimentary breakfast, you may want to reduce the amount of the per diem by 10 percent.</span></span>                               |
|<span data-ttu-id="67bc0-182">**Reducering (procentandel) för lunch**</span><span class="sxs-lookup"><span data-stu-id="67bc0-182">**Reduction in percentage for lunch**</span></span>    | <span data-ttu-id="67bc0-183">Ange beloppet som dagtraktamentet minskar för lunch.</span><span class="sxs-lookup"><span data-stu-id="67bc0-183">Enter the amount that the per diem is reduced for lunch.</span></span> <span data-ttu-id="67bc0-184">Om medarbetaren till exempel får gratis lunch kan du välja att sänka beloppet för dagtraktamentet med 15 procent.</span><span class="sxs-lookup"><span data-stu-id="67bc0-184">For example, if an employee receives a complimentary lunch, you may want to reduce the amount of the per diem by 15 percent.</span></span>                                       |
|<span data-ttu-id="67bc0-185">**Reducering (procentandel) för middag**</span><span class="sxs-lookup"><span data-stu-id="67bc0-185">**Reduction in percentage for dinner**</span></span>   | <span data-ttu-id="67bc0-186">Ange beloppet som dagtraktamentet minskar för middag.</span><span class="sxs-lookup"><span data-stu-id="67bc0-186">Enter the amount that the per diem is reduced for dinner.</span></span> <span data-ttu-id="67bc0-187">Om medarbetaren till exempel får gratis middag kan du välja att sänka beloppet för dagtraktamentet med 25 procent.</span><span class="sxs-lookup"><span data-stu-id="67bc0-187">For example, if an employee receives a complimentary dinner, you may want to reduce the amount of the per diem by 25 percent.</span></span>                                     |
|<span data-ttu-id="67bc0-188">**Beräkna måltidsreducering med**</span><span class="sxs-lookup"><span data-stu-id="67bc0-188">**Calculate meal reduction by**</span></span>         | <span data-ttu-id="67bc0-189">Välj hur systemet beräknar reducering av traktamente genom att välja om reduceringen baseras på måltidstyp per resa eller per dag, eller om den reduceras baserat på antalet måltider som tillåts per dag.</span><span class="sxs-lookup"><span data-stu-id="67bc0-189">Select how the system should calculate the per diem meal reduction by selecting if the reduction is based on the meal type per trip or per day, or if the reduction is based on the number of meals allowed per day.</span></span>|
|<span data-ttu-id="67bc0-190">**Avrundning av dagtraktamente**</span><span class="sxs-lookup"><span data-stu-id="67bc0-190">**Per diem rounding**</span></span>                  | <span data-ttu-id="67bc0-191">Välj den typ av avrundning som ska användas för dagtraktamentsutgifter.</span><span class="sxs-lookup"><span data-stu-id="67bc0-191">Select the type of rounding that is used for per diem expenses.</span></span> <span data-ttu-id="67bc0-192">Om du väljer normal avrundning avrundas traktamenteutgifter som har ett belopp på 0,50 upp till 1,00 och traktamentesutgifter som har ett belopp som är mindre än 0,50 avrundas nedåt till 0,00.</span><span class="sxs-lookup"><span data-stu-id="67bc0-192">If you select normal rounding, any per diem expense that has an amount of 0.50 is rounded up to 1.00, and any per diem expense that has an amount that is less than 0.50 is rounded down to 0.00.</span></span>                                                                                              |
|<span data-ttu-id="67bc0-193">**Basera beräkning av dagtraktamente på**</span><span class="sxs-lookup"><span data-stu-id="67bc0-193">**Base per diem calculation on**</span></span>         | <span data-ttu-id="67bc0-194">Anger om beloppet för dagtraktamenten baseras på en kalenderdag eller en 24-timmars period.</span><span class="sxs-lookup"><span data-stu-id="67bc0-194">Select whether a per diem amount is based on a calendar day or a 24-hour period.</span></span>       |

### <a name="fax-cover-pages"></a><span data-ttu-id="67bc0-195">Faxförsättssida</span><span class="sxs-lookup"><span data-stu-id="67bc0-195">Fax cover pages</span></span>

| <span data-ttu-id="67bc0-196">**Fält**</span><span class="sxs-lookup"><span data-stu-id="67bc0-196">**Field**</span></span>                      | <span data-ttu-id="67bc0-197">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-197">**Description**</span></span>            |
|--------------------------------|-----------------------------------------------------------------------------|
| <span data-ttu-id="67bc0-198">**Instruktioner**</span><span class="sxs-lookup"><span data-stu-id="67bc0-198">**Instructions**</span></span>                   | <span data-ttu-id="67bc0-199">Ange instruktionerna som anställda måste följa när de skapar en försättssida för ett faxmeddelande som används för att skicka kvitton relaterade till en utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-199">Enter the instructions that employees must follow when they create a cover page for a fax that is used to send receipts that are related to an expense report.</span></span> <span data-ttu-id="67bc0-200">Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk.</span><span class="sxs-lookup"><span data-stu-id="67bc0-200">Click the **Translations** button to enter language-specific text that will be displayed based on the user language.</span></span> |
|<span data-ttu-id="67bc0-201">**Användar-ID (streckkodsinformation)**</span><span class="sxs-lookup"><span data-stu-id="67bc0-201">**User ID (Bar code information)**</span></span> | <span data-ttu-id="67bc0-202">Välj det här alternativet om du vill lagra en arbetares unika identifierare i streckkoden som används på faxets försättssida.</span><span class="sxs-lookup"><span data-stu-id="67bc0-202">Select this option to store an employee’s unique identifier in the bar code that is used on the cover page of the fax.</span></span>                 |
|<span data-ttu-id="67bc0-203">**Streckkod**</span><span class="sxs-lookup"><span data-stu-id="67bc0-203">**Bar code**</span></span>                      | <span data-ttu-id="67bc0-204">Välj streckkoden som används på försättssidan av faxet.</span><span class="sxs-lookup"><span data-stu-id="67bc0-204">Select the bar code that is used on the cover page of the fax.</span></span> <span data-ttu-id="67bc0-205">Streckkoder 39 och 128 stöds med utgiftshantering.</span><span class="sxs-lookup"><span data-stu-id="67bc0-205">Bar codes 39 and 128 are supported with Expense management.</span></span>               |

### <a name="anti-corruption"></a><span data-ttu-id="67bc0-206">Antikorruption</span><span class="sxs-lookup"><span data-stu-id="67bc0-206">Anti-corruption</span></span>

| <span data-ttu-id="67bc0-207">**Fält**</span><span class="sxs-lookup"><span data-stu-id="67bc0-207">**Field**</span></span>                             | <span data-ttu-id="67bc0-208">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="67bc0-208">**Description**</span></span>      |
|---------------------------------------|------------------------------------------------------------------------|
|<span data-ttu-id="67bc0-209">**Visa antikorruptionsattestering**</span><span class="sxs-lookup"><span data-stu-id="67bc0-209">**Display anti-corruption attestation**</span></span>   | <span data-ttu-id="67bc0-210">Välj detta alternativ om du vill visa antikorruptionstexten när du skapar en ny utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-210">Select this option to display the anti-corruption text when creating a new expense report.</span></span> <span data-ttu-id="67bc0-211">Särskilda kostnadskategorier kan aktiveras som kräver att antikorruptionsattestering väljs i utgiftsrapporten.</span><span class="sxs-lookup"><span data-stu-id="67bc0-211">Specific expense categories can then be enabled that will require the anti-corruption attestation to be selected on the expense report.</span></span> <span data-ttu-id="67bc0-212">Exempelvis kan en gåvokategori relaterad till officiella offentliga utgifter kräva att medarbetare bekräftar att utgiften uppfyller företagets policy relaterat till statliga tjänstemän.</span><span class="sxs-lookup"><span data-stu-id="67bc0-212">For example, a gift category related to a government official expense may require the employee to confirm that the expense meets company policy related to government officials.</span></span> |
|<span data-ttu-id="67bc0-213">**Antikorruptionsmeddelande till insändare**</span><span class="sxs-lookup"><span data-stu-id="67bc0-213">**Anti-corruption message for submitter**</span></span> | <span data-ttu-id="67bc0-214">Ange den text som ska visas för medarbetaren när du skapar en ny utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-214">Enter the text that will be displayed to the employee when creating a new expense report.</span></span> <span data-ttu-id="67bc0-215">Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk.</span><span class="sxs-lookup"><span data-stu-id="67bc0-215">Click the **Translations** button to enter language specific text that will be displayed based on the user language.</span></span>         |
|<span data-ttu-id="67bc0-216">**Antikorruptionsmeddelande till godkännare**</span><span class="sxs-lookup"><span data-stu-id="67bc0-216">**Anti-corruption message for approver**</span></span>  | <span data-ttu-id="67bc0-217">Ange den text som ska visas för godkännaren när du skapar en ny utgiftsrapport.</span><span class="sxs-lookup"><span data-stu-id="67bc0-217">Enter the text that will be displayed to the approver when creating a new expense report.</span></span> <span data-ttu-id="67bc0-218">Klicka på knappen **översättningar** för att ange språkspecifik text som ska visas baserat på användarens språk.</span><span class="sxs-lookup"><span data-stu-id="67bc0-218">Click the **Translations** button to enter language specific text that will be displayed based on the user language.</span></span>        |
