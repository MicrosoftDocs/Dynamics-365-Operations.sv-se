---
title: Översikt över avdragen indiskt moms vid källa (TDS)
description: Det här ämnet ger detaljerad information om indiskt momsavdrag vid källan (TDS). TDS-dokumentationen innehåller funktioner för den här kapaciteten.
author: kailiang
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023611"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="7aed0-104">Översikt över avdragen indiskt moms vid källa (TDS)</span><span class="sxs-lookup"><span data-stu-id="7aed0-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7aed0-105">Det här ämnet ger detaljerad information om indiskt momsavdrag vid källan (TDS).</span><span class="sxs-lookup"><span data-stu-id="7aed0-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="7aed0-106">TDS-dokumentationen innehåller funktioner för den här kapaciteten.</span><span class="sxs-lookup"><span data-stu-id="7aed0-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="7aed0-107">Här förklaras också de grundläggande inställningarna för TDS, beräknar TDS för transaktioner, slutför TDS-kvittningsprocessen, registrerar TDS-certifikatnummer och genererar TDS-förfrågningar, TDS-utdrag och TDS-certifikat.</span><span class="sxs-lookup"><span data-stu-id="7aed0-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="7aed0-108">Dokumentationen innehåller följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="7aed0-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="7aed0-109">Grundinställning för TDS</span><span class="sxs-lookup"><span data-stu-id="7aed0-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="7aed0-110">Formeldesigner och tröskelgränsfunktion som används för TDS-beräkning</span><span class="sxs-lookup"><span data-stu-id="7aed0-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="7aed0-111">Beräkning av TDS på fakturor, betalningar, skuldsedlar och koncerninterna transaktioner</span><span class="sxs-lookup"><span data-stu-id="7aed0-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="7aed0-112">Periodisk TDS-kvittningsprocess och kvittning av TDS-belopp till leverantörer inom TDS-myndigheten</span><span class="sxs-lookup"><span data-stu-id="7aed0-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="7aed0-113">Registrera och uppdatera TDS-certifikatnummer och -datum</span><span class="sxs-lookup"><span data-stu-id="7aed0-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="7aed0-114">Introduktion till TDS</span><span class="sxs-lookup"><span data-stu-id="7aed0-114">Introduction to TDS</span></span>

<span data-ttu-id="7aed0-115">Enligt inkomstskattelagen från 1961 dras inkomstskatt av vid källan av mottagaren av tjänsten vid förskottsbetalningen eller kreditredovisningen, beroende på vilket av alternativen som inträffar först.</span><span class="sxs-lookup"><span data-stu-id="7aed0-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="7aed0-116">Den person som gör betalningen måste dra av momsbeloppet och bara betala nettosaldot till tjänsteleverantören.</span><span class="sxs-lookup"><span data-stu-id="7aed0-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="7aed0-117">TDS tillämpas på tjänster som staten anger, och skatten dras av genom att använda de satser som staten anger för en period.</span><span class="sxs-lookup"><span data-stu-id="7aed0-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="7aed0-118">Avdragssatsen baseras på statusen för enheten som tar emot betalningen eller tillhandahåller tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7aed0-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="7aed0-119">Status inkluderar **Individ**, **Hinduistisk odelad familj** (**HUF**), **Företag**, **Firma**, **Association av personer** (**AOP**), **Samling individer** (**BOI**) och **Lokan myndighet**.</span><span class="sxs-lookup"><span data-stu-id="7aed0-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="7aed0-120">I de följande avsnitten listas de tjänster som TDS används på, enligt vad som angetts av Indiens regering.</span><span class="sxs-lookup"><span data-stu-id="7aed0-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="7aed0-121">**Invånare**</span><span class="sxs-lookup"><span data-stu-id="7aed0-121">**Residents**</span></span>

- <span data-ttu-id="7aed0-122">Löneinkomst (under avsnitt 192)</span><span class="sxs-lookup"><span data-stu-id="7aed0-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="7aed0-123">Ränteintäkter på värdepapper (under avsnitt 193)</span><span class="sxs-lookup"><span data-stu-id="7aed0-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="7aed0-124">Inkomst från utdelningar (under avsnitt 194)</span><span class="sxs-lookup"><span data-stu-id="7aed0-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="7aed0-125">Inkomst från ränta (under avsnitt 194A)</span><span class="sxs-lookup"><span data-stu-id="7aed0-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="7aed0-126">Inkomst från lotterier eller spel (under avsnitt 194B)</span><span class="sxs-lookup"><span data-stu-id="7aed0-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="7aed0-127">Vinst från hästkapplöpning osv. (Under avsnitt 194BB)</span><span class="sxs-lookup"><span data-stu-id="7aed0-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="7aed0-128">Leverantörer och underleverantörer (under avsnitt 194C)</span><span class="sxs-lookup"><span data-stu-id="7aed0-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="7aed0-129">Försäkringskommission (under avsnitt 194D)</span><span class="sxs-lookup"><span data-stu-id="7aed0-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="7aed0-130">Intäkt från insättning enligt nationella sparscheman (under avsnitt 194EE)</span><span class="sxs-lookup"><span data-stu-id="7aed0-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="7aed0-131">Inkomst från en gemensam fond eller UTI (under avsnitt 194F)</span><span class="sxs-lookup"><span data-stu-id="7aed0-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="7aed0-132">Provision, ersättning, pris osv. från försäljning eller lotteri (under avsnitt 194G)</span><span class="sxs-lookup"><span data-stu-id="7aed0-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="7aed0-133">Betalning av provision eller mäklararvode (under avsnitt 194H)</span><span class="sxs-lookup"><span data-stu-id="7aed0-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="7aed0-134">Hyra (under avsnitt 194I)</span><span class="sxs-lookup"><span data-stu-id="7aed0-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="7aed0-135">Yrkesservice (under avsnitt 194J)</span><span class="sxs-lookup"><span data-stu-id="7aed0-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="7aed0-136">Inkomst från enheter (under avsnitt 194K)</span><span class="sxs-lookup"><span data-stu-id="7aed0-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="7aed0-137">Betalning av kompensation vid anskaffning av viss fast egendom (under avsnitt 194LA)</span><span class="sxs-lookup"><span data-stu-id="7aed0-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="7aed0-138">**Icke-invånare**</span><span class="sxs-lookup"><span data-stu-id="7aed0-138">**Non-residents**</span></span>

- <span data-ttu-id="7aed0-139">Betalningar till utländska atleter eller sportföreningar (under avsnitt 194E)</span><span class="sxs-lookup"><span data-stu-id="7aed0-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="7aed0-140">Andra summor (under avsnitt 195)</span><span class="sxs-lookup"><span data-stu-id="7aed0-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="7aed0-141">Inkomst med avseende på enheter som inte är invånare (under avsnitt 196A)</span><span class="sxs-lookup"><span data-stu-id="7aed0-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="7aed0-142">Inkomst från utländska valutor eller aktier i det indiska företaget (under avsnitt 196C)</span><span class="sxs-lookup"><span data-stu-id="7aed0-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="7aed0-143">Utländska investerares intäkter från värdepapper (under avsnitt 196D)</span><span class="sxs-lookup"><span data-stu-id="7aed0-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="7aed0-144">Lön och alla andra positiva inkomster under varje inkomsthuvud (avsnitt 192)</span><span class="sxs-lookup"><span data-stu-id="7aed0-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="7aed0-145">Ränta på värdepapper (avsnitt 193)</span><span class="sxs-lookup"><span data-stu-id="7aed0-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="7aed0-146">Annan ränta än ränta på värdepapper (avsnitt 194A)</span><span class="sxs-lookup"><span data-stu-id="7aed0-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="7aed0-147">Betalningar till leverantörer och underleverantörer (avsnitt 194C)</span><span class="sxs-lookup"><span data-stu-id="7aed0-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="7aed0-148">Vinster från lotteri eller korsord (avsnitt 194B)</span><span class="sxs-lookup"><span data-stu-id="7aed0-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="7aed0-149">Vinster från hästkapplöpning (avsnitt 194BB)</span><span class="sxs-lookup"><span data-stu-id="7aed0-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="7aed0-150">Försäkringsprovision som täcker alla betalningar för att anskaffa försäkringsaffärer (avsnitt 194D)</span><span class="sxs-lookup"><span data-stu-id="7aed0-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="7aed0-151">Alla andra räntor än ränta på säkerheter som ska betalas till icke-invånare som inte är ett företag eller till ett utländskt företag (avsnitt 195)</span><span class="sxs-lookup"><span data-stu-id="7aed0-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="7aed0-152">Betalning till atleter som inte är invånare, inklusive atlet- och sportassociationer eller -institutioner.</span><span class="sxs-lookup"><span data-stu-id="7aed0-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="7aed0-153">För atleter som inte är invånare, betalningar avseende reklam samt artiklar om spel/sport i Indien i tidningar, tidskrifter och så vidare.</span><span class="sxs-lookup"><span data-stu-id="7aed0-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="7aed0-154">ingår (avsnitt 194E)</span><span class="sxs-lookup"><span data-stu-id="7aed0-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="7aed0-155">Betalning för insättningar enligt NSS \[National Savings Scheme\] (avsnitt 194EE)</span><span class="sxs-lookup"><span data-stu-id="7aed0-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="7aed0-156">Betalning av återköpta enheter av gemensam fond eller UTI (avsnitt 194F)</span><span class="sxs-lookup"><span data-stu-id="7aed0-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="7aed0-157">Betalning av provision eller mäklararvode (avsnitt 194H)</span><span class="sxs-lookup"><span data-stu-id="7aed0-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="7aed0-158">Betalning av hyra (avsnitt 194I)</span><span class="sxs-lookup"><span data-stu-id="7aed0-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="7aed0-159">Betalning av avgifter för yrkesmässiga eller tekniska tjänster (avsnitt 194J)</span><span class="sxs-lookup"><span data-stu-id="7aed0-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="7aed0-160">Provision till aktieleverantörer, distributörer, inköpare och säljare av lotter, inklusive ersättning eller pris för sådana lotter (avsnitt 194G)</span><span class="sxs-lookup"><span data-stu-id="7aed0-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="7aed0-161">Intäkter från enheter som köpts i utländsk valuta eller långsiktig kapitalvinst som härrör från överföring av sådana enheter som köpts in i utländsk valuta (avsnitt 196B)</span><span class="sxs-lookup"><span data-stu-id="7aed0-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="7aed0-162">Betalning av annan inkomst än vad gäller ränta eller utdelning på värdepapper och aktier (avsnitt 196C)</span><span class="sxs-lookup"><span data-stu-id="7aed0-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="7aed0-163">TDS beräknas på inköp, försäljning, försäljningsreturer, kreditfakturor, anskaffningar av anläggningstillgångar, förskottsbetalningar, skuldsedlar, moms och koncerninterna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="7aed0-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="7aed0-164">I det aktuella indiska skattescenariot beräknas TDS inte på försäljningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="7aed0-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="7aed0-165">Systemet innehåller dock en bestämmelse för beräkning av TDS som kan återställas på försäljningstransaktioner, särskilt för koncerninterna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="7aed0-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="7aed0-166">Beräkningen av TDS tar alltid hänsyn till tröskelvärdet och undantagströskeln som definieras för TDS-komponenten.</span><span class="sxs-lookup"><span data-stu-id="7aed0-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="7aed0-167">Den periodiska TDS-kvittningsprocessen måste köras, och TDS-betalningar måste kvittas mot leverantörer inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="7aed0-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="7aed0-168">Certifikatnumren och datumen för TDS-certifikat som tas emot från leverantörer eller kunder kan registreras och uppdateras.</span><span class="sxs-lookup"><span data-stu-id="7aed0-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="7aed0-169">Kvartalsutdrag för Formulär 26Q och Formulär 27Q samt Formulär 16A-certifikat för TDS kan också genereras i Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="7aed0-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="7aed0-170">Ställa in och arbeta med TDS</span><span class="sxs-lookup"><span data-stu-id="7aed0-170">Setting up and working with TDS</span></span>

<span data-ttu-id="7aed0-171">Här är en översikt över processen för inställning och arbete med TDS:</span><span class="sxs-lookup"><span data-stu-id="7aed0-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="7aed0-172">**TDS-inställning:**</span><span class="sxs-lookup"><span data-stu-id="7aed0-172">**TDS setup:**</span></span>

    - <span data-ttu-id="7aed0-173">Parameterinställningar:</span><span class="sxs-lookup"><span data-stu-id="7aed0-173">Parameter setup:</span></span>

        - <span data-ttu-id="7aed0-174">Aktivera parametrar som är relaterade till TDS i Redovisningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="7aed0-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="7aed0-175">Ställ in nummerserien för källskattebetalningar i Redovisningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="7aed0-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="7aed0-176">Konfigurera parametrar i Leverantörsreskontra och Kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="7aed0-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="7aed0-177">Grundinställning:</span><span class="sxs-lookup"><span data-stu-id="7aed0-177">Basic setup:</span></span>

        - <span data-ttu-id="7aed0-178">Ställ in TDS-registreringsnummer för ett företag, kunder och leverantörer.</span><span class="sxs-lookup"><span data-stu-id="7aed0-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="7aed0-179">Ställ in TDS-komponentgrupper.</span><span class="sxs-lookup"><span data-stu-id="7aed0-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="7aed0-180">Ställ in TDS-komponenter, koppla TDS-komponentgrupper till dem och definiera tröskelvärde och undantagströskel för dem.</span><span class="sxs-lookup"><span data-stu-id="7aed0-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="7aed0-181">Ställ in TDS-myndigheter.</span><span class="sxs-lookup"><span data-stu-id="7aed0-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="7aed0-182">Ställ in TDS-kvittningsperioder.</span><span class="sxs-lookup"><span data-stu-id="7aed0-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="7aed0-183">Ställ in TDS-momskoder och koppla TDS-komponenter till dem.</span><span class="sxs-lookup"><span data-stu-id="7aed0-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="7aed0-184">Ställ in TDS-momsgrupper och koppla TDS-momskoder till dem.</span><span class="sxs-lookup"><span data-stu-id="7aed0-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="7aed0-185">I formeldesignern definierar du en formel för att beräkna TDS för en TDS-grupp.</span><span class="sxs-lookup"><span data-stu-id="7aed0-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="7aed0-186">Registrera koncessionscertifikatnummer för TDS.</span><span class="sxs-lookup"><span data-stu-id="7aed0-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="7aed0-187">Redovisningskonton och inställningar för företag:</span><span class="sxs-lookup"><span data-stu-id="7aed0-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="7aed0-188">Ställ in leverantörsreskontra och kundreskontra för TDS.</span><span class="sxs-lookup"><span data-stu-id="7aed0-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="7aed0-189">Ställ in ett nummer för skatteavdrag och inkassokonto (TAN) och en avdragstypkategori för företaget.</span><span class="sxs-lookup"><span data-stu-id="7aed0-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="7aed0-190">Övriga inställningar:</span><span class="sxs-lookup"><span data-stu-id="7aed0-190">Other setup:</span></span>

        - <span data-ttu-id="7aed0-191">Ställ in en betalningsplan som inkluderar TDS-allokering.</span><span class="sxs-lookup"><span data-stu-id="7aed0-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="7aed0-192">Ställ in en betalningsavgiftstyp för betalningar till TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="7aed0-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="7aed0-193">Ställ in information om TDS-grupper, permanenta kontonummer (PAN) och TAN för leverantörer och kunder.</span><span class="sxs-lookup"><span data-stu-id="7aed0-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="7aed0-194">**Beräkning av TDS i transaktioner:**</span><span class="sxs-lookup"><span data-stu-id="7aed0-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="7aed0-195">Fakturor och betalningar</span><span class="sxs-lookup"><span data-stu-id="7aed0-195">Invoices and payments</span></span>
    - <span data-ttu-id="7aed0-196">Skuldsedlar</span><span class="sxs-lookup"><span data-stu-id="7aed0-196">Promissory notes</span></span>
    - <span data-ttu-id="7aed0-197">Förskottsbetalningar</span><span class="sxs-lookup"><span data-stu-id="7aed0-197">Advance payments</span></span>
    - <span data-ttu-id="7aed0-198">Förskottsbetalningar</span><span class="sxs-lookup"><span data-stu-id="7aed0-198">Prepayments</span></span>

3. <span data-ttu-id="7aed0-199">**TDS-kvittning:**</span><span class="sxs-lookup"><span data-stu-id="7aed0-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="7aed0-200">Periodisk TDS-kvittningsprocess</span><span class="sxs-lookup"><span data-stu-id="7aed0-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="7aed0-201">Kvittning av TDS-betalningar till TDS-myndigheter och generering av TDS challan</span><span class="sxs-lookup"><span data-stu-id="7aed0-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="7aed0-202">**TDS-förfrågningar, utdrag och certifikat:**</span><span class="sxs-lookup"><span data-stu-id="7aed0-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="7aed0-203">Registrera och uppdatera TDS-certifikatnummer och -datum.</span><span class="sxs-lookup"><span data-stu-id="7aed0-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="7aed0-204">Skapa en TDS-förfrågan och en bokförd TDS-förfrågan.</span><span class="sxs-lookup"><span data-stu-id="7aed0-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="7aed0-205">Generera formulär 27A, formulär 26Q och formulär 27Q TDS och kvartalsutdrag för e-TDS.</span><span class="sxs-lookup"><span data-stu-id="7aed0-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="7aed0-206">Generera formulär 16A TDS-certifikat.</span><span class="sxs-lookup"><span data-stu-id="7aed0-206">Generate a Form 16A TDS certificate.</span></span>
