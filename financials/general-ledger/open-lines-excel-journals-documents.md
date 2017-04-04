---
title: "Publicera journalrader och dokument från Microsoft Excel"
description: "Det här avsnittet beskrivs hur du anger och publicera rader för allmänna journaler från Microsoft Excel. Den innehåller information om de olika mallar som du kan använda beroende på vilken typ av transaktioner som du har angett."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 087339cb3002b42bcb985c2ccfc2d97c752a817c
ms.lasthandoff: 03/31/2017


---

# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicera journalrader och dokument från Microsoft Excel

Det här avsnittet beskrivs hur du anger och publicera rader för allmänna journaler från Microsoft Excel. Den innehåller information om de olika mallar som du kan använda beroende på vilken typ av transaktioner som du har angett.

Användarna kan ange och publicera rader för redovisningsjournaler från Microsoft Excel. När en användare skapar en journal i **öppna rader i Excel** visas knappen mallar som är tillgängliga. Mallar är utformade för att stödja speciella scenarier stöds dock inte alla kombinationer av kontotypen i journalen. Följande tabell visar de mallar som finns tillgängliga och kontotyper som de stöder.
|                          |                                                                                                                         |                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| **Template**             | **Kontotyper som stöds**                                                                                             | **Så här öppnar du mallen**                                                          |
| Redovisningsjournalrader     | Konto: Redovisning, kund, leverantör, Bank motbokas konto: redovisning, kund, leverantör, Bank koncerninterna stöds.       | Allmän journal                                                                         |
| Fakturaregister         | Konto: Leverantör motkonto: stöds inte för koncernintern redovisning.                                                    | AP fakturaregister                                                                     |
| Fakturajournal          | Konton: Leverantör motkonto: koncernintern redovisning som stöds.                                                      | Fakturajournal för LR                                                                      |
| Leverantörsfaktura           |                                                                                                                         | Leverantörsfaktura                                                                          |
| Kundfakturajournal | Konto: Kund motkonto: koncernintern redovisning som stöds.                                                     | Allmän journal                                                                         |
| Fritextfaktura        |                                                                                                                         | I den **fritextfaktura** klickar du på **öppna i Excel** (ikonen Microsoft Office). |
| Journal för anläggningstillgångar     | Tillgång till redovisnings-, bank, kund eller leverantör. Koncerninterna stöds inte.                                               | Journal för anläggningstillgångar                                                                     |
| Leverantörsbetalningsjournal   | Konto: Leverantör motkonto: redovisning, Bank koncerninterna stöds.                                                 | Leverantörsbetalningsjournal                                                                  |
| Kundbetalningsjournal | Konto: Kund motkonto: redovisning, Bank koncerninterna stöds.                                               | Kundbetalningsjournal                                                                |
| Projektutgiftsjournal  | Konto: Projekt, redovisning, kund, leverantör motbokas konto: projekt, redovisning, kund, leverantörens koncerninterna stöds. | Redovisningsjournal utgift (under projekthantering och redovisning)                       |

När rader har publicerats valideras för att kontrollera att de uppfyller de regler som anges i de ekonomiska journalerna. När rader publiceras användare redigera eller bokföra verifikationerna från Microsoft Dynamics 365 för operationer. 

Ytterligare ändringar krävs om du vill lägga till ekonomiska dimensioner i en mall. Mer information finns i [lägga till dimensioner i Microsoft Excel-mallen](\dev-itpro\financial-dimensions\add-dimensions-excel-templates). När dimensionerna läggs till entiteten är tillgängliga i Excel designer och kan läggas till i mallen.




