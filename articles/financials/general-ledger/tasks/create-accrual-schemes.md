---
title: Skapa periodiseringsscheman
description: Den här uppgiften leder dig genom stegen för att skapa ett periodiseringsschema.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553141"
---
# <a name="create-accrual-schemes"></a>Skapa periodiseringsscheman

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften leder dig genom stegen för att skapa ett periodiseringsschema. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Redovisning > Journalkonfigurering > Periodiseringsscheman.
2. Klicka på Ny.
3. Skriv ett värde i fältet Identifiering av periodisering.
4. Skriv ett värde i fältet Beskrivning av periodiseringsschema.
5. Ange önskade värden i fältet Debet.
    * Det definierade huvudkontot ersätter debethuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.  
6. Ange önskade värden i fältet Kredit.
    * Det definierade huvudkontot ersätter kredithuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.  
7. I fältet Verifikation väljer du hur du vill att verifikationen ska fastställas när transaktionerna bokförs.
8. I fältet Beskrivning skriver du ett värde som beskriver vilka transaktioner som ska bokföras.
9. Välj hur ofta transaktionerna ska ske i fältet Periodfrekvens.
10. Ange ett värde i fältet Antal förekomster per period.
11. I fältet Bokför transaktioner väljer du när transaktionerna ska bokföras, till exempel varje månad.

