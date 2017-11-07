---
title: "Ekonomiska råbalansrapporter"
description: "Den här artikeln beskriver standardrapporter för råbalanser. Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6405599186c8d07ac5ade19d3b7d27ae83b036ff
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="trial-balance-financial-reports"></a>Ekonomiska råbalansrapporter

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver standardrapporter för råbalanser. Det beskriver även de byggstenar som är associerade med dessa rapporter och hur du kan ändra rapporterna så att de passar ditt företags behov. 

<a name="default-trial-balance-reports"></a>Standardrapporter för råbalans
-----------------------------

Det finns tre råbalansrapporter i ekonomisk rapportering i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

| Standardrapport                                 | Vad den gör                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Detaljerad råbalans – standardinställning               | Visar saldoinformation för alla konton med och inkluderar debet- och kreditsaldon och nettot för dessa saldon, tillsammans med transaktionsdatum, verifikation och journalbeskrivning.                  |
| Råbalanssammanfattning - standardinställning                | Visar information om saldo för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens.                                        |
| Summerad råbalans på årsbasis – standardinställning | Visar saldoinformation för alla konton och inkluderar in- och utgående balanser och debet- och kreditsaldon tillsammans med deras nettodifferens för aktuellt år och föregående år. |

## <a name="building-blocks"></a>Byggstenar
Råbalansrapporterna använder följande byggstenar.

| Standardrapport                                 | Raddefinition          | Kolumndefinition                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Detaljerad råbalans – standardinställning               | Råbalans – standardinställning | Detaljerad råbalans – standardinställning               |
| Råbalanssammanfattning - standardinställning                | Råbalans – standardinställning | Råbalanssammanfattning – standardinställning                |
| Summerad råbalans på årsbasis – standardinställning | Råbalans – standardinställning | Summerad råbalans på årsbasis – standardinställning |

### <a name="row-definition"></a>Raddefinition

Raddefinitionen Råbalans – standard innehåller en rad som tar emot alla huvudkonton. Därför kan alla generera rapporten, utan att behöva göra några ändringar. När du visar rapporten borrar du till enskild rad om du vill se information om varje konto. Du kan ändra raddefinitionen så att den innehåller mer information. Om du vill ändra Råbalans – standardinställning så att den innehåller rader för alla konton, följer du stegen nedan.

1.  Klicka på **Redigera** och sedan på **Infoga rader från dimensioner**. Kommandot **Infoga rader från dimensioner** gör att du kan välja dimensionerna du vill ha i raddefinitionen. För den här raddefinitionen ska du använda **Huvudkonto**.
2.  Se till att **Huvudkonto** bara innehåller et-tecken och välj sedan **OK**.

Raddefinitionen innehåller nu alla huvudkonton för din juridiska standardperson.

### <a name="column-definition"></a>Kolumndefinition

Alla råbalansrapporter använder olika kolumndefinitioner. Dessa kolumndefinitioner innehåller olika typer av kolumner för att tillhandahålla andra nivåer av information och ekonomiska data.

-   **Detaljerad råbalans – standardkolumntyper:**
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **ACCT** – kontokoder
    -   **ATTR (3)** – attribut:
        -   Transaktionsdatum
        -   Verifikation
        -   Journalbeskrivning
    -   **FD** – ekonomisk data som bara innehåller debet
    -   **FD** – ekonomisk data som bara innehåller kredit
    -   **CALC** – nettoskillnaden
-   **Råbalanssammanfattning – standardkolumntyper:**
    -   **ACCT** – kontokoder
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **ATTR** – ett attribut:
        -   Verifikation
    -   **FD** – den ingående balansen
    -   **FD** – ekonomisk data som bara innehåller debet
    -   **FD** – ekonomisk data som bara innehåller kredit
    -   **CALC** – nettoskillnaden
    -   **CALC** – den utgående balansen
-   **Summerad råbalans på årsbasis – standardinställning:**
    -   **ACCT** – kontokoder
    -   **DESC** – beskrivningen från raddefinitionen.
    -   **ATTR** – ett attribut
        -   Verifikation
    -   **FD** – den ingående balansen för det innevarande året
    -   **FD** – ekonomisk data som bara innehåller debet för innevarande året
    -   **FD** – ekonomisk data som bara innehåller kredit för innevarande året
    -   **CALC** – nettoskillnaden
    -   **CALC** – den utgående balansen
    -   **FD** – ekonomisk data som bara innehåller debet för det senaste året
    -   **FD** – ekonomisk data som bara innehåller kredit för det senaste året

 

<a name="see-also"></a>Se även
--------

[Ekonomisk rapportering](financial-reporting-getting-started.md)

[Visa ekonomiska rapporter](view-financial-reports.md)

[Dynamics-ekonomirapporteringsblogg](http://blogs.msdn.com/b/dynamics_financial_reporting/)




