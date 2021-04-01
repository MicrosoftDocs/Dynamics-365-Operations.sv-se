---
title: Åldersfördelningsrapport för kunder
description: Rapporten åldersfördelning visar de saldon som är förfallna från kunder, sorterade efter datumintervall eller åldersfördelningsperiod.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 384e44ef07771a174aaed4f8fb893e75b0206da7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236996"
---
# <a name="customer-aging-report"></a><span data-ttu-id="5e019-103">Åldersfördelningsrapport för kunder</span><span class="sxs-lookup"><span data-stu-id="5e019-103">Customer aging report</span></span> 

<span data-ttu-id="5e019-104">Rapporten **åldersfördelning** visar de saldon som är förfallna från kunder, sorterade efter datumintervall eller åldersfördelningsperiod.</span><span class="sxs-lookup"><span data-stu-id="5e019-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="5e019-105">När du genererar den här rapporten visas följande standardparametrar.</span><span class="sxs-lookup"><span data-stu-id="5e019-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="5e019-106">Du kan använda de här parametrarna om du vill filtrera vilka data som ska visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="5e019-107">Mer information finns i [Ställ in samlingar](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="5e019-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5e019-108">Fält</span><span class="sxs-lookup"><span data-stu-id="5e019-108">Field</span></span></p></th>
<th><p><span data-ttu-id="5e019-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="5e019-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e019-110"><strong>Faktureringsklassificering</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-111">Välj en eller flera faktureringsklassificeringar som ska inkluderas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="5e019-112">**Obs**! Den här kontrollen är bara tillgänglig om konfigurationsnyckeln <STRONG>Offentlig sektor</STRONG> har valts.</span><span class="sxs-lookup"><span data-stu-id="5e019-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-113"><strong>Inkludera transaktioner utan faktureringsklassificering</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-114">Om den här kryss rutan är markerad kommer alla transaktioner som inte har någon tilldelad faktureringsklassificering att visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="5e019-115">**Obs**! Den här kontrollen är bara tillgänglig om konfigurationsnyckeln <STRONG>Offentlig sektor</STRONG> har valts.</span><span class="sxs-lookup"><span data-stu-id="5e019-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-116"><strong>Åldersfördelning på</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-117">Ange det datum som används för den aktuella åldersgruppen.</span><span class="sxs-lookup"><span data-stu-id="5e019-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-118"><strong>Saldo per den</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-119">Ange för vilket datum du vill visa kundsaldon.</span><span class="sxs-lookup"><span data-stu-id="5e019-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="5e019-120">Detta kallas även för ett sista datum för transaktioner.</span><span class="sxs-lookup"><span data-stu-id="5e019-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-121"><strong>Startdatum</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-122">Ange ett datum som finns inom det första periodintervallet eller åldersfördelningsperiod som ska ingå i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-123"><strong>Villkor</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-124">Välj den typ av datum som rapporten ska baseras på.</span><span class="sxs-lookup"><span data-stu-id="5e019-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="5e019-125"><strong>Transaktionsdatum</strong> – Bokföringsdatum för de valda transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="5e019-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="5e019-126">Det kan till exempel vara ett fakturadatum som ligger till grund för beräkningen av förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="5e019-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="5e019-127"><strong>Förfallodatum</strong> – Transaktionernas förfallodatum enligt betalningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="5e019-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="5e019-128"><strong>Dokumentdatum</strong> – Användardefinierat dokumentdatum som ligger till grund för beräkningen av förfallodatumet.</span><span class="sxs-lookup"><span data-stu-id="5e019-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-129"><strong>Definition för åldersfördelningsperiod</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-130">Välj en åldersfördelningsperiod</span><span class="sxs-lookup"><span data-stu-id="5e019-130">Select an aging period definition.</span></span> <span data-ttu-id="5e019-131">Fältet <strong>Intervall</strong> används inte om du väljer en definition av åldersfördelningsperiod.</span><span class="sxs-lookup"><span data-stu-id="5e019-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="5e019-132">Det går inte att använda definitioner av åldersperiod med fler än sex åldersfördelningsperioder i den utskrivna rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="5e019-133">**Obs!** Du kan ställa in åldersperioder på sidan <STRONG>Definitioner av åldersperioder</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5e019-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-134"><strong>Skriv ut beskrivning av åldersfördelningsperiod</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-135">Välj <strong>Ja</strong> om du vill ta med beskrivningar av åldersperioder högst upp i varje åldersperiodkolumn i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="5e019-136">Välj <strong>Nej</strong> om du vill skriva ut rapporten utan kolumnrubriker.</span><span class="sxs-lookup"><span data-stu-id="5e019-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-137"><strong>Intervall</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-138">Definiera perioden som ska användas genom att ange antalet dags- eller månadsenheter i varje period.</span><span class="sxs-lookup"><span data-stu-id="5e019-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="5e019-139">Om du till exempel vill visa åldersfördelningsinformation per vecka anget du 7 i det här fältet och väljer <strong>Dag</strong> i fältet <strong>Dag/månad</strong>.</span><span class="sxs-lookup"><span data-stu-id="5e019-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="5e019-140">**Obs!** Informationen som du anger i det här fältet används bara om du inte väljer någon definition av åldersfördelningsperiod.</span><span class="sxs-lookup"><span data-stu-id="5e019-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="5e019-141">I annat fall definieras utskriftsriktningen för definitionen av åldersfördelningsperioder.</span><span class="sxs-lookup"><span data-stu-id="5e019-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-142"><strong>Dag/mån</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-143">Välj enheten, antingen <strong>Dag</strong> eller <strong>Månad</strong>, som används för att definiera perioden i fältet <strong>Intervall</strong>.</span><span class="sxs-lookup"><span data-stu-id="5e019-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-144"><strong>Utskriftsriktning</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-145">Välj om du vill beräkna saldon och skriva ut åldersfördelningsrapporten för tidigare eller framtida perioder.</span><span class="sxs-lookup"><span data-stu-id="5e019-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="5e019-146">Datumen utvärderas i förhållande till det datum som har valts i fältet <strong>Saldo som på</strong>.</span><span class="sxs-lookup"><span data-stu-id="5e019-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="5e019-147">Välj <strong>Bakåt</strong> för att visa information för tidigare perioder.</span><span class="sxs-lookup"><span data-stu-id="5e019-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="5e019-148">Välj <strong>Framåt</strong> för att visa information för framtida perioder.</span><span class="sxs-lookup"><span data-stu-id="5e019-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="5e019-149">
  
<STRONG>Obs!</STRONG> Informationen som du anger i det här fältet används bara om du inte väljer någon definition av åldersfördelningsperiod.</span><span class="sxs-lookup"><span data-stu-id="5e019-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-150"><strong>Information</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-151">Markera för att ange transaktioner som ingår i de saldon som visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5e019-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-152"><strong>Inkludera belopp i transaktionsvaluta</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-153">Välj om du vill inkludera belopp i transaktionsvalutan utöver belopp i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="5e019-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="5e019-154">Om den här kryssrutan inte markeras visas beloppen i rapporten endast i redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="5e019-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-155"><strong>Negativt saldo</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-156">Välj om du vill inkludera kundkonton med negativa saldon.</span><span class="sxs-lookup"><span data-stu-id="5e019-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e019-157"><strong>Exkludera nollsaldokonton</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-158">Välj om du vill utesluta kundkonton med nollsaldo.</span><span class="sxs-lookup"><span data-stu-id="5e019-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e019-159"><strong>Betalningspositionering</strong></span><span class="sxs-lookup"><span data-stu-id="5e019-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="5e019-160">Välj om du vill visa betalningar som inte har kvittats.</span><span class="sxs-lookup"><span data-stu-id="5e019-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="5e019-161">Dessa visas i rapportens första kolumn.</span><span class="sxs-lookup"><span data-stu-id="5e019-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]