---
title: "Använd Snabb import/export"
description: "Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: dynamics-ax-2012
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11cf53af2db453471175cec5de63d38f8b680c9b
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Kör Test Data Transfer Tool (beta) för Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg.

Vi har lagt till funktionen Snabb import/export så att användarna kan importera eller exportera enkla jobb som de vill köra snabbt. Den här funktionen används bäst i scenarier där en fil mappas automatiskt till systemet och där användaren inte behöver gå via Avancerad mappning eller Skapa återkommande import- eller exportjobb.

-   Den här funktionen stöder arbete med både OOB- och anpassade entiteter.
-   Du kan importera från filer och om du använder en ODBC-datakälla kan du välja en fråga som du använder för att definiera importen.
-   Du måste tidigare har definierat källdataformat för antingen AX eller Fil och veta var de finns.
-   Du behöver inte skapa en bearbetningsgrupp för att använda funktionen Snabb import/export. Det skapas en automatiskt av systemet när du kör import- eller exportjobbet. Du kan också välja spara historiken över de data som importerats med hjälp av funktionen Snabb import/export.

  Observera att funktionen Snabb import/export förutsätter att du känner till DIXF-begrepp.




