---
title: Ändra format för elektronisk rapportering genom att tillämpa mallar från Excel igen
description: Det här ämnet beskriver hur du ändrar formatet för elektronisk rapportering (ER) som används för att skapa affärsdokument genom att tillämpa en ändrad Excel-mall.
author: NickSelin
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50b115448bc89bba7e9abeb8062d03d31a163b64
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906743"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Ändra format för elektronisk rapportering genom att återtillämpa Excel-mallar

[!include [banner](../includes/banner.md)]

Verktyget för elektronisk rapportering (ER) används för att skapa affärsdokument i elektroniskt format. Om du vill skapa ett affärsdokument måste du skapa ett ER-format, och sedan använda ER-designer för att definiera utseendet på affärsdokumentet och ange de data som ska inkluderas i den. Kör sedan ER-formatet för att skapa affärsdokumentet.

ER-verktyget kan användas för att skapa affärsdokument som Microsoft Excel-filer. Du kan använda Excel-dokument som en mall för dessa dokument. Om du vill ange dokumentets layout i ER-designer kan du importera innehållet i Excel-dokument som du vill använda som mall i det definierade formatet för ER. För mer detaljer, och för att träna detta scenario, spela upp arbetsguiden **ER utformar en konfiguration för rapportgenerering i OPENXML-format** (del av 7.5.4.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)). I steget för uppgiftsguide där du importerar en Excel-mall använder du den initiala mallen för Excel-filen för betalningsrapporten, [SampleVendPaymWsReport](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx).

Om du redigerar Excel-dokument som används som en mall för ett affärsdokument gör ny ER-funktion att du kan återanvända den uppdaterade mallen till ER-format. Då uppdateras ER-formatet så att det följer den uppdaterade mallen. För mer information om den här funktionen, spela uppgiftsguiden **ER ändra formatet genom att använda en Excel-mall** (del av 7.5.5.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller IT-lösningar (10683)). I uppgiftsguiden där du importerar en uppdaterad mall använder du en ändrad mall av betalningsrapportens Excel-fil, [SampleVendPaymWsReport2](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx).

## <a name="additional-resources"></a>Ytterligare resurser

[Uppdatera en mall](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
