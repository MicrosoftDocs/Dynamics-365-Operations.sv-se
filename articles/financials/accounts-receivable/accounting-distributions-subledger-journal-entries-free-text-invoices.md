---
title: "Redovisningsfördelningar och redovisningsjournalposter för fritextfakturor"
description: "Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas. Exempelvis hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d13fbd98597fc8138bfb4d549608d75f790e0e52
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a>Redovisningsfördelningar och redovisningsjournalposter för fritextfakturor

[!INCLUDE [banner](../includes/banner.md)]

Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas. Exempelvis hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar.

<a name="accounting-distributions"></a>Redovisningsfördelningar
------------------------

Du kan använda följande knappar på sidan Fritextfaktura om du vill visa, och möjligen ändra, redovisningsfördelningarna för varje belopp på fritextfakturan.

-   **Fördela belopp**—Visa och ändra redovisningsfördelningarna för en enskild rad och eventuella underordnade rader, till exempel moms eller avgifter. Du kan också visa och ändra redovisningsfördelningarna för den underordnade raden direkt från sidan Momstransaktioner eller sidan Transaktioner för avgifter.
    -   Ändra huvudbeloppen på fritextfakturan, till exempel avgifter eller valutaavrundningsbelopp.
    -   Ändra radbeloppen för en fritextfaktura
-   **Visa fördelningar** – Visa redovisningsfördelningarna för alla rader i dokumentet. Du kan inte ändra redovisningsfördelningarna från den här vyn.
    -   Visa huvud- och radbelopp.

## <a name="distributing-amounts"></a>Fördela belopp
När du anger en fritextfaktura kommer varje belopp fördelas på följande sätt.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ av penningbelopp</th>
<th>Var huvudkontot visas från</th>
<th>Prioritetsordning som bestämmer vilken ekonomisk standarddimension som visas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fritextfakturarad</td>
<td>Redovisningskontot på fritextfakturaraden.</td>
<td><ol>
<li>Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</li>
<li>Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</li>
</ol></td>
</tr>
<tr class="even">
<td>Fritextfakturarad för en kombination av Anläggningstillgångsnummer och värdemodell
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Obs! </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Huvudkontot på fritextfakturaraden kommer att vara kontot för avyttring av anläggningstillgångar.</td>
</tr>
</tbody>
</table>
</div></td>
<td>Redovisningskontot på fritextfakturaraden.</td>
<td><ol>
<li>Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Radrabatt på fritextfaktura</td>
<td>Fältet Huvudkonto för kundrabatter på sidan Kassarabatter.</td>
<td><ol>
<li>Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</li>
<li>Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</li>
</ol></td>
</tr>
<tr class="even">
<td>Momsbelopp på fritextfaktura</td>
<td>Fältet Momsskuld på sidan Redovisningsbokföringsgrupper.</td>
<td><ol>
<li>Använd ekonomiska dimensioner som definieras på fritextfakturaradbeloppet eller fördelningarna för avgiftsradbeloppet.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Avgiftsradbelopp på fritextfaktura</td>
<td>Fältet Kreditkonto på sidan Kod för avgifter.</td>
<td><ol>
<li>Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</li>
<li>Om huvudkontot inte är ett allokeringskonto ska du använda standardmallen för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner på fritextfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från redovisningskontot på sidan Kontoplan.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Fördela moms
Redovisningsfördelning för skatter går inte att skapa förrän skatter har beräknats. Om du vill beräkna moms måste du färdigställa en av följande uppgifter i formuläret Fritextfaktura:
-   Visa momsen.
-   Visa fakturasumman.
-   Visa kassaflödet.
-   Visa redovisningsfördelningar för hela fritextfakturan.
-   Visa redovisningsjournalen.

## <a name="subledger-journals-for-free-text-invoices"></a> Redovisningsjournaler för fritextfakturor
Innan du bokför en fritextfaktura kan du visa hela redovisningsposten för fakturan, som inkluderar debiteringar och krediteringar, för att kontrollera att fakturan bokförs till rätt konton. Denna vy av hela redovisningsposten kallas en redovisningsjournal. Om posten i reskontrajournalen är fel när du granskar den innan du journalför fritextfakturan kan du inte ändra posten i reskontrajournalen. I stället måste du ändra redovisningsfördelningarna eller bokföringsprofilen. Redovisningsfördelningarna används för att definiera ena sidan i redovisningposten, debet eller kredit. Den förskjutande kontoposten i reskontrajournalen skapas från bokföringsprofilerna, till exempel från kundkontot eller moms.




