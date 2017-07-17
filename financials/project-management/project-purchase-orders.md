---
title: "Inköpsorder för ett projekt"
description: "Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 9715d33598c0749ff1ad2523f2fa8834987998ed
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Inköpsorder för ett projekt
<a id="purchase-orders-for-a-project" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt.

I Microsoft Dynamics 365 for Finance and Operations, Enterprise edition kan du använda flera olika metoder för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern, när de inköpta artiklarna förbrukas, och när inköpta artiklarna debiteras ett projekt.

### Metoder för att skapa en inköpsorder
<a id="methods-for-creating-a-purchase-order" class="xliff"></a>

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




