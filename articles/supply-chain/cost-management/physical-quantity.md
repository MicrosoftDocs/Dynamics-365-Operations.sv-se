---
title: Värden för lagerobjekt
description: Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f14248ffa8f9f5a460b090ca5754442cd50bf45a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263552"
---
# <a name="inventory-object-values"></a>Värden för lagerobjekt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas. 

En ny funktion med namnet, **fysisk kvantitet** visar värdena för ett visst lagerobjekt. 

Ett kostnadsobjekt representerar enhetsnivån där lagerredovisning utförs. Mer information om kostnadsobjekt finns i [Kostnadsobjekt](cost-object.md). 

För att visa värdena för ett visst lagerobjekt, klicka på **Fysisk kvantitet** på sidan **Kostnadsobjekt**. Här visas hur värdet för ett lagerobjekt beräknas: 

Lagerobjekt på lager. Värde = kostnadsobjekt. Genomsnittlig enhetskostnad × lagerobjekt. Kvantitet 

Följande exempel visar hur värdena beräknas för ett objekt i lagret och en kostnadsobjekt. Två produktinleveranshändelser registreras på artikel A:

-   Produktinleverans 1: Kvantitet = 100 st., Belopp = 1 000,00 USD, Plats = 1, Lagerställe =11, Buntnr. = B1
-   Produktinleverans 2: Kvantitet = 50 st., Belopp = 800,00 USD, Plats = 1, Lagerställe =11, Buntnr. = B2

Följande tabell visar beräkningsresultatet för ett kostnadsobjekt. Du kan visa resultaten på sidan **Kostnadsobjekt**.

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Objekttyp</th>
<th>Artikelnummer</th>
<th>Plats</th>
<th>Kvantitet</th>
<th>Lagerenhet</th>
<th>Värde</th>
<th>Genomsnittlig enhetskostnad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kostnadsobjekt</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>Stk.</td>
<td><p>1800,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
</tbody>
</table>

Följande tabell visar beräkningsresultatet för ett lagerobjekt. Du kan visa resultaten genom att klicka på **Fysisk kvantitet** på sidan **Kostnadsobjekt**.

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Objekttyp</th>
<th>Artikelnummer</th>
<th>Plats</th>
<th>Lagerställe</th>
<th>Buntnr.</th>
<th>Kvantitet</th>
<th>Lagerenhet</th>
<th>Värde</th>
<th>Genomsnittlig enhetskostnad</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lagerobjekt</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Stk.</td>
<td><p>1200,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
<tr class="even">
<td>Lagerobjekt</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Stk.</td>
<td><p>600,00 USD</p></td>
<td><p>12,00 USD</p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Ytterligare resurser
--------

[Kostnadsobjekt](cost-object.md)

[Kostnadsposter](cost-entries.md)

[Nyheter och ändringar](../../fin-and-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]