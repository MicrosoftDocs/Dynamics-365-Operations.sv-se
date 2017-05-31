---
title: Startsidan Budgetering
description: "Det här ämnet innehåller en översikt med komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapportering i Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5abe09cb52d204d96fadeb1beff991f09fb5bfd2
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="budgeting-home-page"></a>Startsidan Budgetering

[!include[banner](../includes/banner.md)]


Det här ämnet innehåller en översikt med komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapportering i Microsoft Dynamics 365 for Operations. 

<a name="components-of-budgeting-functionality"></a>Komponenter i budgeteringsfunktionen
-------------------------------------

Resursplanläggningscykeln för ett företag består typiskt av aktiviteter för planering, budgetering och prognostisering.
[![Budgetfunktionens komponenter](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) Processerna för både långsiktig strategisk planering och årsbudgetplanering stöds genom ett budgetplandokument. Budgetplandokument är väl integrerade med Microsoft Excel. Användarna kan konfigurera obegränsade monetära och kvantitativa scenarier och även definiera en organisationshierarki för budgetering som stöder budgetmetoder både uppifrån och ned och nedifrån och upp. När en budget har skapats och godkänts i Microsoft Dynamics 365 for Operations, konverterar du budgetplanen till en budgetregisterpost. Budgetregisterposter innehåller verktyg för underhåll av budgeten för att göra beloppen spårningsbara med budgetkoder. Budgetregisterposter gör att det går att ändra ursprungliga budgetar, utföra överföringar och överföra budgetbelopp från föregående år. Utifrån den upprättade budgeten kan företaget aktivera budgetkontroll. Nivån på kontrollen beror på organisationens kultur och mognadsnivå. Organisationer med en lägre mognadsnivå kan lämna budgeten som den är och kan vara mer reaktiva än proaktiva om en budget inte uppfyller förväntningarna. Andra organisationer kan aktivera budgetkontrollregler som hindrar att användare gör inköp om budgeterade medel inte finns tillgängliga. Slutligen: Väl utvecklade organisationer kan skapa en organisationskultur där medarbetare utbildas om organisationens mål och följer dessa mål genom olika principer, t.ex. "Överväg internetkonferenser istället för resor." Dynamics 365 for Operations omfattar ett ramverk för budgetkontroll som låter företagets ledning välja antingen hård styrning (som förhindrar bokföringar som skulle överskrida budgeten) eller mjuk styrning (där användarna varnas att de kommer att överskrida tillgängliga budgetmedel, men själva kan bestämma hur de vill fortsätta). Slutligen går det även att använda löpande prognoser. En rullande prognos är en jämförelse av budgeten och de verkliga siffrorna och används för att definiera hur bra företaget går i förhållande till budgeten. En rullande prognos kan också identifiera tendenser. Microsoft Dynamics 365 for Operations stöder rullande prognoser genom ett budgetplandokument som första planeringsaktivitet. Rullande prognoser kan utföras parallellt med planeringen för nästkommande budgetcykel.

-   [Grundläggande budgetering: Översikt och konfiguration](basic-budgeting-overview-configuration.md)
-   [Budgetkontroll: Översikt och konfiguration](budget-control-overview-configuration.md)
-   [Budgetplanering: Översikt och konfiguration](budget-planning-overview-configuration.md)
-   [Befattningsprognos](position-forecasting.md)
-   [Motiveringsdokument för budgetplanering](budget-planning-justification-docs.md)
-   [Microsoft Excel-mallar för budgetplanering](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Budgeteringsverktyg i Dynamics 365 for Operations
[![Budgeteringsverktyg](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Ytterligare funktioner för planering och budgetering finns i Dynamics 365 for Operations och är integrerade i redovisningsbudgetarna.

-   **Personalbudgetar** – personalbudgeteringen innefattar detaljerad planering av budgetkostnadskomponenter för befattningar, kompensationsgrupper osv.
-   **Budgetar för anläggningstillgångar** – Med utgångspunkt från information om anläggningstillgångar går det att beräkna avskrivningar och registrera andra planerade transaktioner som rör anläggningstillgångar.
-   **Projektbudgetar** – I projektmodulen går det att skapa detaljerade projektprognoser. Projektprognoserna inkluderar information om planerade timmar, utgifter, avgifter och artiklar.
-   **Efterfrågeprognostisering** – Med utgångspunkt från historiska transaktionsdata går det att uppskatta framtida lagerefterfrågan och skapa efterfrågeprognoser.

Information om att hämta planeringsdata från andra moduler till budgetplaner finns i [Integrering av budgetplanering med andra moduler](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Användargränssnitt och rapporteringsfunktioner
I Dynamics 365 for Operations kan användarna skapa budgetplaner antingen direkt i Dynamics 365 for Operations-klienten (genom att använda en konfigurerbar sida i budgetplansdokumentet) eller i Excel. Excel innehåller flera ytterligare funktioner. Det går till exempel att använda externa uppgifter som källa till en budgetplan, göra egna beräkningar och använda Microsoft pivottabeller och diagram. De flesta variablerna i budgetplaneringsprocessen går att konfigurera. Det går till exempel att definiera vem som gör budgeten, vad som budgeteras och hur processen går till. Även om du använder Excel till budgetplanering, behålls Dynamics 365 for Operations som en enda sanningskälla som förhindrar budgetkontrollproblem. Periodiska processer kan användas för att införa startuppgifter för budgeteringen i budgetplanen. Till rapporteringen erbjuder Dynamics 365 for Operations en uppsättning standardförfrågningssidor som gör det möjligt att visa och analysera budgeteringsdata. Budgetplandata går att öppna i Management Reporter och enskilda budgetplansscenarier går att visa som kolumner i Management Reporter-rapporten.







