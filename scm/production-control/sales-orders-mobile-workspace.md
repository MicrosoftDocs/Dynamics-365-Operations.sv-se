---
title: "Mobil arbetsyta för försäljningsorder för programmet Microsoft Dynamics 365 for Operations"
description: "Med den mobila arbetsytan för försäljningsorder kan du hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst."
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

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobil arbetsyta för försäljningsorder för programmet Microsoft Dynamics 365 for Operations

Med den mobila arbetsytan för försäljningsorder kan du hålla dig uppdaterad om dina försäljningsorder var som helst och när som helst. 

<a name="prerequisites"></a>Förutsättningar
-------------

| Förutsättning                                                         | beskrivning                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Läs mer om den mobila plattformen Microsoft Dynamics 365 for Operations | [Den mobila plattformen Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Se till att använda en miljö med Microsoft Dynamics 365 for Operations version 1611 och plattformen Microsoft Dynamics for Operations med uppdatering 3 (november 2016). |
| Snabbkorrigering KB 3215650                                                    | Installera snabbkorrigeringen om du vill aktivera de arbetsytor som finns i Microsoft Dynamics 365 for Operations.                                                                       |
| Mobil enhet med programmet Dynamics 365 for Operations installerat | Hämta programmet Dynamics 365 for Operations från din mobilappsbutik.                                                                                                      |

## <a name="overview"></a>Översikt
Denna mobila arbetsyta får åtkomst till programmet Dynamics 365 for Operations och låter dig visa detaljerad information om varje order som t.ex. orderstatus, kontaktinformation för kund och kontaktinformation för ordermottagaren. Den mobila arbetsytan ger en direkt översikt över försäljningsorder. Du kan visa försäljningsorder per kund, eller visa alla försäljningsorder eller visa information om en specifik försäljningsorder. Den mobila arbetsytan innehåller två vyer som hjälper dig att analysera försäljningsorder på djupet.

### <a name="view-all-sales-orders"></a>Visa alla försäljningsorder

Den här vyn visar en lista över alla försäljningsorder.

-   Använd ett av följande filter för att välja de försäljningsorder som du vill visa.
    -   Sök efter försäljningsorder
    -   Sök efter kundkonto
    -   Sök efter kundnamn
    -   Sök efter status
    -   Sök efter frisläppningsstatus
    -   Sök efter skapat datum och klockslag

<!-- -->

-   När du valt en försäljningsorder kan visa du uppgifter om särskilda order. Du kan dessutom visa
    -   Information om kundens namn och adress
    -   Andra försäljningsorderdatum, som t.ex. t ex begärt transportdatum och bekräftat transportdatum
    -   Ordermottagarens kontaktinformation
    -   Kundens kontaktinformation
    -   Orderrader
    -   Leveranser som visar hur och när en försäljningsorder har levererats

### <a name="view-orders-for-a-customer-"></a>Visa order för en kund** **

Denna vy listar försäljningsorder per kund.

-   Använd något av följande filter för att visa order för en kund.
    -   Sök efter namn
    -   Sök efter konto

<!-- -->

-   När du har valt en kund kan du visa:
    -   Kundens namn och grupp
    -   Kundens kontaktinformation
    -   Försäljningsorder för kunden och information om försäljningsorder:
        -   Information om kundens namn och adress
        -   Datum för olika försäljningsorder.
        -   Ordermottagarens kontaktinformation
        -   Kundens kontaktinformation
        -   Orderrader
        -   Leveranser som visar hur och när en försäljningsorder har levererats

## <a name="get-started"></a>Kom igång
Följ dessa steg för att komma igång med den mobila arbetsytan för försäljningsorder på din mobila enhet.

1.  Hämta och installera appen Microsoft Dynamics 365 for Operations från din mobilappsbutik.
2.  Starta appen på din enhet.
3.  Ange din webbadress för Dynamics 365.
4.  Ange ett företag att logga in på. Ange till exempel **USMF**.
5.  Första gången du loggar in uppmanas du ange användarnamn och lösenord för ditt Microsoft Dynamics 365 for Operations-konto. Ange dina autentiseringsuppgifter. När du loggar in visas tillgängliga arbetsytor för ditt företag.

Om du vill visa arbetsytor i din mobilapp måste du först publicera önskade arbetsytor i appen Dynamics 365 for Operations app.

1.  Starta Dynamics 365 for Operations.
2.  Navigera till **Systemadministration** &gt; **Inställningar** &gt; **systemparametrar**.
3.  Välj **Hantera mobilapp**.
4.  Markera arbetsytan att publicera i den mobila plattformen.
5.  Välj **Publicera arbetsyta**.
6.  Uppdatera enheten om du vill se de publicerade arbetsytorna.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Visa information om försäljningsorder för en kund.
1.  På din mobila enhet väljer du arbetsytan **Försäljningsorder**.
2.  Välj **Visa order för en kund**.
3.  Använd informationen **Konto** eller **Kundnamn** för att hitta önskad kund.
4.  Välj kunden.
5.  Välj **Kontaktinformation** eller **Försäljningsorder**.
6.  Om **Försäljningsorder** markeras visas en lista över försäljningsorder för kunden.
7.  Välj **Försäljningsorder**.
8.  Här kan du visa information om försäljningsorderrader, leveranser, kundkontaktinformation och ordermottagarinformation.




