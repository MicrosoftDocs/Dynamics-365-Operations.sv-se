---
title: "Använd snabbt importera/exportera"
description: "Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 2012 R3 CU8
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: a0329cd2710820fb1e82f761a414a3f08910078b
ms.lasthandoff: 03/31/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Kör testet Data överföra verktyget (beta) för Dynamics AX (AX 2012)

Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg.

Vi har lagt till funktionen Snabb import/export så att användarna kan importera eller exportera enkla jobb som de vill köra snabbt. Den här funktionen används bäst i scenarier där en fil mappas automatiskt till systemet och där användaren inte behöver gå via Avancerad mappning eller Skapa återkommande import- eller exportjobb.

-   Den här funktionen stöder arbete med både OOB- och anpassade entiteter.
-   Du kan importera från filer och om du använder en ODBC-datakälla kan du välja en fråga som du använder för att definiera importen.
-   Du måste tidigare har definierat källdataformat för antingen AX eller Fil och veta var de finns.
-   Du behöver inte skapa en bearbetningsgrupp för att använda funktionen Snabb import/export. Det skapas en automatiskt av systemet när du kör import- eller exportjobbet. Du kan också välja spara historiken över de data som importerats med hjälp av funktionen Snabb import/export.

  Observera att funktionen Snabb import/export förutsätter att du känner till DIXF-begrepp.


