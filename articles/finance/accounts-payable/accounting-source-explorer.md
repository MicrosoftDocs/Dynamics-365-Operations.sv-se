---
title: Utforskare för redovisningskälla
description: Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4624a740538493c247b6c3a0f051ed6208c52504
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820941"
---
# <a name="accounting-source-explorer"></a>Utforskare för redovisningskälla

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.

Utforskaren för redovisningskälla är en ny sida som visar källinformation. Du kan använda utforskaren för redovisningskälla som ett fristående verktyg eller för att analysera detaljerna bakom kontoposterna i redovisningen. Du kan exempelvis använda utforskaren för redovisningskällor för att få den mest detaljerade källinformationen för redovisningssaldo eller en verifikationstransaktion. Du kan sedan använda funktionen för export till MS Excel för att titta noggrannare på informationen i Microsoft Excel (exempelvis i en pivottabell eller en pivotrapport).

Utforskaren för redovisningskälla visar alltid samma totalbelopp per huvudbokskonto som huvudboken visar (exempelvis i råbalansen). I råbalansen kan du visa segment i olika kolumner. Välj lämplig uppsättning av ekonomisk dimension. 

Du kan använda parametrar för att definiera ett datumintervall för analysen. Denna funktion liknar också funktionen i råbalansen.

För alla dokument som använder källdokumentet som ramverk, visar utforskaren för redovisningskälla ytterligare information baserat på redovisningsfördelningar samt, i tillämpliga fall, redovisningsfördelningar för projekt. Denna information omfattar penningbeloppstyp, projekt, kategori, aktivitet och radegenskap. Nedan följer några exempel på analyser som du kan göra:

-   Avvikelser mellan inköpsorder och leverantörsfakturor, eftersom varje avvikelse representeras av en typ av monetärt belopp, till exempel tilläggsavvikelse
-   Fakturerbara kontra inte fakturerbara timmar och utgifter per projekt, affärsenhet och huvudkonto

För källdokument som använder begreppet för källdokumentreferensidentiteter, visar källutforskaren även mer information, till exempel kund, leverantör, arbetare, produkt, kvantitet, enhettext och beskrivningar. Nedan följer några exempel på analyser som du kan göra:

-   Hotellutgifter per affärsenhet och hotellkedjan för en räkenskapsperiod som baseras på utgiftsrapporter
-   Rabatter per leverantör, produkt, avdelning

För dessa dokument kan du också navigera till det verkliga källdokumentet från utforskaren för redovisningskälla.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]