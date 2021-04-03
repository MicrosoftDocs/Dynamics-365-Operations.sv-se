---
title: Tolka inkommande dokument i JSON-format
description: Det här avsnittet innehåller information om hur du ställer in format för elektronisk rapportering (ER) för parsning av inkommande dokument i JSON-format (JavaScript Object Notation).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d39a697876641b4c9647dc1a55243ac2ca7cb9e7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564505"
---
# <a name="parse-incoming-documents-in-json-format"></a>Tolka inkommande dokument i JSON-format

[!include[banner](../includes/banner.md)]

Du kan utforma format för elektronisk rapportering (ER) för att tolka inkommande elektroniska dokument som representerar data i ett textformat som baseras på Java Script (dvs. filer i \[JSON\]-format JavaScript Object Notation).

Om du vill veta mer om den här funktionen kan du hämta filerna i följande tabell och sedan spela upp filen för att skapa en formatkonfiguration för import av data från en extern uppgiftsguide för JSON-filer. Den här uppgiftsguiden visar hur ett ER-format kan användas för att tolka en inkommande JSON-fil för att uppdatera programdata.

| Namn                                  | Filnamn |
|----------------------------------------|-----------|
| Konfiguration för ER-fomat                | [Format för import av leverantörers trans_JSON.xml](https://go.microsoft.com/fwlink/?linkid=874111) |
| Exempel på inkommande fil i .csv-format | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Behov

Innan du slutför ER skapar du en formatkonfiguration för att importera data från en extern uppgiftsguide för JSON-filer måste följande krav uppfyllas:

- De överordnade elementen i JSON-filen kan bara vara objektelement.
- Kapslade element för ett objekt ska vara egenskapselement, så att en giltig JSON-struktur skapas.
- JSON-matriser kan bara innehålla kapslade element för ett objekts egenskapselement.
- JSON-matriser kan bara innehålla JSON-objekt. De får inte innehålla direkta strängar/numeriska värden och kapslade matriser. Element i dessa matriser tolkas i angiven ordning, eftersom de anges i formatet. Sammansatta inställningar för varje JSON-objekt kommer att beaktas.

Du måste dessutom fylla i uppgiftsguiden [ER Skapa erforderliga konfigurationer för att importera data från en extern fil](tasks/er-required-configurations-import-data.md) om du inte redan har fyllt i den. Hämta följande fil för att slutföra uppgiftsguiden.

| Namn                  | Filnamn |
|------------------------|-----------|
| ER modellkonfiguration | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]