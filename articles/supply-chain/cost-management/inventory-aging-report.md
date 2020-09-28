---
title: Exempel och logik på åldersfördelningsrapport för lager
description: I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från en åldersfördelningsrapport för lager.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759554"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Exempel och logik på åldersfördelningsrapport för lager

[!include [banner](../includes/banner.md)]

I det här avsnittet presenteras några exempel som visar hur du tolkar resultaten från rapporten **åldersfördelning för lager**. I den här rapporten kategoriseras lagerbehållningskvantitet och lagervärden för en vald artikel eller artikelgrupp till flera periodgrupper. I det här avsnittet visas också rapportens interna logik.

Exemplen i det här avsnittet visar resultat som visas i en standardrapport för **Lagerföråldring**. I allmänhet rekommenderar vi dock att du använder versionen [Lagring av Lagerföråldringsrapport](inventory-aging-report-storage.md) för den här rapporten, särskilt när du har många artiklar och lagerställen som måste bearbetas. Lagring av Lagerföråldringsrapport sparar varje rapport som du skapar, visar resultaten som en interaktiv sida och ett diagram och låter dig exportera alla sparade rapporter.

## <a name="sample-data-that-is-used-in-these-examples"></a>Exempeldata som används i dessa exempel

Exemplen i det här avsnittet är baserade på transaktionsdata för exempellager som beskrivs i det här avsnittet.

### <a name="storage-dimension-setup"></a>Inställningar av lagringsdimension

Exempelsystemet innehåller följande inställning av lagringsdimensioner.

| Namn      | Aktiva | Fysiskt lager | Ekonomiskt lager |
|-----------|--------|--------------------|---------------------|
| Webbplats      | Ja    | Ja                | Ja                 |
| Lagerställe | Ja    | Ja                | Nr                  |

### <a name="inventory-model"></a>Lagermodell

För systemexemplet är lagermodellen för de frisläppta produkterna *FIFO* och inställningen **självkostnad** för lagermodellen är *inkludera fysiskt värde*.

### <a name="inventory-transactions"></a>Lagertransaktioner

Exempelsystemet innehåller följande lagertransaktioner för en frisläppt produkt som har artikel numret *1000*.

| Referens      | Webbplats | Lagerställe | Inleverans   | Utfärda | Fysiskt datum | Ekonomiskt datum | Kvantitet | Kostnadsbelopp | Fysiskt kostnadsbelopp |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Inköpsorder | 1    | 11        | Inköpt |       | 15 mars      | 15 mars       | 10       | 1 000       | 1 000                |
| Inköpsorder | 2    | 21        | Inköpt |       | 15 mars      | 15 mars       | 10       | 2,000       | 2,000                |
| Inköpsorder | 1    | 11        | Inlevererat  |       | 15 april      |                | 5        |             | 375                  |
| Överföringsorder | 1    | 11        |           | Sålt  | 2 maj         | 2 maj          | -5       | -458,33     | -458,33              |
| Överföringsorder | 1    | 12        | Inköpt |       | 2 maj         | 2 maj          | 5        | 458.33      | 458.33               |
| Försäljningsorder    | 1    | 12        |           | Sålt  | 3 maj         | 3 maj          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Hur kvantiteter och belopp i varje periodgrupp beräknas

Genom att använda de exempeldata som beskrivs i föregående avsnitt kan du köra en rapport **Lagerföråldring** med följande inställningar:

- **Från och med:** *9 maj 2020*
- **plats:** *Vy*
- **Lagerställe:** *Nej*
- **Artikelnummer:** *Total*
- **Åldersfördelningsperiod:** Ange det här fältet om du vill generera månatliga grupper.

I det här fallet kommer innehållet i den rapport som genereras att likna följande exempel.

<table>
<thead>
<tr>
    <th rowspan="2">Artikelnummer</th>
    <th rowspan="2">Webbplats</th>
    <th rowspan="2">Lagerbehållning</th>
    <th rowspan="2">Behållningsvärde</th>
    <th rowspan="2">Lagervärdekvantitet</th>
    <th rowspan="2">Lagervärde</th>
    <th rowspan="2">Genomsnittlig enhetskostnad</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Kvantitet</th>
    <th>P1:Belopp</th>
    <th>P2:Kvantitet</th>
    <th>P2:Belopp</th>
    <th>P3:Kvantitet</th>
    <th>P3:Belopp</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1 000 summor</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Lägg märke till följande information i exempelrapporten:

- Värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som visas i rapporten är värden för den finansiella inventeringsdimensionen (**plats**, i detta fall).

    För t.ex. plats 1 visar rapporten följande information:

    - Värdet för **Lagervärdets kvantitet** är *14* (= 10 + 5 – 5 + 5 – 1).
    - Värdet för **Lagervärde** är *1,283.33* (= 1,000 + 375 – 458,33 + 458,33 – 91,67).
    - Värdet för **Genomsnittlig enhetskostnad**är *91,67*.
    - Värdet **Behållningsvärde** och **Belopp** i varje period grupp beräknas med hjälp av värdet **Genomsnittlig enhetskostnad**.

- Rapporten bestämmer lagerbehållningen för varje periodgrupp genom att summera den totala inlevererade lagerkvantiteten för varje periodgrupp. Därefter tillämpas principen först in, först ut (FIFO) för att dra av den totala utfärdade kvantiteten, oavsett vilken lagermodell som används för artiklarna.

Om du kör samma rapport igen, men den här gången du anger båda fälten **plats** och **Lagerställe** till *Vy*, kommer den nya rapporten att likna följande exempel.

<table>
<thead>
<tr>
    <th rowspan="2">Artikelnummer</th>
    <th rowspan="2">Webbplats</th>
    <th rowspan="2">Lagerställe</th>
    <th rowspan="2">Lagerbehållning</th>
    <th rowspan="2">Behållningsvärde</th>
    <th rowspan="2">Lagervärdekvantitet</th>
    <th rowspan="2">Lagervärde</th>
    <th rowspan="2">Genomsnittlig enhetskostnad</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Kvantitet</th>
    <th>P1:Belopp</th>
    <th>P2:Kvantitet</th>
    <th>P2:Belopp</th>
    <th>P3:Kvantitet</th>
    <th>P3:Belopp</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1 000 summor</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Den här gången är plats 1 uppdelad i två rader, en för lagerställe 11 och ett för lagerställe 12. Men värdena **Lagervärdets kvantitet**, **Lagervärde** och **Genomsnittlig enhetskostnad** som är samma eftersom **Lagerställe** inte är en ekonomisk lagerdimension.

Observera dessutom att kvantitetsfördelningen för plats 1 är annorlunda. I den första rapporten som du körde ignorerade systemet överföringsordern som inträffade på samma plats och dragit av kvantiteten av försäljningsfakturan från **3/31/2020-3/1/2020** periodgrupp 1 på plats 1. I den nya rapporten drar systemet emellertid av kvantiteten på försäljningsfakturan från **5/8/2020 - 5/1/2020** periodgrupp i lagerstället 12.

## <a name="effects-of-inventory-closing"></a>Effekter av stängning av lager

Om du kör lagerstängningen för maj och sedan kör föregående rapport igen, men ställer in fältet **Från och med** till *31 maj 2020*, kommer du att märka följande resultat:

- **Lagervärdet** och **Genomsnittlig enhetskostnad** uppdateras.
- Värdet **Behållningsvärde** och värdena **Belopp** i varje periodgrupp uppdateras därefter.

Den nya rapporten liknar följande exempel:

<table>
<thead>
<tr>
    <th rowspan="2">Artikelnummer</th>
    <th rowspan="2">Webbplats</th>
    <th rowspan="2">Lagerställe</th>
    <th rowspan="2">Lagerbehållning</th>
    <th rowspan="2">Behållningsvärde</th>
    <th rowspan="2">Lagervärdekvantitet</th>
    <th rowspan="2">Lagervärde</th>
    <th rowspan="2">Genomsnittlig enhetskostnad</th>
    <th colspan="2">5/31/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Kvantitet</th>
    <th>P1:Belopp</th>
    <th>P2:Kvantitet</th>
    <th>P2:Belopp</th>
    <th>P3:Kvantitet</th>
    <th>P3:Belopp</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1 000 summor</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
