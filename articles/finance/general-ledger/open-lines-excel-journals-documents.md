---
title: Publicera journalrader och dokument från Excel
description: I den här artikeln beskrivs hur du anger och publicerar rader för allmänna journaler från Microsoft Excel. Det innehåller information om de olika mallar som du kan använda beroende på vilken typ av transaktioner som du har angett.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 62213
ms.assetid: 211874a7-4bf0-4a0c-96c2-fa05042777d3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ccb3e7a420f7f048ba93b6fadf5491e312e7ce33
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872482"
---
# <a name="publish-journal-lines-and-documents-from-excel"></a>Publicera journalrader och dokument från Excel

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du anger och publicerar rader för allmänna journaler från Microsoft Excel. Det innehåller information om de olika mallar som du kan använda beroende på vilken typ av transaktioner som du har angett.

Användarna kan ange och publicera rader för redovisningsjournaler från Microsoft Excel. När en användare skapar en journal visar knappen **Öppna rader i Excel** de mallar som är tillgängliga. Mallar är utformade för att stödja speciella scenarier, men alla kombinationer av kontotypen i journalen stöds dock inte. Följande tabell visar de mallar som finns tillgängliga och kontotyper som de stöder.

| Mall             | Kontotyper som stöds | Så här öppnar du mallen                                                          |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Redovisningsjournalrader     | Konto: Redovisning, kund, leverantör, bankmotkonto: redovisning, kund, leverantör, Bank koncernintern stöds.       | Allmän journal                                                                         |
| Fakturaregister         | Konto: Leverantör motkonto: koncernintern redovisning stöds inte.                                                    | LR-fakturaregister                                                                     |
| Fakturajournal          | Konton: Leverantörsmotkonto: koncernintern redovisning stöds.                                                      | Fakturajournal för LR                                                                      |
| Leverantörsfaktura           |                                                                                                                         | Leverantörsfaktura                                                                          |
| Kundfakturajournal | Konto: Kundmotkonto: koncernintern redovisning stöds.                                                     | Allmän journal                                                                         |
| Fritextfaktura        |                                                                                                                         | På sidan **Fritextfaktura**, klicka på **Öppna i Excel** (Microsoft Office-ikonen). |
| Journal för anläggningstillgångar     | Tillgång till redovisning, bank, kund eller leverantör. Koncernintern stöds inte.                                               | Journal för anläggningstillgångar                                                                     |
| Leverantörsbetalningsjournal   | Konto: Leverantörsmotkonto: redovisning, bank koncernintern stöds.                                                 | Leverantörsbetalningsjournal                                                                  |
| Kundbetalningsjournal | Konto: Kundmotkonto: redovisning, bank koncernintern stöds.                                               | Kundbetalningsjournal                                                                |
| Projektutgiftsjournal  | Konto: Projekt, Redovisning, kund, leverantörsmotkonto: projekt, redovisning, kund, leverantör koncernintern stöds. | Redovisningsjournal utgift (under Projekthantering och redovisning)                       |

När rader har publicerats valideras de för att kontrollera att de uppfyller de regler som anges i de ekonomiska journalerna. När rader publiceras kan användare redigera eller bokföra verifikationerna från Dynamics 365 Finance. 

Ytterligare ändringar krävs om du vill lägga till ekonomiska dimensioner i en mall. Mer information finns i [Lägga till dimensioner i Microsoft Excel-mall](../../fin-ops-core/dev-itpro/financial/add-dimensions-excel-templates.md). När dimensionerna har lagts till i enheten är de tillgängliga i Excel-designern och kan läggas till i mallen.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
