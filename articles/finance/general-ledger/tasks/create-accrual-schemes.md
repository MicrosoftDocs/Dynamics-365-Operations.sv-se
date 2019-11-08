---
title: Skapa periodiseringsscheman
description: Det här avsnittet innehåller information om hur du skapar periodiseringsschema.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8f8cf8546187ae1c65d4966887e1c5842dff431
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175640"
---
# <a name="create-accrual-schemes"></a>Skapa periodiseringsscheman

[!include [task guide banner](../../includes/task-guide-banner.md)]

Det här avsnittet innehåller information om hur du skapar periodiseringsschema. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalkonfiguration > Periodiseringsscheman**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Identifiering av periodisering**.
4. Skriv ett värde i fältet **Beskrivning av periodiseringsschema**.
5. Ange önskade värden i fältet **Debet**. Det definierade huvudkontot ersätter debethuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.  
6. Ange önskade värden i fältet **Kredit**. Det definierade huvudkontot ersätter kredithuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.  
7. I fältet **Verifikation** väljer du hur du vill att verifikationen ska fastställas när transaktionerna bokförs.
8. I fältet **Beskrivning** skriver du ett värde som beskriver vilka transaktioner som ska bokföras.
9. Välj hur ofta transaktionerna ska ske i fältet **Periodfrekvens**.
10. Ange ett värde i fältet **Antal förekomster per period**.
11. I fältet **Bokför transaktioner** väljer du när transaktionerna ska bokföras, till exempel **Varje månad**.
