---
title: Tolka inkommande dokument i Excel-format
description: Det här avsnittet innehåller information om hur du utformar elektronisk rapportering (ER)-format för att tolka innehållet på inkommande filer i Microsoft Excel-filer.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 6e27806d3b94eb485705cec539a4849b81fbba91
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685797"
---
# <a name="parse-incoming-documents-in-excel-format"></a>Tolka inkommande dokument i Excel-format

[!include[banner](../includes/banner.md)]

Du kan utforma elektronisk rapportering (ER)-format för att analysera inkommande filer i Microsoft Excel som visar data i Microsoft Excel-arbetsböcker (filerna i XLSX-format). Du kan sedan använda innehållet från dessa filer till att uppdatera programdata. Detta är användbart om du:

- Designar en ny modell och format och vill testa dem under körning. I det här fallet simulerar Excel verkliga programdata.
- Hantera data utanför programmet i Excel och vill importera denna data för att skicka en specifik rapport.

Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiderna **ER importera data från en Microsoft Excel-fil (Del 1: Designformat)** och **ER importera data från en Microsoft Excel-fil (Del 2: Importera data)** (delar av affärsprocessen 7.5.4.3 hämta/utveckla IT-tjänst/lösningskomponenter (10677)). Uppguftsguidera uppgift går igenom hur den inkommande Excel-filen kan tolkas med ER-formatet för att importera information från inkommande dokument och uppdatera programdata. Du kan hämta uppgiftsguidefilerna från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).

Hämta följande filer för att slutföra uppgiftsguiderna som nämns ovan.

| Beskrivning av innehåll                         | Fil                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| Inkommande fil i XLSX-format - mall    | [1099import template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| Inkommande fil i XLSX-format - exempeldata | [1099import data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Om du inte har spelat upp följande uppgiftsguide, [ER Skapa erforderliga konfigurationer för att importera data från en extern fil](./tasks/er-required-configurations-import-data.md) i den aktuella Finance and Operations-appen ska du hämta följande fil.

| Beskrivning av innehåll    | Fil                                                            |
|------------------------|-----------------------------------------------------------------|
| ER modellkonfiguration | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]