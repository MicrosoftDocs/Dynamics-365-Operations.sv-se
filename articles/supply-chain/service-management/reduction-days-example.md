---
title: Exempel på avdragsdagar
description: Exempel på avdragsdagar.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 509d1a9e2abd79938376209d8feab1b935394833
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010532"
---
# <a name="reduction-days-example"></a>Exempel på avdragsdagar 

[!include [banner](../includes/banner.md)]


Du har skapat en abonnemangstransaktion för en kunds underhållsabonnemang på det sätt som beskrivs i tabellen nedan.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
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
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
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

  


