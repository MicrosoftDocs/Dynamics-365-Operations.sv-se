---
title: Konfigurera utgiftshantering
description: "Det här avsnittet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c87909d9eb3a4d717e0c40289353da0267a51f60
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="configure-expense-management"></a><span data-ttu-id="15bde-103">Konfigurera utgiftshantering</span><span class="sxs-lookup"><span data-stu-id="15bde-103">Configure expense management</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="15bde-104">Det här ämnet ger en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar Utgiftshantering i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="15bde-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="15bde-105">I utgiftshanteraren kan du lagra information om betalsätt, reserekvisitioner, utgiftsrapporter, policyer och så vidare.</span><span class="sxs-lookup"><span data-stu-id="15bde-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="15bde-106">Eftersom flera av besluten som du gör när du planerar konfigurationen för Utgiftshantering baseras på organisationens hierarki och ekonomiska struktur, måste du hänvisa till planläggningsdokumenten för dessa områden.</span><span class="sxs-lookup"><span data-stu-id="15bde-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="15bde-107">Koncerninterna utgifter</span><span class="sxs-lookup"><span data-stu-id="15bde-107">Intercompany expenses</span></span>

<span data-ttu-id="15bde-108">När du aktiverar företagsinterna utgifter tillåter du juridiska entiteter och medarbetare att ådra sig utgifter å en annan juridisk persons vägnar, samt att inhämta betalning från den juridiska anställningspersonen inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="15bde-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="15bde-109">En medarbetare inom Juridisk Person A slutför exempelvis ett projekt för Juridisk Person B, och projektet medför reserelaterade utgifter.</span><span class="sxs-lookup"><span data-stu-id="15bde-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="15bde-110">Om företagsinterna utgifter har aktiverats kan medarbetaren därefter lämna in en utgiftsrapport som bokför utgiften hos Juridisk Person B, och utgiften måste sedan betalas av Juridisk Person A. Om din organisation inte har flera olika juridiska personer, behöver du inte aktivera företagsinterna utgifter.</span><span class="sxs-lookup"><span data-stu-id="15bde-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="15bde-111">**Beslut:** Vill du aktivera koncerninterna utgifter?</span><span class="sxs-lookup"><span data-stu-id="15bde-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="15bde-112">Ekonomisk styrning</span><span class="sxs-lookup"><span data-stu-id="15bde-112">Financial management</span></span>

<span data-ttu-id="15bde-113">Utgiftshantering är väl integrerad med ekonomisk hanteringen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="15bde-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="15bde-114">Stora delar av dina inställningar för utgiftshantering baseras på de beslut som du har fattat angående din organisations finanser.</span><span class="sxs-lookup"><span data-stu-id="15bde-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="15bde-115">Följande avsnitt beskriver de områden som kräver planering och beslut, vilket baseras på din organisations finansiella beslut samt vägledningen från ditt ledningsteam.</span><span class="sxs-lookup"><span data-stu-id="15bde-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="15bde-116">Dagtraktamenten</span><span class="sxs-lookup"><span data-stu-id="15bde-116">Per diems</span></span>

<span data-ttu-id="15bde-117">Du måste definiera medarbetarens dagtraktamente som din organisation ger.</span><span class="sxs-lookup"><span data-stu-id="15bde-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="15bde-118">Eftersom dagtraktamente vanligtvis används för utgifter som till exempel logi, måltider och andra tillfälliga utgifter, kan du skapa regler för dagtraktamenteavdragen som din organisation ger.</span><span class="sxs-lookup"><span data-stu-id="15bde-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="15bde-119">traktamentsnivåerna kan baseras på årstid, resmål eller båda.</span><span class="sxs-lookup"><span data-stu-id="15bde-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="15bde-120">När du skapar en traktamentsregel kan du ange att hålla inne en procentandel av traktamentstariffen om medarbetaren bjuds på måltider eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="15bde-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="15bde-121">Du kan också definiera traktamentsreglernas skikt för att ange lägsta och högsta antal timmar som dagtraktamentetariffen kan tillämpas på en arbetares resor.</span><span class="sxs-lookup"><span data-stu-id="15bde-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="15bde-122">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-122">**Decisions:**</span></span>

- <span data-ttu-id="15bde-123">Standardregler för traktamente för de första och sista dagarna:</span><span class="sxs-lookup"><span data-stu-id="15bde-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="15bde-124">Vad är minsta antal timmar som en medarbetare kan fordra för en dag och får fortfarande en dagtraktamente?</span><span class="sxs-lookup"><span data-stu-id="15bde-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="15bde-125">Minskar det belopp som erbjuds för måltider under första och sista dagen?</span><span class="sxs-lookup"><span data-stu-id="15bde-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="15bde-126">Vid minskning, till vilken procentsats sker minskningen?</span><span class="sxs-lookup"><span data-stu-id="15bde-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="15bde-127">Minskar det belopp som erbjuds för hotell under första och sista dagen?</span><span class="sxs-lookup"><span data-stu-id="15bde-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="15bde-128">Vid minskning, till vilken procentsats sker minskningen?</span><span class="sxs-lookup"><span data-stu-id="15bde-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="15bde-129">Minskar det belopp som erbjuds för andra utgifter som uppstår under första och sista dagen?</span><span class="sxs-lookup"><span data-stu-id="15bde-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="15bde-130">Vid minskning, till vilken procentsats sker minskningen?</span><span class="sxs-lookup"><span data-stu-id="15bde-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="15bde-131">Standardregler för traktamente:</span><span class="sxs-lookup"><span data-stu-id="15bde-131">Default per diem rules:</span></span>

    - <span data-ttu-id="15bde-132">Finns det en procentuell reducering i dagtraktamentet för varje måltid om till exempel måltiden är kostnadsfri?</span><span class="sxs-lookup"><span data-stu-id="15bde-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="15bde-133">Vid minskning, till vilken procentsats sker minskningen för respektive måltid?</span><span class="sxs-lookup"><span data-stu-id="15bde-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="15bde-134">Beräknas måltidsreduceringen per dag, per resa eller med antal måltider per dag?</span><span class="sxs-lookup"><span data-stu-id="15bde-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="15bde-135">Bör traktamentsbelopp avrundas på sedvanligt sätt, eller avrundas uppåt?</span><span class="sxs-lookup"><span data-stu-id="15bde-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="15bde-136">Beräknas dagtraktamente på en 24-timmarsperiod eller på en kalenderdag?</span><span class="sxs-lookup"><span data-stu-id="15bde-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="15bde-137">Traktamentsregler baserade på plats:</span><span class="sxs-lookup"><span data-stu-id="15bde-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="15bde-138">Varierar traktamentsregler beroende på plats?</span><span class="sxs-lookup"><span data-stu-id="15bde-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="15bde-139">Vilka platser är inkluderade i?</span><span class="sxs-lookup"><span data-stu-id="15bde-139">What locations are included?</span></span>
    - <span data-ttu-id="15bde-140">Om traktamentsnivåerna varierar efter plats och för varje enskild plats, vilket procentandelsbelopp erbjuds för följande utgiftstyper:</span><span class="sxs-lookup"><span data-stu-id="15bde-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="15bde-141">Måltider</span><span class="sxs-lookup"><span data-stu-id="15bde-141">Meals</span></span>
        - <span data-ttu-id="15bde-142">Hotell</span><span class="sxs-lookup"><span data-stu-id="15bde-142">Hotel</span></span>
        - <span data-ttu-id="15bde-143">Andra kostnader</span><span class="sxs-lookup"><span data-stu-id="15bde-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="15bde-144">Utgiftshanteringsjournaler och konton</span><span class="sxs-lookup"><span data-stu-id="15bde-144">Expense management journals and accounts</span></span>

<span data-ttu-id="15bde-145">Utgiftshantering kräver att du använder flera journaler och konton.</span><span class="sxs-lookup"><span data-stu-id="15bde-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="15bde-146">Du måste bestämma om till exempel samma konto används för förskott och kreditkortstvister.</span><span class="sxs-lookup"><span data-stu-id="15bde-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="15bde-147">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-147">**Decisions:**</span></span>

- <span data-ttu-id="15bde-148">I vilken redovisningsjournal bokförs godkända utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="15bde-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="15bde-149">Vilket konto används för förskott?</span><span class="sxs-lookup"><span data-stu-id="15bde-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="15bde-150">Ska förskott bokföras direkt?</span><span class="sxs-lookup"><span data-stu-id="15bde-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="15bde-151">Betalningsmetoder</span><span class="sxs-lookup"><span data-stu-id="15bde-151">Payment methods</span></span>

<span data-ttu-id="15bde-152">När du beviljar medarbetare utlägg på uppdrag av ditt företag, måste du definiera de betalningsmetoder som medarbetare har behörighet att använda.</span><span class="sxs-lookup"><span data-stu-id="15bde-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="15bde-153">Du kan till exempel tillåta att använda kontanter eller ett företagskort.</span><span class="sxs-lookup"><span data-stu-id="15bde-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="15bde-154">Du kan även tillåta medarbetare att använda personliga kreditkort och sedan ersätta dem.</span><span class="sxs-lookup"><span data-stu-id="15bde-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="15bde-155">Du måste göra följande beslut för varje betalningsmetod som du tillåter.</span><span class="sxs-lookup"><span data-stu-id="15bde-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="15bde-156">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-156">**Decisions:**</span></span>

- <span data-ttu-id="15bde-157">Vilka betalningsmetoder är tillåtna?</span><span class="sxs-lookup"><span data-stu-id="15bde-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="15bde-158">Vem äger betalningsmetoden för utgifterna?</span><span class="sxs-lookup"><span data-stu-id="15bde-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="15bde-159">Finns det en motkontotyp?</span><span class="sxs-lookup"><span data-stu-id="15bde-159">Is there an offset account type?</span></span> <span data-ttu-id="15bde-160">Vid konto av förskjutningstyp, vilken typ?</span><span class="sxs-lookup"><span data-stu-id="15bde-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="15bde-161">Om det finns ett motkonto, vilket är kontot?</span><span class="sxs-lookup"><span data-stu-id="15bde-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="15bde-162">Om betalningsmetoden är kreditkort, ska betalningsmetoden användas endast med importerade transaktioner?</span><span class="sxs-lookup"><span data-stu-id="15bde-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="15bde-163">Utgiftskategorier och delade kategorier</span><span class="sxs-lookup"><span data-stu-id="15bde-163">Expense categories and shared categories</span></span>

<span data-ttu-id="15bde-164">När medarbetare skapar en utgiftsrapport måste varje utgift som de registrerar associeras med en utgiftskategori.</span><span class="sxs-lookup"><span data-stu-id="15bde-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="15bde-165">Utgiftskategorier baseras på delade kategorier som kan delas över samtliga juridiska entiteter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="15bde-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="15bde-166">Dessa kategorier kan också delas inom projekthantering och redovisning, beroende på hur din organisation är utformad.</span><span class="sxs-lookup"><span data-stu-id="15bde-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="15bde-167">Baserat på hur din organisation är utformat samt på vägledning från implementeringsteamet måste du avgöra huruvida kategorierna som används i utgiftshanteringen endast ska användas där, eller om de ska delas mellan projekthantering och redovisnings- och utgiftshantering.</span><span class="sxs-lookup"><span data-stu-id="15bde-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="15bde-168">Observera att dessa kategorier kan delas mellan projekt och utgifter eller projekt och produktion, men inte mellan utgifter och produktion.</span><span class="sxs-lookup"><span data-stu-id="15bde-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="15bde-169">Du måste göra följande beslut för varje utgiftskategori.</span><span class="sxs-lookup"><span data-stu-id="15bde-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="15bde-170">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-170">**Decisions:**</span></span>

- <span data-ttu-id="15bde-171">Vilken är utgiftskategorin?</span><span class="sxs-lookup"><span data-stu-id="15bde-171">What is the expense category?</span></span> <span data-ttu-id="15bde-172">Exemplen omfattar kategorier för flyg, hotell eller reseersättning.</span><span class="sxs-lookup"><span data-stu-id="15bde-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="15bde-173">Kan utgiftskategorin även användas inom projekthantering och redovisning?</span><span class="sxs-lookup"><span data-stu-id="15bde-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="15bde-174">Vilken är utgiftstypen?</span><span class="sxs-lookup"><span data-stu-id="15bde-174">What is the expense type?</span></span>
- <span data-ttu-id="15bde-175">Vilken är standardbetalningsmetoden för utgiftskategorin?</span><span class="sxs-lookup"><span data-stu-id="15bde-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="15bde-176">Måste utgifter i utgiftskategorin specificeras?</span><span class="sxs-lookup"><span data-stu-id="15bde-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="15bde-177">Vilket är huvudstandardkontot för utgiftskategorin?</span><span class="sxs-lookup"><span data-stu-id="15bde-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="15bde-178">Vilken är standardartikelmomsgruppen för utgiftskategorin?</span><span class="sxs-lookup"><span data-stu-id="15bde-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="15bde-179">Är ytterligare betalningsmetoder tillåtna för utgiftskategorin?</span><span class="sxs-lookup"><span data-stu-id="15bde-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="15bde-180">Om ytterligare betalsätt tillåts, vilka betalsätt?</span><span class="sxs-lookup"><span data-stu-id="15bde-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="15bde-181">Finns det underkategorier i denna utgiftskategori?</span><span class="sxs-lookup"><span data-stu-id="15bde-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="15bde-182">Om det finns underkategorier måste du också fatta följande beslut:</span><span class="sxs-lookup"><span data-stu-id="15bde-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="15bde-183">Exkluderas någon av underkategorierna från momsåterbetalning?</span><span class="sxs-lookup"><span data-stu-id="15bde-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="15bde-184">Vilken är underkategoriernas artikelmomsgrupp?</span><span class="sxs-lookup"><span data-stu-id="15bde-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="15bde-185">Om utgiftskategorin även används inom projekthantering och redovisning, besvara då följande frågor:</span><span class="sxs-lookup"><span data-stu-id="15bde-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="15bde-186">Annars går du vidare till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="15bde-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="15bde-187">Vilka kostnadskonton kommer att användas för följande utgifter?</span><span class="sxs-lookup"><span data-stu-id="15bde-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="15bde-188">Kostnad</span><span class="sxs-lookup"><span data-stu-id="15bde-188">Cost</span></span>
    - <span data-ttu-id="15bde-189">Löneallokering</span><span class="sxs-lookup"><span data-stu-id="15bde-189">Payroll allocation</span></span>
    - <span data-ttu-id="15bde-190">PIA - Kostnadsvärde</span><span class="sxs-lookup"><span data-stu-id="15bde-190">WIP-cost value</span></span>
    - <span data-ttu-id="15bde-191">Kostnad - Artikel</span><span class="sxs-lookup"><span data-stu-id="15bde-191">Cost-item</span></span>
    - <span data-ttu-id="15bde-192">PIA - Kostnadsvärde - Artikel</span><span class="sxs-lookup"><span data-stu-id="15bde-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="15bde-193">Upplupen förlust</span><span class="sxs-lookup"><span data-stu-id="15bde-193">Accrued loss</span></span>
    - <span data-ttu-id="15bde-194">PIA - upplupen förlust</span><span class="sxs-lookup"><span data-stu-id="15bde-194">WIP-accrued loss</span></span>

- <span data-ttu-id="15bde-195">Vilka intäktskonton används för följande?</span><span class="sxs-lookup"><span data-stu-id="15bde-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="15bde-196">Fakturerade intäkter</span><span class="sxs-lookup"><span data-stu-id="15bde-196">Invoiced revenue</span></span>
    - <span data-ttu-id="15bde-197">Upplupna intäkter - Försäljningsvärde</span><span class="sxs-lookup"><span data-stu-id="15bde-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="15bde-198">PIA - Försäljningsvärde</span><span class="sxs-lookup"><span data-stu-id="15bde-198">WIP-sales value</span></span>
    - <span data-ttu-id="15bde-199">Upplupna intäkter - Produktion)</span><span class="sxs-lookup"><span data-stu-id="15bde-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="15bde-200">PIA - Produktion</span><span class="sxs-lookup"><span data-stu-id="15bde-200">WIP-production</span></span>
    - <span data-ttu-id="15bde-201">Upplupna intäkter - Vinst</span><span class="sxs-lookup"><span data-stu-id="15bde-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="15bde-202">PIA - Vinst</span><span class="sxs-lookup"><span data-stu-id="15bde-202">WIP-profit</span></span>
    - <span data-ttu-id="15bde-203">Upplupen intäkt - Abonnemang</span><span class="sxs-lookup"><span data-stu-id="15bde-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="15bde-204">PIA - abonnemang</span><span class="sxs-lookup"><span data-stu-id="15bde-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="15bde-205">Skatter</span><span class="sxs-lookup"><span data-stu-id="15bde-205">Taxes</span></span>

<span data-ttu-id="15bde-206">För utgiftsrelaterade skatter måste du bestämma vad som inkluderas eller aktiveras i utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="15bde-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="15bde-207">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-207">**Decisions:**</span></span>

- <span data-ttu-id="15bde-208">Inkluderas moms i utgiftsbeloppen?</span><span class="sxs-lookup"><span data-stu-id="15bde-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="15bde-209">Ska momsåterbetalning aktiveras på utgifter?</span><span class="sxs-lookup"><span data-stu-id="15bde-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="15bde-210">Du kan inte aktivera skatteåtervinning på utgifter om du valde att tillämpa amerikansk moms och att använda skatteregler när du planerade din redovisning.</span><span class="sxs-lookup"><span data-stu-id="15bde-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="15bde-211">(För att använda amerikansk moms och skatteregler, ange alternativet **Applicera momsskatteregler** som **Ja**.)</span><span class="sxs-lookup"><span data-stu-id="15bde-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="15bde-212">Policyer</span><span class="sxs-lookup"><span data-stu-id="15bde-212">Policies</span></span>

<span data-ttu-id="15bde-213">Genom att skapa policyer för utgiftsrapporter kan du hjälpa din organisation att spara tid och pengar när medarbetarna ådrar sig utgifter å dess vägnar.</span><span class="sxs-lookup"><span data-stu-id="15bde-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="15bde-214">Policyer hjälper till att säkerställa att medarbetarna håller sig inom budget, tillhandahåller all erforderlig information och endast spenderar pengar på nödvändigheter.</span><span class="sxs-lookup"><span data-stu-id="15bde-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="15bde-215">Du måste ta följande beslut för varje utgiftsrapportpolicy och policy för utgiftsrapportgodkännande som du skapar.</span><span class="sxs-lookup"><span data-stu-id="15bde-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="15bde-216">**Beslut:**</span><span class="sxs-lookup"><span data-stu-id="15bde-216">**Decisions:**</span></span>

- <span data-ttu-id="15bde-217">Vilket är namnet på policyn?</span><span class="sxs-lookup"><span data-stu-id="15bde-217">What is the name of the policy?</span></span>
- <span data-ttu-id="15bde-218">Vad gäller utgiftspolicyn för?</span><span class="sxs-lookup"><span data-stu-id="15bde-218">What is the expense policy for?</span></span>
- <span data-ttu-id="15bde-219">Om du tidigare har beslutat att aktivera företagsinterna utgifter, vilka företag inom din organisation omfattas då av denna policy?</span><span class="sxs-lookup"><span data-stu-id="15bde-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="15bde-220">När börjar principen gälla?</span><span class="sxs-lookup"><span data-stu-id="15bde-220">When does the policy become effective?</span></span>
- <span data-ttu-id="15bde-221">När upphör policyn?</span><span class="sxs-lookup"><span data-stu-id="15bde-221">When does the policy expire?</span></span>
- <span data-ttu-id="15bde-222">Vilken är policyregeln?</span><span class="sxs-lookup"><span data-stu-id="15bde-222">What is the policy rule?</span></span>
- <span data-ttu-id="15bde-223">Vilket är resultatet av policyregeln?</span><span class="sxs-lookup"><span data-stu-id="15bde-223">What is the outcome of the policy rule?</span></span>

