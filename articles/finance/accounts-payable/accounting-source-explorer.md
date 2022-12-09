---
title: Utforskare för redovisningskälla
description: Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.
author: RyanCCarlson2
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: kfend
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd5580dc0be37ec89e6c7934b47c7d5593d8716
ms.sourcegitcommit: 5f8f042f3f7c3aee1a7303652ea66e40d34216e3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/29/2022
ms.locfileid: "9806444"
---
# <a name="accounting-source-explorer"></a>Utforskare för redovisningskälla

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om **utforskaren för redovisningskälla**, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.

**Utforskaren för redovisningskälla** är en ny sida som visar källinformation. Du kan använda den som ett fristående verktyg eller för att analysera detaljerna bakom kontoposterna i redovisningen. Du kan exempelvis använda sidan för att få den mest detaljerade källinformationen för redovisningssaldo eller en verifikationstransaktion. Du kan sedan använda funktionen för **export till MS Excel** för att titta noggrannare på informationen i Microsoft Excel (exempelvis i en pivottabell eller en pivotrapport).

**Utforskaren för redovisningskälla** visar alltid samma totalbelopp per huvudbokskonto som huvudboken visar (exempelvis i råbalansen). I råbalansen kan du visa segment i olika kolumner. Välj lämplig uppsättning av ekonomisk dimension. 

Du kan använda parametrar för att definiera ett datumintervall för analysen. Denna funktion liknar också funktionen i råbalansen.

För alla dokument som använder källdokumentet som ramverk, visar **utforskaren för redovisningskälla** ytterligare information baserat på redovisningsfördelningar samt, i tillämpliga fall, redovisningsfördelningar för projekt. Denna information omfattar värdet **penningbeloppstyp**, **projekt**, **aktivitet**, **kategori** och **radegenskap**. Nedan följer några exempel på analyser som du kan göra:

- Avvikelser mellan inköpsorder och leverantörsfakturor, eftersom varje avvikelse representeras av en typ av monetärt belopp, till exempel tilläggsavvikelse
- Fakturerbara kontra inte fakturerbara timmar och utgifter per projekt, affärsenhet och huvudkonto

För källdokument som använder begreppet för källdokumentreferensidentiteter, visar sidan **Utforskare för redovisningskälla** mer information som värdena **kund**, **leverantör**, **arbetare**, **produkt**, **kvantitet**, **enhettext** och **beskrivning**. Nedan följer några exempel på analyser som du kan göra:

- Hotellutgifter per affärsenhet och hotellkedjan för en räkenskapsperiod som baseras på utgiftsrapporter
- Rabatter per leverantör, produkt, avdelning

För dessa dokument kan du också navigera till det verkliga källdokumentet från **utforskaren för redovisningskälla**.

> [!NOTE]
> Från och med version 10.0.31 finns en ny funktion för **Avancerad filtrering för utforskare för redovisningskälla** i funktionshantering. Den här funktionen ersätter knappen **Uppdatera** för att ge en mer robust avancerad frågeupplevelse som liknar det som finns på sidan **Verifikationstransaktioner**. Med det avancerade filtret kan du filtrera efter liknande fält som du hittar på sidan **Fråga om verifikationstransaktioner**, t.ex. **Huvudbokskonto**, **Affärsenhet**, **Kostnadsställe** och **Avdelning**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
