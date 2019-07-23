---
title: Bokföringsprofiler för leverantörer
description: Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.
author: abruer
manager: AnnBe
ms.date: 06/12/2019
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
ms.openlocfilehash: c3f62df7ec5627556561db950d54ff4347d2b4d6
ms.sourcegitcommit: ce84a1faeda6013ef6a90038d811a72f375b604e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/12/2019
ms.locfileid: "1625905"
---
# <a name="vendor-posting-profiles"></a><span data-ttu-id="766bf-103">Bokföringsprofiler för leverantörer</span><span class="sxs-lookup"><span data-stu-id="766bf-103">Vendor posting profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="766bf-104">Leverantörsbokföringsprofiler styr bokföringen av leverantörstransaktioner i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="766bf-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="766bf-105">Bokföringsprofiler för leverantörer</span><span class="sxs-lookup"><span data-stu-id="766bf-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="766bf-106">Leverantörsbokföringsprofiler gör det möjligt att tilldela redovisningskonton och dokumentinställningar till alla leverantörer, en grupp leverantörer eller en enskild leverantörer.</span><span class="sxs-lookup"><span data-stu-id="766bf-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors, or a single vendor.</span></span> <span data-ttu-id="766bf-107">De här inställningarna kan användas när inköpsorder leverantörsfakturor och kontantbetalningar skapas.</span><span class="sxs-lookup"><span data-stu-id="766bf-107">These settings will be used when you create purchase orders, vendor invoices, and cash payments.</span></span> <span data-ttu-id="766bf-108">För en del transaktioner kan du markera en bokföringsprofil som skiljer sig från och har företräde framför de bokföringsprofiler som har ställts in för transaktioner på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="766bf-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions on this page.</span></span> <span data-ttu-id="766bf-109">Standardbokföringsprofilen definieras på snabbfliken **Redovisning och moms** på parametersidan **Leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="766bf-109">The default posting profile is defined on the **Ledger and Sales Tax** FastTab on the **Accounts payable parameters** page.</span></span> <span data-ttu-id="766bf-110">Standardbokföringsprofilen inkluderas sedan automatiskt i rubriken för nya dokument som du kan ändra den till en annan bokföringsprofil, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="766bf-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile, if needed.</span></span>

<span data-ttu-id="766bf-111">Du kan även koppla bokföringsdefinitioner med transaktionsbokföringstyper på sidan **Bokföringsdefinitioner för transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="766bf-111">You can also associate posting definitions with transaction posting types on the **Transaction posting definitions** page.</span></span> <span data-ttu-id="766bf-112">Bokföringsprofiler styr bokföringen av leverantörstransaktionerna i redovisningen istället för bokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="766bf-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="766bf-113">Skapa en bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="766bf-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="766bf-114">**Inställningar**</span><span class="sxs-lookup"><span data-stu-id="766bf-114">**Setup**</span></span>

<span data-ttu-id="766bf-115">Ange vilka redovisningskonton som används vid bokföring av transaktioner som använder den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="766bf-116">Välj en kontokod och, om möjligt, en kontogrupp eller ett gruppnummer för den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="766bf-117">Under bokföringsprocessen hittar programmet den lämpligaste bokföringsprofilen för varje transaktion genom att söka efter den/det mest detaljerade kontokoden, kontonumret eller grupp- och nummerkombinationen enligt följande prioritetsordning:</span><span class="sxs-lookup"><span data-stu-id="766bf-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority.</span></span>

| <span data-ttu-id="766bf-118">Fältvärde **Kontokod**</span><span class="sxs-lookup"><span data-stu-id="766bf-118">**Account code** field value</span></span> | <span data-ttu-id="766bf-119">Fältvärde **Konto-/gruppnummer**</span><span class="sxs-lookup"><span data-stu-id="766bf-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="766bf-120">Sökprioritet</span><span class="sxs-lookup"><span data-stu-id="766bf-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="766bf-121">**Register**</span><span class="sxs-lookup"><span data-stu-id="766bf-121">**Table**</span></span>                    | <span data-ttu-id="766bf-122">Specifikt leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="766bf-122">Specific vendor account</span></span>                     | <span data-ttu-id="766bf-123">1</span><span class="sxs-lookup"><span data-stu-id="766bf-123">1</span></span>               |
| <span data-ttu-id="766bf-124">**Grupp**</span><span class="sxs-lookup"><span data-stu-id="766bf-124">**Group**</span></span>                    | <span data-ttu-id="766bf-125">Leverantörsgrupp som är kopplad till leverantören</span><span class="sxs-lookup"><span data-stu-id="766bf-125">Vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="766bf-126">2</span><span class="sxs-lookup"><span data-stu-id="766bf-126">2</span></span>               |
| <span data-ttu-id="766bf-127">**Allt**</span><span class="sxs-lookup"><span data-stu-id="766bf-127">**All**</span></span>                      | <span data-ttu-id="766bf-128">Tom</span><span class="sxs-lookup"><span data-stu-id="766bf-128">Blank</span></span>                                       | <span data-ttu-id="766bf-129">3</span><span class="sxs-lookup"><span data-stu-id="766bf-129">3</span></span>               |

<span data-ttu-id="766bf-130">Om du vill att alla leverantörstransaktioner ska ha samma bokföringsprofil skapar du bara en bokföringsprofil genom att välja **Alla** i fältet **Kontokod**.</span><span class="sxs-lookup"><span data-stu-id="766bf-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with **All** in the **Account code** field.</span></span> <span data-ttu-id="766bf-131">Ange följande värden om du vill ställa in din bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="766bf-131">Specify the following values to set up your posting profile.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="766bf-132">Fält</span><span class="sxs-lookup"><span data-stu-id="766bf-132">Field</span></span></th>
<th><span data-ttu-id="766bf-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="766bf-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="766bf-134"><strong>Bokföringsprofil</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="766bf-135">Ange en kod för bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="766bf-136">Till exempel kan du skapa två bokföringsprofiler för att skapa ett konto för leverantörssaldon i den nationella valutan och ett annat för leverantörssaldon i en utländsk valuta.</span><span class="sxs-lookup"><span data-stu-id="766bf-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="766bf-137">Du kan kalla en för Nationell och den andra för Utländsk.</span><span class="sxs-lookup"><span data-stu-id="766bf-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="766bf-138"><strong>Beskrivning</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="766bf-139">Ange en beskrivning av bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="766bf-140"><strong>Kontokod</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="766bf-141">Ange om bokföringsprofilen gäller för en specifik leverantör, en grupp leverantörer eller alla leverantörer:</span><span class="sxs-lookup"><span data-stu-id="766bf-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="766bf-142"><strong>Tabell</strong> – Bokföringsprofilen gäller för en enskild leverantör.</span><span class="sxs-lookup"><span data-stu-id="766bf-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="766bf-143">Välj leverantörskontot i fältet <strong>Konto-/gruppnummer</strong>.</span><span class="sxs-lookup"><span data-stu-id="766bf-143">Select the vendor account in the <strong>Account/Group number</strong> field.</span></span></li>
<li><span data-ttu-id="766bf-144"><strong>Grupp</strong> – Bokföringsprofilen gäller för en leverantörsgrupp.</span><span class="sxs-lookup"><span data-stu-id="766bf-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="766bf-145">Välj leverantörsgruppen i fältet <strong>Konto-/gruppnummer</strong>.</span><span class="sxs-lookup"><span data-stu-id="766bf-145">Select the vendor group in the <strong>Account/Group number</strong> field.</span></span></li>
<li><span data-ttu-id="766bf-146"><strong>Alla</strong> – Bokföringsprofilen gäller för alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="766bf-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="766bf-147">Lämna fältet <strong>Konto-/gruppnummer</strong> tomt.</span><span class="sxs-lookup"><span data-stu-id="766bf-147">Leave the <strong>Account/Group number</strong> field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="766bf-148"><strong>Konto-/gruppnummer</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="766bf-149">Om du har valt <strong>Tabell</strong> i fältet <strong>Kontokod</strong> anger du kontonumret för leverantören som är associerad med bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-149">If <strong>Table</strong> is selected in the <strong>Account code</strong> field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="766bf-150">Om <strong>Grupp</strong> är markerat markerar du en leverantörsgrupp.</span><span class="sxs-lookup"><span data-stu-id="766bf-150">If <strong>Group</strong> is selected, select a vendor group.</span></span> <span data-ttu-id="766bf-151">Om du har valt <strong>Alla</strong> lämnar du det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="766bf-151">If <strong>All</strong> is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="766bf-152"><strong>Samlingskonto</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="766bf-153">Välj det redovisningskonto som används som samlingskonto för den/de leverantör(er) bokföringsprofilen gäller.</span><span class="sxs-lookup"><span data-stu-id="766bf-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span> <span data-ttu-id="766bf-154">Parametern <strong>Tillåt inte manuell inmatning</strong> för det här huvudkontot kommer att markeras.</span><span class="sxs-lookup"><span data-stu-id="766bf-154">The <strong>Do not allow manual entry</strong> parameter for this main account will be marked.</span></span> <span data-ttu-id="766bf-155">Om du senare tar bort det här kontot från bokföringsprofilen validerar inställningen <strong>Tillåt inte manuell inmatning</strong> på sidan <strong>Huvudkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="766bf-155">If you subsequently remove this account from the posting profile, validate the <strong>Do not allow manual entry</strong> setting on the <strong>Main accounts</strong> page.</span></span> 
<p><span data-ttu-id="766bf-156"><strong>OBS!</strong> Om alternativet <strong>Använd bokföringsdefinitioner</strong> valts på sidan <strong>Allmänna huvudboksparametrar</strong>, används transaktionsbokföringsdefinitionen för leverantörsfakturor i stället för samlingskontot.</span><span class="sxs-lookup"><span data-stu-id="766bf-156"><strong>Note:</strong> If the <strong>Use posting definitions</strong> option is selected on the <strong>General ledger parameters</strong> page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="766bf-157"><strong>Kvittningskonto</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="766bf-158">Välj det likviditetskonto i redovisningen som används för kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="766bf-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="766bf-159">Detta fält är endast tillgängligt när kassaflödesprognoser aktiveras.</span><span class="sxs-lookup"><span data-stu-id="766bf-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="766bf-160"><strong>Förskottsbetalningar av moms</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="766bf-161">Välj kontonumret för momsbetalningar som mottas i förskott.</span><span class="sxs-lookup"><span data-stu-id="766bf-161">Select the account for sales tax payments that are received in advance.</span></span>
<p><span data-ttu-id="766bf-162"><strong>OBS!</strong> Bokföringsprofilen som används när betalningen markeras som en förskottsbetalning väljs i profilen <strong>Bokföringsprofil</strong> med fältet <strong>förskottsbetalningsjournal</strong> i området <strong>Redovisning och moms</strong> på sidan <strong>Parametrar för leverantörsreskontra</strong>.</span><span class="sxs-lookup"><span data-stu-id="766bf-162"><strong>Note:</strong> The posting profile that is used when the payment is marked as a prepayment is selected in the <strong>Posting</strong> profile with <strong>Prepayment journal voucher</strong> field in the <strong>Ledger and sales tax</strong> area on the <strong>Accounts payable parameters</strong> page.</span></span></p>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="766bf-163"><strong>Införsel</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-163"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="766bf-164">Markera redovisningskontot där information om ej godkända fakturor registreras.</span><span class="sxs-lookup"><span data-stu-id="766bf-164">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="766bf-165">Informationen registreras i Fakturaregisterjournal.</span><span class="sxs-lookup"><span data-stu-id="766bf-165">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="766bf-166">Till exempel anger en användare mycket grundläggande information om leverantörsfakturor när de tas emot i fakturaregistret.</span><span class="sxs-lookup"><span data-stu-id="766bf-166">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="766bf-167">När fakturaregistret bokförs, bokförs transaktionerna på det konto som har angetts här och i fältet <strong>Motkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="766bf-167">When the invoice register is posted, the transactions are posted to the account that is entered here and in the <strong>Offset account</strong> field.</span></span> <span data-ttu-id="766bf-168">När fakturorna godkänns överförs skulden från kontot Införselkonto till leverantörens samlingskonto.</span><span class="sxs-lookup"><span data-stu-id="766bf-168">When the invoices are approved, the debt is transferred from the arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="766bf-169"><strong>Motkonto</strong></span><span class="sxs-lookup"><span data-stu-id="766bf-169"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="766bf-170">Markera det redovisningskontonummer som används för motbokning av ej godkända fakturor som uppdateras med fakturaregistret.</span><span class="sxs-lookup"><span data-stu-id="766bf-170">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="766bf-171">Motkontot fungerar som motkonto för transaktioner som bokförts till införselkonton.</span><span class="sxs-lookup"><span data-stu-id="766bf-171">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="766bf-172">Därför innehåller kontot leverantörsinköp som ännu inte har godkänts.</span><span class="sxs-lookup"><span data-stu-id="766bf-172">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a><span data-ttu-id="766bf-173">**Registerbegränsningar**</span><span class="sxs-lookup"><span data-stu-id="766bf-173">**Table restrictions**</span></span>

<span data-ttu-id="766bf-174">Ange om transaktioner kvittas automatiskt, ränta beräknas och kravbrev levereras för transaktioner som har den valda bokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="766bf-174">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="766bf-175">Det går även att välja det konto som används när transaktioner med den valda bokföringsprofilen stängs.</span><span class="sxs-lookup"><span data-stu-id="766bf-175">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="766bf-176">Ange följande värden om du vill ställa in din bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="766bf-176">Specify the following values to set up your posting profile</span></span>

| <span data-ttu-id="766bf-177">Fält</span><span class="sxs-lookup"><span data-stu-id="766bf-177">Field</span></span>          | <span data-ttu-id="766bf-178">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="766bf-178">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="766bf-179">**Kvittning**</span><span class="sxs-lookup"><span data-stu-id="766bf-179">**Settlement**</span></span> | <span data-ttu-id="766bf-180">Välj det här alternativet för att aktivera automatisk kvittning av transaktioner som har denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="766bf-180">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="766bf-181">Om det här alternativet avmarkeras måste du kvitta transaktioner manuellt genom att använda sidan **Kvitta öppna transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="766bf-181">If this option is cleared, you must manually settle transactions by using the **Settle open transactions** page.</span></span> |
| <span data-ttu-id="766bf-182">**Avbryt**</span><span class="sxs-lookup"><span data-stu-id="766bf-182">**Cancel**</span></span>     | <span data-ttu-id="766bf-183">Välj det här alternativet för möjlighet att avbryta transaktioner som har denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="766bf-183">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="766bf-184">**Stäng**</span><span class="sxs-lookup"><span data-stu-id="766bf-184">**Close**</span></span>      | <span data-ttu-id="766bf-185">Markera en bokföringsprofiler att ändra till när transaktionerna med denna bokföringsprofil stängs.</span><span class="sxs-lookup"><span data-stu-id="766bf-185">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="766bf-186">En transaktion betraktas som stängd när den har kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="766bf-186">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |
