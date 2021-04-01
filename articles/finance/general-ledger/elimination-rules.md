---
title: Elimineringsregler
description: Det här avsnittet innehåller information om elimineringsregler och de olika alternativen för rapportering om elimineringar.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8228933f9a1357bf694b8b5bafa7d136ab02627
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236756"
---
# <a name="elimination-rules"></a><span data-ttu-id="dbf3f-103">Elimineringsregler</span><span class="sxs-lookup"><span data-stu-id="dbf3f-103">Elimination rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbf3f-104">Det här avsnittet innehåller information om elimineringsregler och de olika alternativen för rapportering om elimineringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-104">This topic provides information about elimination rules and the various options for reporting about eliminations.</span></span>

<span data-ttu-id="dbf3f-105">Elimineringstransaktioner behövs när en överordnad juridisk person gör affärer med en eller flera underordnade juridiska personer och använder konsoliderad ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-105">Elimination transactions are required when a parent legal entity does business with one or more subsidiary legal entities and uses consolidated financial reporting.</span></span> <span data-ttu-id="dbf3f-106">Konsoliderade bokslut måste innehålla transaktioner som uppstår mellan den konsoliderade organisationen och andra enheter utanför den organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-106">Consolidated financial statements must include only transactions that occur between the consolidated organization and other entities outside that organizations.</span></span> <span data-ttu-id="dbf3f-107">Därför måste transaktioner mellan juridiska personer som ingår i samma organisation tas bort eller elimineras från redovisningen så att de inte visas i ekonomiska rapporter.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-107">Therefore, transactions between legal entities that are part of the same organization must be removed, or eliminated, from the general ledger, so they don't appear on financial reports.</span></span> <span data-ttu-id="dbf3f-108">Det finns flera sätt att rapportera om elimineringar:</span><span class="sxs-lookup"><span data-stu-id="dbf3f-108">There are multiple ways to report about eliminations:</span></span>

-   <span data-ttu-id="dbf3f-109">En elimineringsregel kan skapas och bearbetas i ett konsoliderings- eller elimineringsföretag.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-109">An elimination rule can be created and processed in a consolidation or elimination company.</span></span>
-   <span data-ttu-id="dbf3f-110">Den ekonomiska rapporteringen kan användas för att visa elimineringskontona och dimensionerna i en specifik rad eller kolumn.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-110">Financial reporting can be used to show the eliminations accounts and dimensions on a specific row or column.</span></span>
-   <span data-ttu-id="dbf3f-111">En separat juridisk person kan användas till att bokföra manuella transaktionsposter för att spåra elimineringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-111">A separate legal entity can be used to post manual transaction entries to track eliminations.</span></span>

<span data-ttu-id="dbf3f-112">Det här avsnittet beskriver elimineringsregler som bearbetas i ett konsolidering- eller elimineringsföretag.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-112">This topic focuses on elimination rules that are processed in a consolidation or elimination company.</span></span> <span data-ttu-id="dbf3f-113">Du ställer in elimineringsregler när du vill skapa elimineringstransaktioner i en juridisk person som anges som destination för elimineringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-113">You can set up elimination rules to create elimination transactions in a legal entity that is specified as the destination legal entity for eliminations.</span></span> <span data-ttu-id="dbf3f-114">Den juridiska personen på destinationen kallas för eliminerande juridisk person.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-114">This destination legal entity is known as the elimination legal entity.</span></span> <span data-ttu-id="dbf3f-115">Elimineringsjournaler kan skapas antingen under konsolideringen eller med hjälp av ett elimineringsjournalförslag.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-115">Elimination journals can be generated either during the consolidation process or by using an elimination journal proposal.</span></span> <span data-ttu-id="dbf3f-116">Innan du ställer in elimineringsregler bör du känna till följande termer:</span><span class="sxs-lookup"><span data-stu-id="dbf3f-116">Before you set up elimination rules, you should become familiar with the following terms:</span></span>

-   <span data-ttu-id="dbf3f-117">**Juridisk person, källa** – Den juridiska person där beloppen som elimineras bokfördes.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-117">**Source legal entity** – The legal entity where the amounts that are being eliminated were posted.</span></span>
-   <span data-ttu-id="dbf3f-118">**Destinationens juridiska person** – Den juridiska personen där elimineringsreglerna registreras.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-118">**Destination legal entity** – The legal entity where elimination rules are posted.</span></span>
-   <span data-ttu-id="dbf3f-119">**Juridisk person för eliminering** – Den juridiska person som anges som destination för elimineringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-119">**Elimination legal entity** – The legal entity that is specified as the destination legal entity for eliminations.</span></span>
-   <span data-ttu-id="dbf3f-120">**Konsoliderad juridisk person** – Den juridiska person som skapas för att rapportera ekonomiska resultat för en grupp juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-120">**Consolidated legal entity** – The legal entity that is created to report financial results for a group of legal entities.</span></span> <span data-ttu-id="dbf3f-121">De ekonomiska data från de juridiska personerna konsolideras i den här juridiska personen, och sedan skapas en ekonomisk rapport med hjälp av dessa kombinerade data.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-121">The financial data from the legal entities is consolidated into this legal entity, and then a financial report is created by using the combined data.</span></span>

<span data-ttu-id="dbf3f-122">Följande tabell visar de transaktionstyper som kanske måste elimineras.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-122">The following table shows the types of transactions that might have to be eliminated.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf3f-123">transaktionstyp</span><span class="sxs-lookup"><span data-stu-id="dbf3f-123">Transaction type</span></span></th>
<th><span data-ttu-id="dbf3f-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="dbf3f-124">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="dbf3f-125">Försäljningsorderregistrering och fakturering (centraliserad bearbetning)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-125">Sales order entry and invoicing (centralized processing)</span></span></td>
<td><span data-ttu-id="dbf3f-126">Du säljer en produkt till en kund på uppdrag av en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-126">You sell a product to a customer on behalf of another legal entity in your organization.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-127">Försäljningsorderregistrering (koncernintern/företagsintern) och fakturering</span><span class="sxs-lookup"><span data-stu-id="dbf3f-127">Sales order entry (intercompany/intracompany) and invoicing</span></span></td>
<td><span data-ttu-id="dbf3f-128">Du säljer produkter mellan juridiska personer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-128">You sell products between legal entities in your organization.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dbf3f-129">Inköpsorder (centraliserad bearbetning)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-129">Purchase orders (centralized processing)</span></span></td>
<td><span data-ttu-id="dbf3f-130">Du kan köpa lager, varor, tjänster, anläggningstillgångar och andra produkter från en leverantör på uppdrag av en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-130">You purchase inventory, supplies, services, fixed assets, and other products from a vendor on behalf of another legal entity in your organization.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-131">Lagerhantering (koncernintern/företagsintern)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-131">Inventory management (intercompany/intracompany)</span></span></td>
<td><ul>
<li><span data-ttu-id="dbf3f-132">Du överför en juridisk persons lager till anläggningstillgångar för en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-132">You transfer one legal entity’s inventory to the fixed assets of another legal entity in your organization.</span></span></li>
<li><span data-ttu-id="dbf3f-133">Du överför en juridisk persons lager till lagret för en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-133">You transfer one legal entity’s inventory to the inventory of another legal entity in your organization.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dbf3f-134">Lagerspårning under transport</span><span class="sxs-lookup"><span data-stu-id="dbf3f-134">In-transit inventory tracking</span></span></td>
<td><span data-ttu-id="dbf3f-135">Du överför artiklar mellan lagerställen inom samma juridiska person, men mellan olika geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-135">You transfer items between warehouses in the same legal entity, but across different geographical sites.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-136">Centraliserad fakturabearbetning i leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="dbf3f-136">Accounts payable centralized invoice processing</span></span></td>
<td><span data-ttu-id="dbf3f-137">Du kan registrera en faktura på uppdrag av en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-137">You record an invoice on behalf of another legal entity in your organization.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dbf3f-138">Centraliserad betalningsbearbetning i leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="dbf3f-138">Accounts payable centralized payment processing</span></span></td>
<td><span data-ttu-id="dbf3f-139">Du kan betala en faktura på uppdrag av en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-139">You pay an invoice on behalf of another legal entity in your organization.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-140">Kassahantering (centraliserad hantering)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-140">Cash management and treasury (centralized processing)</span></span></td>
<td><ul>
<li><span data-ttu-id="dbf3f-141">Du kan bearbeta skattebetalningar, återbetalningar av skatt, ränteavgifter, lån, förskott, betalda utdelningar och förutbetalda royalties eller provisioner.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-141">You process tax payments, tax refunds, interest charges, loans, advances, dividend payments, and prepaid royalties or commissions.</span></span></li>
<li><span data-ttu-id="dbf3f-142">Du kan betala en utgift på uppdrag av en annan juridisk person i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-142">You pay an expense on behalf of another legal entity in your organization.</span></span> <span data-ttu-id="dbf3f-143">Fakturan anges i den juridiska målpersonens böcker och du måste göra kvittningar mellan olika juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-143">The invoice is entered in the destination legal entity’s books, and you must cross-settle between legal entities.</span></span> <span data-ttu-id="dbf3f-144">En juridisk person betalar till exempel utgiftsrapporten för en medarbetare i en annan juridisk person.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-144">For example, one legal entity pays the expense report of an employee in another legal entity.</span></span> <span data-ttu-id="dbf3f-145">I det här fallet har medarbetarens utgiftsrapport som är relaterade till en annan juridisk person.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-145">In this case, the employee’s expense report has expenses that are related to another legal entity.</span></span></li>
<li><span data-ttu-id="dbf3f-146">Du överför medel från en juridisk person till en annan i din organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-146">You transfer cash from one legal entity to another in your organization.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dbf3f-147">Kundreskontra (centraliserad hantering)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-147">Accounts receivable (centralized processing)</span></span></td>
<td><span data-ttu-id="dbf3f-148">Du tar emot kontanter för en annan juridisk persons kundfaktura och du sätter in checken på den juridiska personens bankkonto.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-148">You receive cash for another legal entity’s customer invoice, and you deposit the check into that legal entity’s bank account.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-149">Lön (centraliserad hantering, koncernintern/företagsintern)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-149">Payroll (centralized processing, intercompany/intracompany)</span></span></td>
<td><ul>
<li><span data-ttu-id="dbf3f-150">Du kan betala en annan juridisk persons Lön.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-150">You pay another legal entity’s payroll.</span></span> <span data-ttu-id="dbf3f-151">En juridisk person kanske till exempel betalar sina egna löner till de anställda, men debiterar tillbaka arbete som en medarbetare har utfört för en annan juridisk person under lönekörningen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-151">For example, a legal entity pays its own payroll for its employees but charges back work that an employee did for another legal entity during that pay run.</span></span> <span data-ttu-id="dbf3f-152">Eller om en medarbetare har arbetat halvtid för den juridiska personen A och halvtid för den juridiska personen B och förmånerna gäller för hela lönen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-152">Or, an employee worked half-time for legal entity A and half-time for legal entity B, and the benefits are across all pay.</span></span> <span data-ttu-id="dbf3f-153">I så fall innehåller medarbetarens lön betalningen från båda juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-153">In these cases, the employee’s pay includes pay from both legal entities.</span></span> <span data-ttu-id="dbf3f-154">Det är inte bara löner som bokförs utan även skatter, förmåner, avdrag och periodiseringar för löner bokförs.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-154">Not only are the salaries posted, but taxes, benefits, deductions, and accruals for salaries are also posted.</span></span></li>
<li><span data-ttu-id="dbf3f-155">Du överför arbete från en avdelning eller division till en annan.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-155">You transfer labor from one department or division to another.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="dbf3f-156">Anläggningstillgångar (koncernintern/företagsintern)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-156">Fixed assets (intercompany/intracompany)</span></span></td>
<td><span data-ttu-id="dbf3f-157">Du överför anläggningstillgångar till en annan juridisk persons anläggningstillgångar eller lager.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-157">You transfer fixed assets to another legal entity’s fixed assets or inventory.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="dbf3f-158">Allokeringar (koncernintern/företagsintern)</span><span class="sxs-lookup"><span data-stu-id="dbf3f-158">Allocations (intercompany/intracompany)</span></span></td>
<td><span data-ttu-id="dbf3f-159">Du kan bearbeta företagsallokeringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-159">You process corporate allocations.</span></span> <span data-ttu-id="dbf3f-160">Allokeringar är aktiviteter för alla konton som är allokerade, oavsett den ursprungliga modulen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-160">Allocations are activities to any account that is allocated, regardless of the originating module.</span></span></td>
</tr>
</tbody>
</table>

## <a name="example"></a><span data-ttu-id="dbf3f-161">Exempel</span><span class="sxs-lookup"><span data-stu-id="dbf3f-161">Example</span></span>
<span data-ttu-id="dbf3f-162">Din juridiska person, juridisk person A, säljer prylar till en annan juridisk person inom din organisation, juridisk person B. Följande exempel visar hur transaktionerna som uppstår mellan de två juridiska personerna kanske måste elimineras:</span><span class="sxs-lookup"><span data-stu-id="dbf3f-162">Your legal entity, legal entity A, sells widgets to another legal entity in your organization, legal entity B. The following example shows how transactions that occur between the two legal entities might have to be eliminated:</span></span>

-   <span data-ttu-id="dbf3f-163">Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 10,00.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-163">Legal entity A sells a widget that costs 10.00 to legal entity B for 10.00.</span></span>
-   <span data-ttu-id="dbf3f-164">Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 10,00 plus 2,00 i faktiska fraktkostnader.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-164">Legal entity A sells a widget that costs 10.00 to legal entity B for 10.00, plus 2.00 in actual shipping costs.</span></span>
-   <span data-ttu-id="dbf3f-165">Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 15,00 och tillerkänns en marginal på försäljningen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-165">Legal entity A sells a widget that costs 10.00 to legal entity B for 15.00 and recognizes a margin on the sale.</span></span>
-   <span data-ttu-id="dbf3f-166">Juridisk person A säljer en pryl som kostar 10,00 till juridisk person B för 15,00 och tillerkänns halva marginalen på försäljningen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-166">Legal entity A sells a widget that costs 10.00 to legal entity B for 15.00 and recognizes half the margin on the sale.</span></span> <span data-ttu-id="dbf3f-167">Juridisk person B tillerkänns den andra halvan av marginalen på försäljningen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-167">Legal entity B recognizes the other half of the margin on the sale.</span></span> <span data-ttu-id="dbf3f-168">Därför delas intäkten.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-168">Therefore, the revenue is split.</span></span> <span data-ttu-id="dbf3f-169">Delade intäkter ger ett incitament till order från en annan juridisk person i organisationen i stället för en extern organisation.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-169">Split revenue provides an incentive to order from another legal entity in the organization instead of an external organization.</span></span>

<span data-ttu-id="dbf3f-170">Alla dessa transaktioner skapar koncerninterna transaktioner som bokförs på förfaller till- och förfaller från-konton.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-170">All these transactions create intercompany transactions that are posted to due-to and due-from accounts.</span></span> <span data-ttu-id="dbf3f-171">Dessutom kan dessa transaktioner kanske omfatta påläggs- och nedsättningsbelopp när beloppet för den koncerninterna försäljningen inte är lika med kostnaden för de varor som sålts.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-171">In addition, these transactions might include markup and markdown amounts when the amount of the intercompany sale doesn't equal the cost of the goods that were sold.</span></span>

## <a name="set-up-elimination-rules"></a><span data-ttu-id="dbf3f-172">Ställ in elimineringsregler</span><span class="sxs-lookup"><span data-stu-id="dbf3f-172">Set up elimination rules</span></span>
<span data-ttu-id="dbf3f-173">När du ställer in elimineringsregler rekommenderar vi att du skapar en ekonomisk dimension som särskilt avser eliminering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-173">When setting up elimination rules, we recommend that you create a financial dimension specifically for elimination purposes.</span></span> <span data-ttu-id="dbf3f-174">De flesta kunder kallar den Commercespartner eller något liknande.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-174">Most customers name it Trading Partner or something similar.</span></span> <span data-ttu-id="dbf3f-175">Om du inte vill använda en ekonomisk dimension, se då till att ha huvudkonton som gäller endast för koncerninterna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-175">If you decide not to use a financial dimension, then be sure to have main accounts that are specific for intercompany transactions only.</span></span> 

<span data-ttu-id="dbf3f-176">Inställningar för elimineringar finns i området Inställningar i modulen Konsolideringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-176">The setup for eliminations is found in the Setup area of the Consolidations module.</span></span> <span data-ttu-id="dbf3f-177">När du anger en beskrivning för regeln måste du välja det företag som elimineringsjournalen ska bokföra till.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-177">After you enter a description for the rule, you must pick the company that the elimination journal will post to.</span></span> <span data-ttu-id="dbf3f-178">Detta bör vara ett företag som har **Använd för ekonomisk elimineringsprocess** markerat i inställningarna för juridisk enhet.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-178">This should be a company that has **Use for financial elimination process** selected in the Legal entity setup.</span></span> 

<span data-ttu-id="dbf3f-179">Du kan ange ett datum då elimineringsregeln träder i kraft och när den löper ut, om så krävs.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-179">You can set a date on which the elimination rule becomes effective and when it is expired, if needed.</span></span> <span data-ttu-id="dbf3f-180">Du måste ange **Aktiv** som **Ja** om du vill att den ska vara tillgänglig i förslagsprocessen för eliminering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-180">You must set **Active** to **Yes** if you want it to be available in the elimination proposal process.</span></span> <span data-ttu-id="dbf3f-181">Välj ett journalnamn som har en typ av **Eliminering**.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-181">Select a journal name that has a type of **Elimination**.</span></span>

<span data-ttu-id="dbf3f-182">Du kan definiera de faktiska bearbetningsreglerna genom att klicka på **Rader** när du har angett grundläggande information.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-182">After you have defined the basics, you can define the actual processing rules by clicking **Lines**.</span></span> <span data-ttu-id="dbf3f-183">Det finns två olika alternativ för elimineringar: att eliminera nettoändringsbeloppet eller att definiera ett fast belopp.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-183">There are two options for eliminations, eliminating the net change amount or defining a fixed amount.</span></span> 

<span data-ttu-id="dbf3f-184">Markera ditt källkonto.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-184">Select your source account.</span></span> <span data-ttu-id="dbf3f-185">Du kan använda asterisk (\*) som jokertecken.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-185">You can use an asterisk (\*) as a wild card.</span></span> <span data-ttu-id="dbf3f-186">1\* skulle till exempel välja alla konton som börjar med 1 som datakälla för allokeringen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-186">For example, 1\* would select all accounts that start with a 1 as a source of data for the allocation.</span></span> 

<span data-ttu-id="dbf3f-187">När du har valt dina källkonton, avgör **Kontospecifikationen** det konto från destinationsföretaget som används.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-187">After you have selected your source accounts, the **Account specification** determines the account from the destination company that is used.</span></span> <span data-ttu-id="dbf3f-188">Välj **Källa** om du vill använda samma huvudkonto som angetts i kontot **Källa**.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-188">Select **Source** if you want to use the same main account defined in the **Source** account.</span></span> <span data-ttu-id="dbf3f-189">Om du väljer **Användardefinierad** måste du ange ett destinationskonto.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-189">If you select **User defined**, then you must specify a destination account.</span></span> 

<span data-ttu-id="dbf3f-190">Dimensionsspecifikationen fungerar på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-190">The dimension specification acts in the same way.</span></span> <span data-ttu-id="dbf3f-191">Om du väljer **Källa** används samma dimensioner i destinationsföretaget som i källföretaget.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-191">If you select **Source**, it will use the same dimensions in the destination company as the source company.</span></span> <span data-ttu-id="dbf3f-192">Om du väljer **Användardefinierad** måste du ange dimensioner för destinationsföretaget genom att klicka på menyobjektet **Måldimensioner**.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-192">If you select **User defined**, you will need to specify the dimensions in the destination company by clicking the **Destination dimensions** menu item.</span></span> 

<span data-ttu-id="dbf3f-193">Välj källdimensioner och ekonomiska dimensioner, samt de värden som används som källa för eliminering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-193">Select source dimensions and the financial dimensions and values that are used as a source of the elimination.</span></span>

## <a name="process-elimination-transactions"></a><span data-ttu-id="dbf3f-194">Bearbeta elimineringstransaktioner</span><span class="sxs-lookup"><span data-stu-id="dbf3f-194">Process elimination transactions</span></span>
<span data-ttu-id="dbf3f-195">Det finns två sätt att bearbeta elimineringstransaktioner: i samband med konsolideringsprocessen online, eller genom att skapa en journal för eliminering och köra förslagsprocessen för eliminering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-195">There are two ways to process elimination transactions, during the consolidate online process or by creating an elimination journal and running the elimination proposal process.</span></span> <span data-ttu-id="dbf3f-196">Det här avsnittet fokuserar på hur du skapar journalen och kör elimineringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-196">This section focuses on creating the journal and running the elimination process.</span></span> 

<span data-ttu-id="dbf3f-197">I ett företag som definierats som ett elimineringsföretag, välj **Elimineringsjournal** i modulen Konsolideringar.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-197">In a company defined as an elimination company, select **Elimination journal** in the Consolidations module.</span></span> <span data-ttu-id="dbf3f-198">Klicka på **Rader** när du har valt journalnamn.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-198">After you have selected the journal name, click **Lines**.</span></span> <span data-ttu-id="dbf3f-199">Du kan köra förslaget genom att välja menyn **Förslag** och sedan välja **Elimineringsförslag**.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-199">You can run the proposal by selecting the **Proposals** menu and then selecting **Elimination proposal**.</span></span>

<span data-ttu-id="dbf3f-200">Välj det företag som utgör grunden för den konsoliderade datan, och välj sedan den regel som du vill bearbeta.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-200">Select the company that is the source of the consolidated data, and then choose the rule that you want to process.</span></span> <span data-ttu-id="dbf3f-201">Ange ett startdatum för att påbörja sökningen efter elimineringsbelopp och ett slutdatum för att avsluta sökdatum för eliminering.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-201">Enter a start date to begin the search for elimination amounts, and an end date to end the search date for elimination amounts.</span></span> <span data-ttu-id="dbf3f-202">Fältet **GL-bokföringsdatum** är det datum som används för att bokföra journalen i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-202">The **GL posting date** field is the date used for posting the journal to the general ledger.</span></span> <span data-ttu-id="dbf3f-203">När du klickar på **OK** kan du granska belopp och bokföra journalen.</span><span class="sxs-lookup"><span data-stu-id="dbf3f-203">After you click **OK**, you can review the amounts and post the journal.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]