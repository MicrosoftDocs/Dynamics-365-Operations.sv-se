---
title: Återför journalbokföring
description: I det här avsnittet beskrivs funktioner som gör att du kan återföra verifikationer från en verifikationstransaktionslista eller från ekonomiska journaler.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248595"
---
# <a name="reverse-journal-posting"></a>Återför journalbokföring

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs Dynamics 365 Finance-funktioner i Microsoft som gör att du kan återföra en hel journal eller återföra en eller flera verifikationer från verifikationstransaktionslistan oavsett ursprung. 

## <a name="reversing-journals"></a>Återföra journaler

Du kan återföra journalrader individuellt. Med en omvänd journalbokföring kan du även återföra en hel redovisningsjournal. För att återföra en journal: 
- Öppna redovisningsjournalen och filtrera på bokförda journaler
- Klicka på menyn Återför högst upp på sidan.
- Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.
- Välj Ja om du vill använda de befintliga transaktionsdatumen eller Nej om du vill ange ett nytt. I vissa fall kan perioden för den ursprungliga transaktionen stängas och du vill ange ett nytt transaktionsdatum för återföringen.
- Om du har valt nej anger du ett transaktionsdatum för återföringen. 
- Ange en kommentar som du vill lägga till i återföringstransaktionen
- Klicka på knappen Återför.

Transaktionerna kommer att återföras. 

Om antalet verifikationsrader överstiger 100 rader, kommer återföringsprocessen att köras med batch-processen. Du kan granska resultatet av återföringen genom att visa kommentarerna i batch-jobbet som kördes. Alla fel kommer att anges i historiken för batchjobb.

Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart. Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras. Klicka på Ok för att stänga dialogrutan

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Återför verifikationer från listan med verifikationstransaktioner. 

Du kan även återföra verifikationer från **transaktionslistan för verifikationer** i alla redovisningstransaktioner. Dessutom kan du återföra fler än en verifikation åt gången. 

Så här återför du en eller flera verifikationer: 
- Klicka på menyn Återför högst upp på sidan.
- Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.
- Välj Ja om du vill använda de befintliga transaktionsdatumen eller Nej om du vill ange ett nytt. I vissa fall kan perioden för den ursprungliga transaktionen stängas och du vill ange ett nytt transaktionsdatum för återföringen.
- Om du har valt nej anger du ett transaktionsdatum för återföringen. 
- Ange en kommentar som du vill lägga till i återföringstransaktionen
- Klicka på knappen Återför.

Transaktionerna kommer att återföras. 

Om antalet verifikationsrader överstiger 100 rader, kommer återföringsprocessen att köras med batch-processen. Du kan granska resultatet av återföringen genom att visa kommentarerna i batch-jobbet som kördes. Alla fel kommer att anges i historiken för batchjobb.

Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart. Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras. Klicka på Ok för att stänga dialogrutan

