---
title: "Konfigurera leverantörsreskontra"
description: "Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra i Microsoft Dynamics AX. Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: b06623a0eb754654f41c50b92af67dc94a069663
ms.lasthandoff: 03/31/2017


---

# <a name="configure-accounts-payable"></a>Konfigurera leverantörsreskontra

Det här avsnittet innehåller en beskrivning av de sidor som används för att ställa in grundläggande och valfria funktion för Leverantörsreskontra i Microsoft Dynamics AX. Även inställningsstegen som du måste vidta innan du börjar ställa in Leverantörsreskontra beskrivs.

<a name="prerequisites-for-accounts-payable-setup"></a>Krav för inställning av leverantörsreskontra
----------------------------------------

Följande inställning måste göras innan det går att ställa in leverantörsreskontra:

-   I Redovisning:
    -   Om du tänker använda betalningsjournaler, konfigurera betalningsjournaler.
    -   Om du tänker använda valutakursjusteringar, ställ in valutakoder på sidan Valutor, ställ in valutakurstyper på sidan Valutakurstyp och ställ in valutakurser på sidan Valutakurs.
-   Ställ in bankkonton som används med betalningsmetoder i Kassa- och bankhantering.

## <a name="setup-pages-for-accounts-payable"></a>Installationssidorna för Leverantörsreskontra

Använd följande sidor när du vill ställa in de grundläggande funktioner i Leverantörsreskontra för varje juridisk person. Sidorna visas i rekommenderad inställningsordning. Du kan göra inställningsprocessen enklare genom att skapa mallar från de första posterna som du skapas. I en mall anges vanligtvis poster i många fält för att avspegla de funktioner organisationen vill implementera för en viss leverantörstyp.
1.  Definiera betalningsvillkor som du tilldelar till försäljningsorder, inköpsorder, kunder och leverantörer och som fastställer fakturornas förfallodatum på sidan Betalningsvillkor.
2.  Skapa och underhåll information om hur organisationen betalar sina leverantörer på sidan Betalningsmetoder - leverantörer.
3.  Skapa och underhåll grupper av leverantörer med gemensamma nyckelparametrar för bokföring, kvittning och betalning, rapportering och prognostisering på sidan Leverantörsgrupper.
4.  Definiera hur leverantörstransaktioner bokförs i redovisningen på sidan Bokföringsprofiler för leverantörer.
5.  Konfigurera standardinställningar som tillämpas om en mer specifik inställning inte anges, parametrar för olika funktionstyper samt olika nummersekvenser för leverantörsreskontra på sidan Parametrar för leverantörsreskontra.
6.  Definiera formatet för olika dokument som rör leverantörer och som används inom organisationen för att spåra inleveranser från leverantörer samt för att ange orsaker för betalningsflöden till leverantörer på sidan Formulärinställningar.
7.  Skapa och underhåll leverantörskonton och även de skattemyndigheter som organisationen rapporterar moms till på sidan Leverantörer.

## <a name="optional-setup-pages-for-accounts-payable"></a>Valfria inställningar sidor för Leverantörsreskontra
Utöver de grundläggande funktionerna har Leverantörsreskontra andra funktioner som du kan ställa in.

De ytterligare inställningssidorna som används ordnas efter funktion.

**Policies**
-   Ställ in leverantörsfakturapolicyer på sidan Leverantörens fakturapolicy.

**Invoice matching**

-   Ställ in toleranser för fakturasummor på sidan Toleranser för fakturasummor.
-   Ställ in matchningspolicyer för tvåvägs- och trevägsmatchningspolicyer på sidan Matchningspolicy.
-   Ställ in toleranser för enhetspriser på sidan Pristoleranser.
-   Ställ in toleransgrupper för artikelpriserna på sidan Toleransgrupper för artikelpris.
-   Ställ in toleransgrupper för leverantörspriserna på sidan Toleransgrupper för leverantörspris.
-   Ställ in toleranser för avgifter på sidan Avgiftstoleranser.

**Workflow**

-   Ställ in arbetsflödeskonfigurationen för journalgodkännanden och inköpsrekvisitioner på sidan Arbetsflöden för leverantörsreskontra.

**Reasons**

-   Ställ in orsakskoder på sidan Leverantörsorsaker.

**Charges**

-   Ställ in koder för avgifter som används i inköpsorder på sidan Kod för avgifter.
-   Skapa och underhåll grupper för leverantörer på sidan leverantör avgifter grupp.
-   På sidan Avgiftsgrupper för artikel, skapa och underhåll avgiftsgrupper för artiklar.
-   På sidan Automatiska avgifter, definiera de inköpstillägg som tilldelas automatiskt för order.

**Supplementary items**

-   På sidan Fyllnadsartikelgrupper - Leverantör, skapa och underhåll fyllnadsartikelgrupper för leverantörer.
-   På sidan Fyllnadsartikelgrupper - Lager, skapa och underhåll fyllnadsartikelgrupper för artiklar.

**Distribution**

-   Skapa och underhåll villkor för en artikels överföring från säljaren till köparen på sidan Leveransvillkor.
-   På sidan Leveranssätt, skapa och underhåll transportsätt som används när en order levereras från säljaren till köparen.
-   På sidan Destinationskoder, skapa och underhåll identifierare och beskrivningar för leveransdestinationer.

**Forms**

-   På sidan Formulärnoteringar, skapa den standardtext som visas på olika sidor.
-   På sidan Parametrar för formulärsortering, ange sorteringsordning för rekvisitioner, inleveranslistor, följesedlar och fakturor.
-   På sidan Inställningar för utskriftshantering, ställ in information om utskriftshantering för original och kopior av sidor.

**Payments**

-   På sidan, ställ in och underhåll villkoren för erhållande av kassarabatter. Kassarabattkoderna är kopplade till leverantörer och tillämpas på inköpsorder.
-   På sidan Betalningsplaner, ställ in betalningsplaner som används för hantering av avbetalningar till leverantörer.
-   På sidan Betalningsdagar, definiera betalningsdagar som används för beräkning av förfallodatum och ange betalningsdagar för en specifik dag i veckan eller månaden.
-   På sidan Betalningsavgift, skapa och underhåll betalningsavgifter som är associerade med leverantörer.
-   På sidan Betalningsinstruktion, skapa och underhåll betalningsinstruktioner.

**Statistics**

-   På sidan Definitioner för åldersfördelningsperiod, ställ in användardefinierade intervall för analys av förfallodagsfördelningen för leverantörskonton.
-   På sidan Affärsområde, skapa affärsområdeskoderna (LOB) som tilldelas leverantörer.

**1099-skatt**

-   I den **1099-fält** sidan Kontrollera och uppdatera de minimibelopp som ska rapporteras till den tjänsten IRS (Internal Revenue), baserat på de senaste IRS-kraven.

## <a name="optional-setup-for-other-modules"></a>**Valfria inställningar för andra moduler**
**Organization administration**

-   På sidan Nummerserier, ställ in nummerseriegrupper för fakturanummer.
-   Ange adressinformation på efterföljande sidor:
    -   Adressinställning
    -   NAF-koder
    -   Importera postnr

**General ledger**

-   På sidanEkonomiska dimensioner, ställ in ekonomiska dimensioner.
-   Konfigurera skatteinformation på följande sidor:
    -   Momskoder
    -   Momsgrupper
    -   Artikelmomsgrupper
    -   Kontogrupp
    -   Momsbefrielsekoder
    -   Skattemyndigheter
    -   Skattemyndigheter
    -   Momskvittningsperioder

**Cash and bank management**

-   Ställ in centralbankens syfteskoder på sidan Syfteskoder för betalning



