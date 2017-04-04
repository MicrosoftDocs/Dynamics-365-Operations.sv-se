---
title: "Kostnaden styra mobil arbetsytan för Microsoft Dynamics 365 för operationer app"
description: "Med kostnaden kan styra mobil arbetsytan, cost center chefer Se center kostnadseffektivitet när som helst och var som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Kostnaden styra mobil arbetsytan för Microsoft Dynamics 365 för operationer app

Med kostnaden kan styra mobil arbetsytan, cost center chefer Se center kostnadseffektivitet när som helst och var som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om Microsoft Dynamics 365 för operationer | [Dynamics 365 för operationer](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 för operationer                                          | Försäkra dig om att du använder en miljö med Microsoft Dynamics 365 för operationer version 1611 och uppdatera Microsoft Dynamics för operationer 3 (November 2016). |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigering om du vill aktivera arbetsytor som finns i Microsoft Dynamics 365 för operationer.                                                                       |
| Mobil enhet med Dynamics 365 för operationer program installerat | Hämta mobiltelefonprogrammet lagringsplatsen Dynamics 365 för operationer app.                                                                                                      |

## <a name="introduction"></a>Introduktion
Kontrollera mobil arbetsytan kostnaden ger en översikt över aktuell prestanda för kostnadsställen genom att jämföra faktiska kostnader mot de budgeterade kostnaderna. Du kan gå ner status för enskilda kostnadselement.

### <a name="example"></a>Exempel

Medarbetaren får en inbjudan till en internationell konferens. Organisationen måste omfatta alla resekostnader. Medarbetaren får sin Manager om han kan delta i konferensen. Hon öppnar chefen kostnaden mobil arbetsytan sin mobiltelefon styr om han har budgeten för medarbetaren som ska delta i konferensen.

### <a name="data-security"></a>Datasäkerhet

Data i arbetsytan styr kostnaden skyddas av användarens autentiseringsuppgifter. Kostnaden center projektledare får endast se data för eget kostnadsställe. Access postnivåsäkerhet hanteras inom kostnadsredovisningsmodulen. Kostnaden revisorer definiera kostnaden Kontrollera konfigurationen för mobil arbetsytan i kostnadsredovisningsmodulen. När arbetsytan publiceras till Microsoft Dynamics 365 for app operationer, är det i Dynamics 365 för mobiltelefonprogrammet operationer. Detta säkerställer att alla kostnader center chefer i organisationen granskar data i samma format.

### <a name="actions-views-and-links"></a>Åtgärder, vyer och länkar

Kontrollera mobil arbetsytan för Dynamics 365 för operationer app kostnaden innehåller följande åtgärder, vyer och länkar:

-   Åtgärder 
    -   Välj **konfigurationer** att välja en layout.
    -   Välj **kostnadsbärare** att välja kostnadsställen som du vill filtrera data. **Anmärkning:** listan visas enligt åtkomst i modulen kostnadsredovisning.

<!-- -->

-   Utifrån vad som är markerat **åtgärder** och vad konfigureras i modulen kostnadsredovisning kan du visa följande information i fältet. Tänk på att beloppet är i samma format: faktiskt, Budget och avvikelsen avvikelsen %. 
    -   Utfall kontra Budget (aktuell period)
    -   Utfall kontra budget omarbetad (aktuell period)
    -   Utfall kontra Budget (föregående period)
    -   Utfall kontra budget omarbetad (föregående period)
    -   Utfall kontra Budget (hittills under året)
    -   Utfall kontra budget omarbetad (hittills under året)

<!-- -->

-   Länkar
    -   Detaljer för aktuell period.
    -   Detaljer för föregående period.
    -   Detaljer för hittills under året.

När du väljer någon av länkarna visas ett kort per kostnadsfaktorn. Beloppet i fältet som visas i följande format: Budget, verklig avvikelse från Budget Budget varians %, omarbetad budget, omarbetad avvikelse från budget och omarbetad budget avvikelsen %.  [![Kontrollera kostnad](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Kom igång
Så här börjar använda mobiltelefonprogrammet kostnad kontroll på din mobila enhet.

1.  Hämta och installera Microsoft Dynamics 365 for app operationer på din mobiltelefonprogrammet butik.
2.  Starta programmet för enheten.
3.  Ange en Webbadress för Dynamics 365.
4.  Ange att logga in på företaget. Till exempel anger **USMF**.
5.  Första gången du loggar in, uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 för operationer. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor på din mobiltelefonprogrammet måste du publicera önskade arbetsytor till Dynamics 365 for app operationer.

1.  Starta Dynamics 365 för operationer.
2.  Gå till **systemadministration**&gt;**inställningar**&gt;**systemparametrar**.
3.  Välj **hantera mobiltelefonprogrammet**.
4.  Markera arbetsytan ** kostnad styra ** publiceras mobil plattform.
5.  Välj **publicera arbetsytan**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-the-performance-of-your-cost-center"></a>Visa hur din kostnadsställe
1.  På din mobila enhet väljer du den **kostnad styra** arbetsytan.
2.  Välj **kostnad objekt styr**.
3.  Klicka på **åtgärder**.
4.  Klicka på **Select configuration** att välja en kostnad Kontrollera layout.
5.  Click **Done**.
6.  Klicka på **åtgärder**.
7.  Klicka på **Välj kostnadsbäraren** att välja kostnadsställen som du har beviljats åtkomst.
8.  Click **Done**.
9.  Visa prestanda för dina kostnadsställe.
10. Klicka på **detaljer för aktuell period**.
11. Visa prestanda för enskilda kostnadselement.
12. Du kan också söka efter specifika kostnadselement.



