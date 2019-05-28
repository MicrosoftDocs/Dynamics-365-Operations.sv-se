---
title: Upprätta villkor för kundbetalning
description: I den här proceduren definieras kassarabatt- och förfallodatuminställningar.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49f4047ab4bff6bdfbe8326a6680f9d8f9762c95
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547943"
---
# <a name="establish-customer-payment-terms"></a>Upprätta villkor för kundbetalning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren definieras kassarabatt- och förfallodatuminställningar. I den här uppgiftsguiden används demonstrationsföretaget USMF.

1. Gå till Kundreskontra > Betalningsinställning > Betalningsdagar.
    * Inställningar för betalningsvillkoren delas för kundreskontra och leverantörsreskontra. Om du definierar den i modulen, kommer den att vara tillgängliga i den andra modulen också. För den här uppgifthandbok ställer in I alla betalningsvillkor under kundreskontra.  
2. Klicka på Ny.
    * Skapa en betalningsdag, om betalningsvillkoret kräver en specifik dag i veckan (måndag, tisdag, etc.) eller ett visst datum i månaden (5:e, 10:e etc.).  
3. Ange ett ID för betalningsdagen i betalningsdagfältet i betalningsdagfältet.
4. Ange en beskrivning av betalningsdagen i fältet Beskrivning.
5. Välj antingen veckan eller månaden i vecka-/månadfältet.
    * Om du vill ange en dag i veckan, till exempel måndag, markera veckan. Om du vill ange ett datum i månaden, till exempel 10:e, välj månad. I det här exemplet väljer du Månad.  
6. Ange ett datum i fältet Datum.
    * Datumet då anges som ett tal, till exempel ”10”, och inte som ”10:e”.  
7. Klicka på Spara.
8. Stäng sidan.
9. Gå till Kundreskontra > Betalningsinställning > Betalningsvillkor.
10. Klicka på Ny.
    * Betalningsvillkoren används för att definiera hur förfallodatumen ska beräknas. Kassarabattdatuminställningar definieras i en separat sida.  
11. I betalningsvillkoret infogas ett ID i betalningsvillkorfältet.
12. Ange en beskrivning i beskrivningsfältet.
13. Välj en betalningsmetod, till exempel postförskott, netto, aktuell månad, etc.
    * Betalningsvillkoren används för att definiera hur förfallodatumen börjar beräknas.  Till exempel, netto används om förfallodatumet är alltid ett visst antal månader eller dagar efter fakturadatum. Postförskott kan användas för att, när betalning krävs vid faktura, så ett förfallodatum beräknas inte. Välj aktuell månad för den här uppgifthandbok.  
14. Välj en betalningsdag, om en specifik dag i veckan eller datum tas med i beräkningen.
    * Beroende på betalningsvillkoret kan du ange en kvantitet i månader eller dagar. Du kan använda betalningsplanen, eller betalningsdagen ”till” lägger till slutet av betalningsmetoden. Om förfallodatumet är alltid 10:e i nästa månad, välj betalningsdag den 10:e.  
15. Klicka på Spara.
16. Stäng sidan.
17. Gå till Kundreskontra > Betalningsinställning > Kassarabatter.
18. Klicka på Ny.
    * På den här sidan används för att definiera hur kassarabattdatum beräknas.  
19. Ange ett ID i kassarabattfältet i kassarabattfältet.
20. Ange en beskrivning i beskrivningsfältet.
21. Om en tiered kassarabatt är tillgänglig, väljer nästa rabattkoden som gäller efter det nya kassarabatt.
22. Ange det antal dagar som används för att beräkna kassarabattdatumet.
    * Om Nettoprincipen markeras, antal dagar ska läggas till fakturadatumet för att beräkna kassarabattdatumet.  
23. Ange procentbeloppet för kassarabatten.
24. Ange huvudkontot som kassarabatten ska bokföras på för kundfakturor.
25. Välj alternativ på samma sätt som i fältet Rabattmotkonton.
    * Om du väljer ”konton på fakturaraderna, ska bokföra kassarabatten till samma tillgångs/utgifthuvudkontot på raderna för leverantörsfakturan. Om du väljer Använd huvudkonto för leverantörsfakturor, kassarabatten ska bokföras i huvudkontot som du definierar i Använd huvudkonto för leverantörsfakturor. För det här exemplet väljs Använd huvudkonto för leverantörsfakturor.  
26. Ange huvudkontot som kassarabatten ska bokföras på för leverantörsfakturor.
27. Klicka på Spara.

