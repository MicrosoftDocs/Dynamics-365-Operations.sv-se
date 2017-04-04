---
title: "Utforskare för redovisningskälla"
description: "Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 8913e61285d5d180883471991b659ddcb260afe3
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-source-explorer"></a>Utforskare för redovisningskälla

Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.

Utforskaren för redovisningskälla är en ny sida som visar källinformation. Du kan använda redovisning Utforskaren för datakällor som ett fristående verktyg eller analysera detaljerna bakom kontoposter i redovisningen. Du kan exempelvis använda redovisning Utforskaren för datakällor för att få den mest detaljerade källinformationen för redovisningsspårning saldo balans eller en verifikationstransaktionen. Du kan sedan använda funktionen för export till Microsoft Excel för att titta noggrannare på informationen i Microsoft Excel (exempelvis i en pivottabell eller en pivotrapport).

Utforskaren för redovisningskälla visar alltid samma totalbelopp per huvudbokskonto som huvudboken visar (exempelvis i råbalansen). I råbalansen kan du visa segment i olika kolumner. Välj lämplig uppsättning av ekonomisk dimension. 

Du kan använda parametrar för att definiera ett datumintervall för analysen. Denna funktion liknar också funktionen i råbalansen.

För alla dokument som använder källan dokumentet framework, redovisning källa explorer visar ytterligare information utifrån redovisningsfördelningar och i tillämpliga fall projektredovisning fördelningar. Informationen omfattar penningbelopp typ, projekt, kategori, aktivitet och radegenskap. Nedan följer några exempel på analyser som du kan göra:

-   Avvikelser mellan inköpsorder och leverantörsfakturor, eftersom varje avvikelse representeras av en typ av monetärt belopp, till exempel tilläggsavvikelse
-   Fakturerbara kontra inte fakturerbara timmar och utgifter per projekt, affärsenhet och huvudkonto

För källdokument som använder begreppet för källdokumentreferensidentiteter, visar källutforskaren även mer information, till exempel kund, leverantör, arbetare, produkt, kvantitet, enhettext och beskrivningar. Nedan följer några exempel på analyser som du kan göra:

-   Hotellutgifter per affärsenhet och hotellkedjan för en räkenskapsperiod som baseras på utgiftsrapporter
-   Rabatter per leverantör, produkt, avdelning

För dessa dokument kan du också navigera till det verkliga källdokumentet från utforskaren för redovisningskälla.


