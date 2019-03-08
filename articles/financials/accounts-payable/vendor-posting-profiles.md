---
title: Bokföringsprofiler för leverantörer
description: Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae019ebec2788fc499b0f2ef27a7eb2832ceaa9d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "346535"
---
# <a name="vendor-posting-profiles"></a><span data-ttu-id="23686-103">Bokföringsprofiler för leverantörer</span><span class="sxs-lookup"><span data-stu-id="23686-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23686-104">Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="23686-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="23686-105">Bokföringsprofiler för leverantörer</span><span class="sxs-lookup"><span data-stu-id="23686-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="23686-106">Leverantörsbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar till alla leverantörer, en grupp leverantörer eller en enskild leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23686-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="23686-107">De här inställningarna kan användas när inköpsorder leverantörsfakturor och kontantbetalningar skapas.</span><span class="sxs-lookup"><span data-stu-id="23686-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="23686-108">För en del transaktioner kan du markera en bokföringsprofil som skiljer sig från och har företräde framför de bokföringsprofiler som har ställts in för transaktioner på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="23686-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="23686-109">Standardbokföringsprofilen definieras på snabbfliken Redovisning och moms på parametersidan Leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="23686-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="23686-110">Standardbokföringsprofilen inkluderas sedan automatiskt i rubriken för nya dokument som du kan ändra den till en annan bokföringsprofil, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="23686-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="23686-111">Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan Bokföringsdefinitioner för transaktioner.</span><span class="sxs-lookup"><span data-stu-id="23686-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="23686-112">Bokföringsprofiler styr bokföringen av leverantörstransaktionerna i redovisningen istället för bokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="23686-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="23686-113">Skapa en bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="23686-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="23686-114">**Inställningar**</span><span class="sxs-lookup"><span data-stu-id="23686-114">**Setup**</span></span>

<span data-ttu-id="23686-115">Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="23686-116">Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="23686-117">Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:</span><span class="sxs-lookup"><span data-stu-id="23686-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="23686-118">Fältvärde **Kontokod**</span><span class="sxs-lookup"><span data-stu-id="23686-118">**Account code** field value</span></span> | <span data-ttu-id="23686-119">Fältvärde **Konto-/gruppnummer**</span><span class="sxs-lookup"><span data-stu-id="23686-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="23686-120">Sökprioritet</span><span class="sxs-lookup"><span data-stu-id="23686-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="23686-121">**Register**</span><span class="sxs-lookup"><span data-stu-id="23686-121">**Table**</span></span>                    | <span data-ttu-id="23686-122">Specifikt leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="23686-122">Specific vendor account</span></span>                     | <span data-ttu-id="23686-123">1</span><span class="sxs-lookup"><span data-stu-id="23686-123">1</span></span>               |
| <span data-ttu-id="23686-124">**Grupp**</span><span class="sxs-lookup"><span data-stu-id="23686-124">**Group**</span></span>                    | <span data-ttu-id="23686-125">leverantörsgrupp som är kopplad till leverantören</span><span class="sxs-lookup"><span data-stu-id="23686-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="23686-126">2</span><span class="sxs-lookup"><span data-stu-id="23686-126">2</span></span>               |
| <span data-ttu-id="23686-127">**Alla**</span><span class="sxs-lookup"><span data-stu-id="23686-127">**All**</span></span>                      | <span data-ttu-id="23686-128">Tom</span><span class="sxs-lookup"><span data-stu-id="23686-128">Blank</span></span>                                       | <span data-ttu-id="23686-129">3</span><span class="sxs-lookup"><span data-stu-id="23686-129">3</span></span>               |

<span data-ttu-id="23686-130">Om du vill att alla leverantörstransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja Alla i fältet Kontokod.</span><span class="sxs-lookup"><span data-stu-id="23686-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="23686-131">Ange följande värden om du vill ställa in din bokföringsprofil:</span><span class="sxs-lookup"><span data-stu-id="23686-131">Specify the following values to set up your posting profile:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="23686-132">Fält</span><span class="sxs-lookup"><span data-stu-id="23686-132">Field</span></span></th>
<th><span data-ttu-id="23686-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="23686-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="23686-134"><strong>Bokföringsprofil</strong></span><span class="sxs-lookup"><span data-stu-id="23686-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="23686-135">Ange en kod för bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="23686-136">Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för leverantörssaldon i den nationella valutan och ett annat för leverantörssaldon i en utländsk valuta.</span><span class="sxs-lookup"><span data-stu-id="23686-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="23686-137">Du kan kalla en för Nationell och den andra för Utländsk.</span><span class="sxs-lookup"><span data-stu-id="23686-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="23686-138"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="23686-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="23686-139">Ange en beskrivning av bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="23686-140"><strong>Kontokod</strong></span><span class="sxs-lookup"><span data-stu-id="23686-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="23686-141">Ange om bokföringsprofilen gäller för en specifik leverantör, en grupp leverantörer eller alla leverantörer:</span><span class="sxs-lookup"><span data-stu-id="23686-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="23686-142"><strong>Tabell</strong> – Bokföringsprofilen gäller för en enskild leverantör.</span><span class="sxs-lookup"><span data-stu-id="23686-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="23686-143">Välj leverantörskontot i fältet Konto-/gruppnummer.</span><span class="sxs-lookup"><span data-stu-id="23686-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="23686-144"><strong>Grupp</strong> – Bokföringsprofilen gäller för en leverantörsgrupp.</span><span class="sxs-lookup"><span data-stu-id="23686-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="23686-145">Välj leverantörsgruppen i fältet Konto-/gruppnummer.</span><span class="sxs-lookup"><span data-stu-id="23686-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="23686-146"><strong>Alla</strong> – Bokföringsprofilen gäller för alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="23686-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="23686-147">Lämna fältet Konto-/gruppnummer tomt.</span><span class="sxs-lookup"><span data-stu-id="23686-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="23686-148"><strong>Konto-/gruppnummer</strong></span><span class="sxs-lookup"><span data-stu-id="23686-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="23686-149">Om du har valt Tabell i fältet Kontokod anger du kontonumret för leverantören som är associerad med bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="23686-150">Om Grupp är markerat markerar du en leverantörsgrupp.</span><span class="sxs-lookup"><span data-stu-id="23686-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="23686-151">Om du har valt Alla lämnar du det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="23686-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="23686-152"><strong>Samlingskonto</strong></span><span class="sxs-lookup"><span data-stu-id="23686-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="23686-153">Välj det redovisningskonto som används som samlingskonto för den/de leverantör(er) bokföringsprofilen gäller.</span><span class="sxs-lookup"><span data-stu-id="23686-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Kommentar" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="23686-155"><strong>Obs!</strong></span><span class="sxs-lookup"><span data-stu-id="23686-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="23686-156">Om växlingsknappen Använd bokföringsdefinitioner valts på sidan Allmänna huvudboksparametrar, används transaktionsbokföringsdefinitionen för leverantörsfakturor i stället för samlingskontot.</span><span class="sxs-lookup"><span data-stu-id="23686-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="23686-157"><strong>Kvittningskonto</strong></span><span class="sxs-lookup"><span data-stu-id="23686-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="23686-158">Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="23686-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="23686-159">Detta fält är endast tillgängligt när kassaflödesprognoser aktiveras.</span><span class="sxs-lookup"><span data-stu-id="23686-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="23686-160"><strong>Förskottsbetalningar av moms</strong></span><span class="sxs-lookup"><span data-stu-id="23686-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="23686-161">Välj kontonumret för momsbetalningar som mottas i förskott.</span><span class="sxs-lookup"><span data-stu-id="23686-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Kommentar" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="23686-163"><strong>Obs!</strong></span><span class="sxs-lookup"><span data-stu-id="23686-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="23686-164">Bokföringsprofilen som används när betalningen markeras som en förskottsbetalning markeras i fältet Bokföringsprofil vid verifikation för förskottsbetalningsjournal i området Redovisning och moms på sidan Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="23686-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="23686-165"><strong>Införsel</strong></span><span class="sxs-lookup"><span data-stu-id="23686-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="23686-166">Markera redovisningskontot där information om ej godkända fakturor registreras.</span><span class="sxs-lookup"><span data-stu-id="23686-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="23686-167">Informationen registreras i Fakturaregisterjournal.</span><span class="sxs-lookup"><span data-stu-id="23686-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="23686-168">Till exempel anger en användare mycket grundläggande information om leverantörsfakturor när de tas emot i fakturaregistret.</span><span class="sxs-lookup"><span data-stu-id="23686-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="23686-169">När fakturaregistret bokförs, bokförs transaktionerna på det konto som har angetts här och i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="23686-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="23686-170">När fakturorna godkänns överförs skulden från kontot Införselkonto till leverantörens samlingskonto.</span><span class="sxs-lookup"><span data-stu-id="23686-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="23686-171"><strong>Motkonto</strong></span><span class="sxs-lookup"><span data-stu-id="23686-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="23686-172">Markera det redovisningskontonummer som används för motbokning av ej godkända fakturor som uppdateras med fakturaregistret.</span><span class="sxs-lookup"><span data-stu-id="23686-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="23686-173">Motkontot fungerar som motkonto för transaktioner som bokförts till införselkonton.</span><span class="sxs-lookup"><span data-stu-id="23686-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="23686-174">Därför innehåller kontot leverantörsinköp som ännu inte har godkänts.</span><span class="sxs-lookup"><span data-stu-id="23686-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="23686-175">**Registerbegränsningar**</span><span class="sxs-lookup"><span data-stu-id="23686-175">**Table restrictions**</span></span>

<span data-ttu-id="23686-176">Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="23686-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="23686-177">Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.</span><span class="sxs-lookup"><span data-stu-id="23686-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="23686-178">Ange följande värden om du vill ställa in din bokföringsprofil:</span><span class="sxs-lookup"><span data-stu-id="23686-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="23686-179">Fält</span><span class="sxs-lookup"><span data-stu-id="23686-179">Field</span></span>          | <span data-ttu-id="23686-180">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="23686-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="23686-181">**Kvittning**</span><span class="sxs-lookup"><span data-stu-id="23686-181">**Settlement**</span></span> | <span data-ttu-id="23686-182">Välj det här alternativet för att aktivera automatisk kvittning av transaktioner som har denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="23686-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="23686-183">Om det här alternativet avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan Kvitta öppna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="23686-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="23686-184">**Avbryt**</span><span class="sxs-lookup"><span data-stu-id="23686-184">**Cancel**</span></span>     | <span data-ttu-id="23686-185">Välj det här alternativet för möjlighet att avbryta transaktioner som har denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="23686-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="23686-186">**Stäng**</span><span class="sxs-lookup"><span data-stu-id="23686-186">**Close**</span></span>      | <span data-ttu-id="23686-187">Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs.</span><span class="sxs-lookup"><span data-stu-id="23686-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="23686-188">En transaktion betraktas som stängd när den har kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="23686-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |





