---
title: Felsök produktinleveranser och fakturering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinleveranser och fakturering.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3522a024261ff6dfffb53f2101139460be7669e4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832020"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="390d0-103">Felsök produktinleveranser och fakturering</span><span class="sxs-lookup"><span data-stu-id="390d0-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="390d0-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktinleveranser och fakturering.</span><span class="sxs-lookup"><span data-stu-id="390d0-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="390d0-105">Jag kan inte bokföra fler än en faktura för en inköpsorderrad som har kategoribaserade artiklar.</span><span class="sxs-lookup"><span data-stu-id="390d0-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="390d0-106">En kvantitet är obligatorisk om du vill bokföra fakturor.</span><span class="sxs-lookup"><span data-stu-id="390d0-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="390d0-107">Om hela kvantiteten av en rad endast har fakturerats för ett delbelopp, kan du alltså inte fakturera resten av beloppet på en annan faktura.</span><span class="sxs-lookup"><span data-stu-id="390d0-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="390d0-108">Jag får felmeddelandet "objektreferensen har inte angetts" vid en inköpsorderbekräftelse, eller ett undantag har utlösts av målet för ett anropsundantag uppstår under bokföringen av leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="390d0-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="390d0-109">Det här problemet kan uppstå på grund av inkonsekvenser i inköpsorderns fördelningar.</span><span class="sxs-lookup"><span data-stu-id="390d0-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="390d0-110">Om du vill häva blockeringen och återställa inköpsordern till tillstånd *utkast* går du till **Anskaffning och källa \> Periodiska uppgifter \> Rensa \> Återställningen av inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="390d0-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="390d0-111">Mer information finns i följande blogginlägg: [korrigera inköpsorder distributionsfel i Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="390d0-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="390d0-112">Jag kan inte konsolidera flera produktinleveranser till en enda inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="390d0-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="390d0-113">Du kan inte konsolidera flera produktinleveranser till en enda inköpsorder om de olika produktinleveranser raderna har olika redovisningsdatum.</span><span class="sxs-lookup"><span data-stu-id="390d0-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="390d0-114">I tidigare versioner av Microsoft Dynamics 365 Supply Chain Management var konsolideringen tillåten i den här situationen.</span><span class="sxs-lookup"><span data-stu-id="390d0-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="390d0-115">Men övningen är benägen för fel.</span><span class="sxs-lookup"><span data-stu-id="390d0-115">However, the practice is prone to error.</span></span> <span data-ttu-id="390d0-116">Redovisningsdatumet på inköpsorderraderna som skapas ska inte skilja sig från redovisningsdatumet på de produktinleveranser som dessa inköps orderrader skapades från.</span><span class="sxs-lookup"><span data-stu-id="390d0-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="390d0-117">(Redovisningsdatumet på inköpsorderraderna matchar redovisningsdatumet i inköpsorderrubriken.) Därför är konsolideringen av flera produktinleveranser i en enskild inköpsorder inte längre tillåten.</span><span class="sxs-lookup"><span data-stu-id="390d0-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="390d0-118">Redovisningsdatumet används till exempel för budgetreservationer och inteckning.</span><span class="sxs-lookup"><span data-stu-id="390d0-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="390d0-119">Därför bör den behållas under övergången från produktinleverans till inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="390d0-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="390d0-120">När produktinleveranser annulleras kan transaktioner bokföras till ett uppskjutet redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="390d0-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="390d0-121">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="390d0-121">Issue description</span></span>

<span data-ttu-id="390d0-122">Om en produktinleverans annulleras tillåter systemet att transaktionerna bokförs på avbrutna redovisningskonton även om huvudkontona är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="390d0-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="390d0-123">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="390d0-123">Reproduce the issue</span></span>

<span data-ttu-id="390d0-124">Följande procedur anger ett sätt att skapa reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="390d0-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="390d0-125">På sidan **Parametrar för leverantörsreskontra** på fliken **Allmänt** se till att alternativet **Bokför produktinleverans i redovisning** anges till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="390d0-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="390d0-126">Skapa en inköpsorder och lägg till en orderrad som har kvantiteten *1 000* för en produkt.</span><span class="sxs-lookup"><span data-stu-id="390d0-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="390d0-127">Bekräfta inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="390d0-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="390d0-128">Bokför produktinleveransen och kontrollera verifikationerna.</span><span class="sxs-lookup"><span data-stu-id="390d0-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="390d0-129">Gör uppehåll för de relevanta huvudkontona *200140* och *140200*.</span><span class="sxs-lookup"><span data-stu-id="390d0-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="390d0-130">Annullera den bokförda produktinleveransen.</span><span class="sxs-lookup"><span data-stu-id="390d0-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="390d0-131">Lägg märke till att transaktioner kan bokföras på uppskjutna redovisningskonton.</span><span class="sxs-lookup"><span data-stu-id="390d0-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="390d0-132">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="390d0-132">Issue resolution</span></span>

<span data-ttu-id="390d0-133">Transaktioner kan bokföras på uppskjutna redovisningskonton när produktinleveranser annulleras, eftersom detta möjliggör rätt bokföring.</span><span class="sxs-lookup"><span data-stu-id="390d0-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="390d0-134">Ett verifikationsnummer för produktinleverans förbrukas även om ingen ekonomisk verifikation genereras vid produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="390d0-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="390d0-135">Om alternativet **Periodisera skulder vid produktinleverans** anges till *Nej* för artikelmodellgruppen görs inga bokföringar i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="390d0-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="390d0-136">En fysisk händelse registreras emellertid i syfte att bokföras i redovisningen och den händelsen kräver ett verifikationsnummer.</span><span class="sxs-lookup"><span data-stu-id="390d0-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="390d0-137">Detta verifikationsnummer är det verifikationsnummer som refereras i lagertransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="390d0-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="390d0-138">Vi rekommenderar att du ställer in alternativet **Periodisera skulder vid produktinleverans** till *Ja*, vilket beskrivs i följande blogginlägg: [Bokför tillägg vid inleverans av produkten](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="390d0-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="390d0-139">Bokför till debiteringskonto i redovisningsinställningen är inte aktiverat.</span><span class="sxs-lookup"><span data-stu-id="390d0-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="390d0-140">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="390d0-140">Issue description</span></span>

<span data-ttu-id="390d0-141">Det här problemet uppstår när en inköpsorder faktureras, om alternativet **Bokför till debiteringskonto i redovisning** är inställt på *Ja* på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="390d0-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="390d0-142">Återskapa problemet</span><span class="sxs-lookup"><span data-stu-id="390d0-142">Reproduce the issue</span></span>

<span data-ttu-id="390d0-143">Följande procedur anger ett sätt att skapa reproducera problemet.</span><span class="sxs-lookup"><span data-stu-id="390d0-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="390d0-144">Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="390d0-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="390d0-145">På fliken **faktura** ange alternativet **Bokför till debiteringskonto i redovisning** till *Ja*.</span><span class="sxs-lookup"><span data-stu-id="390d0-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="390d0-146">Gå till **Lagerhantering \> Inställningar \> Bokföring \> Bokföring**.</span><span class="sxs-lookup"><span data-stu-id="390d0-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="390d0-147">På fliken **Inköpsorder** ser du till att du har tagit bort alla rader i inköpsutgifterna för produkten.</span><span class="sxs-lookup"><span data-stu-id="390d0-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="390d0-148">Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="390d0-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="390d0-149">Skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="390d0-149">Create a purchase order.</span></span> <span data-ttu-id="390d0-150">På fältet **leverantörskonto** välj *1001 Acme kontorsmaterial*.</span><span class="sxs-lookup"><span data-stu-id="390d0-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="390d0-151">Lägg till en inköpsorderrad med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="390d0-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="390d0-152">**Artikelnummer:** *D0011 laserprojektor*</span><span class="sxs-lookup"><span data-stu-id="390d0-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="390d0-153">**Plats:** *1*</span><span class="sxs-lookup"><span data-stu-id="390d0-153">**Site:** *1*</span></span>
    - <span data-ttu-id="390d0-154">**Lagerställe:** *11*</span><span class="sxs-lookup"><span data-stu-id="390d0-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="390d0-155">**Kvantitet:** *4*</span><span class="sxs-lookup"><span data-stu-id="390d0-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="390d0-156">I Åtgärdsfönstret, på fliken **inköp**, i gruppen **åtgärd**, markerar du **bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="390d0-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="390d0-157">I åtgärdsfönstret, på fliken **Inleverera** i gruppen **Generera**, markerar du **Produktinleverans**.</span><span class="sxs-lookup"><span data-stu-id="390d0-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="390d0-158">I dialogrutan **Bokför produktinleverans** i fältet **Produktinleverans** ange ett godtyckligt nummer och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="390d0-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="390d0-159">I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="390d0-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="390d0-160">I fältet **Nummer** ange ett godtyckligt nummer som fakturanummer.</span><span class="sxs-lookup"><span data-stu-id="390d0-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="390d0-161">Uppdatera matchningsstatus och bokför.</span><span class="sxs-lookup"><span data-stu-id="390d0-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="390d0-162">Observera att du nu får följande fel när du genererar en faktura från en inköpsorder: "Kontonummer för transaktionstyp Inköpsutgifter för produkten finns inte."</span><span class="sxs-lookup"><span data-stu-id="390d0-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="390d0-163">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="390d0-163">Issue resolution</span></span>

<span data-ttu-id="390d0-164">Detta beror på parameterinställningarna för fakturor och fakturagrupper.</span><span class="sxs-lookup"><span data-stu-id="390d0-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="390d0-165">Mer information finns i följande blogginlägg: [Redovisning av inköpsavgift och lagervariation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="390d0-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]