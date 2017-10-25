---
title: Nummerserier
description: "Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare."
author: MargoC
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bd1f4d383848e6205d64be160da4c529adeaccf2
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="number-sequences"></a><span data-ttu-id="9f013-103">Nummerserier</span><span class="sxs-lookup"><span data-stu-id="9f013-103">Number sequences</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9f013-104">Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare.</span><span class="sxs-lookup"><span data-stu-id="9f013-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="9f013-105">En huvuddatapost eller en transaktionspost som kräver en identifierare kallas för en *referens*.</span><span class="sxs-lookup"><span data-stu-id="9f013-105">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span>

<span data-ttu-id="9f013-106">Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen.</span><span class="sxs-lookup"><span data-stu-id="9f013-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="9f013-107">Vi rekommenderar att du använder sidorna i **Organisationsadministration** för att ställa in nummerserier.</span><span class="sxs-lookup"><span data-stu-id="9f013-107">We recommend that you use the pages in **Organization administration** to set up number sequences.</span></span> <span data-ttu-id="9f013-108">Om modulspecifika inställningar krävs kan du använda parametersidan i en modul för att ange nummerserier för referenserna i den modulen.</span><span class="sxs-lookup"><span data-stu-id="9f013-108">If module-specific settings are required, you can use the parameters page in a module to specify number sequences for the references in that module.</span></span> <span data-ttu-id="9f013-109">I **Kundreskontra** och **Leverantörsreskontra** kan du till exempel ställa in nummerseriegrupper för att allokera specifika nummerserier till vissa kunder eller leverantörer.</span><span class="sxs-lookup"><span data-stu-id="9f013-109">For example, in **Accounts receivable** and **Accounts payable**, you can set up number sequence groups to allocate specific number sequences to specific customers or vendors.</span></span> 

<span data-ttu-id="9f013-110">När du anger en nummerserie, måste du ange omfång, som definierar vilken organisation som använder nummerserien.</span><span class="sxs-lookup"><span data-stu-id="9f013-110">When you set up a number sequence, you must specify a scope, which defines which organization uses the number sequence.</span></span> <span data-ttu-id="9f013-111">Omfånget kan vara **Delat**, **Företag**, **Juridisk person** eller **Driftenhet**.</span><span class="sxs-lookup"><span data-stu-id="9f013-111">The scope can be **Shared**, **Company**, **Legal entity**, or **Operating unit**.</span></span> <span data-ttu-id="9f013-112">Omfattningarna **Juridisk person** och **Företag** kan kombineras med **Räkenskapskalenderperiod** för att skapa ännu mer specifika nummerserier.</span><span class="sxs-lookup"><span data-stu-id="9f013-112">**Legal entity** and **Company** scopes can be combined with **Fiscal calendar period** to create even more specific number sequences.</span></span> 

<span data-ttu-id="9f013-113">Nummerserieformat består av segment.</span><span class="sxs-lookup"><span data-stu-id="9f013-113">Number sequence formats consist of segments.</span></span> <span data-ttu-id="9f013-114">Nummerserier som har ett annat omfång än **Delat** kan innehålla segment som motsvarar omfånget.</span><span class="sxs-lookup"><span data-stu-id="9f013-114">Number sequences with a scope other than **Shared** can contain segments that correspond to the scope.</span></span> <span data-ttu-id="9f013-115">Till exempel kan en nummerserie med omfånget **Juridisk person** innehålla ett segment med en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="9f013-115">For example, a number sequence with a scope of **Legal entity** can contain a legal entity segment.</span></span> <span data-ttu-id="9f013-116">Genom att inkludera ett omfångsegment i nummerserieformatet kan du identifiera omfånget för en viss post med hjälp av numret.</span><span class="sxs-lookup"><span data-stu-id="9f013-116">By including a scope segment in the number sequence format, you can identify the scope of a particular record by looking at its number.</span></span> 

<span data-ttu-id="9f013-117">Förutom segment som motsvarar omfång kan nummerserieformat innehålla **konstanta** och **alfanumeriska segment**.</span><span class="sxs-lookup"><span data-stu-id="9f013-117">In addition to segments that correspond to scopes, number sequence formats can contain **Constant** and **Alphanumeric segments**.</span></span> <span data-ttu-id="9f013-118">Ett **konstant** segment innehåller en uppsättning bokstäver, siffror eller symboler som inte ändras.</span><span class="sxs-lookup"><span data-stu-id="9f013-118">A **Constant** segment contains a set of letters, numbers, or symbols that does not change.</span></span> <span data-ttu-id="9f013-119">Ett **alfanumeriskt** segment innehåller en uppsättning bokstäver eller siffror som ökar varje gång ett nummer används.</span><span class="sxs-lookup"><span data-stu-id="9f013-119">An **Alphanumeric** segment contains a set of letters or numbers that increment every time that a number is used.</span></span> <span data-ttu-id="9f013-120">Använd ett nummertecken (\#) om du vill ange ökande nummer och ett et-tecken (&) om du vill ange att ökande bokstäver.</span><span class="sxs-lookup"><span data-stu-id="9f013-120">Use a number sign (\#) to represent incrementing numbers and an ampersand (&) to represent incrementing letters.</span></span> <span data-ttu-id="9f013-121">Med formatet \#\#\#\#\#\_2017 skapas till exempel serien 00001\_2017, 00002\_2017, och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9f013-121">For example, the format \#\#\#\#\#\_2017 creates the sequence 00001\_2017, 00002\_2017, and so on.</span></span>

<a name="number-sequence-examples"></a><span data-ttu-id="9f013-122">Exempel på nummerserier</span><span class="sxs-lookup"><span data-stu-id="9f013-122">Number sequence examples</span></span>
------------------------

<span data-ttu-id="9f013-123">Följande exempel visar hur du använder segment när du vill skapa nummerserieformat.</span><span class="sxs-lookup"><span data-stu-id="9f013-123">The following examples show how to use segments to create number sequence formats.</span></span> <span data-ttu-id="9f013-124">Närmare bestämt visar exemplen effekterna av att använda omfångsegment.</span><span class="sxs-lookup"><span data-stu-id="9f013-124">In particular, the examples demonstrate the effects of using scope segments.</span></span>

### <a name="expense-report-numbers"></a><span data-ttu-id="9f013-125">Utgiftsrapportnummer</span><span class="sxs-lookup"><span data-stu-id="9f013-125">Expense report numbers</span></span>

<span data-ttu-id="9f013-126">I följande exempel ställs utgiftsrapportnummer in för den juridiska personen med namnet **CS**.</span><span class="sxs-lookup"><span data-stu-id="9f013-126">In the following example, expense report numbers are set up for the legal entity that is titled **CS**.</span></span> 

- <span data-ttu-id="9f013-127">**Område:** Resor och utgifter</span><span class="sxs-lookup"><span data-stu-id="9f013-127">**Area:** Travel and expense</span></span> 
- <span data-ttu-id="9f013-128">**Referens:** Rapportnummer för utgifter</span><span class="sxs-lookup"><span data-stu-id="9f013-128">**Reference:** Expense report number</span></span> 
- <span data-ttu-id="9f013-129">**Omfång:** Juridisk person</span><span class="sxs-lookup"><span data-stu-id="9f013-129">**Scope:** Legal entity</span></span> 
- <span data-ttu-id="9f013-130">**Juridisk person:** CS</span><span class="sxs-lookup"><span data-stu-id="9f013-130">**Legal entity:** CS</span></span>

| <span data-ttu-id="9f013-131">Segment</span><span class="sxs-lookup"><span data-stu-id="9f013-131">Segments</span></span>  | <span data-ttu-id="9f013-132">Segmenttyp</span><span class="sxs-lookup"><span data-stu-id="9f013-132">Segment type</span></span> | <span data-ttu-id="9f013-133">Värde</span><span class="sxs-lookup"><span data-stu-id="9f013-133">Value</span></span>     |
|-----------|--------------|-----------|
| <span data-ttu-id="9f013-134">Segment 1</span><span class="sxs-lookup"><span data-stu-id="9f013-134">Segment 1</span></span> | <span data-ttu-id="9f013-135">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="9f013-135">Legal entity</span></span> | <span data-ttu-id="9f013-136">CS</span><span class="sxs-lookup"><span data-stu-id="9f013-136">CS</span></span>        |
| <span data-ttu-id="9f013-137">Segment 2</span><span class="sxs-lookup"><span data-stu-id="9f013-137">Segment 2</span></span> | <span data-ttu-id="9f013-138">Konstant</span><span class="sxs-lookup"><span data-stu-id="9f013-138">Constant</span></span>     | <span data-ttu-id="9f013-139">-UTGIFT-</span><span class="sxs-lookup"><span data-stu-id="9f013-139">-EXPENSE-</span></span> |
| <span data-ttu-id="9f013-140">Segment 3</span><span class="sxs-lookup"><span data-stu-id="9f013-140">Segment 3</span></span> | <span data-ttu-id="9f013-141">Alfanumerisk</span><span class="sxs-lookup"><span data-stu-id="9f013-141">Alphanumeric</span></span> | \#\#\#\#  |

<span data-ttu-id="9f013-142">**Exempel på formaterat nummer**: CS-UTGIFT-0039</span><span class="sxs-lookup"><span data-stu-id="9f013-142">**Example of formatted number**: CS-EXPENSE-0039</span></span> 

<span data-ttu-id="9f013-143">Du kan ställa in ett liknande nummersekvensformat för andra juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="9f013-143">You can set up a similar number sequence format for other legal entities.</span></span> <span data-ttu-id="9f013-144">Om du bara ändrar värdet för segmentet med en juridisk person, **RW**, är det formaterade numret RW-EXPENSE-0039, till exempel.</span><span class="sxs-lookup"><span data-stu-id="9f013-144">For example, for a legal entity that is named **RW**, if you change only the value of the legal entity segment, the formatted number is RW-EXPENSE-0039.</span></span> <span data-ttu-id="9f013-145">Du kan också ändra heltalsekvensformatet för andra juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="9f013-145">You can also change the whole number sequence format for other legal entities.</span></span> <span data-ttu-id="9f013-146">Du kan till exempel utesluta ett segment med ett omfång av juridiska personer om du vill skapa ett formaterat nummer, som Exp-0001.</span><span class="sxs-lookup"><span data-stu-id="9f013-146">For example, you can omit the legal entity scope segment to create a formatted number such as Exp-0001.</span></span>

### <a name="sales-order-numbers"></a><span data-ttu-id="9f013-147">Försäljningsordernummer</span><span class="sxs-lookup"><span data-stu-id="9f013-147">Sales order numbers</span></span>

<span data-ttu-id="9f013-148">I följande exempel ställts försäljningsordernummer in för företags-ID **CEU**.</span><span class="sxs-lookup"><span data-stu-id="9f013-148">In the following example, sales order numbers are set up for the company ID **CEU**.</span></span> 

- <span data-ttu-id="9f013-149">**Område:** Försäljning</span><span class="sxs-lookup"><span data-stu-id="9f013-149">**Area:** Sales</span></span> 
- <span data-ttu-id="9f013-150">**Referens:** Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="9f013-150">**Reference:** Sales order</span></span> 
- <span data-ttu-id="9f013-151">**Omfång:** Företag</span><span class="sxs-lookup"><span data-stu-id="9f013-151">**Scope:** Company</span></span> 
- <span data-ttu-id="9f013-152">**Företag:** CEU</span><span class="sxs-lookup"><span data-stu-id="9f013-152">**Company:** CEU</span></span>

| <span data-ttu-id="9f013-153">Segment</span><span class="sxs-lookup"><span data-stu-id="9f013-153">Segments</span></span>  | <span data-ttu-id="9f013-154">Segmenttyp</span><span class="sxs-lookup"><span data-stu-id="9f013-154">Segment type</span></span> | <span data-ttu-id="9f013-155">Värde</span><span class="sxs-lookup"><span data-stu-id="9f013-155">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="9f013-156">Segment 1</span><span class="sxs-lookup"><span data-stu-id="9f013-156">Segment 1</span></span> | <span data-ttu-id="9f013-157">Konstant</span><span class="sxs-lookup"><span data-stu-id="9f013-157">Constant</span></span>     | <span data-ttu-id="9f013-158">SO-</span><span class="sxs-lookup"><span data-stu-id="9f013-158">SO-</span></span>      |
| <span data-ttu-id="9f013-159">Segment 2</span><span class="sxs-lookup"><span data-stu-id="9f013-159">Segment 2</span></span> | <span data-ttu-id="9f013-160">Alfanumerisk</span><span class="sxs-lookup"><span data-stu-id="9f013-160">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="9f013-161">**Exempel på formaterat nummer**: SO-0029</span><span class="sxs-lookup"><span data-stu-id="9f013-161">**Example of formatted number**: SO-0029</span></span> 

<span data-ttu-id="9f013-162">Även om ett omfångssegment inte ingår i formatet ska numreringen börja om för varje företags-ID.</span><span class="sxs-lookup"><span data-stu-id="9f013-162">Even though a scope segment is not included in the format, numbering restarts for each company ID.</span></span> <span data-ttu-id="9f013-163">Om du använder samma format för alla företags-ID:n, används samma nummer i varje företag.</span><span class="sxs-lookup"><span data-stu-id="9f013-163">If you use the same format for all company IDs, the same numbers are used in each company.</span></span> <span data-ttu-id="9f013-164">Försäljningsordernumret SO-0029 används till exempel på varje företag.</span><span class="sxs-lookup"><span data-stu-id="9f013-164">For example, sales order number SO-0029 is used in each company.</span></span> <span data-ttu-id="9f013-165">Du kan också ändra heltalsekvensformatet för andra företags-ID:n.</span><span class="sxs-lookup"><span data-stu-id="9f013-165">You can also change the whole number sequence format for other company IDs.</span></span>

### <a name="purchase-requisition-numbers"></a><span data-ttu-id="9f013-166">Inköpsrekvisitionsnummer</span><span class="sxs-lookup"><span data-stu-id="9f013-166">Purchase requisition numbers</span></span>

<span data-ttu-id="9f013-167">I följande exempel ordnas inköpsrekvisitionsnummer på företagsnivå.</span><span class="sxs-lookup"><span data-stu-id="9f013-167">In the following example, purchase requisition numbers are organization-wide.</span></span> 

- <span data-ttu-id="9f013-168">**Område:** Inköp</span><span class="sxs-lookup"><span data-stu-id="9f013-168">**Area:** Purchase</span></span> 
- <span data-ttu-id="9f013-169">**Referens:** Inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="9f013-169">**Reference:** Purchase requisition</span></span> 
- <span data-ttu-id="9f013-170">**Omfång:** Delat</span><span class="sxs-lookup"><span data-stu-id="9f013-170">**Scope:** Shared</span></span>

| <span data-ttu-id="9f013-171">Segment</span><span class="sxs-lookup"><span data-stu-id="9f013-171">Segments</span></span>  | <span data-ttu-id="9f013-172">Segmenttyp</span><span class="sxs-lookup"><span data-stu-id="9f013-172">Segment type</span></span> | <span data-ttu-id="9f013-173">Värde</span><span class="sxs-lookup"><span data-stu-id="9f013-173">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="9f013-174">Segment 1</span><span class="sxs-lookup"><span data-stu-id="9f013-174">Segment 1</span></span> | <span data-ttu-id="9f013-175">Konstant</span><span class="sxs-lookup"><span data-stu-id="9f013-175">Constant</span></span>     | <span data-ttu-id="9f013-176">Req</span><span class="sxs-lookup"><span data-stu-id="9f013-176">Req</span></span>      |
| <span data-ttu-id="9f013-177">Segment 2</span><span class="sxs-lookup"><span data-stu-id="9f013-177">Segment 2</span></span> | <span data-ttu-id="9f013-178">Alfanumerisk</span><span class="sxs-lookup"><span data-stu-id="9f013-178">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="9f013-179">**Exempel på formaterat nummer**: Req0052</span><span class="sxs-lookup"><span data-stu-id="9f013-179">**Example of formatted number**: Req0052</span></span> 

<span data-ttu-id="9f013-180">Eftersom omfånget är **Shared** används nummerserieformatet i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f013-180">Because the scope is **Shared**, the number sequence format is used across the organization.</span></span> <span data-ttu-id="9f013-181">Du kan inte ställa in olika nummerserieformat för olika delar av organisationen.</span><span class="sxs-lookup"><span data-stu-id="9f013-181">You cannot set up different number sequence formats for different parts of the organization.</span></span> 

<a name="performance-considerations-for-number-sequences"></a><span data-ttu-id="9f013-182">Prestandaöverväganden för nummerserier</span><span class="sxs-lookup"><span data-stu-id="9f013-182">Performance considerations for number sequences</span></span>
-----------------------------------------------

<span data-ttu-id="9f013-183">Beakta följande information om hur konfigurationen av nummerserier kan påverka systemets prestanda innan du ställer in nummerserier.</span><span class="sxs-lookup"><span data-stu-id="9f013-183">Consider the following information about how the configuration of number sequences can affect system performance before you set up number sequences.</span></span>

### <a name="continuous-and-non-continuous-number-sequences"></a><span data-ttu-id="9f013-184">Kontinuerliga och icke-kontinuerliga nummerserier</span><span class="sxs-lookup"><span data-stu-id="9f013-184">Continuous and non-continuous number sequences</span></span>

<span data-ttu-id="9f013-185">Nummerserier kan vara kontinuerliga eller icke-kontinuerliga.</span><span class="sxs-lookup"><span data-stu-id="9f013-185">Number sequences can be continuous or non-continuous.</span></span> <span data-ttu-id="9f013-186">En kontinuerlig nummerserie hoppar inte över något nummer, men numren kan inte användas i följd.</span><span class="sxs-lookup"><span data-stu-id="9f013-186">A continuous number sequence does not skip any numbers, but numbers may not be used sequentially.</span></span> <span data-ttu-id="9f013-187">Nummer från en icke-kontinuerlig nummerserie används efter varandra, men nummerserien kan hoppa över nummer.</span><span class="sxs-lookup"><span data-stu-id="9f013-187">Numbers from a non-continuous number sequence are used sequentially, but the number sequence may skip numbers.</span></span> <span data-ttu-id="9f013-188">Om till exempel en användare annullerar en transaktion, genereras ett nummer men det används inte.</span><span class="sxs-lookup"><span data-stu-id="9f013-188">For example, if a user cancels a transaction, a number is generated, but not used.</span></span> <span data-ttu-id="9f013-189">I en kontinuerlig nummerserie återanvänds det numret senare.</span><span class="sxs-lookup"><span data-stu-id="9f013-189">In a continuous number sequence, that number is recycled later.</span></span> <span data-ttu-id="9f013-190">I en icke-kontinuerlig nummersekvens används inte numret.</span><span class="sxs-lookup"><span data-stu-id="9f013-190">In a non-continuous number sequence, the number is not used.</span></span> 

<span data-ttu-id="9f013-191">Kontinuerliga nummerserier krävs vanligtvis för externa dokument, till exempel inköpsorder, försäljningsorder och fakturor.</span><span class="sxs-lookup"><span data-stu-id="9f013-191">Continuous number sequences are typically required for external documents, such as purchase orders, sales orders, and invoices.</span></span> <span data-ttu-id="9f013-192">Kontinuerliga nummerserier kan dock påverka systemsvarstiderna negativt eftersom systemet måste begära ett nummer från databasen varje gång som ett nytt dokument eller en ny post skapas.</span><span class="sxs-lookup"><span data-stu-id="9f013-192">However, continuous number sequences can adversely affect system response times because the system must request a number from the database every time that a new document or record is created.</span></span> 

<span data-ttu-id="9f013-193">Om du använder en icke-kontinuerlig nummersekvens kan du aktivera **Förallokering** på snabbfliken **Prestanda** på sidan **Nummersekvenser**.</span><span class="sxs-lookup"><span data-stu-id="9f013-193">If you use a non-continuous number sequence, you can enable **Preallocation** on the **Performance** FastTab of the **Number sequences** page.</span></span> <span data-ttu-id="9f013-194">När du anger ett antal nummer för förallokering väljer systemet de siffrorna och lagrar dem i minnet.</span><span class="sxs-lookup"><span data-stu-id="9f013-194">When you specify a quantity of numbers to preallocate, the system selects those numbers and stores them in memory.</span></span> <span data-ttu-id="9f013-195">Nya nummer krävs från databasen enbart efter att den förallokerade kvantiteten har använts.</span><span class="sxs-lookup"><span data-stu-id="9f013-195">New numbers are requested from the database only after the preallocated quantity has been used.</span></span> 

<span data-ttu-id="9f013-196">Om det finns ett reglerat krav där du använder kontinuerliga nummerserier, rekommenderar vi att du använder icke-kontinuerliga nummerserier för bättre prestanda.</span><span class="sxs-lookup"><span data-stu-id="9f013-196">Unless there is a regulatory requirement that you use continuous number sequences, we recommend that you use non-continuous number sequences for better performance.</span></span>

### <a name="automatic-cleanup-of-number-sequences"></a><span data-ttu-id="9f013-197">Automatisk rensning av nummerserier</span><span class="sxs-lookup"><span data-stu-id="9f013-197">Automatic cleanup of number sequences</span></span>

<span data-ttu-id="9f013-198">I händelse av strömavbrott, programfel eller annat oväntat fel kan inte systemet återanvända nummer automatiskt för kontinuerliga nummerserier.</span><span class="sxs-lookup"><span data-stu-id="9f013-198">In case of a power failure, an application error, or other unexpected failure, the system cannot recycle numbers automatically for continuous number sequences.</span></span> <span data-ttu-id="9f013-199">Du kan köra rensningen manuellt eller automatiskt återställa de förlorade numren.</span><span class="sxs-lookup"><span data-stu-id="9f013-199">You can run the cleanup process manually or automatically to recover the lost numbers.</span></span> 

<span data-ttu-id="9f013-200">Tänk noggrant igenom serveranvändningen när du planerar rensningen.</span><span class="sxs-lookup"><span data-stu-id="9f013-200">Carefully consider server usage when you plan the cleanup process.</span></span> <span data-ttu-id="9f013-201">Vi rekommenderar att du utför rensningen som ett batchjobb under tider då arbetsbelastningen är låg.</span><span class="sxs-lookup"><span data-stu-id="9f013-201">We recommend that you perform the cleanup as a batch job during non-peak hours.</span></span>





