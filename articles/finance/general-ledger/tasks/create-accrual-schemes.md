---
title: Skapa periodiseringsscheman
description: Den här artikeln innehåller information om hur du skapar periodiseringsschema.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8974eed40a60aeee5a32932ac070a870289ec20a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858437"
---
# <a name="create-accrual-schemes"></a>Skapa periodiseringsscheman

[!include [banner](../../includes/banner.md)]

Den här artikeln innehåller information om hur du skapar periodiseringsschema. I den här uppgiften används demonstrationsföretaget USMF.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
