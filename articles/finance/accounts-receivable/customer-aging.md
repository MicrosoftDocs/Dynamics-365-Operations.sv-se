---
title: Åldersfördelningsrapport för kunder
description: Rapporten åldersfördelning visar de saldon som är förfallna från kunder, sorterade efter datumintervall eller åldersfördelningsperiod.
author: JodiChristiansen
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7c1e3b724c95aa91192c77d5f3b8be4f93f0357f5f2f940c198bc8da47933fa0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769093"
---
# <a name="customer-aging-report"></a>Åldersfördelningsrapport för kunder 

Rapporten **åldersfördelning** visar de saldon som är förfallna från kunder, sorterade efter datumintervall eller åldersfördelningsperiod.

När du genererar den här rapporten visas följande standardparametrar. Du kan använda de här parametrarna om du vill filtrera vilka data som ska visas i rapporten. Mer information finns i [Ställ in samlingar](set-up-collections.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Fält</p></th>
<th><p>beskrivning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Faktureringsklassificering</strong></p></td>
<td><p>Välj en eller flera faktureringsklassificeringar som ska inkluderas i rapporten.</p>
<div class="alert">

**Obs**! Den här kontrollen är bara tillgänglig om konfigurationsnyckeln <STRONG>Offentlig sektor</STRONG> har valts.</P>


</div></td>
</tr>
<tr class="even">
<td><p><strong>Inkludera transaktioner utan faktureringsklassificering</strong></p></td>
<td><p>Om den här kryss rutan är markerad kommer alla transaktioner som inte har någon tilldelad faktureringsklassificering att visas i rapporten.</p>
<div class="alert">

**Obs**! Den här kontrollen är bara tillgänglig om konfigurationsnyckeln <STRONG>Offentlig sektor</STRONG> har valts.</P>

</div></td>
</tr>
<tr class="odd">
<td><p><strong>Åldersfördelning på</strong></p></td>
<td><p>Ange det datum som används för den aktuella åldersgruppen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saldo per den</strong></p></td>
<td><p>Ange för vilket datum du vill visa kundsaldon. Detta kallas även för ett sista datum för transaktioner.</p></td>
</tr>
<tr class="even">
<td><p><strong>Startdatum</strong></p></td>
<td><p>Ange ett datum som finns inom det första periodintervallet eller åldersfördelningsperiod som ska ingå i rapporten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Villkor</strong></p></td>
<td><p>Välj den typ av datum som rapporten ska baseras på.</p>
<ul>
<li><p><strong>Transaktionsdatum</strong> – Bokföringsdatum för de valda transaktionerna. Det kan till exempel vara ett fakturadatum som ligger till grund för beräkningen av förfallodatumet.</p></li>
<li><p><strong>Förfallodatum</strong> – Transaktionernas förfallodatum enligt betalningsvillkoren.</p></li>
<li><p><strong>Dokumentdatum</strong> – Användardefinierat dokumentdatum som ligger till grund för beräkningen av förfallodatumet.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Definition för åldersfördelningsperiod</strong></p></td>
<td><p>Välj en åldersfördelningsperiod Fältet <strong>Intervall</strong> används inte om du väljer en definition av åldersfördelningsperiod.</p>
<p>Det går inte att använda definitioner av åldersperiod med fler än sex åldersfördelningsperioder i den utskrivna rapporten.</p>
<div class="alert">

**Obs!** Du kan ställa in åldersperioder på sidan <STRONG>Definitioner av åldersperioder</STRONG>.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Skriv ut beskrivning av åldersfördelningsperiod</strong></p></td>
<td><p>Välj <strong>Ja</strong> om du vill ta med beskrivningar av åldersperioder högst upp i varje åldersperiodkolumn i rapporten. Välj <strong>Nej</strong> om du vill skriva ut rapporten utan kolumnrubriker.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intervall</strong></p></td>
<td><p>Definiera perioden som ska användas genom att ange antalet dags- eller månadsenheter i varje period. Om du till exempel vill visa åldersfördelningsinformation per vecka anget du 7 i det här fältet och väljer <strong>Dag</strong> i fältet <strong>Dag/månad</strong>.</p>
<div class="alert">

**Obs!** Informationen som du anger i det här fältet används bara om du inte väljer någon definition av åldersfördelningsperiod. I annat fall definieras utskriftsriktningen för definitionen av åldersfördelningsperioder.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Dag/mån</strong></p></td>
<td><p>Välj enheten, antingen <strong>Dag</strong> eller <strong>Månad</strong>, som används för att definiera perioden i fältet <strong>Intervall</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utskriftsriktning</strong></p></td>
<td><p>Välj om du vill beräkna saldon och skriva ut åldersfördelningsrapporten för tidigare eller framtida perioder. Datumen utvärderas i förhållande till det datum som har valts i fältet <strong>Saldo som på</strong>. Välj <strong>Bakåt</strong> för att visa information för tidigare perioder. Välj <strong>Framåt</strong> för att visa information för framtida perioder.</p>
<div class="alert">
  
<STRONG>Obs!</STRONG> Informationen som du anger i det här fältet används bara om du inte väljer någon definition av åldersfördelningsperiod.</P>


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Information</strong></p></td>
<td><p>Markera för att ange transaktioner som ingår i de saldon som visas i rapporten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inkludera belopp i transaktionsvaluta</strong></p></td>
<td><p>Välj om du vill inkludera belopp i transaktionsvalutan utöver belopp i redovisningsvalutan. Om den här kryssrutan inte markeras visas beloppen i rapporten endast i redovisningsvalutan.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Negativt saldo</strong></p></td>
<td><p>Välj om du vill inkludera kundkonton med negativa saldon.</p></td>
</tr>
<tr class="even">
<td><p><strong>Exkludera nollsaldokonton</strong></p></td>
<td><p>Välj om du vill utesluta kundkonton med nollsaldo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Betalningspositionering</strong></p></td>
<td><p>Välj om du vill visa betalningar som inte har kvittats. Dessa visas i rapportens första kolumn.</p></td>
</tr>
</tbody>
</table>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]