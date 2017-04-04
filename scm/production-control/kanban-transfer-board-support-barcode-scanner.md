---
title: "Kanban-Överföringstavla stöd för skannrar streckkod"
description: "Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f393efaf011de103fc172af625816eef5915c642
ms.lasthandoff: 03/31/2017


---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a>Kanban-Överföringstavla stöd för skannrar streckkod

Kanban-överföringstavlan stöder skannerindata från en widgetstreckkodsskanner för att välja, starta, slutföra och tömma ett kanban-jobb.

<a name="registration-modes"></a>Registreringslägen
------------------

På snabbfliken **Skannerregistrering** kan du välja det registreringsläge som styr åtgärden när du skannar ett kanban-kortnummer eller skriver in numret manuellt numret i fältet för kanban-kortnumret.
| Ange registreringsläge | Beskrivning                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| Starta                 | Registrera ett kanban-överföringsjobb som pågående.                                                 |
| Slutförd              | Registrera ett kanban-överföringsjobb som slutfört.                                                   |
| Tom                 | Registrera den materialhanteringsenhet som refereras av kanban-kortet som tomt.              |
| Välj                | Registrera ett kanban-kortnummer och välj automatiskt det jobb som refereras i kanban-listan |

 
<a name="registration-mode-select"></a>Registreringsläge Välj
------------------------

När du använder en streckkodsläsare för att välja ett jobb för kanban-skiva ändras läget. I det här läget gäller följande villkor:

-   Endast skannade kanban-jobb visas.
-   Information om det utvalda jobbet visas på snabbfliken **Detaljer**.
-   Snabbfliken **Meddelanden** visas bara för det valda jobbet.
-   Du kan ändra status för jobbet genom att använda funktionerna som är tillgängliga på Åtgärdsfönster. Kanban-överföringstavla fortsätter att endast visa ett enskilt jobb under denna tid.
-   Du kan uppdatera information i listan över jobb manuellt genom att klicka på **uppdatera** (SKIFT + F5) i åtgärdsfönstret. När du har uppdaterat informationen visas de fullständiga resultaten för jobbfiltret igen.

## <a name="job-status-and-possible-actions"></a>Jobbstatus och möjliga åtgärder
Status för valda jobb och status för alla fixerade jobb för händelsekanban avgör om du kan ytterligare bearbeta jobbet. Följande tabell visar information om dessa status och uppgifter:
-   Status som är tillgängliga för jobb, eller för materialhanteringsenheterna som refereras av jobben.
-   Varje uppgift som du kan utföra för jobbet.

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Jobbtyp</th>
<th>Jobbstatus eller materialhanteringsenhetstatus</th>
<th>Uppdatera plocklista</th>
<th>Starta</th>
<th>Uppdatera registrering</th>
<th>Slutförd</th>
<th>Tom</th>
<th>Skapa händelse-kanban</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Överför</td>
<td><ul>
<li>Inte planerad</li>
<li>Inga fixerade jobb eller fixerade jobb är slutförda</li>
</ul></td>
<td>Ja</td>
<td>Ja</td>
<td>Ja</td>
<td>Ja</td>
<td>Nej</td>
<td>Ja</td>
</tr>
<tr class="even">
<td>Överför</td>
<td><ul>
<li>Inte planerad</li>
<li>Det fixerade jobbet är inte avslutat</li>
</ul></td>
<td>Ja</td>
<td>Nej</td>
<td>Ja</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="odd">
<td>Överför</td>
<td>Pågår</td>
<td>Ja</td>
<td>Nej</td>
<td>Ja</td>
<td>Ja</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="even">
<td>Överför</td>
<td>Slutförd</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Ja</td>
<td>Nej</td>
</tr>
<tr class="odd">
<td>Överföring eller process</td>
<td>Tom</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="even">
<td>Överföring eller process</td>
<td>Ett kanban-kort hittades inte</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="odd">
<td>Överföring eller process</td>
<td>Ett kanban-kort hittades, men det har tilldelats en kanban</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="even">
<td>Bearbeta</td>
<td><ul>
<li>Inte planerad</li>
<li>Förberedd</li>
<li>Pågår</li>
</ul></td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
<tr class="odd">
<td>Bearbeta</td>
<td>Slutförd</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
<td>Nej</td>
</tr>
</tbody>
</table>



