--- 
title: "Bearbeta rabatter för betalning"
description: "I den här proceduren visas hur du konverterar godkända och bearbetade kundrabatter till kreditfakturor."
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
ms.openlocfilehash: 73bfc08115a9727cbdcbe9b37e1427e67341dbd8
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="process-rebates-for-payment"></a>Bearbeta rabatter för betalning

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du konverterar godkända och bearbetade kundrabatter till kreditfakturor. Du kan använda den här guiden i demonstrationsföretaget USMF. Förhandsvillkoret för den här guiden är att ha ett eller flera rabattanspråk som har statusen Markera. Om du använder USMF ska du köra guiden "Generera och bearbeta kundrabatter" innan du startar den här guiden.


## <a name="convert-rebate-claims-to-credit-note"></a>Konvertera rabattanspråk till kreditfaktura
1. Gå till Alla kunder.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Inkasso i åtgärdsfönstret.
5. Klicka på Kvitta transaktioner.
6. Klicka på Funktioner.
7. Klicka på Rabattprogram.
    * På sidan Rabatt visas de rabattanspråk som du har bearbetat i workbenchen för kundrabatten och som har statusen "Markera".    
8. Klicka på Redigera.
    * Markera fältet Markera för de anspråk som du vill inkludera i kreditfakturan.   
9. Klicka på Funktioner.
10. Klicka på Skapa kreditfaktura.
    * Ett meddelande visas för att informera dig om att en journal har bokförts (detta är den journal för kundreskontraförbrukning som har angetts på sidan Parametrar för kundreskontra). Detta gör att real skuld (kredit) belopp som skall flyttas till kunden. Det innebär att kundens konto har krediterats och att periodiseringskontot för rabatt har debiterats.  
11. Stäng sidan.
12. Klicka på Avbryt.
    * Detta uppdaterar sidan, så att du kan se uppdateringarna.  
13. Klicka på Inkasso i åtgärdsfönstret.
14. Klicka på Kvitta transaktioner.
    * Observera att en transaktion för negativt belopp som motsvarar det totala rabattbeloppet utan fakturareferens har lagts till kundbalansen.   
15. Klicka på Avbryt.

