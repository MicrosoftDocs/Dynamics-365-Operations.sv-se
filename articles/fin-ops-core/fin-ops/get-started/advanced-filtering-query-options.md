---
title: Avancerad filtrerings- och frågesyntax
description: Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn matchar i den avancerade filtrerings-/sorteringsdialogen.
author: jasongre
manager: AnnBe
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: sericks
ms.custom: 3811
ms.assetid: b4969b30-2fe1-4a3c-bbea-725dc37c8b60
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b867099b131594a64cad102e50ead7c355594f2b
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694553"
---
# <a name="advanced-filtering-and-query-syntax"></a>Avancerad filtrerings- och frågesyntax

[!include [banner](../includes/banner.md)]

Detta avsnitt beskriver filterings- och frågealternativ som är tillgängliga, när du använder operatorn **matchar** i den avancerade filtrerings-/sorteringsdialogen.

## <a name="advanced-query-syntax"></a>Avancerad frågesyntax

<table>
<thead>
<tr>
<th>Syntax</th>
<th>Teckenbeskrivning</th>
<th>beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr>
<td><em>värde</em></td>
<td>Motsvarar värdet som angavs</td>
<td>Skriv in värdet som du vill hitta.</td>
<td><strong>Smith</strong> hittar &quot;Smith&quot;.</td>
</tr>
<tr>
<td>!<em>-värde</em> (utropstecken)</td>
<td>Motsvarar inte värdet som angavs</td>
<td>Skriv in ett utropstecken och sedan värdet som du vill utesluta.</td>
<td><strong>!Smith</strong> hittar alla värden utom &quot;Smith&quot;.</td>
</tr>
<tr>
<td><em>värdet Från</em>.<em>värdet Till</em> (dubbla punkter)</td>
<td>Mellan de två värdena som angavs åtskilda med dubbla punkter</td>
<td>Skriv in värdet Från, sedan två punkter och sist värdet Till.</td>
<td><strong>1..10</strong> hittar alla värden från 1 till 10. I ett strängfält hittar dock <strong>A..C</strong> alla värden som börjar med &quot;A&quot; och &quot;B&quot; och värden som exakt motsvarar &quot;C&quot;. Till exempel kommer denna fråga inte att hitta &quot;Ca&quot;. Om du vill hitta alla värden från &quot;A<em>&quot; till &quot;C</em>&quot;, skriv då <strong>A..D</strong>.</td>
</tr>
<tr>
<td>..<em>värde</em> (dubbla punkter)</td>
<td>Mindre än eller lika med värdet som angavs.</td>
<td>Skriv in de två punkterna och sedan värdet.</td>
<td><strong>..1000</strong> hittar alla tal som är mindre än eller lika med 1 000, t.ex. &quot;100&quot;, &quot;999,95&quot; och &quot;1 000&quot;.</td>
</tr>
<tr>
<td><em>värde</em>.. (dubbla punkter)</td>
<td>Större än eller lika med värdet som angavs.</td>
<td>Skriv in värdet och sen två punkter.</td>
<td><strong>1000..</strong> hittar alla tal som är större än eller lika med 1 000, t.ex. &quot;1 000&quot;, &quot;1 000,01&quot; och &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&gt;<em>värde</em> (tecknet för "större än")</td>
<td>Större än värdet som angavs.</td>
<td>Ange tecknet för "större än" (<strong>&gt;</strong>) och därefter värdet.</td>
<td><strong>&gt;1 000</strong> hittar alla tal som är större än 1 000, t.ex.s &quot;1000,01&quot;, &quot;20 000&quot; och &quot;1 000 000&quot;.</td>
</tr>
<tr>
<td>&lt;<em>värde</em> (tecknet för "mindre än")</td>
<td>Mindere än värdet som angavs.</td>
<td>Skriv in tecknet för "mindre än" (<strong>&lt;</strong>) och därefter värdet.</td>
<td><strong>&lt;1 000</strong> hittar alla tal, som är mindre än 1 000, t.ex. &quot;999,99&quot;, &quot;1&quot; och &quot;-200&quot;.</td>
</tr>
<tr>
<td><em>värde</em>* (asterisk)</td>
<td>Startar från värdet som angavs</td>
<td>Skriv in startvärdet och sedan en asterisk (<strong>*</strong>).</td>
<td><strong>S*</strong> hittar alla strängar som börjar med &quot;S&quot;, t.ex. &quot;Stockholm&quot;, &quot;Sydney&quot; eller &quot;San Francisco&quot;.</td>
</tr>
<tr>
<td>*<em>värde</em> (asterisk)</td>
<td>Slutar med värdet som angavs.</td>
<td>Skriv in en asterisk och sedan slutvärdet.</td>
<td><strong>*öst</strong> hittar alla strängar som slutar med &quot;öst&quot;, t.ex. &quot;Nordöst&quot; och &quot;Sydöst&quot;.</td>
</tr>
<tr>
<td>*<em>värde</em>* (asterisk)</td>
<td>Innehåller värdet som angavs.</td>
<td>Skriv in en asterisk, sedan ett värde och slutligen en till asterisk.</td>
<td><strong>*st*</strong> hittar alla strängar som innehåller &quot;st&quot;, t.ex. &quot;Nordöst&quot; och &quot;Sydöst&quot;.</td>
</tr>
<tr>
<td>? (frågetecken)</td>
<td>Har ett eller flera okända tecken</td>
<td>Skriv in ett frågetecken vid det okända tecknets placering i värdet.</td>
<td><strong>Sm?th</strong> hittar &quot;Smith&quot; och &quot;Smyth&quot;.</td>
</tr>
<tr>
<td><em>värde</em>,<em>värde</em> (kommatecken)</td>
<td>Matchar värdena som angavs åtskilda med kommatecken.</td>
<td>Skriv in alla kriterier och skilj dem åt med kommatecken.</td>
<td><strong>A, D, F, G</strong> hittar exakt &quot;A&quot;, &quot;D&quot;, &quot;F&quot; och &quot;G&quot;. <strong>10, 20, 30, 100</strong> hittar exakt &quot;10, 20, 30, 100&quot;.</td>
</tr>
<tr>
<td>"" (två dubbla citationstecken)</td>
<td>Matcha ett tomt värde</td>
<td>Skriv två dubbla citationstecken i följd för att filtrera efter tomma värden i det fältet.</td>
<td>Två raka dubbla citationstecken (<strong>""</strong>) hittar rader utan värde för den aktuella kolumnen.</td>
</tr>
<tr>
<td>(<span class="code">Finance and Operations fråga</span>) (Finance and Operations fråga mellan parenteser)</td>
<td>Matchar en definierad fråga</td>
<td>Skriv en fråga som ett SQL-uttryck inom parenteser med hjälp av Finance and Operations frågespråk.</td>
  <td><strong><span class="code">((AccountNum SOM "US *") && (DirPartyTable.Name SOM "Cont*"))</span></strong><br><br> 
       Exempel på syntax för ett filtervillkor för ett fält från rotdatakällan och ett fält från en annan datakälla (för sidan Alla kunder)</td>
</tr>
<tr>
<td>V</td>
<td>Dagens datum</td>
<td>Skriv in <strong>T</strong>.</td>
<td><strong>T</strong> matchar dagens datum.</td>
</tr>
<tr>
<td>(methodName(parameters)) (<strong>SysQueryRangeUtil</strong> metod mellan parentes)</td>
<td>Matcha värdet eller intervallet av värden som anges av parametrar för metoden <strong>SysQueryRangeUtil</strong></td>
<td>Skriv en <strong>SysQueryRangeUtil</strong>-metod med parametrar som specificerar värdet eller intervallet av värden.</td>
<td>
<ol>
<li>Klicka på <strong>Kundreskontra</strong> &gt; <strong>Fakturor</strong> &gt; <strong>Öppna kundfakturor</strong>.</li>
<li>Tryck på Ctrl+Shift+F3 om du vill öppna sidan <strong>Förfrågan</strong>.</li>
<li>På fliken <strong>Intervall</strong> klickar du på <strong>Anslutning</strong>.</li>
<li>I fältet <strong>Tabell</strong> väljer du <strong>Öppna kundtransaktioner</strong>.</li>
<li>I fältet <strong>Fält</strong> väljer du <strong>Förfallodatum</strong>.</li>
<li>I fältet <strong>Kriterium</strong> anger du <strong>2(yearRange(-2,0))</strong>.</li>
<li>Klicka på <strong>OK</strong>. Listsidan uppdateras och visar de fakturor som matchar kriteriet som du angav. För det här exemplet registreras specifika fakturor som förfallit under de föregående två åren.</li>
</ol>
Se tabellen i nästa avsnittet för ytterligare information om <strong>SysQueryRangeUtil</strong>-datummetoder och flera exempel.</td>
</tr>
</tbody>
</table>

## <a name="advanced-date-queries-that-use-sysqueryrangeutil-methods"></a>Avancerade datumfrågor som använder SysQueryRangeUtil-metoder

<table>
<thead>
<tr>
<th>Metod</th>
<th>Beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr>
<td>Dag (_relativeDays=0)</td>
<td>Sök efter en datumrelativ till sessionsdatumet. Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</td>
<td>
<ul>
<li><strong>Imorgon</strong> – Ange <strong>(Dag(1))</strong>.</li>
<li><strong>I dag</strong> – Ange <strong>(Dag(0))</strong>.</li>
<li><strong>Igår</strong> – Ange <strong>(Dag(-1))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>DayRange (_relativeDaysFrom=0, _relativeDaysTo=0)</td>
<td>Hitta ett intervall med datumrelativ till sessionsdatumet. Positiva värden anger framtida datum, och negativa värdeen anger tidigare datum.</td>
<td>
<ul>
<li><strong>De 30 senaste dagarna</strong> – Ange <strong>(DayRange(-30,0))</strong>.</li>
<li><strong>Föregående 30 dagar och framtida 30 dagar</strong> – Ange <strong>(DayRange(-30,30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanDate (_relativeDays=0) GreaterThanUtcDate (_relativeDays=0)</td>
<td>Sök efter alla data efter det angivna relativa datumet.</td>
<td>
<ul>
<li><strong>Mer än 30 dagar från och med nu</strong> – Ange <strong>(GreaterThanDate(30))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>GreaterThanUtcNow ()</td>
<td>Sök efter alla datum/tidposter efter den aktuella tiden.</td>
<td>
<ul>
<li><strong>Alla framtida datum/tider</strong> – Ange <strong>(GreaterThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanDate (_relativeDays=0) LessThanUtcDate (_relativeDays=0)</td>
<td>Sök efter alla data före det angivna relativa datumet.</td>
<td>
<ul>
<li><strong>Mindre än sju dagar från och med nu</strong> – Ange <strong>(LessThanDate(7))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>LessThanUtcNow ()</td>
<td>Sök efter alla datum/tidposter före den aktuella tiden.</td>
<td>
<ul>
<li><strong>Alla förfallna datum/tider</strong> – Ange <strong>(LessThanUtcNow())</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>MonthRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Hitta ett datumintervall baserat på månader i förhållande till den aktuella månaden.</td>
<td>
<ul>
<li><strong>Tidigare två månader</strong> – Ange <strong>(MonthRange(-2,0))</strong>.</li>
<li><strong>Nästa tre månader</strong> – Ange <strong>(MonthRange(0,3))</strong>.</li>
</ul>
</td>
</tr>
<tr>
<td>YearRange (_relativeFrom=0, _relativeTo=0)</td>
<td>Hitta ett datumintervall baserat på år i förhållande till det aktuella året.</td>
<td>
<ul>
<li><strong>Nästa år</strong> – Ange <strong>(YearRange(0, 1))</strong>.</li>
<li><strong>Föregående år</strong> – Ange <strong>(YearRange(-1,0))</strong>.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]