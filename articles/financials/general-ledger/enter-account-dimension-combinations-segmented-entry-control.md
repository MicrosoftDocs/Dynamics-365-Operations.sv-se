---
title: Ange konto- och dimensionskombinationer (segmenterad postkontroll)
description: "Det här avsnittet innehåller en beskrivning av hur du anger konto och dimensionskombinationer eller redovisningskonton. Posterfarenheten kallas ofta för segmenterad postkontroll."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1535ef5c5eec1389272ce8fd2c2c183f532785b1
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a>Ange konto- och dimensionskombinationer (segmenterad postkontroll)

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av hur du anger konto och dimensionskombinationer eller redovisningskonton. Posterfarenheten kallas ofta för segmenterad postkontroll.

Användare anger konto- och dimensionskombinationer på olika sidor, till exempel sidor för allmänna journaler, budgetar och bokföring av defintions. De giltiga konto- och dimensionskombinationerna beror på kontostrukturerna som tilldelas redovisningen och de avancerade regler som är tilldelade kontostrukturerna. När användarna anger en kombination, kan de antingen skriva värdena manuellt eller använda en avancerad sökfunktion. När du anger det här fältet kan du börja skirve och det söker värdet och beskrivningen. Om du till exempel skriver 180, sökar programmet alla värden som börjar med den nummerkombinationen. Du kan skriva in Kontant och programmet söker alla värden som har en beskrivning som börjar med Kontant. Du kan också använda jokertecken, t ex \*Kontant eller \*180 vid sökning om värdet eller beskrivningen innehåller sökvillkoren. 

I följande tabell beskrivnings av kortkommandona som kan användas när sökningen stängs.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tangentbordsgenväg</th>
<th>Åtgärd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Alt+nedpil</td>
<td>Öppnar sökningen. Om du trycker på Alt+nedpil en gång till flyttas fokus till segmenten i den utfällbara menyn.</td>
</tr>
<tr class="even">
<td><ul>
<li>Retur och skift+retur</li>
<li>Kontoplansavgränsare</li>
<li>Högerpil och vänsterpil</li>
</ul></td>
<td>Flytta till nästa eller föregående segment.</td>
</tr>
<tr class="odd">
<td>Tabb</td>
<td>Flytta till nästa fält i rutnätet.</td>
</tr>
</tbody>
</table>

I följande tabell beskrivnings av kortkommandona som kan användas när sökningen öppnas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tangentbordsgenväg</th>
<th>Åtgärd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Esc</td>
<td>Stänger sökningen.</td>
</tr>
<tr class="even">
<td><ul>
<li>Uppil och nedpil</li>
<li>Page Up och Page Down</li>
<li>Home och End</li>
</ul></td>
<td>Flytta till nästa eller föregående värde i listan, till föregående eller nästa grupp av värden eller till det första eller sista elementet i sökningen.</td>
</tr>
<tr class="odd">
<td><ul>
<li>Kontoplansavgränsare</li>
<li>Högerpil och vänsterpil</li>
</ul></td>
<td>Flytta till nästa eller föregående segment.</td>
</tr>
<tr class="even">
<td>Flik</td>
<td>Flytta till nästa fält i rutnätet.</td>
</tr>
<tr class="odd">
<td>Alt+W</td>
<td>Växla mellan <strong>Visa alla</strong> och <strong>Visa giltigt</strong>.</td>
</tr>
</tbody>
</table>

 



