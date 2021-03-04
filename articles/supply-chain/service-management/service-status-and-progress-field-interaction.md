---
title: Samband mellan servicestatus och förloppsfält
description: I formuläret Serviceorder återspeglar fältet Förlopp i serviceorderns huvud statusvärdet för hela serviceordern, och Status anger statusvärdet för enskilda serviceorderrader.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94f2df6a4ddb71a29ff951dfe38618ac7762783
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437359"
---
# <a name="service-status-and-progress-field-interaction"></a>Samband mellan servicestatus och förloppsfält 

[!include [banner](../includes/banner.md)]


I formuläret **Serviceorder**, fältet **Förlopp** i serviceorderns huvud statusvärdet för hela serviceordern, och **Status** anger statusvärdet för enskilda serviceorderrader.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Förlopp</p></th>
<th><p>Status för rad 1</p></th>
<th><p>Status för rad 2</p></th>
<th><p>Status för rad 3</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pågår</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pågår</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Pågår</strong></p></td>
<td><p><strong>Skapat</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Bokförd</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Bokförd</strong></p></td>
<td><p><strong>Bokförd</strong></p></td>
<td><p><strong>Bokförd</strong></p></td>
<td><p><strong>Bokförd</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Bokförd</strong></p></td>
<td><p><strong>Bokförd</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
<td><p><strong>Annullerad</strong></p></td>
</tr>
</tbody>
</table>


En serviceorders förlopp är pågående om alla rader har statusvärdet **Skapad**; och det pågår fortfarande om några av raderna har statusvärdet **Avbruten** eller **Bokförd**.

Om alla rader på en serviceorder markeras som **Bokförd**, är förloppet på statusordern **Bokförd**. Om några rader är **Bokförd** och vissa är **Avbruten**, är förloppet fortfarande **Bokförd**.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]