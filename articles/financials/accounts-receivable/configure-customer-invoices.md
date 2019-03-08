---
title: Skapa en kundfaktura
description: En **kundfaktura för en försäljningsorder** är en faktura som är relaterad till en försäljning och som en organisation skickar till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d7c9a61f935503b74ac27b354c875df095d84b4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "365280"
---
# <a name="create-a-customer-invoice"></a><span data-ttu-id="a498e-103">Skapa en kundfaktura</span><span class="sxs-lookup"><span data-stu-id="a498e-103">Create a customer invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a498e-104">En **kundfaktura för en försäljningsorder** är en faktura som är relaterad till en försäljning och som en organisation skickar till en kund.</span><span class="sxs-lookup"><span data-stu-id="a498e-104">A **customer invoice for a sales order** is a bill that is related to a sale, and that an organization gives to a customer.</span></span> <span data-ttu-id="a498e-105">Den här typen av kundfaktura skapas baserad på en försäljningsorder, vilken inkluderar orderrader och artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="a498e-105">This type of customer invoice is created based on a sales order, which includes order lines and item numbers.</span></span> <span data-ttu-id="a498e-106">Artikelnummer specificeras och bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="a498e-106">Item numbers are specified and posted in the ledger.</span></span> <span data-ttu-id="a498e-107">Poster i redovisningsjournalen är inte tillgängliga för en kundfaktura för en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-107">Subledger journal entries aren't available for a customer invoice for a sales order.</span></span> <span data-ttu-id="a498e-108">Mer information finns i [Skapa försäljningsorderfakturor](tasks/create-sales-order-invoices.md).</span><span class="sxs-lookup"><span data-stu-id="a498e-108">For more information, see [Create sales order invoices](tasks/create-sales-order-invoices.md).</span></span>

<span data-ttu-id="a498e-109">En **fritextfaktura** har inget samband med en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-109">A **free text invoice** isn't related to a sales order.</span></span> <span data-ttu-id="a498e-110">Den innehåller orderrader som inkluderar redovisningskonton, fritextbeskrivningar och en försäljningssumma som du anger.</span><span class="sxs-lookup"><span data-stu-id="a498e-110">It contains order lines that include ledger accounts, free-text descriptions, and a sales amount that you enter.</span></span> <span data-ttu-id="a498e-111">Du kan inte ange ett artikelnummer på den här sortens faktura.</span><span class="sxs-lookup"><span data-stu-id="a498e-111">You can't enter an item number on this kind of invoice.</span></span> <span data-ttu-id="a498e-112">Du måste ange korrekt momsinformation.</span><span class="sxs-lookup"><span data-stu-id="a498e-112">You must enter the appropriate sales tax information.</span></span> <span data-ttu-id="a498e-113">En huvudkonto för försäljningen anges på varje fakturarad, som du kan fördela till flera huvudbokskonton genom att klicka på **Fördela belopp** på sidan **Fritextfaktura** .</span><span class="sxs-lookup"><span data-stu-id="a498e-113">A main account for the sale is indicated on each invoice line, which you can distribute to multiple ledger accounts by clicking **Distribute amounts** on the **Free text invoice** page.</span></span> <span data-ttu-id="a498e-114">Dessutom bokförs kundsaldot till det samlingskonto från bokföringsprofilen som används för fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="a498e-114">Additionally, the customer balance is posted to the summary account from the posting profile that is used for the free text invoice.</span></span>

<span data-ttu-id="a498e-115">Mer information finns i </span><span class="sxs-lookup"><span data-stu-id="a498e-115">For more information see:</span></span>

[<span data-ttu-id="a498e-116">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="a498e-116">Create a free text invoice</span></span>](../accounts-receivable/create-free-text-invoice-new.md)

[<span data-ttu-id="a498e-117">Skapa en mall för fritext</span><span class="sxs-lookup"><span data-stu-id="a498e-117">Create a free text template</span></span>](../accounts-receivable/create-free-text-invoice-template-new.md)

[<span data-ttu-id="a498e-118">Tilldela en mall för fritextfaktura till en kund</span><span class="sxs-lookup"><span data-stu-id="a498e-118">Assign a free text invoice template to a customer</span></span>](tasks/assign-free-text-invoice-template-customer.md)

[<span data-ttu-id="a498e-119">Generera och bokför återkommande fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="a498e-119">Generate and post recurring free text invoices</span></span>](tasks/post-recurring-free-text-invoices.md)


<span data-ttu-id="a498e-120">En **proformafaktura** är en faktura som förbereds som en uppskattning av de faktiska fakturabeloppen innan fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="a498e-120">A **pro forma invoice** is an invoice that is prepared as an estimate of the actual invoice amounts before the invoice is posted.</span></span> <span data-ttu-id="a498e-121">Du kan skriva ut en proformafaktura för antingen en kundfaktura för en försäljningsfaktura eller för en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="a498e-121">You can print a pro forma invoice either for a customer invoice for a sales order or for a free text invoice.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a><span data-ttu-id="a498e-122">Bokför och skriv ut enskilda kundfakturor baserade på försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="a498e-122">Post and print individual customer invoices that are based on sales orders</span></span>
<span data-ttu-id="a498e-123">Använd den här processen för att skapa en faktura baserat på en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-123">Use this process to create an invoice that is based on a sales order.</span></span> <span data-ttu-id="a498e-124">Du kan göra detta om du väljer att fakturera kunden innan du levererar varor eller tjänster.</span><span class="sxs-lookup"><span data-stu-id="a498e-124">You might do this if you decide to invoice the customer before you deliver the goods or services.</span></span> 

<span data-ttu-id="a498e-125">När du bokför en faktura uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de fakturerade kvantiteterna från vald försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-125">When you post an invoice, the **Invoice remainder** quantity for each item is updated with the total of the invoiced quantities from the selected sales order.</span></span> <span data-ttu-id="a498e-126">Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="a498e-126">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="a498e-127">Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den.</span><span class="sxs-lookup"><span data-stu-id="a498e-127">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span>

<span data-ttu-id="a498e-128">Du kan visa status för försäljningsorder på listsidan **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a498e-128">You can view the status of the sales orders on the **All sales orders** list page.</span></span> <span data-ttu-id="a498e-129">Använd listsidan **Öppna kundfakturor** om du vill visa fakturor som du har bokfört.</span><span class="sxs-lookup"><span data-stu-id="a498e-129">Use the **Open customer invoices** list page to view the invoices that you posted.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a><span data-ttu-id="a498e-130">Bokför och skriv ut individuella kundfakturor baserade på följesedlar och datumet</span><span class="sxs-lookup"><span data-stu-id="a498e-130">Post and print individual customer invoices that are based on packing slips and the date</span></span>
<span data-ttu-id="a498e-131">Använd den här processen när en eller flera följesedlar har bokförts för försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="a498e-131">Use this process when one or more packing slips have been posted for the sales order.</span></span> <span data-ttu-id="a498e-132">Kundfakturan baseras på dessa följesedlar och återspeglar kvantiteterna från dem.</span><span class="sxs-lookup"><span data-stu-id="a498e-132">The customer invoice is based on these packing slips and reflects the quantities from them.</span></span> <span data-ttu-id="a498e-133">Den ekonomiska informationen för fakturan baseras på informationen som registreras när du bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="a498e-133">The financial information for the invoice is based on the information that is entered when you post the invoice.</span></span> 

<span data-ttu-id="a498e-134">Du kan skapa en kundfaktura som baseras på de artiklar på följesedeln som har levererats hittills, även om alla artiklar för en viss försäljningsorder ännu inte har levererats.</span><span class="sxs-lookup"><span data-stu-id="a498e-134">You can create a customer invoice that is based on the packing slip line items that have been shipped to date, even if all the items for a particular sales order haven't yet been shipped.</span></span> <span data-ttu-id="a498e-135">Det kanske du vill göra om den juridiska personen utfärdar en faktura per kund och månad som täcker alla leveranser som har gjorts den månaden.</span><span class="sxs-lookup"><span data-stu-id="a498e-135">You might do this if, for example, your legal entity issues one invoice per customer per month that covers all the deliveries that you ship during that month.</span></span> <span data-ttu-id="a498e-136">Varje följesedel representerar en del av eller hela leveransen av artiklarna på försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="a498e-136">Each packing slip represents a partial or complete delivery of the items on the sales order.</span></span> 

<span data-ttu-id="a498e-137">När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de levererade kvantiteterna från de valda följesedlarna.</span><span class="sxs-lookup"><span data-stu-id="a498e-137">When you post the invoice, the **Invoice remainder** quantity for each item is updated with the total of the delivered quantities from the selected packing slips.</span></span> <span data-ttu-id="a498e-138">Om både kvantiteten **Fakturarest** och kvantiteten **Leveransrest** för alla artiklar på försäljningsordern är noll, ändras statusen för försäljningsordern till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="a498e-138">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="a498e-139">Om kvantiteten **Fakturarest** inte är noll, ändras inte försäljningsorderns status och ytterligare fakturor kan registreras för den.</span><span class="sxs-lookup"><span data-stu-id="a498e-139">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span> 

<span data-ttu-id="a498e-140">Lagertransaktioner uppdateras med fakturanumret och statusen i fältet **Radstatus** på försäljningsordern ändras till **Fakturerad**.</span><span class="sxs-lookup"><span data-stu-id="a498e-140">Inventory transactions are updated with the invoice number, and the status in the **Line status** field on the sales order is changed to **Invoiced**.</span></span> 

<span data-ttu-id="a498e-141">Visa status för försäljningsorder på listsidan **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="a498e-141">View the status of the sales orders in the **All sales orders** list page.</span></span>

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a><span data-ttu-id="a498e-142">Konsolidera försäljningsorder och följesedlar för bokföring</span><span class="sxs-lookup"><span data-stu-id="a498e-142">Consolidate sales orders or packing slips for posting</span></span>
<span data-ttu-id="a498e-143">Använd den här processen när en eller flera försäljningsorder är klara att fakturera och du vill konsolidera dem till en enda faktura.</span><span class="sxs-lookup"><span data-stu-id="a498e-143">Use this process when one or more sales orders are ready to be invoiced, and you want to consolidate them into a single invoice.</span></span> 

<span data-ttu-id="a498e-144">Du kan markera flera fakturor på listsidan **Försäljningsorder** och sedan använda **Skapa fakturor** för att konsolidera dem.</span><span class="sxs-lookup"><span data-stu-id="a498e-144">You can select multiple invoices on the **Sales order** list page and then use **Generate invoices** to consolidate them.</span></span> <span data-ttu-id="a498e-145">På sidan **Bokföring av faktura** kan du ändra inställningen **Samlingsorder** att sammanställa efter ordernummer (där flera olika följesedlar finns för en enda försäljningsorder) eller per fakturakonto (där det finns flera olika försäljningsorder för ett enda fakturakonto).</span><span class="sxs-lookup"><span data-stu-id="a498e-145">On the **Posting invoice** page, you can change the **Summary order** setting to summarize by order number (where there are multiple packing slips for a single sales order) or by invoice account (where there are multiple sales orders for a single invoice account).</span></span> <span data-ttu-id="a498e-146">Använd knappen **Ordna** för att konsolidera försäljningsorder till enskilda fakturor som baseras på inställningarna för **Samlingsorder**.</span><span class="sxs-lookup"><span data-stu-id="a498e-146">Use the **Arrange** button to consolidate sales orders into single invoices, based on the **Summary order** settings.</span></span>

## <a name="additional-settings-that-change-the-posting-behavior"></a><span data-ttu-id="a498e-147">Ytterligare inställningar som ändrar bokföringsbeteendet</span><span class="sxs-lookup"><span data-stu-id="a498e-147">Additional settings that change the posting behavior</span></span>
<span data-ttu-id="a498e-148">Följande fält ändrar beteendet för bokföringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a498e-148">The following fields change the behavior of the posting process.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a498e-149">Fält</span><span class="sxs-lookup"><span data-stu-id="a498e-149">Field</span></span></th>
<th><span data-ttu-id="a498e-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a498e-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a498e-151">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="a498e-151">Quantity</span></span></td>
<td><span data-ttu-id="a498e-152">Välj de kvantiteter som bokföringen av dokumentet baseras på.</span><span class="sxs-lookup"><span data-stu-id="a498e-152">Select the quantities to base the posting of the document on.</span></span> <span data-ttu-id="a498e-153">Vilka alternativ som finns tillgängliga beror på vilken typ av dokument du bokför, exempelvis följesedel eller faktura.</span><span class="sxs-lookup"><span data-stu-id="a498e-153">The options that are available vary, depending on the type of document that you are posting, such as a packing slip or an invoice.</span></span>
<ul>
<li><span data-ttu-id="a498e-154"><strong>Leverera nu</strong> – Välj alla kvantiteter som anges i fältet <strong>Leverera nu</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-154"><strong>Deliver now</strong> – Select all quantities that are entered in the <strong>Deliver now</strong> field.</span></span> <span data-ttu-id="a498e-155">Används om du vill bekräfta eller leverera en delorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-155">Use this option to confirm or deliver a partial order.</span></span></li>
<li><span data-ttu-id="a498e-156"><strong>Plockad</strong> – Välj alla kvantiteter som har plockats.</span><span class="sxs-lookup"><span data-stu-id="a498e-156"><strong>Picked</strong> – Select all quantities that have been picked.</span></span></li>
<li><span data-ttu-id="a498e-157"><strong>Alla</strong> – Välj alla försäljningsorderkvantiteter som ännu inte uppdaterats för den aktuella dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="a498e-157"><strong>All</strong> – Select all quantities on the sales order that haven&#39;t yet been updated by the current document type.</span></span></li>
<li><span data-ttu-id="a498e-158"><strong>Följesedel</strong> – Välj alla kvantiteter som har uppdaterats av en följesedel.</span><span class="sxs-lookup"><span data-stu-id="a498e-158"><strong>Packing slip</strong> – Select all quantities that have been updated by a packing slip.</span></span></li>
<li><span data-ttu-id="a498e-159"><strong>Plockad kvantitet och produkter som inte finns i lager</strong> – Välj alla kvantiteter som har plockats och alla produktkvantiteter som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="a498e-159"><strong>Picked quantity and not stocked products</strong> – Select all quantities that have been picked and all product quantities that aren&#39;t stocked.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-160">Bokför</span><span class="sxs-lookup"><span data-stu-id="a498e-160">Posting</span></span></td>
<td><ul>
<li><span data-ttu-id="a498e-161">Välj det här alternativet för att journalföra försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="a498e-161">Select this option to journalize the sales order.</span></span></li>
<li><span data-ttu-id="a498e-162">Avmarkera det här alternativet om du vill skriva ut en proformasäljorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-162">Clear this option to print a pro forma sales order.</span></span> <span data-ttu-id="a498e-163"><strong>Anm.:</strong> Om du har ingått ett avtal om en betalningsplan visas inte betalningsplanen på proformasäljordern.</span><span class="sxs-lookup"><span data-stu-id="a498e-163"><strong>Note:</strong> If you made an agreement for a payment schedule, the payment schedule isn&#39;t shown on the pro forma sales order.</span></span> <span data-ttu-id="a498e-164">Betalningsplanen visas bara på en faktisk försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-164">Payment schedules are shown only on actual sales orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498e-165">Sent urval</span><span class="sxs-lookup"><span data-stu-id="a498e-165">Late selection</span></span></td>
<td><span data-ttu-id="a498e-166">Välj det här alternativet om du vill köra den aktuella frågan senare.</span><span class="sxs-lookup"><span data-stu-id="a498e-166">Select this option to apply the selected query later.</span></span> <span data-ttu-id="a498e-167">Detta alternativ används för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="a498e-167">This option is used for batch jobs.</span></span> <span data-ttu-id="a498e-168">Frågan körs när batchjobbet körs.</span><span class="sxs-lookup"><span data-stu-id="a498e-168">The query is run when the batch job is run.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-169">Minska kvantiteten</span><span class="sxs-lookup"><span data-stu-id="a498e-169">Reduce quantity</span></span></td>
<td><span data-ttu-id="a498e-170">Välj det här alternativet för att automatiskt reducera den levererade kvantiteten, när dokumentet bokförs, så att den levererade kvantiteten är lika med det tillgängliga lagret.</span><span class="sxs-lookup"><span data-stu-id="a498e-170">Select this option to automatically reduce the delivered quantity when the document is posted, so that the delivered quantity equals the available inventory.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498e-171">Skriv ut</span><span class="sxs-lookup"><span data-stu-id="a498e-171">Print</span></span></td>
<td><span data-ttu-id="a498e-172">Välj när du vill skriva ut dokument:</span><span class="sxs-lookup"><span data-stu-id="a498e-172">Select when to print documents:</span></span>
<ul>
<li><span data-ttu-id="a498e-173"><strong>Aktuellt</strong> – Skriv ut dokument när varje faktura har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a498e-173"><strong>Current</strong> – Print documents after each invoice has been updated.</span></span></li>
<li><span data-ttu-id="a498e-174"><strong>Efter</strong> – Skriv ut dokument när alla fakturor har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a498e-174"><strong>After</strong> – Print documents after all the invoices have been updated.</span></span></li>
</ul><span data-ttu-id="a498e-175">
<strong>Anm.:</strong> Fältet <strong>Skriv ut</strong> är bara tillgängligt om du väljer alternativet <strong>Skriv ut faktura</strong>, <strong>Skriv ut bekräftelse</strong>, <strong>Skriv ut plocklista</strong> eller <strong>Skriv ut följesedel</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-175">
<strong>Note:</strong> The <strong>Print</strong> field is available only if you select the <strong>Print invoice</strong>, <strong>Print confirmation</strong>, <strong>Print picking list</strong>, or <strong>Print packing slip</strong> option.</span></span> <span data-ttu-id="a498e-176">Anta att du har konfigurerat sidan <strong>Formulärsortering</strong> till att sortera informationen efter fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="a498e-176">For example, on the <strong>Form sorting</strong> page, you have set up the system to sort the information by invoice account.</span></span> <span data-ttu-id="a498e-177">Du kan sedan välja <strong>Efter</strong> för att skriva ut dokument i en bunt sorterad efter fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="a498e-177">You can then select <strong>After</strong> to print the documents in a batch that is sorted by invoice account.</span></span> <span data-ttu-id="a498e-178">Annars skrivas ut dokumenten ut innan du bearbetningen slutförs och dokumenten sorteras inte i den ordning som anges på sidan <strong>Formulärsortering</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-178">Otherwise, the documents are printed before processing is completed, and the documents aren&#39;t sorted in the order that is specified on the <strong>Form sorting</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-179">Skriv ut faktura</span><span class="sxs-lookup"><span data-stu-id="a498e-179">Print invoice</span></span></td>
<td><span data-ttu-id="a498e-180">Markera det här alternativet om du vill skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="a498e-180">Select this option to print the invoice.</span></span> <span data-ttu-id="a498e-181">Om det här alternativet är inaktiverat kan du bokföra en faktura utan att skriva ut den.</span><span class="sxs-lookup"><span data-stu-id="a498e-181">If this option is turned off, you can post an invoice without printing it.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498e-182">Skicka e-post</span><span class="sxs-lookup"><span data-stu-id="a498e-182">Send e-mail</span></span></td>
<td><span data-ttu-id="a498e-183">Markera det här alternativet för att skicka fakturan för en försäljningsorder till kunden som en e-postbilaga efter att fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="a498e-183">Select this option to send the invoice for a sales order to the customer as an email attachment after the invoice is posted.</span></span> <span data-ttu-id="a498e-184">Bilagor skickas som PDF och XML-filer.</span><span class="sxs-lookup"><span data-stu-id="a498e-184">Attachments are sent as PDF and XML files.</span></span> <span data-ttu-id="a498e-185">Det här alternativet är tillgängligt om du väljer alternativet <strong>Aktivera CFD (elektroniska fakturor)</strong> på sidan <strong>Elektroniska fakturaparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-185">This option is available only if you select the <strong>Enable CFD (electronic invoices)</strong> option on the <strong>Electronic invoice parameters</strong> page.</span></span> <span data-ttu-id="a498e-186"><strong>Anm.:</strong> (MEX) Den här kontrollen är bara tillgänglig för juridiska personer som har den primära adressen i Mexiko.</span><span class="sxs-lookup"><span data-stu-id="a498e-186"><strong>Note:</strong> (MEX) This control is available only to legal entities whose primary address is in Mexico.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-187">Använd destination för utskriftshantering</span><span class="sxs-lookup"><span data-stu-id="a498e-187">Use print management destination</span></span></td>
<td><span data-ttu-id="a498e-188">Markera det här alternativet för att använda utskriftsinställningarna som har angetts för transaktionen, dokumentet eller modulen på sidan <strong>Inställning för utskriftshantering</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-188">Select this option to use the print settings that are specified for the transaction, document, or module on the <strong>Print management setup</strong> page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498e-189">Kontrollera kreditgräns</span><span class="sxs-lookup"><span data-stu-id="a498e-189">Check credit limit</span></span></td>
<td><span data-ttu-id="a498e-190">Välj informationen som ska analyseras när en kreditgränskontroll utförs.</span><span class="sxs-lookup"><span data-stu-id="a498e-190">Select the information that should be analyzed when a credit limit check is performed.</span></span>
<ul>
<li><span data-ttu-id="a498e-191"><strong>Ingen</strong> – Det finns inga krav för kreditgränskontrollen.</span><span class="sxs-lookup"><span data-stu-id="a498e-191"><strong>None</strong> – There is no requirement for the credit limit check.</span></span></li>
<li><span data-ttu-id="a498e-192"><strong>Saldo</strong> – Kreditgränsen kontrolleras mot kundsaldot.</span><span class="sxs-lookup"><span data-stu-id="a498e-192"><strong>Balance</strong> – The credit limit is checked against the customer balance.</span></span></li>
<li><span data-ttu-id="a498e-193"><strong>Saldo+följesedel eller produktinleverans</strong> – Kreditgränsen kontrolleras mot kundsaldot och leveranserna.</span><span class="sxs-lookup"><span data-stu-id="a498e-193"><strong>Balance + packing slip or product receipt</strong> – The credit limit is checked against the customer balance and deliveries.</span></span></li>
<li><span data-ttu-id="a498e-194"><strong>Saldo+Alla</strong> – Kreditgränsen kontrolleras mot kundsaldot, leveranser och öppna order.</span><span class="sxs-lookup"><span data-stu-id="a498e-194"><strong>Balance+All</strong> – The credit limit is checked against the customer balance, deliveries, and open orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-195">Kreditkorrigering</span><span class="sxs-lookup"><span data-stu-id="a498e-195">Credit correction</span></span></td>
<td><span data-ttu-id="a498e-196">Välj det här alternativet om du vill visa en kreditfaktura som debet i verifikationstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="a498e-196">Select this option to display the credit note as a debit in the voucher transactions.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a498e-197">Kreditrestkvantitet</span><span class="sxs-lookup"><span data-stu-id="a498e-197">Credit remaining quantity</span></span></td>
<td><span data-ttu-id="a498e-198">Om du bokför en kreditfaktura väljer du det här alternativet för att behålla den resterande kvantiteten i ordern.</span><span class="sxs-lookup"><span data-stu-id="a498e-198">If you&#39;re posting a credit note, select this option to keep the remaining quantity on order.</span></span> <span data-ttu-id="a498e-199">Om alternativet avmarkeras anges resterande kvantitet till 0 (noll).</span><span class="sxs-lookup"><span data-stu-id="a498e-199">If this option is cleared, the remaining quantity is set to 0 (zero).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a498e-200">Samlingsuppdatering för</span><span class="sxs-lookup"><span data-stu-id="a498e-200">Summary update for</span></span></td>
<td><span data-ttu-id="a498e-201">Välj hur flera olika försäljningsorder ska summeras:</span><span class="sxs-lookup"><span data-stu-id="a498e-201">Select how multiple sales orders should be summarized:</span></span>
<ul>
<li><span data-ttu-id="a498e-202"><strong>Ingen</strong> – Summera inte försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-202"><strong>None</strong> – Don&#39;t summarize sales orders.</span></span> <span data-ttu-id="a498e-203">Skapa till exempel en separat faktura för varje försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a498e-203">For example, a separate invoice will be created for each sales order.</span></span></li>
<li><span data-ttu-id="a498e-204"><strong>Fakturakonto</strong> – Alla valda order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-204"><strong>Invoice account</strong> – Summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span></li>
<li><span data-ttu-id="a498e-205"><strong>Order</strong> – Summera ett angett intervall av order till en order som du anger.</span><span class="sxs-lookup"><span data-stu-id="a498e-205"><strong>Order</strong> – Summarize a selected range of orders into one order that you specify.</span></span> <span data-ttu-id="a498e-206">Dessa order summeras enligt de kriterier som ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-206">The orders are summarized based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="a498e-207">Om detta alternativ är valt måste du välja ett värde i fältet <strong>Försäljningsorder</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-207">If you select this option, you must select a value in the <strong>Sales order</strong> field.</span></span></li>
<li><span data-ttu-id="a498e-208"><strong>Automatisk sammanfattning</strong> – Om samlingsuppdateringar har angetts på sidan <strong>Samlingsuppdatera</strong>, sammanfatta alla valda order, baserat på villkoren som har ställts in på sidan <strong>Samlingsuppdateringsparametrar</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-208"><strong>Automatic summary</strong> – If summary updates have been specified on the <strong>Summary update</strong> page, summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="a498e-209">Om samlingsuppdateringar inte anges, bokförs ordern separat.</span><span class="sxs-lookup"><span data-stu-id="a498e-209">If summary updates haven&#39;t been specified, the order is posted separately.</span></span></li>
<li><span data-ttu-id="a498e-210"><strong>Följesedel</strong> – Summera ett valt intervall av order till en faktura per följesedel.</span><span class="sxs-lookup"><span data-stu-id="a498e-210"><strong>Packing slip</strong> – Summarize a selected range of orders into one invoice for each packing slip.</span></span> <span data-ttu-id="a498e-211">Det här alternativet är endast tillgängligt om <strong>Följesedel</strong> har valts i fältet <strong>Kvantitet</strong>.</span><span class="sxs-lookup"><span data-stu-id="a498e-211">This option is available only if <strong>Packing slip</strong> is selected in the <strong>Quantity</strong> field.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>





