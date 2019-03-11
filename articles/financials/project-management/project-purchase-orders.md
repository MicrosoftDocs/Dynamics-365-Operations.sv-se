---
title: Inköpsorder för ett projekt
description: Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 767a1805e7a2609c5c28bed891b42f7c8c3aaffc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "348697"
---
# <a name="purchase-orders-for-a-project"></a>Inköpsorder för ett projekt

[!include [banner](../includes/banner.md)]

Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt.

I Microsoft Dynamics 365 for Finance and Operations kan du använda flera olika sätt för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern, när de inköpta artiklarna förbrukas, och när inköpta artiklarna debiteras ett projekt.

### <a name="methods-for-creating-a-purchase-order"></a>Metoder för att skapa en inköpsorder

Du kan använda en av följande metoder för att skapa en inköpsorder i Projekthantering och redovisning. Syftet med inköpsordern avgör när inköpsordern förbrukas och därmed när artiklar debiteras ett projekt.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metod</th>
<th>Syfte</th>
<th>Förbrukning av artiklar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skapa en inköpsorder direkt från ett projekt.</td>
<td>Använd den här metoden för att köpa artiklar från en extern leverantör för förbrukning i ett projekt. Du kan skapa inköpsordern på två sätt:
<ul>
<li>Från själva projektet. I det här fallet har projektet redan definierats för inköpsordern.</li>
<li>Genom att navigera till projektinköpsordern. Du måste välja både leverantören och projektet som inköpsordern ska skapas för.</li>
</ul></td>
<td>Artiklar förbrukas när leverantörsfakturan uppdateras.</td>
</tr>
<tr class="even">
<td>Skapa en inköpsorder från en försäljningsorder.</td>
<td>Använd den här metoden för att köpa in artiklar när du skapar en försäljningsorder från ett projekt.</td>
<td>Artiklar förbrukas när försäljningsordern faktureras till kunden.</td>
</tr>
<tr class="odd">
<td>Skapa en inköpsorder från ett artikelbehov.</td>
<td>Använd den här metoden för att köpa in artiklar när du skapar ett artikelbehov från ett projekt.</td>
<td>Artiklar förbrukas när följesedeln för artikelbehov uppdateras.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> När du uppdaterar leverantörsfakturan eller följesedeln uppmanas du att uppdatera följesedeln på artikelbehovet.

Mer information finns i [ta emot artiklar på inköpsorder från ett artikelbehov](tasks/receive-items-purchase-order-item-requirement.md).

