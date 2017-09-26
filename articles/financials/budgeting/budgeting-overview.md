---
title: Startsidan Budgetering
description: "Det här ämnet innehåller en översikt med komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapportering i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: twheeloc
manager: AnnBe
ms.date: 08/09/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 529751c09b8f99f986cad23a633bea661929d558
ms.openlocfilehash: e59c29370353a6e4a67d2b892e2024ca78d560fc
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2017

---

# <a name="budgeting-home-page"></a>Startsidan Budgetering

[!include[banner](../includes/banner.md)]


Det här ämnet innehåller en översikt med komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapportering i Finance and Operations. 

<a name="components-of-budgeting-functionality"></a>Komponenter i budgeteringsfunktionen
-------------------------------------

Resursplanläggningscykeln för ett företag består typiskt av aktiviteter för planering, budgetering och prognostisering.

[![Komponenter för budgetringsfunktioner](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Processerna för såväl långsiktig strategisk planering som årlig budgetplanering stöds via ett budgetplandokument. Budgetplandokument är väl integrerade med Microsoft Excel. Användarna kan konfigurera obegränsade monetära och kvantitativa scenarier och även definiera en organisationshierarki för budgetering som stöder budgetmetoder både uppifrån och ned och nedifrån och upp. När en budget har skapats och godkänts i Finance and Operations, konverterar du budgetplanen till en budgetregisterpost. Budgetregisterposter innehåller verktyg för underhåll av budgeten för att göra beloppen spårningsbara med budgetkoder. Budgetregisterposter gör att det går att ändra ursprungliga budgetar, utföra överföringar och överföra budgetbelopp från föregående år. Utifrån den upprättade budgeten kan företaget aktivera budgetkontroll. Nivån på kontrollen beror på organisationens kultur och mognadsnivå. Organisationer med en lägre mognadsnivå kan lämna budgeten som den är och kan vara mer reaktiva än proaktiva om en budget inte uppfyller förväntningarna. Andra organisationer kan aktivera budgetkontrollregler som hindrar att användare gör inköp om budgeterade medel inte finns tillgängliga.

Slutligen: Väl utvecklade organisationer kan skapa en organisationskultur där medarbetare utbildas om organisationens mål och följer dessa mål genom olika policyer, t.ex. "Överväg internetkonferenser istället för resor." Finance and Operations omfattar ett ramverk för budgetkontroll som låter företagets ledning välja antingen hård styrning (som förhindrar bokföringar som skulle överskrida budgeten) eller mjuk styrning (där användarna varnas att de kommer att överskrida tillgängliga budgetmedel, men själva kan bestämma hur de vill fortsätta). Slutligen går det även att använda löpande prognoser. En rullande prognos är en jämförelse av budgeten och de verkliga siffrorna och används för att definiera hur bra företaget går i förhållande till budgeten. En rullande prognos kan också identifiera tendenser. Finance and Operations stöder rullande prognoser genom ett budgetplandokument som första planeringsaktivitet. Rullande prognoser kan utföras parallellt med planeringen för nästkommande budgetcykel.

-   [Grundläggande budgetering: Översikt och konfiguration](basic-budgeting-overview-configuration.md)
-   [Budgetkontroll: Översikt och konfiguration](budget-control-overview-configuration.md)
-   [Budgetplanering: Översikt och konfiguration](budget-planning-overview-configuration.md)
-   [Befattningsprognos](position-forecasting.md)
-   [Motiveringsdokument för budgetplanering](budget-planning-justification-docs.md)
-   [Microsoft Excel-mallar för budgetplanering](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-finance-and-operations"></a>Budgeteringsverktyg i Finance and Operations
[![Budgeteringsverktyg](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Ytterligare funktioner för planering och budgetering finns i Finance and Operations och är integrerade i redovisningsbudgetarna.

-   **Personalbudgetar** – personalbudgeteringen innefattar detaljerad planering av budgetkostnadskomponenter för befattningar, kompensationsgrupper osv.
-   **Budgetar för anläggningstillgångar** – Med utgångspunkt från information om anläggningstillgångar går det att beräkna avskrivningar och registrera andra planerade transaktioner som rör anläggningstillgångar.
-   **Projektbudgetar** – I projektmodulen går det att skapa detaljerade projektprognoser. Projektprognoserna inkluderar information om planerade timmar, utgifter, avgifter och artiklar.
-   **Efterfrågeprognostisering** – Med utgångspunkt från historiska transaktionsdata går det att uppskatta framtida lagerefterfrågan och skapa efterfrågeprognoser.

Information om att hämta planeringsdata från andra moduler till budgetplaner finns i [Integrering av budgetplanering med andra moduler](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Användargränssnitt och rapporteringsfunktioner
I Finance and Operations kan användarna skapa budgetplaner antingen direkt i Finance and Operations-klienten (genom att använda en konfigurerbar sida i budgetplansdokumentet) eller i Excel. Excel innehåller flera ytterligare funktioner. Det går till exempel att använda externa uppgifter som källa till en budgetplan, göra egna beräkningar och använda Microsoft pivottabeller och diagram. De flesta variablerna i budgetplaneringsprocessen går att konfigurera. 

Det går till exempel att definiera vem som gör budgeten, vad som budgeteras och hur processen går till. Även om du använder Excel till budgetplanering, behålls Finance and Operations som en enda sanningskälla som förhindrar budgetkontrollproblem. Periodiska processer kan användas för att införa startuppgifter för budgeteringen i budgetplanen. Till rapporteringen erbjuder Finance and Operations en uppsättning standardförfrågningssidor som gör det möjligt att visa och analysera budgeteringsdata. Budgetplandata går att öppna i Management Reporter och enskilda budgetplansscenarier går att visa som kolumner i Management Reporter-rapporten.






