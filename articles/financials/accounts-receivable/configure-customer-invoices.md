---
title: Skapa en kundfaktura
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a668e390935e157d9fc7f0ef597f25c2a7b9950
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-customer-invoice"></a><span data-ttu-id="18e4b-102">Skapa en kundfaktura</span><span class="sxs-lookup"><span data-stu-id="18e4b-102">Create a customer invoice</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="18e4b-103">En **kundfaktura för en försäljningsorder** är en faktura som är relaterad till en försäljning och som en organisation skickar till en kund.</span><span class="sxs-lookup"><span data-stu-id="18e4b-103">A **customer invoice for a sales order** is a bill that is related to a sale, and that an organization gives to a customer.</span></span> <span data-ttu-id="18e4b-104">Den här typen av kundfaktura skapas baserad på en försäljningsorder, vilken inkluderar orderrader och artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="18e4b-104">This type of customer invoice is created based on a sales order, which includes order lines and item numbers.</span></span> <span data-ttu-id="18e4b-105">Artikelnummer specificeras och bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="18e4b-105">Item numbers are specified and posted in the ledger.</span></span> <span data-ttu-id="18e4b-106">Poster i redovisningsjournalen är inte tillgängliga för en kundfaktura för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-106">Subledger journal entries aren't available for a customer invoice for a sales order.</span></span> <span data-ttu-id="18e4b-107">Mer information finns i [Skapa försäljningsorderfakturor](tasks/create-sales-order-invoices.md).</span><span class="sxs-lookup"><span data-stu-id="18e4b-107">For more information, see [Create sales order invoices](tasks/create-sales-order-invoices.md).</span></span>

<span data-ttu-id="18e4b-108">En **fritextfaktura** har inget samband med en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-108">A **free text invoice** isn't related to a sales order.</span></span> <span data-ttu-id="18e4b-109">Den innehåller orderrader som inkluderar redovisningskonton, fritextbeskrivningar och en försäljningssumma som du anger.</span><span class="sxs-lookup"><span data-stu-id="18e4b-109">It contains order lines that include ledger accounts, free-text descriptions, and a sales amount that you enter.</span></span> <span data-ttu-id="18e4b-110">Du kan inte ange ett artikelnummer på den här sortens faktura.</span><span class="sxs-lookup"><span data-stu-id="18e4b-110">You can't enter an item number on this kind of invoice.</span></span> <span data-ttu-id="18e4b-111">Du måste ange korrekt momsinformation.</span><span class="sxs-lookup"><span data-stu-id="18e4b-111">You must enter the appropriate sales tax information.</span></span> <span data-ttu-id="18e4b-112">En huvudkonto för försäljningen anges på varje fakturarad, som du kan fördela till flera huvudbokskonton genom att klicka på **Fördela belopp** på sidan **Fritextfaktura** .</span><span class="sxs-lookup"><span data-stu-id="18e4b-112">A main account for the sale is indicated on each invoice line, which you can distribute to multiple ledger accounts by clicking **Distribute amounts** on the **Free text invoice** page.</span></span> <span data-ttu-id="18e4b-113">Dessutom bokförs kundsaldot till det samlingskonto från bokföringsprofilen som används för fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="18e4b-113">Additionally, the customer balance is posted to the summary account from the posting profile that is used for the free text invoice.</span></span>

<span data-ttu-id="18e4b-114">Mer information finns i </span><span class="sxs-lookup"><span data-stu-id="18e4b-114">For more information see:</span></span>

[<span data-ttu-id="18e4b-115">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="18e4b-115">Create a free text invoice</span></span>](tasks/create-free-text-invoice.md)

[<span data-ttu-id="18e4b-116">Skapa en mall för fritext</span><span class="sxs-lookup"><span data-stu-id="18e4b-116">Create a free text template</span></span>](tasks/create-free-text-invoice-template.md)

[<span data-ttu-id="18e4b-117">Tilldela en mall för fritextfaktura till en kund</span><span class="sxs-lookup"><span data-stu-id="18e4b-117">Assign a free text invoice tempate to a customer</span></span>](tasks/assign-free-text-invoice-template-customer.md)

[<span data-ttu-id="18e4b-118">Generera och bokför återkommande fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="18e4b-118">Generate and post recurring free text invoices</span></span>](tasks/post-recurring-free-text-invoices.md)


<span data-ttu-id="18e4b-119">En **proformafaktura** är en faktura som förbereds som en uppskattning av de faktiska fakturabeloppen innan fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="18e4b-119">A **pro forma invoice** is an invoice that is prepared as an estimate of the actual invoice amounts before the invoice is posted.</span></span> <span data-ttu-id="18e4b-120">Du kan skriva ut en proformafaktura för antingen en kundfaktura för en försäljningsfaktura eller för en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="18e4b-120">You can print a pro forma invoice either for a customer invoice for a sales order or for a free text invoice.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a><span data-ttu-id="18e4b-121">Bokför och skriv ut enskilda kundfakturor baserade på försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="18e4b-121">Post and print individual customer invoices that are based on sales orders</span></span>
<span data-ttu-id="18e4b-122">Använd den här processen för att skapa en faktura baserat på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-122">Use this process to create an invoice that is based on a sales order.</span></span> <span data-ttu-id="18e4b-123">Du kan göra detta om du väljer att fakturera kunden innan du levererar varor eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="18e4b-123">You might do this if you decide to invoice the customer before you deliver the goods or services.</span></span> 

<span data-ttu-id="18e4b-124">När du bokför en faktura uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de fakturerade kvantiteterna från vald försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-124">When you post an invoice, the **Invoice remainder** quantity for each item is updated with the total of the invoiced quantities from the selected sales order.</span></span> <span data-ttu-id="18e4b-125">Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-125">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="18e4b-126">Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den.</span><span class="sxs-lookup"><span data-stu-id="18e4b-126">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span>

<span data-ttu-id="18e4b-127">Du kan visa status för försäljningsorder på listsidan **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-127">You can view the status of the sales orders on the **All sales orders** list page.</span></span> <span data-ttu-id="18e4b-128">Använd listsidan **Öppna kundfakturor** om du vill visa fakturor som du har bokfört.</span><span class="sxs-lookup"><span data-stu-id="18e4b-128">Use the **Open customer invoices** list page to view the invoices that you posted.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a><span data-ttu-id="18e4b-129">Bokför och skriv ut individuella kundfakturor baserade på följesedlar och datumet</span><span class="sxs-lookup"><span data-stu-id="18e4b-129">Post and print individual customer invoices that are based on packing slips and the date</span></span>
<span data-ttu-id="18e4b-130">Använd den här processen när en eller flera följesedlar har bokförts för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="18e4b-130">Use this process when one or more packing slips have been posted for the sales order.</span></span> <span data-ttu-id="18e4b-131">Kundfakturan baseras på dessa följesedlar och återspeglar kvantiteterna från dem.</span><span class="sxs-lookup"><span data-stu-id="18e4b-131">The customer invoice is based on these packing slips and reflects the quantities from them.</span></span> <span data-ttu-id="18e4b-132">Den ekonomiska informationen för fakturan baseras på informationen som registreras när du bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="18e4b-132">The financial information for the invoice is based on the information that is entered when you post the invoice.</span></span> 

<span data-ttu-id="18e4b-133">Du kan skapa en kundfaktura som baseras på de artiklar på följesedeln som har levererats hittills, även om alla artiklar för en viss försäljningsorder ännu inte har levererats.</span><span class="sxs-lookup"><span data-stu-id="18e4b-133">You can create a customer invoice that is based on the packing slip line items that have been shipped to date, even if all the items for a particular sales order haven't yet been shipped.</span></span> <span data-ttu-id="18e4b-134">Det kanske du vill göra om den juridiska personen utfärdar en faktura per kund och månad som täcker alla leveranser som har gjorts den månaden.</span><span class="sxs-lookup"><span data-stu-id="18e4b-134">You might do this if, for example, your legal entity issues one invoice per customer per month that covers all the deliveries that you ship during that month.</span></span> <span data-ttu-id="18e4b-135">Varje följesedel representerar en del av eller hela leveransen av artiklarna på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="18e4b-135">Each packing slip represents a partial or complete delivery of the items on the sales order.</span></span> 

<span data-ttu-id="18e4b-136">När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de levererade kvantiteterna från de valda följesedlarna.</span><span class="sxs-lookup"><span data-stu-id="18e4b-136">When you post the invoice, the **Invoice remainder** quantity for each item is updated with the total of the delivered quantities from the selected packing slips.</span></span> <span data-ttu-id="18e4b-137">Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-137">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="18e4b-138">Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den.</span><span class="sxs-lookup"><span data-stu-id="18e4b-138">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span> 

<span data-ttu-id="18e4b-139">Lagertransaktioner uppdateras med fakturanumret och statusen i fältet **Radstatus** på försäljningsordern ändras till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-139">Inventory transactions are updated with the invoice number, and the status in the **Line status** field on the sales order is changed to **Invoiced**.</span></span> 

<span data-ttu-id="18e4b-140">Visa status för försäljningsorder på listsidan **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-140">View the status of the sales orders in the **All sales orders** list page.</span></span>

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a><span data-ttu-id="18e4b-141">Konsolidera försäljningsorder och följesedlar för bokföring</span><span class="sxs-lookup"><span data-stu-id="18e4b-141">Consolidate sales orders or packing slips for posting</span></span>
<span data-ttu-id="18e4b-142">Använd den här processen när en eller flera försäljningsorder är klara att fakturera och du vill konsolidera dem till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="18e4b-142">Use this process when one or more sales orders are ready to be invoiced, and you want to consolidate them into a single invoice.</span></span> 

<span data-ttu-id="18e4b-143">Du kan markera flera fakturor på listsidan **Försäljningsorder** och sedan använda **Skapa fakturor** för att konsolidera dem.</span><span class="sxs-lookup"><span data-stu-id="18e4b-143">You can select multiple invoices on the **Sales order** list page and then use **Generate invoices** to consolidate them.</span></span> <span data-ttu-id="18e4b-144">På sidan **Bokföring av faktura** kan du ändra inställningen **Samlingsorder** att sammanställa efter ordernummer (där flera olika följesedlar finns för en enda försäljningsorder) eller per fakturakonto (där det finns flera olika försäljningsorder för ett enda fakturakonto).</span><span class="sxs-lookup"><span data-stu-id="18e4b-144">On the **Posting invoice** page, you can change the **Summary order** setting to summarize by order number (where there are multiple packing slips for a single sales order) or by invoice account (where there are multiple sales orders for a single invoice account).</span></span> <span data-ttu-id="18e4b-145">Använd knappen **Ordna** för att konsolidera försäljningsorder till enskilda fakturor som baseras på inställningarna för **Samlingsorder**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-145">Use the **Arrange** button to consolidate sales orders into single invoices, based on the **Summary order** settings.</span></span>

## <a name="additional-settings-that-change-the-posting-behavior"></a><span data-ttu-id="18e4b-146">Ytterligare inställningar som ändrar bokföringsbeteendet</span><span class="sxs-lookup"><span data-stu-id="18e4b-146">Additional settings that change the posting behavior</span></span>
<span data-ttu-id="18e4b-147">Följande fält ändrar beteendet för bokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="18e4b-147">The following fields change the behavior of the posting process.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18e4b-148">Fält</span><span class="sxs-lookup"><span data-stu-id="18e4b-148">Field</span></span></th>
<th><span data-ttu-id="18e4b-149">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="18e4b-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="18e4b-150">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="18e4b-150">Quantity</span></span></td>
<td><span data-ttu-id="18e4b-151">Välj de kvantiteter som bokföringen av dokumentet baseras på.</span><span class="sxs-lookup"><span data-stu-id="18e4b-151">Select the quantities to base the posting of the document on.</span></span> <span data-ttu-id="18e4b-152">Vilka alternativ som finns tillgängliga beror på vilken typ av dokument du bokför, exempelvis följesedel eller faktura.</span><span class="sxs-lookup"><span data-stu-id="18e4b-152">The options that are available vary, depending on the type of document that you are posting, such as a packing slip or an invoice.</span></span>
<ul>
<li><span data-ttu-id="18e4b-153"><strong>Leverera nu</strong> – Välj alla kvantiteter som anges i fältet <strong>Leverera nu</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-153"><strong>Deliver now</strong> – Select all quantities that are entered in the <strong>Deliver now</strong> field.</span></span> <span data-ttu-id="18e4b-154">Används om du vill bekräfta eller leverera en delorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-154">Use this option to confirm or deliver a partial order.</span></span></li>
<li><span data-ttu-id="18e4b-155"><strong>Plockad</strong> – Välj alla kvantiteter som har plockats.</span><span class="sxs-lookup"><span data-stu-id="18e4b-155"><strong>Picked</strong> – Select all quantities that have been picked.</span></span></li>
<li><span data-ttu-id="18e4b-156"><strong>Alla</strong> – Välj alla försäljningsorderkvantiteter som ännu inte uppdaterats för den aktuella dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="18e4b-156"><strong>All</strong> – Select all quantities on the sales order that haven't yet been updated by the current document type.</span></span></li>
<li><span data-ttu-id="18e4b-157"><strong>Följesedel</strong> – Välj alla kvantiteter som har uppdaterats av en följesedel.</span><span class="sxs-lookup"><span data-stu-id="18e4b-157"><strong>Packing slip</strong> – Select all quantities that have been updated by a packing slip.</span></span></li>
<li><span data-ttu-id="18e4b-158"><strong>Plockad kvantitet och produkter som inte finns i lager</strong> – Välj alla kvantiteter som har plockats och alla produktkvantiteter som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="18e4b-158"><strong>Picked quantity and not stocked products</strong> – Select all quantities that have been picked and all product quantities that aren't stocked.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-159">Bokför</span><span class="sxs-lookup"><span data-stu-id="18e4b-159">Posting</span></span></td>
<td><ul>
<li><span data-ttu-id="18e4b-160">Välj det här alternativet för att journalföra försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="18e4b-160">Select this option to journalize the sales order.</span></span></li>
<li><span data-ttu-id="18e4b-161">Avmarkera det här alternativet om du vill skriva ut en proformasäljorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-161">Clear this option to print a pro forma sales order.</span></span> <span data-ttu-id="18e4b-162"><strong>Anm.:</strong> Om du har ingått ett avtal om en betalningsplan visas inte betalningsplanen på proformasäljordern.</span><span class="sxs-lookup"><span data-stu-id="18e4b-162"><strong>Note:</strong> If you made an agreement for a payment schedule, the payment schedule isn't shown on the pro forma sales order.</span></span> <span data-ttu-id="18e4b-163">Betalningsplanen visas bara på en faktisk försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-163">Payment schedules are shown only on actual sales orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18e4b-164">Sent urval</span><span class="sxs-lookup"><span data-stu-id="18e4b-164">Late selection</span></span></td>
<td><span data-ttu-id="18e4b-165">Välj det här alternativet om du vill köra den aktuella frågan senare.</span><span class="sxs-lookup"><span data-stu-id="18e4b-165">Select this option to apply the selected query later.</span></span> <span data-ttu-id="18e4b-166">Detta alternativ används för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="18e4b-166">This option is used for batch jobs.</span></span> <span data-ttu-id="18e4b-167">Frågan körs när batchjobbet körs.</span><span class="sxs-lookup"><span data-stu-id="18e4b-167">The query is run when the batch job is run.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-168">Minska kvantiteten</span><span class="sxs-lookup"><span data-stu-id="18e4b-168">Reduce quantity</span></span></td>
<td><span data-ttu-id="18e4b-169">Välj det här alternativet för att automatiskt reducera den levererade kvantiteten, när dokumentet bokförs, så att den levererade kvantiteten är lika med det tillgängliga lagret.</span><span class="sxs-lookup"><span data-stu-id="18e4b-169">Select this option to automatically reduce the delivered quantity when the document is posted, so that the delivered quantity equals the available inventory.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18e4b-170">Skriv ut</span><span class="sxs-lookup"><span data-stu-id="18e4b-170">Print</span></span></td>
<td><span data-ttu-id="18e4b-171">Välj när du vill skriva ut dokument:</span><span class="sxs-lookup"><span data-stu-id="18e4b-171">Select when to print documents:</span></span>
<ul>
<li><span data-ttu-id="18e4b-172"><strong>Aktuellt</strong> – Skriv ut dokument när varje faktura har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="18e4b-172"><strong>Current</strong> – Print documents after each invoice has been updated.</span></span></li>
<li><span data-ttu-id="18e4b-173"><strong>Efter</strong> – Skriv ut dokument när alla fakturor har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="18e4b-173"><strong>After</strong> – Print documents after all the invoices have been updated.</span></span></li>
</ul><span data-ttu-id="18e4b-174">
<strong>Anm.:</strong> Fältet <strong>Skriv ut</strong> är bara tillgängligt om du väljer alternativet <strong>Skriv ut faktura</strong>, <strong>Skriv ut bekräftelse</strong>, <strong>Skriv ut plocklista</strong> eller <strong>Skriv ut följesedel</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-174">
<strong>Note:</strong> The <strong>Print</strong> field is available only if you select the <strong>Print invoice</strong>, <strong>Print confirmation</strong>, <strong>Print picking list</strong>, or <strong>Print packing slip</strong> option.</span></span> <span data-ttu-id="18e4b-175">Anta att du har konfigurerat sidan <strong>Formulärsortering</strong> till att sortera informationen efter fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="18e4b-175">For example, on the <strong>Form sorting</strong> page, you have set up the system to sort the information by invoice account.</span></span> <span data-ttu-id="18e4b-176">Du kan sedan välja <strong>Efter</strong> för att skriva ut dokument i en bunt sorterad efter fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="18e4b-176">You can then select <strong>After</strong> to print the documents in a batch that is sorted by invoice account.</span></span> <span data-ttu-id="18e4b-177">Annars skrivas ut dokumenten ut innan du bearbetningen slutförs och dokumenten sorteras inte i den ordning som anges på sidan <strong>Formulärsortering</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-177">Otherwise, the documents are printed before processing is completed, and the documents aren't sorted in the order that is specified on the <strong>Form sorting</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-178">Skriv ut faktura</span><span class="sxs-lookup"><span data-stu-id="18e4b-178">Print invoice</span></span></td>
<td><span data-ttu-id="18e4b-179">Markera det här alternativet om du vill skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="18e4b-179">Select this option to print the invoice.</span></span> <span data-ttu-id="18e4b-180">Om det här alternativet är inaktiverat kan du bokföra en faktura utan att skriva ut den.</span><span class="sxs-lookup"><span data-stu-id="18e4b-180">If this option is turned off, you can post an invoice without printing it.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18e4b-181">Skicka e-post</span><span class="sxs-lookup"><span data-stu-id="18e4b-181">Send e-mail</span></span></td>
<td><span data-ttu-id="18e4b-182">Markera det här alternativet för att skicka fakturan för en försäljningsorder till kunden som en e-postbilaga efter att fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="18e4b-182">Select this option to send the invoice for a sales order to the customer as an email attachment after the invoice is posted.</span></span> <span data-ttu-id="18e4b-183">Bilagor skickas som PDF och XML-filer.</span><span class="sxs-lookup"><span data-stu-id="18e4b-183">Attachments are sent as PDF and XML files.</span></span> <span data-ttu-id="18e4b-184">Det här alternativet är tillgängligt om du väljer alternativet <strong>Aktivera CFD (elektroniska fakturor)</strong> på sidan <strong>Elektroniska fakturaparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-184">This option is available only if you select the <strong>Enable CFD (electronic invoices)</strong> option on the <strong>Electronic invoice parameters</strong> page.</span></span> <span data-ttu-id="18e4b-185"><strong>Anm.:</strong> (MEX) Den här kontrollen är bara tillgänglig för juridiska personer som har den primära adressen i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="18e4b-185"><strong>Note:</strong> (MEX) This control is available only to legal entities whose primary address is in Mexico.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-186">Använd destination för utskriftshantering</span><span class="sxs-lookup"><span data-stu-id="18e4b-186">Use print management destination</span></span></td>
<td><span data-ttu-id="18e4b-187">Markera det här alternativet för att använda utskriftsinställningarna som har angetts för transaktionen, dokumentet eller modulen på sidan <strong>Inställning för utskriftshantering</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-187">Select this option to use the print settings that are specified for the transaction, document, or module on the <strong>Print management setup</strong> page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18e4b-188">Kontrollera kreditgräns</span><span class="sxs-lookup"><span data-stu-id="18e4b-188">Check credit limit</span></span></td>
<td><span data-ttu-id="18e4b-189">Välj informationen som ska analyseras när en kreditgränskontroll utförs.</span><span class="sxs-lookup"><span data-stu-id="18e4b-189">Select the information that should be analyzed when a credit limit check is performed.</span></span>
<ul>
<li><span data-ttu-id="18e4b-190"><strong>Ingen</strong> – Det finns inga krav för kreditgränskontrollen.</span><span class="sxs-lookup"><span data-stu-id="18e4b-190"><strong>None</strong> – There is no requirement for the credit limit check.</span></span></li>
<li><span data-ttu-id="18e4b-191"><strong>Saldo</strong> – Kreditgränsen kontrolleras mot kundsaldot.</span><span class="sxs-lookup"><span data-stu-id="18e4b-191"><strong>Balance</strong> – The credit limit is checked against the customer balance.</span></span></li>
<li><span data-ttu-id="18e4b-192"><strong>Saldo+följesedel eller produktinleverans</strong> – Kreditgränsen kontrolleras mot kundsaldot och leveranserna.</span><span class="sxs-lookup"><span data-stu-id="18e4b-192"><strong>Balance + packing slip or product receipt</strong> – The credit limit is checked against the customer balance and deliveries.</span></span></li>
<li><span data-ttu-id="18e4b-193"><strong>Saldo+Alla</strong> – Kreditgränsen kontrolleras mot kundsaldot, leveranser och öppna order.</span><span class="sxs-lookup"><span data-stu-id="18e4b-193"><strong>Balance+All</strong> – The credit limit is checked against the customer balance, deliveries, and open orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-194">Kreditkorrigering</span><span class="sxs-lookup"><span data-stu-id="18e4b-194">Credit correction</span></span></td>
<td><span data-ttu-id="18e4b-195">Välj det här alternativet om du vill visa en kreditfaktura som debet i verifikationstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="18e4b-195">Select this option to display the credit note as a debit in the voucher transactions.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="18e4b-196">Kreditrestkvantitet</span><span class="sxs-lookup"><span data-stu-id="18e4b-196">Credit remaining quantity</span></span></td>
<td><span data-ttu-id="18e4b-197">Om du bokför en kreditfaktura väljer du det här alternativet för att behålla den resterande kvantiteten i ordern.</span><span class="sxs-lookup"><span data-stu-id="18e4b-197">If you're posting a credit note, select this option to keep the remaining quantity on order.</span></span> <span data-ttu-id="18e4b-198">Om alternativet avmarkeras anges resterande kvantitet till 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="18e4b-198">If this option is cleared, the remaining quantity is set to 0 (zero).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="18e4b-199">Samlingsuppdatering för</span><span class="sxs-lookup"><span data-stu-id="18e4b-199">Summary update for</span></span></td>
<td><span data-ttu-id="18e4b-200">Välj hur flera olika försäljningsorder ska summeras:</span><span class="sxs-lookup"><span data-stu-id="18e4b-200">Select how multiple sales orders should be summarized:</span></span>
<ul>
<li><span data-ttu-id="18e4b-201"><strong>Ingen</strong> – Summera inte försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-201"><strong>None</strong> – Don't summarize sales orders.</span></span> <span data-ttu-id="18e4b-202">Skapa till exempel en separat faktura för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="18e4b-202">For example, a separate invoice will be created for each sales order.</span></span></li>
<li><span data-ttu-id="18e4b-203"><strong>Fakturakonto</strong> – Alla valda order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-203"><strong>Invoice account</strong> – Summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span></li>
<li><span data-ttu-id="18e4b-204"><strong>Order</strong> – Summera ett angett intervall av order till en order som du anger.</span><span class="sxs-lookup"><span data-stu-id="18e4b-204"><strong>Order</strong> – Summarize a selected range of orders into one order that you specify.</span></span> <span data-ttu-id="18e4b-205">Dessa order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-205">The orders are summarized based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="18e4b-206">Om detta alternativ är valt måste du välja ett värde i fältet <strong>Försäljningsorder</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-206">If you select this option, you must select a value in the <strong>Sales order</strong> field.</span></span></li>
<li><span data-ttu-id="18e4b-207"><strong>Automatisk sammanfattning</strong> – Om samlingsuppdateringar har angetts på sidan <strong>Samlingsuppdatera</strong>, sammanfatta alla valda order, baserat på villkoren som har ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-207"><strong>Automatic summary</strong> – If summary updates have been specified on the <strong>Summary update</strong> page, summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="18e4b-208">Om samlingsuppdateringar inte anges, bokförs ordern separat.</span><span class="sxs-lookup"><span data-stu-id="18e4b-208">If summary updates haven't been specified, the order is posted separately.</span></span></li>
<li><span data-ttu-id="18e4b-209"><strong>Följesedel</strong> – Summera ett valt intervall av order till en faktura per följesedel.</span><span class="sxs-lookup"><span data-stu-id="18e4b-209"><strong>Packing slip</strong> – Summarize a selected range of orders into one invoice for each packing slip.</span></span> <span data-ttu-id="18e4b-210">Det här alternativet är endast tillgängligt om <strong>Följesedel</strong> har valts i fältet <strong>Kvantitet</strong>.</span><span class="sxs-lookup"><span data-stu-id="18e4b-210">This option is available only if <strong>Packing slip</strong> is selected in the <strong>Quantity</strong> field.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






