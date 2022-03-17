---
title: Redovisningsfördelningar och journalposter för leverantörsfakturor
description: Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas, till exempel hur utgiften, momsen eller avgifterna ska redovisas på en leverantörsfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358191"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Redovisningsfördelningar och journalposter för leverantörsfakturor

[!include [banner](../includes/banner.md)]

Redovisningsfördelningar används för att definiera hur ett belopp ska redovisas, till exempel hur utgiften, momsen eller avgifterna ska redovisas på en leverantörsfaktura. Varje belopp som måste redovisas när leverantörsfakturan journalförs ska ha en eller flera redovisningsfördelningar. 

## <a name="accounting-distributions"></a>Redovisningsfördelningar 

Du kan använda följande knappar i formuläret Leverantörsfaktura om du vill visa, och möjligen ändra, redovisningsfördelningarna för varje belopp på leverantörsfakturan.
-   **Fördela belopp** – Visa och ändra redovisningsfördelningar för en enskild rad och eventuella underordnade rader, till exempel moms eller avgifter. Du kan också visa och ändra redovisningsfördelningarna för den underordnade raden direkt från sidan  **Momstransaktioner** eller sidan **Avgiftstransaktioner**.
    -   Ändra huvudbeloppen på leverantörsfakturan, till exempel avgifter eller valutaavrundningsbelopp.
    -   Ändra radbelopp på leverantörsfaktura
-   **Visa fördelningar** – Visa redovisningsfördelningarna för alla rader i dokumentet. Du kan inte ändra redovisningsfördelningarna från den här vyn.
    -   Visa huvud- och radbelopp.

Om leverantörsfakturan refererar till en inköpsorder, kan du dela upp och ändra redovisningsfördelningarna för rader som innehåller en artikel som inte finns i lager. Om leverantörsfakturaraden inte refererar till en inköpsorderrad kan du också ta bort en redovisningsfördelning. Du kan inte dela eller ta bort rader för tillägg, moms och radrabatter. Du kan ändra redovisningskonto, men du kan inte ändra beloppen eller procentsatserna.
> [!NOTE]                                                                                                                                 
> Om den överordnade raden innehåller en artikel som inte lagerförs, och redovisningsfördelningarna är delade, kommer den underordnade raden delas automatiskt för att matcha de ekonomiska dimensionerna för den överordnade raden. Redovisningsfördelningarna för den underordnade raden kan inte ytterligare delas eller tas bort, men beroende på inställningarna för den underordnade raden kan det gå att ändra huvudbokskontot för redovisningsfördelningarna för den underordnade raden.

## <a name="distributing-amounts"></a>Fördela belopp
När du registrerar en leverantörsfaktura, kommer varje belopp fördelas på följande sätt.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ av leverantörsfakturarad</th>
<th>Prioritetsordning som avgör var huvudkontot visas från</th>
<th>Prioritetsordning som bestämmer vilken ekonomisk standarddimension som visas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Produkt i lager</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden.</li>
<li>Fältet <strong>Huvudkonto</strong> när inköpomkostnad för produkt har valts på sidan <strong>bokföring</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd standardvärdena för ekonomiska dimensionen på leverantörsfakturan.</li>
</ol></td>
</tr>
<tr class="even">
<td>En anskaffningskategori eller en produkt som inte finns i lager</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om leverantörsfakturaraden refererar till en inköpsorderrad.</li>
<li>Fältet <strong>Huvudkonto</strong> när inköpomkostnad för utgift har valts på sidan <strong>bokföring</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</li>
<li>Använd standardvärdena för ekonomiska dimensionen på leverantörsfakturan.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Anläggningstillgång</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om leverantörsfakturaraden refererar till en inköpsorderrad.</li>
<li>Om <strong>Anskaffning</strong> har valts i fältet <strong>Transaktionstyp</strong> på sidan <strong>Leverantörsfaktura</strong> väljs fältet <strong>Huvudkonto</strong> när <strong>Anskaffning</strong> har markerats på sidan <strong>Bokföringsprofiler för anläggningstillgångar</strong>.</li>
<li>Om <strong>Anskaffningsjustering</strong> har valts i fältet <strong>Transaktionstyp</strong> väljs fältet <strong>Huvudkonto</strong> när <strong>Anskaffningsjustering</strong> har markerats på sidan <strong>Bokföringsprofiler för anläggningstillgångar</strong>.</li>
</ol></td>
<td><ol>
<li>Använd redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Projektet har definierats på leverantörsfakturaraden</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Om <strong>Saldo</strong> väljs i fältet <strong>Bokföringskostnader – artikel</strong> på sidan <strong>Projektgrupp</strong> i fältet <strong>Huvudkonto</strong> när <strong>Kostnad</strong> har markerats på sidan <strong>Inställning av redovisningsbokföring</strong>.</li>
<li>Om <strong>Vinst och förlust</strong> väljs i fältet <strong>Bokföringskostnader – artikel</strong> på sidan <strong>Projektgrupp</strong> i fältet <strong>Huvudkonto</strong> när <strong>Kostnad – artikel</strong> har markerats på sidan <strong>Inställning av redovisningsbokföring</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Radrabatt</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Fältet <strong>Huvudkonto</strong>, när <strong>Rabatt</strong> är markerat på sidan <strong>Bokföring</strong>.</li>
<li>Om ett huvudkonto för en rabatt inte har definierats på bokföringsprofilen, redovisningsfördelningen för det slutliga priset på inköpsorderraden.</li>
</ol></td>
<td><ol>
<li>Använd redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen på leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Avgift på inköp som anges på fliken <strong>Pris och rabatt</strong> för inköpsorderraden</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Redovisningsfördelningen av det slutliga priset på inköpsorderraden.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Radavgift</td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Om <strong>Redovisningskonto</strong> har valts i fältet <strong>Debettyp</strong> på sidan <strong>Avgiftskod</strong> väljs fältet <strong>Debetkonto</strong> på sidan <strong>Avgiftskod</strong>.</li>
<li>Om <strong>Artikel</strong> har valts i fältet <strong>Debettyp</strong> på sidan <strong>Avgiftskod</strong> är redovisningsfördelningen för det slutliga priset på inköpsorderraden.</li>
<li>Om <strong>Kund/leverantör</strong> har valts i fätlet <strong>Debettyp</strong> på sidan <strong>Avgiftskod</strong> väljs fältet <strong>Kreditkonto</strong> på sidan <strong>Avgiftskod</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Moms, med följande villkor:
<ul>
<li>Alternativet <strong>Tillämpa amerikanska skatteregler</strong> har valts på sidan <strong>Allmänna redovisningsparametrar</strong>.</li>
</ul></td>
<td><ol>
<li>Redovisningsfördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Redovisningsfördelningen av det slutliga priset eller tillägget.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Moms, med följande villkor:
<ul>
<li>Alternativet <strong>Tillämpa amerikanska skatteregler</strong> har avmarkerats på sidan <strong>Allmänna redovisningparametrar</strong>.</li>
<li>Fältet <strong>Importavgift</strong> för momsgruppen är avmarkerat i <strong>momsgruppsidan</strong>.</li>
</ul></td>
<td><ol>
<li>Om momsbeloppet är återbetalningsbart, fältet <strong>Momsfordran</strong> på sidan <strong>Redovisningsbokföringsgrupper</strong>.</li>
<li>Om momsbeloppet inte är återvinningsbart, det slutliga priset eller redovisningsfördelningen för avgiften.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från det slutliga priset eller från redovisningsfördelningarna för avgiften på leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Moms, med följande villkor:
<ul>
<li>Alternativet Tillämpa amerikanska skatteregler har avmarkerats på sidan <strong>Allmänna redovisningparametrar</strong>.</li>
<li>Fältet <strong>Importavgift</strong> för momsgruppen är markerat på sidan <strong>momsgrupper</strong>.</li>
</ul></td>
<td><ol>
<li>Om momsbeloppet är återbetalningsbart, fältet <strong>Momsfordran</strong> på sidan <strong>Redovisningsbokföringsgrupper</strong>.</li>
<li>Om momsbeloppet inte är återbetalningsbart, fältet <strong>Importavgift</strong>, utgift på sidan <strong>Redovisningsbokföringsgrupper</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från det slutliga priset eller från redovisningsfördelningarna för avgiften på leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Huvudtillägg</td>
<td><ol>
<li>Om <strong>Redovisningskonto</strong> har valts i fältet <strong>Debettyp</strong> på sidan <strong>Avgiftskod</strong> väljs fältet <strong>Debetkonto</strong> på sidan <strong>Avgiftskod</strong>.</li>
<li>Om <strong>Kund/leverantör</strong> har valts i fätlet <strong>Debettyp</strong> på sidan <strong>Avgiftskod</strong> väljs fältet <strong>Kreditkonto</strong> på sidan <strong>Avgiftskod</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Om huvudkontot är ett allokeringskonto ska du använda standardvärdet från allokeringskontodefinitionen.</li>
<li>Använd värdena i standardmallen för ekonomiska dimensionen från leverantörsfakturarubriken.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Rubrikrabatt</td>
<td><ol>
<li>Fältet <strong>Huvudkonto</strong> för <strong>bokföringstypen Leverantörsfakturarabatt</strong> på sidan <strong>Konton för automatiska transaktioner</strong>.</li>
</ol></td>
<td><ol>
<li>Använd kontofördelningen för inköpsorderraden, om fakturaraden refererar till en inköpsorderrad.</li>
<li>Använd värdena för de ekonomiska dimensionerna från redovisningsfördelningarna för det slutliga priset för leverantörsorderraden.</li>
<li>Använd värdena för den ekonomiska dimensionen från leverantörsfakturaraden.</li>
<li>Använd de förvalda värdena för ekonomiska dimensioner från huvudkontot på sidan <strong>Kontoplan</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Fördela moms

Redovisningsfördelning för skatter går inte att skapa förrän skatter har beräknats. Om du vill beräkna moms måste du färdigställa en av följande uppgifter på sidan **Leverantörsfaktura**.
-   Visa fakturasumman.
-   Visa momsen.
-   Visa redovisningsjournalen.
-   Visa redovisningsfördelningar för den slutförda leverantörsfakturan.
-   Spärra leverantörsfakturan.
-   Bokför leverantörsfakturan.

## <a name="subledger-journals-for-vendor-invoices"></a>Redovisningsjournaler för leverantörsfakturor
Innan du bokför en leverantörsfaktura kan du visa hela redovisningsposten för fakturan, som inkluderar debiteringar och krediteringar, för att kontrollera att fakturan bokförs till rätt konton. Denna vy av hela redovisningsposten kallas en redovisningsjournal. 

Om posten i reskontrajournalen är fel när du granskar den innan du journalför leverantörsfakturan, kan du inte ändra posten i reskontrajournalen. I stället måste du ändra redovisningsfördelningarna eller bokföringsprofilen. Redovisningsfördelningarna används för att definiera ena sidan i redovisningposten, debet eller kredit. Den förskjutande kontoposten i reskontrajournalen skapas med hjälp av bokföringsprofilerna, till exempel från leverantörskontot eller moms.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
