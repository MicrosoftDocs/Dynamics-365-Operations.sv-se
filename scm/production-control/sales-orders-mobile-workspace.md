---
title: "Försäljningsorder mobil arbetsytan för Microsoft Dynamics 365 för operationer app"
description: "Med mobil arbetsytan försäljningsorder du hålla dig uppdaterad på försäljningsorder var som helst och när som helst."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Försäljningsorder mobil arbetsytan för Microsoft Dynamics 365 för operationer app

Med mobil arbetsytan försäljningsorder du hålla dig uppdaterad på försäljningsorder var som helst och när som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om Microsoft Dynamics 365 för operationer | [Dynamics 365 för operationer](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 för operationer                                          | Försäkra dig om att du använder en miljö med Microsoft Dynamics 365 för operationer version 1611 och uppdatera Microsoft Dynamics för operationer 3 (November 2016). |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigering om du vill aktivera arbetsytor som finns i Microsoft Dynamics 365 för operationer.                                                                       |
| Mobil enhet med Dynamics 365 för operationer program installerat | Hämta mobiltelefonprogrammet lagringsplatsen Dynamics 365 för operationer app.                                                                                                      |

## <a name="overview"></a>Översikt
Mobil arbetsytan till Dynamics 365 för operationer programmet och du kan visa detaljerad information om varje order som orderstatus, information om kunder och order hos Prometric kontaktinformation. Mobil arbetsytan ger en översikt över försäljningsorder. Du kan visa försäljningsorder per kund, eller visa alla försäljningsorder eller visa information om en specifik försäljningsorder. Mobil arbetsytan innehåller två vyer som hjälper dig att analysera försäljningsorder på djupet.

### <a name="view-all-sales-orders"></a>Visa alla försäljningsorder

Den här vyn visar en lista över alla försäljningsorder.

-   Använd någon av följande filter för att välja de försäljningsorder som du vill visa.
    -   Sök efter försäljningsorder
    -   Sök efter kund-ID
    -   Söka efter kundnamn
    -   Söka efter status
    -   Söka efter status för frisläppning
    -   Söka efter datum och tid

<!-- -->

-   När du valt en försäljningsorder kan visa du uppgifter om särskilda order. Du kan dessutom visa
    -   Namn och adress kundinformation
    -   Annan försäljningsorder datum, t ex Begärt speditionsdatum och bekräftat speditionsdatum
    -   Kontaktinformation för order hos Prometric
    -   Kundkontaktinformation
    -   Orderrader
    -   Försändelser som visar hur och när en försäljningsorder som har levererats

### <a name="view-orders-for-a-customer-"></a>Visa order för kunden ** **

Den här vyn visar en lista över försäljningsorder per kund.

-   Använd någon av följande filter för att visa order för en kund.
    -   Sök efter namn
    -   Söka efter konto

<!-- -->

-   När du har valt en kund kan visa du:
    -   Kundnamn och grupp
    -   Kundkontaktinformation
    -   Försäljningsorder för kunden och information om försäljningsorder:
        -   Namn och adress kundinformation
        -   Datum för olika försäljningsorder.
        -   Kontaktinformation för order hos Prometric
        -   Kundkontaktinformation
        -   Orderrader
        -   Försändelser som visar hur och när en order har levererats.

## <a name="get-started"></a>Kom igång
Gör så här för att komma igång med mobil arbetsytan försäljningsorder på en mobil enhet.

1.  Hämta och installera Microsoft Dynamics 365 for app operationer på din mobiltelefonprogrammet butik.
2.  Starta programmet för enheten.
3.  Ange en Webbadress för Dynamics 365.
4.  Ange att logga in på företaget. Till exempel anger **USMF**.
5.  Första gången du loggar in, uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 för operationer. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor på din mobiltelefonprogrammet måste du publicera önskade arbetsytor till Dynamics 365 for app operationer.

1.  Starta Dynamics 365 för operationer.
2.  Gå till **systemadministration**&gt;**inställningar**&gt;**systemparametrar**.
3.  Välj **hantera mobiltelefonprogrammet**.
4.  Markera arbetsytan för att publicera på en mobil plattform.
5.  Välj **publicera arbetsytan**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Visa information om försäljningsorder för en kund
1.  På din mobila enhet väljer du den **försäljningsorder** arbetsytan.
2.  Välj **visa order för en kund**.
3.  Använd ** konto ** eller ** kundnamn ** information för att hitta önskad kund.
4.  Välj kunden.
5.  Välj **kontaktinformation** eller **försäljningsorder**.
6.  Om **försäljningsorder** är visas en lista över försäljningsorder för kunden visas.
7.  Välj **försäljningsorder**.
8.  Här kan du visa information om försäljningsorderrader, försändelser, information om kunder och order hos Prometric kontaktinformation.




