---
title: Startsidan Budgetering
description: Det här avsnittet innehåller en översikt över komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapporteringskapaciteter i Microsoft Dynamics 365 Finance.
author: panolte
ms.date: 04/29/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "106043"
- intro-internal
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ad0d055702a3801bf9fe9ac3159eba7c297b6f0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983962"
---
# <a name="budgeting-home-page"></a>Startsidan Budgetering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över komponenter för budgeteringsfunktioner, budgeteringsverktyg och rapporteringskapaciteter. 

## <a name="components-of-budgeting-functionality"></a>Komponenter i budgeteringsfunktionen

Resursplanläggningscykeln för ett företag består typiskt av aktiviteter för planering, budgetering och prognostisering.

[![Komponenter för budgeteringsfunktioner.](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

Processerna för såväl långsiktig strategisk planering som årlig budgetplanering stöds via ett budgetplandokument. Budgetplandokument är väl integrerade med Microsoft Excel. Användarna kan konfigurera obegränsade monetära och kvantitativa scenarier och även definiera en organisationshierarki för budgetering som stöder budgetmetoder både uppifrån och ned och nedifrån och upp. När en budget har skapats och godkänts i appen, konverterar du budgetplanen till en budgetregisterpost. Budgetregisterposter innehåller verktyg för underhåll av budgeten för att göra beloppen spårningsbara med budgetkoder. Budgetregisterposter gör att det går att ändra ursprungliga budgetar, utföra överföringar och överföra budgetbelopp från föregående år. Utifrån den upprättade budgeten kan företaget aktivera budgetkontroll. Nivån på kontrollen beror på organisationens kultur och mognadsnivå. Organisationer med en lägre mognadsnivå kan lämna budgeten som den är och kan vara mer reaktiva än proaktiva om en budget inte uppfyller förväntningarna. Andra organisationer kan aktivera budgetkontrollregler som hindrar att användare gör inköp om budgeterade medel inte finns tillgängliga.

Slutligen: Väl utvecklade organisationer kan skapa en organisationskultur där medarbetare utbildas om organisationens mål och följer dessa mål genom olika policyer, t.ex. "Överväg internetkonferenser istället för resor." Appen omfattar ett ramverk för budgetkontroll som låter företagets ledning välja antingen hård styrning (som förhindrar bokföringar som skulle överskrida budgeten) eller mjuk styrning (där användarna varnas att de kommer att överskrida tillgängliga budgetmedel, men själva kan bestämma hur de vill fortsätta). Slutligen går det även att använda löpande prognoser. En rullande prognos är en jämförelse av budgeten och de verkliga siffrorna och används för att definiera hur bra företaget går i förhållande till budgeten. En rullande prognos kan också identifiera tendenser. Finance and Operations stöder rullande prognoser genom ett budgetplandokument som första planeringsaktivitet. Rullande prognoser kan utföras parallellt med planeringen för nästkommande budgetcykel.

-   [Budgetöversikt](basic-budgeting-overview-configuration.md)
-   [Översikt över budgetkontroll](budget-control-overview-configuration.md)
-   [Översikt över budgetplanering](budget-planning-overview-configuration.md)
-   [Befattningsprognos](position-forecasting.md)
-   [Motiveringsdokument för budgetplanering](budget-planning-justification-docs.md)
-   [Budgetplaneringsmallar för Excel](budget-planning-excel-templates.md)

## <a name="budgeting-tools"></a>Budgeteringsverktyg
[![Budgeteringsverktyg.](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Det finns ytterligare funktioner för planering och budgetering som är integrerade i redovisningsbudgetarna.

-   **Personalbudgetar** – personalbudgeteringen innefattar detaljerad planering av budgetkostnadskomponenter för befattningar, kompensationsgrupper osv.
-   **Budgetar för anläggningstillgångar** – Med utgångspunkt från information om anläggningstillgångar går det att beräkna avskrivningar och registrera andra planerade transaktioner som rör anläggningstillgångar.
-   **Projektbudgetar** – I projektmodulen går det att skapa detaljerade projektprognoser. Projektprognoserna inkluderar information om planerade timmar, utgifter, avgifter och artiklar.
-   **Efterfrågeprognostisering** – Med utgångspunkt från historiska transaktionsdata går det att uppskatta framtida lagerefterfrågan och skapa efterfrågeprognoser.

Information om att hämta planeringsdata från andra moduler till budgetplaner finns i [Integrering av budgetplanering med andra moduler](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Användargränssnitt och rapporteringsfunktioner
Användarna kan skapa budgetplaner antingen direkt på klienten (genom att använda en konfigurerbar sida i budgetplansdokumentet) eller i Excel. Excel innehåller flera ytterligare funktioner. Det går till exempel att använda externa uppgifter som källa till en budgetplan, göra egna beräkningar och använda Microsoft pivottabeller och diagram. De flesta variablerna i budgetplaneringsprocessen går att konfigurera. 

Det går till exempel att definiera vem som gör budgeten, vad som budgeteras och hur processen går till. Även om du använder Excel till budgetplanering, behålls appen som en enda sanningskälla som förhindrar budgetkontrollproblem. Periodiska processer kan användas för att införa startuppgifter för budgeteringen i budgetplanen. För rapporteringsändamål innehåller appen en uppsättning standardförfrågningssidor som gör det möjligt att visa och analysera budgeteringsdata. Budgetplandata går att öppna i [Ekonomisk rapportering](../general-ledger/financial-reporting-getting-started.md) och enskilda budgetplansscenarier går att visa som kolumner i den ekonomiska rapporten.








[!INCLUDE[footer-include](../../includes/footer-banner.md)]
