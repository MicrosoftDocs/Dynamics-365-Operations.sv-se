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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f641d75e06b11ca325d2624f836fc2a7c92d69e4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447913"
---
# <a name="establish-customer-payment-terms"></a>Upprätta villkor för kundbetalning

[!include [banner](../../includes/banner.md)]

I den här proceduren definieras kassarabatt- och förfallodatuminställningar. I den här uppgiftsguiden används demonstrationsföretaget USMF.

1. Gå till **navigeringsfönstret > Moduler > Kundreskontra > Betalningsinställning > Betalningsdagar**. Inställningar för **betalningsvillkoren** delas för **kundreskontra** och **leverantörsreskontra**. Om du definierar den i modulen, kommer den att vara tillgängliga i den andra modulen också. För den här uppgifthandbok ställer in I alla betalningsvillkor under **kundreskontra**.
2. Klicka på **Ny**. Skapa en betalningsdag, om betalningsvillkoret kräver en specifik dag i veckan (måndag, tisdag, etc.) eller ett visst datum i månaden (5:e, 10:e etc.). 
3. Ange ett ID i fältet **Betalningsdag**.
4. Ange en beskrivning av betalningsdagen i fältet **Beskrivning**.
5. Välj antingen veckan eller månaden i fältet **vecka-/månad**. Om du vill ange en dag i veckan, till exempel måndag, markera veckan. Om du vill ange ett datum i månaden, till exempel 10:e, välj månad. I det här exemplet väljer du Månad. 
6. Ange ett datum i fältet **Datum**. Datumet då anges som ett tal, till exempel ”10”, och inte som ”10:e”. 
7. Klicka på **Spara**.
8. Stäng sidan.
9. Gå till **navigeringsfönstret > Moduler > Kundreskontra > Betalningsinställning > Betalningsvillkor**.
10. Klicka på **Ny**. Betalningsvillkoren används för att definiera hur förfallodatumen ska beräknas. Kassarabattdatuminställningar definieras i en separat sida. 
11. Ange ett ID i fältet **Betalningsvillkor**.
12. Ange en beskrivning i fältet **beskrivning**.
13. Välj en **betalningsmetod**, t.ex. COD, netto, aktuell månad, etc. Betalningsmetoden används för att definiera starten på hur förfallo kommer att beräknas. Till exempel, netto används om förfallodatumet är alltid ett visst antal månader eller dagar efter fakturadatum. Postförskott kan användas för att, när betalning krävs vid faktura, så ett förfallodatum beräknas inte. Välj aktuell månad för den här uppgifthandbok.  
14. Välj en **betalningsdag**, om en specifik dag i veckan eller datum tas med i beräkningen. Beroende på betalningsvillkoret kan du ange en kvantitet i månader eller dagar. Du kan använda **betalningsplanen**, eller **betalningsdagen** ”till” lägger till slutet av betalningsmetoden. Om förfallodatumet är alltid 10:e i nästa månad, välj **betalningsdag** den 10:e. 
15. Klicka på **Spara**.
16. Stäng sidan.
17. Gå till **Kundreskontra > Betalningsinställning > Kassarabatter**.
18. Klicka på **Ny**. På den här sidan används för att definiera hur kassarabattdatum beräknas. 
19. Ange ett ID i fältet **Kassarabatt**.
20. Ange en beskrivning i fältet **beskrivning**.
21. Om en tiered kassarabatt är tillgänglig, väljer **nästa rabattkod** som gäller efter det nya kassarabatt.
22. Ange det antal **dagar** som används för att beräkna kassarabattdatumet. Om **Netto**-principen markeras, antal dagar ska läggas till fakturadatumet för att beräkna kassarabattdatumet.  
23. I fältet **Rabatt i procent** anger du procentandelen av kassarabatten.
24. I **Huvudkonto för kundrabatter** anger du det huvudkonto där kassarabatten ska bokföras för kundfakturor.
25. Välj alternativ på samma sätt som i fältet **Rabattmotkonton**. Om du väljer ”konton på fakturaraderna, ska bokföra kassarabatten till samma tillgångs/utgifthuvudkontot på raderna för leverantörsfakturan. Om du väljer Använd huvudkonto för leverantörsfakturor, kassarabatten ska bokföras i huvudkontot som du definierar i Använd huvudkonto för leverantörsfakturor. För det här exemplet väljs Använd huvudkonto för leverantörsfakturor. 
26. I **Huvudkonto för leverantörsrabatter** anger du det huvudkonto där kassarabatten ska bokföras för leverantörsfakturor.
27. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]