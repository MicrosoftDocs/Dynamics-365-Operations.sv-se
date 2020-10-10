---
title: Felsöka priser, rabatter, avtal och avdrag
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med priser, rabatter, avtal och avdrag.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b83490acdc58c9ee0ffae9480f69a99477913843
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834429"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="c90cc-103">Felsöka priser, rabatter, avtal och avdrag</span><span class="sxs-lookup"><span data-stu-id="c90cc-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="c90cc-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med priser, rabatter, avtal och avdrag.</span><span class="sxs-lookup"><span data-stu-id="c90cc-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="c90cc-105">Jag kan inte länka ett inköpsavtal till en inköpsorderrad efter att inköpsordern har skapats.</span><span class="sxs-lookup"><span data-stu-id="c90cc-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="c90cc-106">Ett inköpsavtal måste vara kopplat till en inköpsorder när inköpsordern skapas.</span><span class="sxs-lookup"><span data-stu-id="c90cc-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="c90cc-107">Annars kan inte inköpsorderrader kopplas till inköpsavtalsrader.</span><span class="sxs-lookup"><span data-stu-id="c90cc-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="c90cc-108">Vilken kontroll utlöser meddelandet "uppdatera priser och rabatter som angetts manuellt eller i det externa dokumentet"?</span><span class="sxs-lookup"><span data-stu-id="c90cc-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="c90cc-109">När du ändrar leveransdatumet kan du få ett meddelande om att "uppdatera priser och rabatter som angetts manuellt eller i ett externt dokument".</span><span class="sxs-lookup"><span data-stu-id="c90cc-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="c90cc-110">Det här meddelandet visas om leveransdatumet ändras, kan ett annat handels- eller försäljningsavtal utlösas och orsaka prisändringar.</span><span class="sxs-lookup"><span data-stu-id="c90cc-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="c90cc-111">En ändring av leveransdatumet kan också påverka lagerplaner och annan information.</span><span class="sxs-lookup"><span data-stu-id="c90cc-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="c90cc-112">Meddelandet utlöses när något av datumen eller några andra parametrar ändras.</span><span class="sxs-lookup"><span data-stu-id="c90cc-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="c90cc-113">Syftet med meddelandet är att säkerställa att du är medveten om de prisändringar som kan uppstå på grund av dessa ändringar.</span><span class="sxs-lookup"><span data-stu-id="c90cc-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="c90cc-114">Meddelandet är TAE-dialog (handelsavtalets utvärdering).</span><span class="sxs-lookup"><span data-stu-id="c90cc-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="c90cc-115">En fullständig beskrivning finns i [policyer för utvärdering av handelsavtal](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="c90cc-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="c90cc-116">En inleverans för inköpsorder inkluderar inte alla avgifter.</span><span class="sxs-lookup"><span data-stu-id="c90cc-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="c90cc-117">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="c90cc-117">Reproduce the issue</span></span>

<span data-ttu-id="c90cc-118">Följande procedur anger ett sätt att skapa reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="c90cc-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="c90cc-119">På sidan **Anskaffnings- och källparametrar** på fliken **Leverans** se till att alternativet **Skapa ändringar i produktinleverans** anges till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="c90cc-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="c90cc-120">Skapa en inköpsorder som inkluderar avgifter.</span><span class="sxs-lookup"><span data-stu-id="c90cc-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="c90cc-121">Bekräfta inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="c90cc-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="c90cc-122">Få en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c90cc-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="c90cc-123">Granska den totala inleveransen och jämför den med den förväntade totala summan.</span><span class="sxs-lookup"><span data-stu-id="c90cc-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="c90cc-124">Lägg märke till att inte alla avgifter tas med i inleveransen för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="c90cc-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c90cc-125">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-125">Issue resolution</span></span>

<span data-ttu-id="c90cc-126">Lösningen beror på hur tilläggen har ställts in.</span><span class="sxs-lookup"><span data-stu-id="c90cc-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="c90cc-127">Information om hur du ställer in tillägg för att uppfylla dina krav finns i följande blogginlägg: [Bokför tillägg vid tiden för produktinleveransen](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="c90cc-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="c90cc-128">Priser och rabatter för handelsavtal tillämpas inte på försäljnings- eller inköpsorderrader som importeras via datahantering.</span><span class="sxs-lookup"><span data-stu-id="c90cc-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c90cc-129">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c90cc-129">Issue description</span></span>

<span data-ttu-id="c90cc-130">Handelsavtal som tillämpas på försäljnings- eller inköpsorderrader tillämpas inte på rader som importeras via datahantering.</span><span class="sxs-lookup"><span data-stu-id="c90cc-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="c90cc-131">Samma handelsavtal tillämpas emellertid på försäljnings- eller inköpsorderrader som skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="c90cc-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="c90cc-132">Orsak till problemet</span><span class="sxs-lookup"><span data-stu-id="c90cc-132">Reason for the issue</span></span>

<span data-ttu-id="c90cc-133">Om inköpsorderrader som importeras via datahantering redan inkluderar prisinformation kommer handelsavtalet inte att utvärderas igen för dessa rader.</span><span class="sxs-lookup"><span data-stu-id="c90cc-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="c90cc-134">Om t.ex. **Radrabatt i procent** eller om något av pris- och rabattvärdena är inställda för en rad, kommer inte handelsavtalen att letas upp för den raden.</span><span class="sxs-lookup"><span data-stu-id="c90cc-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="c90cc-135">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-135">Issue workaround</span></span>

<span data-ttu-id="c90cc-136">Det här beteendet förväntas och används på liknande sätt för både försäljningsorder och inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c90cc-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="c90cc-137">Importera inköpsorderraderna utan att ange någon prisinformation.</span><span class="sxs-lookup"><span data-stu-id="c90cc-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="c90cc-138">Handelsavtalen kommer sedan att tillämpas och inköpsorderraderna uppdateras baserat på de definierade handelsavtalen.</span><span class="sxs-lookup"><span data-stu-id="c90cc-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="c90cc-139">En leverantörsrabatt ackumuleras inte utifrån fakturor.</span><span class="sxs-lookup"><span data-stu-id="c90cc-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c90cc-140">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c90cc-140">Issue description</span></span>

<span data-ttu-id="c90cc-141">Om fakturor som bokförs har olika förfallodatum, återspeglas dessa fakturor inte i leverantörsrabatter som genereras från dem.</span><span class="sxs-lookup"><span data-stu-id="c90cc-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c90cc-142">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-142">Issue resolution</span></span>

<span data-ttu-id="c90cc-143">Efter design beaktas inte förfallodatumet när leverantörsrabatten beräknas.</span><span class="sxs-lookup"><span data-stu-id="c90cc-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="c90cc-144">Överväg att anpassa systemet så att förfallodatumet och relationen till fakturan blir mer uppenbara när det gäller den faktiska leverantörsrabatten.</span><span class="sxs-lookup"><span data-stu-id="c90cc-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="c90cc-145">Enhetspris på inköpsorder beräknas inte utifrån enhetskonverteringen.</span><span class="sxs-lookup"><span data-stu-id="c90cc-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c90cc-146">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c90cc-146">Issue description</span></span>

<span data-ttu-id="c90cc-147">När en enhet ändras på en inköpsorder räknas inte handelsavtalets priser om enligt enhetskonverteringens definitioner.</span><span class="sxs-lookup"><span data-stu-id="c90cc-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c90cc-148">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-148">Issue resolution</span></span>

<span data-ttu-id="c90cc-149">Priser hämtas alltid från handelsavtal (eller andra prisinställningar i systemet, t.ex. försäljningsavtal eller artikelpriser) och ställs in för en enhet.</span><span class="sxs-lookup"><span data-stu-id="c90cc-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="c90cc-150">Om enheten ändras på en orderrad letar systemet efter ett pris för den nya enheten och tillämpar det priset.</span><span class="sxs-lookup"><span data-stu-id="c90cc-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="c90cc-151">Om det inte finns något pris för enheten tillämpar inte systemet priset.</span><span class="sxs-lookup"><span data-stu-id="c90cc-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="c90cc-152">Enhetskonverteringen kan inte användas för att räkna om priset till en annan enhet.</span><span class="sxs-lookup"><span data-stu-id="c90cc-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="c90cc-153">Teoretiskt sett får priset för en ruta på tio inte vara lika med tio gånger priset för en ruta.</span><span class="sxs-lookup"><span data-stu-id="c90cc-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="c90cc-154">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-154">Issue workaround</span></span>

<span data-ttu-id="c90cc-155">Ett sätt att undvika det här problemet är att se till att det finns handelsavtal för enheterna som du förväntar dig kommer att använda på orderrader för artikeln.</span><span class="sxs-lookup"><span data-stu-id="c90cc-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="c90cc-156">Valutakonverteringsproblem uppstår i handelsavtal.</span><span class="sxs-lookup"><span data-stu-id="c90cc-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="c90cc-157">Handelsavtalspriser räknas inte om enligt valutan när valutan skiljer sig åt på en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c90cc-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="c90cc-158">Med funktionen *allmän valuta* kan du definiera priser och rabatter i bara en valuta.</span><span class="sxs-lookup"><span data-stu-id="c90cc-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="c90cc-159">Du kan sedan konvertera till andra valutor efter behov.</span><span class="sxs-lookup"><span data-stu-id="c90cc-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="c90cc-160">När konverteringen är klar kan funktionen dessutom automatiskt tillämpa smart avrundning.</span><span class="sxs-lookup"><span data-stu-id="c90cc-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="c90cc-161">När jag öppnar sidan för inköpsavtal i ett radvisningsläge kan jag inte anpassa sidan genom att lägga till fältet prisenhet i översikten för raden.</span><span class="sxs-lookup"><span data-stu-id="c90cc-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="c90cc-162">Vissa delade fält i avtalsramverket kan inte inkluderas i anpassningar.</span><span class="sxs-lookup"><span data-stu-id="c90cc-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="c90cc-163">Den här begränsningen beror på den datamodell som implementeras.</span><span class="sxs-lookup"><span data-stu-id="c90cc-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="c90cc-164">Därför kan du inte personanpassa fältet **Prisenhet**.</span><span class="sxs-lookup"><span data-stu-id="c90cc-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="c90cc-165">Den maximala gränsen från ett inköpsavtal är inte effektiv på en inköpsrekvisition.</span><span class="sxs-lookup"><span data-stu-id="c90cc-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c90cc-166">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="c90cc-166">Issue description</span></span>

<span data-ttu-id="c90cc-167">När en inköpsrekvisition är kopplad till ett inköpsavtal gäller inte den maximala gränsen från inköpsavtalet på inköpsrekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="c90cc-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="c90cc-168">Standard prisinformationen anges korrekt, men mer än den högsta gränsen från inköpsavtalet kan beställas i inköpsrekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="c90cc-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c90cc-169">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="c90cc-169">Issue resolution</span></span>

<span data-ttu-id="c90cc-170">Detta är ett förväntat beteende.</span><span class="sxs-lookup"><span data-stu-id="c90cc-170">This behavior is expected.</span></span> <span data-ttu-id="c90cc-171">Eftersom rekvisitioner inte alltid godkänns ska en kvantitet eller ett belopp inte reserveras i inköpsavtalet.</span><span class="sxs-lookup"><span data-stu-id="c90cc-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="c90cc-172">Därför kommer du inte att uppfylla den högsta gränsen från inköpsavtalet.</span><span class="sxs-lookup"><span data-stu-id="c90cc-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="c90cc-173">Handelsavtal kan skapas från avvisade anbudsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="c90cc-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="c90cc-174">Därför hindrar systemet inte handelsavtalsjournaler från att skapas om raden i anbudsförfrågan inte har accepterats.</span><span class="sxs-lookup"><span data-stu-id="c90cc-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="c90cc-175">Du kan skapa handelsavtal för alla svar på en anbudsförfrågan, oavsett om de har accepterats eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="c90cc-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="c90cc-176">För mer information, se [översikt över begära offert (anbudsförfrågan)](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="c90cc-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>

