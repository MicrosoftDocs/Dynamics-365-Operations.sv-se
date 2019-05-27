---
title: Sätta in kundbetalningar
description: Insättning av kundbetalningar.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565495"
---
# <a name="deposit-customer-payments"></a>Sätta in kundbetalningar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Insättning av kundbetalningar. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Kundreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Välj betalningsjournal. 
5. Klicka på Rader.
6. Ange kund som du har tagit emot en betalning för i fältet Konto.
7. Ange beloppet i fältet Kredit.
    * Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.  
8. Skriv ett värde i fältet Betalningsreferens.
    * Betalningsreferensen kan vara checknumret för en betalning som du anger. Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.  
9. Välj rutan Använd ett insättningskvitto.
    * Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.  
10. Klicka på Ny.
11. Välj kund för nästa betalning i fältet Konto.
12. Ange betalningsbeloppet i fältet Kredit.
13. Skriv ett värde i fältet Betalningsreferens.
14. Välj rutan Använd ett insättningskvitto.
15. Klicka på Bokför.
    * Betalningar måste bokföras, för insättningskvittot kan genereras. Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.  
16. Klicka på Funktioner.
17. Klicka på Insättningskvitto.
18. Klicka på OK.
    * Den första sidan används för att skapa insättningskvittot.  
19. Klicka på OK.
    * I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.  

