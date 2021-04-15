---
title: Stäm av frakt i transporthantering
description: Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d523af235d645bd282af07d6a1f617bca5fba2dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809096"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="bdcac-103">Stäm av frakt i transporthantering</span><span class="sxs-lookup"><span data-stu-id="bdcac-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdcac-104">Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="bdcac-105">Fraktavstämning kan utföras manuellt eller ställas in för att utföras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bdcac-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="bdcac-106">Om du vill använda automatisk fraktavstämning måste du ställa in en granskningsmall där du kan definiera kriterierna som avgör vilka fraktväxlar som matchas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bdcac-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="bdcac-107">Fraktavstämningsprocessen</span><span class="sxs-lookup"><span data-stu-id="bdcac-107">The freight reconciliation process</span></span>

<span data-ttu-id="bdcac-108">Fraktsatser beräknas med hjälp av tariffmotorer som kopplas till relevanta transportföretag.</span><span class="sxs-lookup"><span data-stu-id="bdcac-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="bdcac-109">När en last bekräftas genereras en fraktsedel och fraktsatser överförs till den.</span><span class="sxs-lookup"><span data-stu-id="bdcac-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="bdcac-110">Fraktsatser fördelas som tilläggsavgifter till det aktuella källdokumentet (inköpsorder, försäljningsorder och/eller överföringsorder) beroende på inställningarna som används för den vanliga faktureringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="bdcac-111">Fraktavstämningsprocessen (som också kallas matchande processen) kan starta så snart fraktfakturan inkommer från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="bdcac-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="bdcac-112">Fakturan kan tas emot elektroniskt eller som pappersfaktura.</span><span class="sxs-lookup"><span data-stu-id="bdcac-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="bdcac-113">Om det är en pappersfaktura kan du generera en elektronisk faktura med hjälp av fraktsedeln som mall.</span><span class="sxs-lookup"><span data-stu-id="bdcac-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span>

<span data-ttu-id="bdcac-114">[![Fraktavstämningsprocess](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="bdcac-114">[![Freight reconciliation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="bdcac-115">Manuell avstämning</span><span class="sxs-lookup"><span data-stu-id="bdcac-115">Manual reconciliation</span></span>

<span data-ttu-id="bdcac-116">Om du stämmer av frakten manuellt måste du matcha varje fakturarad med fraktsedelns rad eller rader för lasten som faktureras.</span><span class="sxs-lookup"><span data-stu-id="bdcac-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="bdcac-117">Du utför den här matchningen på sidan **Fraktsedel och fakturamatchning**.</span><span class="sxs-lookup"><span data-stu-id="bdcac-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="bdcac-118">Om beloppet på fakturaraden inte överensstämmer med beloppet på fraktsedeln måste du välja en orsak till avstämningsavvikelsen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="bdcac-119">Om det finns flera skäl för avstämning kan du dela upp omatchade belopp över dem.</span><span class="sxs-lookup"><span data-stu-id="bdcac-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="bdcac-120">Avstämningsorsaken avgör hur de avvikande beloppen bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="bdcac-121">När avstämningen av hela fakturabeloppet redovisas skickas den för godkännande och sedan bokförs.journalen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="bdcac-122">I bilden nedan visas hur du skapar en fraktfaktura och utför fraktavstämning.</span><span class="sxs-lookup"><span data-stu-id="bdcac-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span>

<span data-ttu-id="bdcac-123">[![Fraktavstämningsuppgifter](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="bdcac-123">[![Freight reconciliation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>

## <a name="automatic-reconciliation"></a><span data-ttu-id="bdcac-124">Automatisk avstämning</span><span class="sxs-lookup"><span data-stu-id="bdcac-124">Automatic reconciliation</span></span>

<span data-ttu-id="bdcac-125">Du måste ange tidsplanen för avstämning, fakturorna och vilket transportföretag som ska användas om du vill använda automatisk avstämning.</span><span class="sxs-lookup"><span data-stu-id="bdcac-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="bdcac-126">Matchningen av fakturarader och fraktsedlarna utförs enligt inställningarna för granskningsmallen och fraktsedelstypen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="bdcac-127">När du har kört automatisk avstämning måste du hantera alla fakturor som systemet inte kan matcha.</span><span class="sxs-lookup"><span data-stu-id="bdcac-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="bdcac-128">Du måste sedan behandla dessa fakturor manuellt innan du kan bokföra alla fakturor för betalning.</span><span class="sxs-lookup"><span data-stu-id="bdcac-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a><span data-ttu-id="bdcac-129">Matcha fraktfakturor med fraktfakturor med automatisk eller manuell avstämning</span><span class="sxs-lookup"><span data-stu-id="bdcac-129">Match freight bills with freight invoices using automatic or manual reconciliation</span></span>

<span data-ttu-id="bdcac-130">*Matchning* är processen att hitta de fraktsedlar som motsvarar respektive fraktfaktura.</span><span class="sxs-lookup"><span data-stu-id="bdcac-130">*Matching* is the process of finding the freight bills that correspond to each freight invoice.</span></span> <span data-ttu-id="bdcac-131">Detta kan göras genom att fakturaraderna matchas en efter en (manuell matchning) eller genom att alla tillgängliga fakturor matchas samtidigt (automatchning).</span><span class="sxs-lookup"><span data-stu-id="bdcac-131">This can be done by matching the invoice lines one-by-one (manual matching), or by matching all available invoices at once (auto matching).</span></span>

### <a name="auto-matching"></a><span data-ttu-id="bdcac-132">Automatchning</span><span class="sxs-lookup"><span data-stu-id="bdcac-132">Auto matching</span></span>

<span data-ttu-id="bdcac-133">När du matchar flera fraktfakturor på samma fraktsedel fungerar processen för automatchning på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="bdcac-133">When matching multiple freight invoices to the same freight bill, the process for auto matching works as follows:</span></span>

1. <span data-ttu-id="bdcac-134">Alla fraktfakturor som inte matchas sorteras efter belopp, med det största beloppet först.</span><span class="sxs-lookup"><span data-stu-id="bdcac-134">All freight invoices not matched are sorted by amount, with largest amount first.</span></span>
1. <span data-ttu-id="bdcac-135">Fraktfakturor matchas en efter en tills fraktsedeln inte har något positivt belopp kvar.</span><span class="sxs-lookup"><span data-stu-id="bdcac-135">The freight invoices are matched one-by-one, until the freight bill has no positive amount remaining.</span></span>
1. <span data-ttu-id="bdcac-136">Beroende på inställningarna för revisionsmallen och resten av beloppet på fraktfakturor, anges resten av beloppet.</span><span class="sxs-lookup"><span data-stu-id="bdcac-136">Depending on the setup of the audit master and the remaining amount on the freight invoices, the remaining amount is set.</span></span>

### <a name="manual-matching"></a><span data-ttu-id="bdcac-137">Manuell matchning</span><span class="sxs-lookup"><span data-stu-id="bdcac-137">Manual matching</span></span>

<span data-ttu-id="bdcac-138">Alla fraktsedlar med positiva belopp går att matcha.</span><span class="sxs-lookup"><span data-stu-id="bdcac-138">All freight bills with positive amounts will be available for matching.</span></span> <span data-ttu-id="bdcac-139">Liknande automatchning kommer att användaren bara kunna matcha fraktfakturor med negativa belopp mot fraktsedlar som inte är helt matchade.</span><span class="sxs-lookup"><span data-stu-id="bdcac-139">Similar to auto matching, the user will only be able to match freight invoices with negative amounts to freight bills not fully matched.</span></span>

### <a name="example"></a><span data-ttu-id="bdcac-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="bdcac-140">Example</span></span>

<span data-ttu-id="bdcac-141">Anta att du har en fraktsedel (FB) i beloppet 1 500 och att du har skapat tre fraktfakturor för fraktsedeln med en fakturarad för varje faktura med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="bdcac-141">Suppose that you have a freight bill (FB) for an amount of 1500 and you have created three freight invoices for the freight bill with one invoice line for each invoice with following settings:</span></span>

- <span data-ttu-id="bdcac-142">Ursprunglig fraktsedel (FB): Belopp 1 500</span><span class="sxs-lookup"><span data-stu-id="bdcac-142">Original freight bill (FB): Amount 1500</span></span>
- <span data-ttu-id="bdcac-143">Faktura 1 (Inv1): Belopp 1 000</span><span class="sxs-lookup"><span data-stu-id="bdcac-143">Invoice 1 (Inv1): Amount 1000</span></span>
- <span data-ttu-id="bdcac-144">Faktura 2 (Inv2): Belopp 600</span><span class="sxs-lookup"><span data-stu-id="bdcac-144">Invoice 2 (Inv2): Amount 600</span></span>
- <span data-ttu-id="bdcac-145">Faktura 3 (Inv3): Belopp -100</span><span class="sxs-lookup"><span data-stu-id="bdcac-145">Invoice 3 (Inv3): Amount -100</span></span>

#### <a name="automatic-matching-result"></a><span data-ttu-id="bdcac-146">Automatiskt matchningsresultat</span><span class="sxs-lookup"><span data-stu-id="bdcac-146">Automatic matching result</span></span>

<span data-ttu-id="bdcac-147">Automatchning utförs i följande ordning:</span><span class="sxs-lookup"><span data-stu-id="bdcac-147">Auto matching will execute in following order:</span></span>

1. <span data-ttu-id="bdcac-148">Sortera alla fraktfakturor fallande efter belopp: Inv1 -> Inv2 -> Inv3.</span><span class="sxs-lookup"><span data-stu-id="bdcac-148">Sort all freight invoices descending by amount: Inv1 -> Inv2 -> Inv3.</span></span>
1. <span data-ttu-id="bdcac-149">Matcha Inv1 med FB.</span><span class="sxs-lookup"><span data-stu-id="bdcac-149">Match Inv1 with FB.</span></span> <span data-ttu-id="bdcac-150">Inv1 har 1 000 matchade och FB har 500 belopp kvar, så statusen anges till *Delvis matchad*.</span><span class="sxs-lookup"><span data-stu-id="bdcac-150">Inv1 has 1000 matched and FB has 500 amount remaining, so the status is set to *Partially matched*.</span></span>
1. <span data-ttu-id="bdcac-151">Matcha Inv2 med FB.</span><span class="sxs-lookup"><span data-stu-id="bdcac-151">Match Inv2 with FB.</span></span> <span data-ttu-id="bdcac-152">Inv2 har 500 matchade och FB har 0 kvar, så statusen anges till *Helt matchad*.</span><span class="sxs-lookup"><span data-stu-id="bdcac-152">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="bdcac-153">Eftersom FB nu är helt matchad kommer Inv3 inte att bearbetas.</span><span class="sxs-lookup"><span data-stu-id="bdcac-153">Because FB is now fully matched, Inv3 won't be processed.</span></span>

#### <a name="manual-matching-result"></a><span data-ttu-id="bdcac-154">Manuellt matchningsresultat</span><span class="sxs-lookup"><span data-stu-id="bdcac-154">Manual matching result</span></span>

<span data-ttu-id="bdcac-155">För manuell matchning varierar resultaten beroende på matchningens ordning, vilket visas i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="bdcac-155">For manual matching, the results vary depending on the order of the matching, as illustrated in the following example cases.</span></span>

##### <a name="manual-matching-case-1"></a><span data-ttu-id="bdcac-156">Manuell matchning ärende 1</span><span class="sxs-lookup"><span data-stu-id="bdcac-156">Manual matching case 1</span></span>

<span data-ttu-id="bdcac-157">Ett sätt att skapa manuell matchning för det här exemplet är att fortsätta enligt följande:</span><span class="sxs-lookup"><span data-stu-id="bdcac-157">One way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="bdcac-158">Matcha FB med Inv1.</span><span class="sxs-lookup"><span data-stu-id="bdcac-158">Match FB with Inv1.</span></span> <span data-ttu-id="bdcac-159">FB har 500 matchade kvar, så statusen anges till *Delvis matchad*.</span><span class="sxs-lookup"><span data-stu-id="bdcac-159">FB has 500 amount remaining, so the status set to *Partially matched*.</span></span>
1. <span data-ttu-id="bdcac-160">Matcha Inv2 med FB.</span><span class="sxs-lookup"><span data-stu-id="bdcac-160">Match Inv2 with FB.</span></span> <span data-ttu-id="bdcac-161">Inv2 har 500 matchade och FB har 0 kvar, så statusen anges till *Helt matchad*.</span><span class="sxs-lookup"><span data-stu-id="bdcac-161">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="bdcac-162">När du matchar Inv3 manuellt hittar du inga omatchade fraktsedlar.</span><span class="sxs-lookup"><span data-stu-id="bdcac-162">When manually matching Inv3, you won't find any unmatched freight bills.</span></span>

<span data-ttu-id="bdcac-163">I det här fallet är det i grund och botten samma som automatchning</span><span class="sxs-lookup"><span data-stu-id="bdcac-163">This case is essentially the same as auto matching</span></span>

##### <a name="manual-matching-case-2"></a><span data-ttu-id="bdcac-164">Manuell matchning ärende 2</span><span class="sxs-lookup"><span data-stu-id="bdcac-164">Manual matching case 2</span></span>

<span data-ttu-id="bdcac-165">Ett sätt att skapa manuell matchning för det här exemplet är att fortsätta enligt följande:</span><span class="sxs-lookup"><span data-stu-id="bdcac-165">Another way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="bdcac-166">Matcha Inv3 med FB.</span><span class="sxs-lookup"><span data-stu-id="bdcac-166">Match Inv3 with FB.</span></span> <span data-ttu-id="bdcac-167">Nu har FB resterande 1 600 belopp, vilket är samma som att subtrahera negativa 100 ovanpå 1 500.</span><span class="sxs-lookup"><span data-stu-id="bdcac-167">Now FB has amount remaining 1600, which is the same as subtracting negative 100 on top of 1500.</span></span> <span data-ttu-id="bdcac-168">Både FB och Inv3 har en matchad kvantitet på -100.</span><span class="sxs-lookup"><span data-stu-id="bdcac-168">Both FB and Inv3 have a matched quantity of -100.</span></span>
1. <span data-ttu-id="bdcac-169">Matcha Inv1 och Inv 2 med FB en efter en.</span><span class="sxs-lookup"><span data-stu-id="bdcac-169">Match Inv1 and Inv 2 with FB one after another.</span></span> <span data-ttu-id="bdcac-170">FB matchas fullständigt.</span><span class="sxs-lookup"><span data-stu-id="bdcac-170">FB is fully matched.</span></span>

<span data-ttu-id="bdcac-171">Som det här exemplet visar bör matchande fraktfakturor med negativa belopp endast göras manuellt.</span><span class="sxs-lookup"><span data-stu-id="bdcac-171">As this example shows, matching freight invoices with negative amounts should only be done manually.</span></span> <span data-ttu-id="bdcac-172">Då går det alltid att matcha fraktfakturor med negativa belopp mot en fraktsedel helt och hållet matchad eftersom du då kan styra matchningssekvensen.</span><span class="sxs-lookup"><span data-stu-id="bdcac-172">This will ensure that it is always possible to match the freight invoices with negative amounts to a freight bill not fully matched because that enables you to control the matching sequence.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]