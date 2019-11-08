---
title: Snabb import/export
description: Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg.
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.openlocfilehash: 7655de1399c49328bae1736c796325e546796bd5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181161"
---
# <a name="quick-import-export"></a>Snabb import/export

[!include [banner](../../includes/banner.md)]

Syftet med funktionen Snabb import/export är att du ska kunna importera och exportera med färre steg.

Vi har lagt till funktionen Snabb import/export så att användarna kan importera eller exportera enkla jobb som de vill köra snabbt. Den här funktionen används bäst i scenarier där en fil mappas automatiskt till systemet och där användaren inte behöver gå via Avancerad mappning eller Skapa återkommande import- eller exportjobb.

- Den här funktionen stöder arbete med både OOB- och anpassade entiteter.
- Du kan importera från filer och om du använder en ODBC-datakälla kan du välja en fråga som du använder för att definiera importen.
- Du måste tidigare har definierat källdataformat för antingen AX eller Fil och veta var de finns.
- Du behöver inte skapa en bearbetningsgrupp för att använda funktionen Snabb import/export. Det skapas en automatiskt av systemet när du kör import- eller exportjobbet. Du kan också välja spara historiken över de data som importerats med hjälp av funktionen Snabb import/export.

  Observera att funktionen Snabb import/export förutsätter att du känner till DIXF-begrepp.


