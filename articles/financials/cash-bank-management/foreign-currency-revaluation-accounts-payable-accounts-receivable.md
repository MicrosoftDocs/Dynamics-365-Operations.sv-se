---
title: "Omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra"
description: "Variationer i valutakurser gör att det teoretiska värdet (bokförda värdet) för öppna kundtransaktioner i utländska valutor varierar över tiden. Den här artikeln innehåller information om den process för omräkning i utländsk valuta som du kör om du vill uppdatera värdet för öppna transaktioner i Leverantörsreskontra och Kundreskontra."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 259b487b0f11b19af9609d63f12114dcaa61be52
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="foreign-currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>Omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra

[!include[banner](../includes/banner.md)]


Variationer i valutakurser gör att det teoretiska värdet (bokförda värdet) för öppna kundtransaktioner i utländska valutor varierar över tiden. Den här artikeln innehåller information om den process för omräkning i utländsk valuta som du kör om du vill uppdatera värdet för öppna transaktioner i Leverantörsreskontra och Kundreskontra. 

Det teoretiska värdet (bokförda värdet) för öppna leverantörstransaktioner i utländska valutor varierar över tiden med förändringar av valutakursen. Om du vill uppdatera värdet för öppna transaktioner i Leverantörsreskontra och Kundreskontra kan du köra processen för omvärdering i utländsk valuta . Omräkning i utländsk valuta kan köras för Leverantörsreskontra och Kundreskontra Processen använder en ny valutakurs för omvärdering av de öppna beloppen eller ej kvittade belopp, på ett angivet datum. Skillnaderna mellan de ursprungliga bokförda belopp och de revalverade belopp orsakar en orealiserad vinst eller förlust för varje öppen transaktion. Leverantörsreskontra och Kundreskontra uppdateras sedan för att avspegla den orealiserade vinsten eller förlusten, och en bokföringspost ska bokföras i redovisningen.

## <a name="simulate-a-foreign-currency-revaluation"></a>Simulera en omräkning i utländsk valuta
Innan du omvärderar utländska valutabelopp för öppna transaktioner, kan du köra en simuleringsrapport av omräkningen av utländska valutabelopp för samma datum och metod. Om du vill köra simuleringsrapporten kan du på sidan **Omvärdering i utländsk valuta** klicka på knappen **Prissimulering**. Rapporten innehåller en förhandsgranskning av orealiserad vinst eller förlust baserad på de parametrar som är definierade för simuleringen.

## <a name="process-a-foreign-currency-revaluation"></a>Bearbeta en omvärdering i utländsk valuta
Använd **omvärdering i utländsk valuta** sidan under **periodiska uppgifter** för att omvärdera öppna transaktioner. Du kan köra processen i realtid eller schemalägga den för att köra med en batch. När du definierar inställningar för omvärderingsprocessen, bör du kontrollera om du vill skriva ut en rapport över resultaten. Omvärderingsrapporten kan inte skrivas ut på nytt när processen är klar. Om du genererar en rapport för omräkning i utländsk valuta kommer den att visa olika saldon på kund-/leverantörnivån och valutanivån:

-   Saldona för kunder eller leverantörer som har transaktioner i utländsk valuta, som har omvärderats. Följande saldon visas:
    -   Det totala ursprungliga saldot i utländsk valuta.
    -   Det totala beloppet i utländsk valuta, i redovisningsvalutan som den föregående omvärderingen.
    -   Det totala beloppet i utländsk valuta, i redovisningsvalutan som den nuvarande omvärderingen.
    -   Differensen mellan föregående och nuvarande omvärdering. Denna skillnad är den ytterligare orealiserade vinsten eller förlusten.
-   Den totala orealiserade vinsten eller förlusten för varje valuta.

En registrering görs varje gång du kör en omräkning i utländsk valuta. Från registreringen på sidan **Värdering i utländsk valuta** väljer du **Transaktioner** om du vill visa den detaljerade listan över transaktioner som har skapats på grund av omvärdering. Varje verifikationstransaktion representerar den öppna transaktionen som omvärderades. Om en öppen transaktion har omvärderas mer än en gång, visas två poster som använder samma verifikation. En post ska gälla för återföringen av föregående orealiserade vinst eller förlust, och den andra posten ska gälla för den nya orealiserade vinsten eller förlusten. Om du vill köra omvärderingsprocessen klickar du på knappen **Omvärdering i utländsk valuta** Definiera lämpliga inställningar för följande parametrar:

-   **Metod** – Metoden som användes i det valda jobbet för omräkning i utländsk valuta.
    -   **Standard** – Jobben för omräkning i utländsk valuta bokförs oavsett om resultatet är en vinst eller en förlust.
    -   **Minimum** – Minsta innebär att jobben för omräkning i utländsk valuta endast bokförs om resultatet är en förlust.
    -   **Fakturadatum** – Fakturadatum innebär att jobben för omräkning i utländsk valuta använder den ursprungliga valutakursen för transaktionerna, som omvärderas till sitt ursprungliga värde i redovisningsvalutan. Effekten av eventuella föregående omräkningar i utländsk valuta annulleras.
-   **Övervägt datum** – Datumet då alla transaktioner som har öppna (ej kvittade) belopp på det datumet hittas. Belopp i utländsk valuta omvärderas med hjälp av valutakurserna som anges i på sidan **Valutakurser** för det övervägda datumet. När belopp i utländsk valuta omvärderas på ett övervägt datum, blir detta datum det sista datumet för omräkning i utländsk valuta för de transaktioner som justeras. Om du bestämmer dig för att köra en omräkning i utländsk valuta för ett övervägt datum som är tidigare än det senaste datumet för omräkning i utländsk valuta på redan justerade transaktioner, justerar inte det periodiska jobbet de transaktioner som är öppna på det tidigare övervägda datumet men som har ett nyare senaste datum för omräkning i utländsk valuta genom det periodiska jobbet.
-   **Kursdatum** – Datumet som bestämmer valutakursen som används i transaktionen för omräkning i utländsk valuta.
-   **Använd bokföringsprofilen från** - Bokföringsprofilen som används för att ange standardhuvudkontot för Kundreskontra eller Leverantörsreskontra för redovisningsposterna av omräkning i utländsk valutatransaktionerna:
    -   **Bokföring** – Bokföringsprofilen för kundtransaktionen används.
    -   **Välj** – Ange bokföringsprofil i fältet **Bokföringsprofiler**.
-   **Bokföringsprofil** – Om **Välj** är markerad i fältet **Använd bokföringsprofil från** bestämmer den bokföringsprofil som du anger i det här fältet bokföringsprofilen för omvärderingstransaktionerna i utländsk valuta.
-   **Ekonomiska dimensioner** – De ekonomiska dimensionerna som bokförs i redovisningsposterna för omräkning i utländsk valuta.
    -   **Ingen** – Inga ekonomiska dimensioner bokförs. Om du har en obligatorisk ekonomisk dimension i din kontostruktur, körs omvärderingsprocessen fortfarande och skapar redovisningsposter som saknar ekonomiska dimensioner. Du får ett varningsmeddelande först, så att du kan avbryta omvärderingen.
    -   **Register** – De ekonomiska dimensionerna för kundkontot eller leverantörskontot bokförs i transaktioner för omräkning i utländsk valuta.
    -   **Bokföring** – De ekonomiska dimensionerna för transaktionen som omvärderas bokförs i transaktioner för omräkning i utländsk valuta. Som standard ska ekonomiska dimensioner från den ursprungliga transaktionens AR/AP-redovisningskonto användas för omvärderingtransaktionens huvudkontot för AR/AP, och ekonomiska dimensioner från den ursprungliga transaktionens kostnader/tillgångar/intäktsredovisningskonto ska användas för omvärderingtransaktionens huvudkontot för orealiserad vinst/förlust.





