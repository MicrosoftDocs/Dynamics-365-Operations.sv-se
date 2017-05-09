---
title: "Värden för lagerobjekt"
description: "Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-07 09 - 09 - 05
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 8898d5d91ffb4f73ea68f1251e1a99440e81bcd4
ms.lasthandoff: 03/29/2017


---

# <a name="inventory-object-values"></a>Värden för lagerobjekt

Det här avsnittet innehåller information om hur värdena för ett lagerobjekt beräknas. 

En ny funktion med namnet **fysisk kvantitet** visar värdena för ett visst lagerobjekt. Ett kostnadsobjekt representerar enhetsnivån där lagerredovisning utförs. Mer information om kostnadsobjekt finns i [Kostnadsobjekt](cost-object.md). För att visa värdena för ett visst lagerobjekt, klicka på **Fysisk kvantitet** på sidan **Kostnadsobjekt**. Så här beräknas värdet på lagerobjektet: Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity Följande exempel visar hur värdena för ett lagerobjekt och ett kostnadsobjekt beräknas. Två produktinleveranshändelser registreras på artikel A:

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



<a name="see-also"></a>Se även
--------

[Kostnadsobjekt](cost-object.md)

[Kostnadsposter](cost-entries.md)

[Nyheter och ändringar i Microsoft Dynamics AX](/dynamics365/operations/dev-itpro/get-started/whats-new-changed)


