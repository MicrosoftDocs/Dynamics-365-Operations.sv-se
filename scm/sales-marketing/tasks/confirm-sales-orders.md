--- 
title: "Bekräfta försäljningsorder"
description: "I den här proceduren visas hur du bekräftar försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b0853e6a326a90b022bedc3b898d6c1b218c5fa2
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="confirm-sales-orders"></a>Bekräfta försäljningsorder

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du bekräftar försäljningsorder. Du får reda på hur du bekräftar en enstaka order och hur du bekräftar flera order på en gång. Dessa uppgifter utförs vanligtvis via en försäljningsorderbehandlare. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Kontrollera att det finns flera öppna försäljningsorder för samma kund innan du börjar. Om du använder USMF kan du använda kunden US-027.


## <a name="confirm-a-single-sales-order"></a>Bekräfta en enskild försäljningsorder
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Hitta och markera den order du vill bekräfta i listan.
3. Klicka på länken för försäljningsordernumret för att öppna den valda ordern.
4. Klicka på Sälj i åtgärdsfönstret.
5. Klicka på Bekräfta försäljningsorder.
6. Utöka eller komprimera avsnittet Parametrar.
    * Kontrollera att fältet Bokföring ja är aktivt.  
7. Ställ in alternativet Skriv ut bekräftelse på Ja.
    * Fältet Checkkreditgräns anger vilken metod som ska användas för att beräkna en kunds återstående kredit. Som standard kopieras den från sidan Parametrar för kundreskontra. Om du vill hoppa över kreditgränskontrollen när du bekräftar en specifik försäljningsorder anger du checkkreditgränsen till Ingen. Du bör dock vara medveten om att även om det här fältet är inställt på Ingen, så kommer kreditgränskontrollen fortfarande att utföras om alternativet Obligatorisk kreditgräns har valts i kundhuvuddata.  
8. Klicka på OK.
9. Klicka på Ja.
10. Stäng sidan.
11. Klicka på Alternativ i åtgärdsfönstret.
12. Klicka på Ändra vy.
13. Klicka på Huvudvy.
    * När en order har bekräftats anges dokumentstatusen till Bekräftelse.  
14. Klicka på Sälj i åtgärdsfönstret.
15. Klicka på Försäljningsorderbekräftelse.
16. Stäng sidan.

## <a name="confirm-multiple-sales-orders-at-once"></a>Bekräfta flera försäljningsorder samtidigt
1. Gå till Försäljning och marknadsföring > Försäljningsorder > Orderbekräftelse > Bekräfta försäljningsorder.
2. Klicka på Välj.
3. Välj den post som refererar till fältet Kundkonto i listan på fliken Intervall.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kriterier.
5. Hitta och välj kundkontot som har flera order som du vill massbekräfta.
    * Om du använder USMF kan du välja kontot US-027.  
6. Klicka på OK.
    * På fliken Översikt visas en lista över order som matchar frågekriterierna. Dessa inkluderas i bekräftelsen.  
    * I fältet Samlingsuppdatering för anges den parameter som ska användas för att summera flera order till ett bekräftelsedokument. Som standard kopieras alternativet från inställningen Standardvärden för samlingsuppdatering på sidan Parametrar för kundreskontra.  
7. Välj "Order" i Samlingsuppdatering för fält.
    * Minimiparametrarna som krävs för att skapa samlingsuppdateringar är Fakturakonto och Valuta. Det innebär att samlingsuppdateringar som har olika fakturakonton och olika valutor inte är tillåtna. Ytterligare parametrar kan ställas in på sidan Samlingsuppdateringsparametrar som är tillgänglig från sidan Parametrar för kundreskontra.  
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsorder.
9. Markera det ordernummer som du vill ska vara samlingsorder i listan.
10. Klicka på Ordna.
11. Klicka på OK.
12. Klicka på OK.


