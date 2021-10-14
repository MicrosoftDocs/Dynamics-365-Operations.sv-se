---
title: Exempel på avdragsdagar
description: Exempel på avdragsdagar.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97fb032d02df1dbedaeccec14496cb1d63e8cf70
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567953"
---
# <a name="reduction-days-example"></a>Exempel på avdragsdagar

[!include [banner](../includes/banner.md)]

Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Från-datum</p></th>
<th><p>Till-datum</p></th>
<th><p>Abonnemang</p></th>
<th><p>Abonnemangstyp</p></th>
<th><p>Project</p></th>
<th><p>Kategori</p></th>
<th><p>Försäljningsvaluta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>01 mars 2011</p></td>
<td><p>31 mars 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Vanligt</strong></p></td>
<td><p>9013</p></td>
<td><p>Underkategori2</p></td>
<td><p>Euro</p></td>
<td><p>200,00</p></td>
</tr>
</tbody>
</table>

Kunden rapporterar att han eller hon inte behöver servicetäckning under två dagar (10 och 11 mars). Du går med på att minska abonnemanget med dessa två dagar.

Du skapar en ny transaktion av typen **Reduceringsdagar** på det sätt som beskrivs i tabellen nedan.

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Från-datum</p></th>
<th><p>Till-datum</p></th>
<th><p>Abonnemang</p></th>
<th><p>Abonnemangstyp</p></th>
<th><p>Project</p></th>
<th><p>Kategori</p></th>
<th><p>Försäljningsvaluta</p></th>
<th><p>Försäljningspris</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>10 mars 2011</p></td>
<td><p>11 mars 2011</p></td>
<td><p>NR-2</p></td>
<td><p><strong>Reduceringsdagar</strong></p></td>
<td><p>9013</p></td>
<td><p>Underkategori2</p></td>
<td><p>Euro</p></td>
<td><p>-12,90</p></td>
</tr>
</tbody>
</table>

När transaktioner för mars 2011 faktureras minskas försäljningspriset på 200 euro med 12,90 euro. Det debiterbara beloppet för abonnemangstransaktionen blir därför 187,10 euro, och två transaktioner på sammanlagt 187,10 euro faktureras.

## <a name="see-also"></a>Se även

[Minska antalet dagar på abonnemangsavgifter](reduce-the-days-on-subscription-fees.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]