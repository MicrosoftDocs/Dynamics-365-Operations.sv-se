---
title: "Inköpsorder för ett projekt"
description: "Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 82305cfe38e7193cece3b9e7784fb81fd40f9c70
ms.lasthandoff: 03/31/2017


---

# <a name="purchase-orders-for-a-project"></a>Inköpsorder för ett projekt

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt.

I Microsoft Dynamics 365 for Operations kan du använda flera olika sätt för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern, när de inköpta artiklarna förbrukas, och när inköpta artiklarna debiteras ett projekt.

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




