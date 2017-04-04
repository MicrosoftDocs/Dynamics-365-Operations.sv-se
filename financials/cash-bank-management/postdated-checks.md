---
title: Efterdaterade checkar
description: "Den här artikeln innehåller information om stöd för efterdaterade checkar i Microsoft Dynamics 365 för operationer. Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Därför kan checken inte lösas in förrän på angivet datum."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 7349771b7f9a1ad4cd5b239f1d10bd3229d2d0df
ms.lasthandoff: 03/31/2017


---

# <a name="postdated-checks"></a>Efterdaterade checkar

Den här artikeln innehåller information om stöd för efterdaterade checkar i Microsoft Dynamics 365 för operationer. Postdaterade checkar är checkar som har utfärdats för att skapa och ta emot betalningar vid ett framtida datum. Därför kan checken inte lösas in förrän på angivet datum.

Microsoft Dynamics 365 för operationer stöder hantering av hela cykeln för efterdaterade checkar både i Kundreskontra och Leverantörsreskontra, som visas i följande tabell.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Detaljer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ställ in efterdaterade checkar</td>
<td>Du måste ställa in en ny betalningsmetod och ange betalningsrutin för clearingkonton för betalda checkar, mottagna checkar och källskatt.</td>
</tr>
<tr class="even">
<td>Registrera och bokför en efterdaterad check för en leverantör</td>
<td>Registrera information om en efterdaterad check som du utfärdar till en leverantör. När betalningen bokförs leverantör skuld redovisas och bankkontot inte ännu kreditera. I stället används ett clearingkonto för detta ändamål.</td>
</tr>
<tr class="odd">
<td>Registrera och bokför en efterdaterad check för en kund</td>
<td>Registrera information om en efterdaterad check som tas emot från en kund. När betalningen bokförs kunden Kundreskontra kredit, men bankkontot inte ännu debiteras. I stället används ett clearingkonto för detta ändamål.</td>
</tr>
<tr class="even">
<td>Registrera och bokföra en efterdaterade Ersättningscheck för en kund eller leverantör</td>
<td>
Om din ursprungliga check till en leverantör eller från en kund förloras eller skadas kan du utfärda en efterdaterad check som substitut. När du registrerar informationen om checken ska du ange en referens till den ursprungliga checken och indikera att den nya checken ersätter den ursprungliga. Du kan även bokföra utbyteschecken.</td>
</tr>
<tr class="odd">
<td>Överför en efterdaterad kundcheck till en leverantör</td>
<td>När du får en efterdaterad check från en kund kan du överföra den till en leverantör som betalning.</td>
</tr>
<tr class="even">
<td>Betala en postdaterad check för en kund eller leverantör</td>
<td>Kvitta en efterdaterad check som har bokförts på ett interimskonto för en kund eller leverantör när checken har förfallit. När checken kvittad har banken slutligen debiterats eller krediterats mot clearingkontot som användes tidigare.</td>
</tr>
<tr class="odd">
<td>Annullera en efterdaterad check för en leverantör</td>
<td>Du kan avbryta en bokförd efterdaterade check i sådana fall:-kontrollen returneras av banken.
-Kontrollen används en felaktig faktura.
-Kontant betalning mot checken.
</td>
</tr>
<tr class="even">
<td>Stoppa betalning för efterdaterade checkar</td>
<td>Du kan stoppa en efterdaterad checkbetalning som utfärdades till en leverantör av orsaker såsom otillräckliga medel, ändringar av villkoren för avtalet med leverantören, leverans av defekta varor från leverantören eller returnering av varor till leverantören. Du kan stoppa betalning endast på checkar som inte har avmarkerat.</td>
</tr>
</tbody>
</table>




