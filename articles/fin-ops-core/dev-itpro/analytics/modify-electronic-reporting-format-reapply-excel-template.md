---
title: Ändra format för elektronisk rapportering genom att återtillämpa Excel-mallar
description: Det här ämnet innehåller information om hur du ändrar formatet för elektronisk rapportering (ER) som används för att skapa affärsdokument genom att tillämpa en ändrad Excel-mall.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: fa15ae3111f7b91fd63afedb3ef21709d7d866d8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682227"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Ändra format för elektronisk rapportering genom att återtillämpa Excel-mallar

[!include [banner](../includes/banner.md)]

Verktyget för elektronisk rapportering (ER) används för att skapa affärsdokument i elektroniskt format. Om du vill skapa ett affärsdokument måste du skapa ett ER-format, och sedan använda ER-designer för att definiera utseendet på affärsdokumentet och ange de data som ska inkluderas i den. Kör sedan ER-formatet för att skapa affärsdokumentet.

ER-verktyget kan användas för att skapa affärsdokument som Microsoft Excel-filer. Du kan använda Excel-dokument som en mall för dessa dokument. Om du vill ange dokumentets layout i ER-designer kan du importera innehållet i Excel-dokument som du vill använda som mall i det definierade formatet för ER. För mer detaljer, och för att träna detta scenario, spela upp arbetsguiden **ER utformar en konfiguration för rapportgenerering i OPENXML-format** (del av 7.5.4.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller -lösningar (10677)).

Om du redigerar Excel-dokument som används som en mall för ett affärsdokument gör ny ER-funktion att du kan återanvända den uppdaterade mallen till ER-format. Då uppdateras ER-formatet så att det följer den uppdaterade mallen. För mer information om den här funktionen, spela uppgiftsguiden **ER ändra formatet genom att använda en Excel-mall** (del av 7.5.5.3 affärsprocessen skaffa/utveckla komponenter för IT-tjänster eller IT-lösningar (10683)). I uppgiftsguiden där du importerar en uppdaterad mall använder du en ändrad mall av betalningsrapportens Excel-fil, SampleVendPaymWsReport2 som en mall.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]