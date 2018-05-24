---
title: Kombinera serviceorder
description: Du kan kombinera serviceorder.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8bc28d03d36d184e4bf41de2c50dac15e6d7813c
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="combine-service-orders"></a>Kombinera serviceorder   

[!include [banner](../includes/banner.md)]


När du skapar serviceorderrader automatiskt i formuläret **serviceavtal** kan du välja ett av följande alternativ för att ange hur du vill gruppera dem:

  - **Per serviceavtal**

  - **Per serviceuppgift**

  - **Per anställd**

  - **Per serviceobjekt**

## <a name="example"></a>Exempel

Du skapar ett serviceavtal med startdatum 2007-03-31. I fältet **kombinera serviceorder** väljer du **Per serviceobjekt**. Därefter skapar du följande serviceavtalsrader:

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Avtalsradnummer</p></th>
<th><p>transaktionstyp</p></th>
<th><p>beskrivning</p></th>
<th><p>Intervall</p></th>
<th><p>Serviceobjekt</p></th>
<th><p>Startdatum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Timme</strong></p></td>
<td><p>SAL1</p></td>
<td><p>Varje vecka</p></td>
<td><p>X-1</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Timme</strong></p></td>
<td><p>SAL2</p></td>
<td><p>Varannan vecka</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Timme</strong></p></td>
<td><p>SAL3</p></td>
<td><p>Varje vecka</p></td>
<td><p>X-2</p></td>
<td><p>2007-04-01</p></td>
</tr>
</tbody>
</table>


Du anger inte några tidsfönster för serviceavtalsraderna. Därför flyttas serviceorderraderna inte från den beräknade dag de infaller.

Därefter skapar du serviceavtalsrader i formuläret **Skapa serviceorder** från 2007-04-01 till 2007-04-30.

Totalt skapas 10 serviceorder. Eftersom du valde den kombinerade inställningen **Per serviceobjekt**, har de serviceorder som skapas endast serviceorderrader med ett specifikt serviceobjekt. Serviceorderrader som genereras från serviceavtalet och har samma servicedatum och samma objekt kombineras till en serviceorder.


> [!NOTE]
> <P>I det här exemplet finns det inga stängda dagar i den kalender som angavs i formuläret <STRONG>Servicehanteringsparametrar</STRONG>.</P>



Ytterligare gruppering av serviceorderrader till serviceordrar görs enligt de tidsfönster som du anger på serviceavtalsraderna.

## <a name="see-also"></a>Se även

[Skapa serviceorder automatiskt](create-service-orders-automatically.md)

  



