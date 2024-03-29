---
title: Kombinera serviceorder
description: Du kan kombinera serviceorder.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f89c60561746ac9f1c2e9d611089bfac69089081
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676787"
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

<table>
<colgroup>
<col />
<col />
<col />
<col />
<col />
<col />
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

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]