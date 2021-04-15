---
title: Bearbeta rabatter för betalning
description: I den här proceduren visas hur du konverterar godkända och bearbetade kundrabatter till kreditfakturor.
author: omulvad
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c617abd6ad715fff658451a7af3e775cf5e83292
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816470"
---
# <a name="process-rebates-for-payment"></a>Bearbeta rabatter för betalning

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]