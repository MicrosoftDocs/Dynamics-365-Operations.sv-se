---
title: "Kundtjänstfunktioner"
description: "Det här ämnet innehåller en översikt över funktionen för callcenterförsäljning i Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 52b3e2e78a03ac67507ee65a03e0884e5ed44678
ms.openlocfilehash: 75dc09ffc84ef8ec48f50ea410974c99aabc212e
ms.contentlocale: sv-se
ms.lasthandoff: 11/14/2017

---

# <a name="call-center-functionality"></a>Kundtjänstfunktioner

[!INCLUDE [banner](includes/banner.md)]

Det här avsnittet innehåller en översikt över funktionen för callcenterförsäljning i Microsoft Dynamics 365 for Retail.

Dynamics 365 for Retail stöder också kundtjänst som en typ av butikskanal. I kundtjänsten tar anställda emot beställningar från kunder per telefon och skapar försäljningsorder. Kundtjänst innehåller funktioner som gör det enklare att ta emot telefonbeställningar och hantera kundtjänst genom hela orderbehandlingsprocessen. Callcentermedarbetare kan registrera betalningsinformation direkt till försäljningsordern och visa en detaljerad sammanfattning över avgifter och betalningar innan de skickar ordern. Arbetstagarna har också alternativ för att styra prissättningen, och kan nå olika data om kunder, produkter och priser från **försäljning** . Dessutom callcenter har förbättrade funktioner för spårning av kundens historia och beställningsstatus. Varje kundtjänst kan ha sina egna användare, betalningsmetoder, prisgrupper, ekonomiska dimensioner och leveranssätt. Du kan konfigurera dessa alternativ, när du skapar kundtjänst. Du kan dessutom använda **Call center-** sidan för att aktivera eller inaktivera följande grupper av funktioner som är unika för call center:

-   **Orderns färdigdatum** – Denna grupp omfattar funktioner som är relaterade till betalningar och beställningen slutförs på **försäljningen** .
-   **Riktad försäljning** – Denna grupp omfattar funktioner som är relaterade till källkoder, manuskript, och katalog.

När du aktiverar funktionerna i call center-inställningarna, de finns på **Försäljningsorder** till användare som är associerade med call center. De flesta av dessa funktioner kräver ytterligare inställningar innan de kan användas. Innan användare kan skapa call center-order måste du lägga till användarna till call center som call center-användare. Det här steget gör att call center kanal-specifika konfigurationer och funktionalitet. Här är några exempel på funktioner som blir tillgängliga:

-   Guidad försäljning tillhandahåller konfigurationsalternativ för telefonförsäljning manuskript och bilder för att hjälpa och vägleda försäljning clerks medan de tar order.
-   Beställningar kan inte slutföras förrän försäljningen i butiken har fångat minst ett betalningssätt.
-   Merförsäljning och korsförsäljning av reglerna kan konfigureras att försäljningen i butiken för att främja särskilda produkter till kunden.
-   Försäljningen i butiken kan fånga källkoden för den katalog som en kund beställer från.
-   Försäljningen i butiken kan lägga till detaljhandlarens kuponger till ordern.
-   Försäljningen i butiken kan sälja förbindelse program.
-   Beställningar kan parkeras automatiskt eller manuellt, för att indikera att ytterligare utredning krävs innan den kan bearbetas.





