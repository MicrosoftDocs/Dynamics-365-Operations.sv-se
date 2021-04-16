---
title: Kundbokföringsprofiler
description: Bokföringsprofiler för kund styr bokföringen av kundtransaktionerna i redovisningen.kundpool
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b03d176791ee476ccddbf519471becafd086b0b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826381"
---
# <a name="customer-posting-profiles"></a><span data-ttu-id="7b4d5-103">Kundbokföringsprofiler</span><span class="sxs-lookup"><span data-stu-id="7b4d5-103">Customer posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b4d5-104">Bokföringsprofiler för kund styr bokföringen av kundtransaktionerna i redovisningen.kundpool</span><span class="sxs-lookup"><span data-stu-id="7b4d5-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="7b4d5-105">Kundbokföringsprofiler</span><span class="sxs-lookup"><span data-stu-id="7b4d5-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="7b4d5-106">Kundbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar för alla kunder, en grupp av kunder eller en enskild kund.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="7b4d5-107">Dessa inställningar kommer att användas när du skapar försäljningsorder, fritextfakturor, kontantbetalningar, kravbrev samt räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="7b4d5-108">För en del transaktioner kan du markera en bokföringsprofil som skiljer sig från och har företräde framför de bokföringsprofiler som har ställts in för transaktioner på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="7b4d5-109">Standardbokföringsprofilen definieras på snabbfliken Redovisning och moms på parametersidan Kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="7b4d5-110">Standardbokföringsprofilen inkluderas sedan automatiskt i rubriken för nya dokument som du kan ändra den till en annan bokföringsprofil, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="7b4d5-111">Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan Bokföringsdefinitioner för transaktioner.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="7b4d5-112">Bokföringsprofiler styr bokföringen av kundtransaktionerna i redovisningen istället för bokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="7b4d5-113">Skapa en bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-113">Creating a posting profile</span></span>
<span data-ttu-id="7b4d5-114">Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="7b4d5-115">Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="7b4d5-116">Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:</span><span class="sxs-lookup"><span data-stu-id="7b4d5-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="7b4d5-117">Fältvärde **Kontokod**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-117">**Account code** field value</span></span> | <span data-ttu-id="7b4d5-118">Fältvärde **Konto-/gruppnummer**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="7b4d5-119">Sökprioritet</span><span class="sxs-lookup"><span data-stu-id="7b4d5-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="7b4d5-120">**Register**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-120">**Table**</span></span>                    | <span data-ttu-id="7b4d5-121">Specifikt kundkonto</span><span class="sxs-lookup"><span data-stu-id="7b4d5-121">Specific customer account</span></span>                       | <span data-ttu-id="7b4d5-122">1</span><span class="sxs-lookup"><span data-stu-id="7b4d5-122">1</span></span>               |
| <span data-ttu-id="7b4d5-123">**Grupp**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-123">**Group**</span></span>                    | <span data-ttu-id="7b4d5-124">Kundgrupp som kunden är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="7b4d5-125">2</span><span class="sxs-lookup"><span data-stu-id="7b4d5-125">2</span></span>               |
| <span data-ttu-id="7b4d5-126">**Alla**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-126">**All**</span></span>                      | <span data-ttu-id="7b4d5-127">Tom</span><span class="sxs-lookup"><span data-stu-id="7b4d5-127">Blank</span></span>                                           | <span data-ttu-id="7b4d5-128">3</span><span class="sxs-lookup"><span data-stu-id="7b4d5-128">3</span></span>               |

<span data-ttu-id="7b4d5-129">Om du vill att alla kundtransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja Alla i fältet Kontokod.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="7b4d5-130">Ange följande värden om du vill ställa in din bokföringsprofil:</span><span class="sxs-lookup"><span data-stu-id="7b4d5-130">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7b4d5-131">Fält</span><span class="sxs-lookup"><span data-stu-id="7b4d5-131">Field</span></span></th>
<th><span data-ttu-id="7b4d5-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7b4d5-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7b4d5-133"><strong>Bokföringsprofil</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="7b4d5-134">Ange en kod för bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="7b4d5-135">Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för kundsaldon i den nationella valutan och ett annat för kundsaldon i en utländsk valuta.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="7b4d5-136">Du kan kalla en för Nationell och den andra för Utländsk.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b4d5-137"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="7b4d5-138">Ange en beskrivning av bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="7b4d5-139">Detta används endast för att bättre identifiera bokföringsprofilen när du visar den på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b4d5-140"><strong>Kontokod</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="7b4d5-141">Ange om bokföringsprofilen gäller för en enda kund, en grupp kunder eller alla kunder:</span><span class="sxs-lookup"><span data-stu-id="7b4d5-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="7b4d5-142"><strong>Tabell</strong> – Bokföringsprofilen gäller för en enskild kund.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="7b4d5-143">Välj kundkontot i fältet Konto-/gruppnummer.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="7b4d5-144"><strong>Grupp</strong> – Bokföringsprofilen gäller för en kundgrupp.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="7b4d5-145">Välj kundgruppen i fältet Konto-/gruppnummer.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="7b4d5-146"><strong>Alla</strong> – Bokföringsprofilen gäller för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="7b4d5-147">Lämna fältet Konto-/gruppnummer tomt.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b4d5-148"><strong>Konto-/gruppnummer</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="7b4d5-149">Om du har valt Tabell i fältet Kontokod anger du kontonumret för kunden som är associerad med bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="7b4d5-150">Om du väljer Grupp ska du välja kundgruppen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="7b4d5-151">Om du har valt Alla lämnar du det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b4d5-152"><strong>Samlingskonto</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="7b4d5-153">Välj det redovisningskonto som används som kundsamlingskonto för kunderna som är associerade med bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b4d5-154"><strong>Kvittningskonto</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="7b4d5-155">Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="7b4d5-156">Det här fältet visas bara om kassaflödesprognoser aktiveras.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b4d5-157"><strong>Förskottsbetalningar av moms</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="7b4d5-158">Välj momskontonumret för betalningar som mottas i förskott.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Kommentar" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="7b4d5-160"><strong>Obs!</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7b4d5-161">Använd parametersidan Kundreskontra för att ange bokföringsprofilen som används när en betalning markeras som förskottsbetalning.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b4d5-162"><strong>Skulder för diskonteringskonto</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="7b4d5-163">Välj huvudbokskontot för diskonterade skulder.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7b4d5-164"><strong>Kravbrevsserie</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="7b4d5-165">Välj identifieraren för kravbrevsserien som används för kunder som tilldelas bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7b4d5-166"><strong>Räntekod</strong></span><span class="sxs-lookup"><span data-stu-id="7b4d5-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="7b4d5-167">Välj räntekoden för beräkning av ränta för kunder som tilldelas bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="7b4d5-168">**Registerbegränsningar**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-168">**Table restrictions**</span></span>

<span data-ttu-id="7b4d5-169">Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="7b4d5-170">Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="7b4d5-171">Ange följande värden om du vill ställa in din bokföringsprofil:</span><span class="sxs-lookup"><span data-stu-id="7b4d5-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="7b4d5-172">Fält</span><span class="sxs-lookup"><span data-stu-id="7b4d5-172">Field</span></span>                 | <span data-ttu-id="7b4d5-173">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7b4d5-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="7b4d5-174">**Kvittning**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-174">**Settlement**</span></span>        | <span data-ttu-id="7b4d5-175">Markera den här växlingsknappen för automatisk kvittning av transaktioner som har denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="7b4d5-176">Om den här växlingsknappen avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan Kvitta öppna transaktioner eller sidan Ange kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="7b4d5-177">**Intresse**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-177">**Interest**</span></span>          | <span data-ttu-id="7b4d5-178">Markera den här växlingsknappen om ränta ska beräknas på utestående saldon för kundkonton som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="7b4d5-179">Om växlingsknappen är avmarkerad beräknas ingen ränta för dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="7b4d5-180">**Kravbrev**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-180">**Collection letter**</span></span> | <span data-ttu-id="7b4d5-181">Markera den här växlingsknappen om kravbrev ska skapas för kundkonton som använder den här profilen.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="7b4d5-182">Om växlingsknappen är avmarkerad skapas inga kravbrev för dessa kunder.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="7b4d5-183">**Stäng**</span><span class="sxs-lookup"><span data-stu-id="7b4d5-183">**Close**</span></span>             | <span data-ttu-id="7b4d5-184">Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="7b4d5-185">En transaktion betraktas som stängd när den har kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="7b4d5-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="7b4d5-186">Mer information finns i [Översikt över kundbetalning](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7b4d5-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]