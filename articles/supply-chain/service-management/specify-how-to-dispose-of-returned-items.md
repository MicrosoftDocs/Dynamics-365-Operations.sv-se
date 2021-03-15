---
title: Ange hur returnerade artiklar ska avyttras
description: Ange hur returnerade artiklar ska avyttras
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0049e47d5e0e5f8a2a6d7cc5feb29593c764d323
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991550"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Ange hur returnerade artiklar ska avyttras 

[!include [banner](../includes/banner.md)]


När du hanterar en returorder måste du ange en orsakskod som visar varför produkten returneras identifiera. Du måste även ange en dispositionskod och dispositionsåtgärden om vad som ska göras med den returnerade produkten.

En dispositionskod kan anges när du skapar returordern, registrerar eller följesedelsuppdaterar artikelinförseln och avslutar en karantänorder.

Du kan definiera alla de dispostionskoder du behöver som stöd för affärsprocesserna. Följande register innehåller ett antal vanliga koder som tilldelas returnerade artiklar.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Dispositionstyp</p></th>
<th><p>Vanlig kod</p></th>
<th><p>beskrivning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Avyttrande</p></td>
<td><p>SC</p></td>
<td><p>Skrota/förstör</p></td>
</tr>
<tr class="even">
<td><p>Avyttrande</p></td>
<td><p>DC</p></td>
<td><p>Donera till välgörande ändamål</p></td>
</tr>
<tr class="odd">
<td><p>Avyttrande</p></td>
<td><p>TD</p></td>
<td><p>Avyttrande till tredje part</p></td>
</tr>
<tr class="even">
<td><p>Avyttrande</p></td>
<td><p>SL</p></td>
<td><p>Återvinn</p></td>
</tr>
<tr class="odd">
<td><p>Avyttrande</p></td>
<td><p>TS</p></td>
<td><p>Försäljning till tredje part (sekundära marknader)</p></td>
</tr>
<tr class="even">
<td><p>Reparera/ändra</p></td>
<td><p>RW</p></td>
<td><p>Omarbeta</p></td>
</tr>
<tr class="odd">
<td><p>Reparera/ändra</p></td>
<td><p>RF</p></td>
<td><p>Omtillverka/renovera</p></td>
</tr>
<tr class="even">
<td><p>Reparera/ändra</p></td>
<td><p>MD</p></td>
<td><p>Ändra</p></td>
</tr>
<tr class="odd">
<td><p>Reparera/ändra</p></td>
<td><p>RP</p></td>
<td><p>Reparera</p></td>
</tr>
<tr class="even">
<td><p>Reparera/ändra</p></td>
<td><p>RV</p></td>
<td><p>Retur till leverantören</p></td>
</tr>
<tr class="odd">
<td><p>Övrigt</p></td>
<td><p>AI</p></td>
<td><p>Använd i befintligt skick</p></td>
</tr>
<tr class="even">
<td><p>Övrigt</p></td>
<td><p>RS</p></td>
<td><p>Återförsäljning</p></td>
</tr>
<tr class="odd">
<td><p>Övrigt</p></td>
<td><p>EX</p></td>
<td><p>Växel</p></td>
</tr>
<tr class="even">
<td><p>Övrigt</p></td>
<td><p>MS</p></td>
<td><p>Diverse</p></td>
</tr>
</tbody>
</table>


För varje dispositionskod, som du definierar, måste du välja dispositionsåtgärden. Dispositionsåtgärden avgör de fysiska och ekonomiska följderna av dispositionskoderna. Till exempel bestämmer dispositionsåtgärden den fysiska användningen av den returnerade artikeln, ekonomiska effekten av den returnerade artikeln, och om en ersättningsartikel måste skickas till kunden. Du kan definiera ett obegränsat antal dispositionskoder enligt dina affärsbehov, men det finns bara sex fördefinierade dispositionsuppgifter som du kan välja från. I följande register finns dispositionsåtgärderna med definitioner.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Dispositionsåtgärd</p></th>
<th><p>beskrivning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Kredit</strong></p></td>
<td><p>Returnera artikeln till lagret och kreditera kunden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endast kreditering</strong></p></td>
<td><p>Kreditera kunden, utan att kräva att förvänta att artikeln ska returneras.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Kassation</strong></p></td>
<td><p>Kassera artikeln och kreditera kunden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ersätt och kreditera</strong></p></td>
<td><p>Returnera artikeln till lagret, skapa en ersättningsorder och kreditera kunden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ersätt och kassera</strong></p></td>
<td><p>Kassera artikeln, skapa en ersättningsorder och kreditera kunden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Returnera till kund</strong></p></td>
<td><p>Avvisa den returnerade artikeln och skicka tillbaka den till kunden.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Välja en dispositionskod för en karantänorder

1.  Klicka på **Lagerhantering** \> **Periodisk** \> **Kvalitetshantering** \> **Karantänorder**.

2.  För en befintlig karantänorder väljer du en åtgärd i fältet **Dispositionskod** på fliken **Översikt**.



## <a name="see-also"></a>Se även

[Karantänorder (formulär)](https://technet.microsoft.com/library/aa554073(v=ax.60))

[Dispositionskoder (formulär)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]