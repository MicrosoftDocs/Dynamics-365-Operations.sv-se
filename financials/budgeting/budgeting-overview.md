---
title: Startsidan Budgetering
description: "Det här avsnittet innehåller en översikt över funktionen komponenter, verktyg budgetering och rapportering i Microsoft Dynamics 365 för operationer."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: index-page
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106043
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: b21fd97426b331726c12ea29f89817a46dd445c3
ms.openlocfilehash: f7b4efc06b8e64c05da026850b41cb5b68c33ec3
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-home-page"></a>Startsidan Budgetering

Det här avsnittet innehåller en översikt över funktionen komponenter, verktyg budgetering och rapportering i Microsoft Dynamics 365 för operationer.

<a name="components-of-budgeting-functionality"></a>Komponenter i budgeteringsfunktionen
-------------------------------------

Resursplanläggningscykeln för ett företag består vanligtvis av planerings-, budgeterings- och prognostiseringsaktiviteter.
[![Komponenter för budgeteringsfunktioner](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg) processerna för långsiktig strategisk planering och årliga budgetplanering stöds via ett budgetplandokument. Budgetplandokument är väl integrerade med Microsoft Excel. Användarna kan konfigurera obegränsade monetära och kvantitativa scenarier och definiera en organisationshierarki för budgetering som stöder budgetmetoder både uppifrån och ned och nedifrån och upp. När en budget har skapats och godkänts i Microsoft Dynamics 365 for Operations, konverterar du budgetplanen till en budgetregisterpost. Budgetregisterposter innehåller verktyg för underhåll av budgeten för att kunna ha beloppen spårningsbara via budgetkoder. Budgetregisterposter gör att du kan ändra ursprungliga budgetar, utföra överföringar och överföra budgetbelopp från föregående år. Utifrån den etablerade budgeten, kan ett företag aktivera budgetkontroll. Nivån på kontrollen beror på organisationens kultur och mognadsnivå. Organisationer som har en lägre mognadsnivå kan lämna budgeten som den är och kan vara mer reaktiva än proaktiva om en budget inte uppfyller förväntningarna. Andra organisationer kan aktivera budgetkontrollregler som hindrar att användare gör inköp om budgeterade medel inte är tillgängliga. Slutligen inrättar välutvecklad organisationer en organisations kultur där medarbetare educated om organisationens mål och följa dessa mål genom principer, t ex "Tänk mötet i stället för en resa." Dynamics 365 för åtgärder som omfattar en Budgetkontrollramverket där företagets ledning, Välj antingen hård kontrollen (förhindrar att bokföringar som skulle överskrida budgeten) eller mjuk (där användarna varnas de kommer att överskrida det tillgängliga budgetmedlen men själva bestämma hur du vill fortsätta). Du kan dessutom använda löpande prognoser. En rullande prognos är en vanlig jämförelse av budget till verkliga värden och används för att definiera hur väl företaget bedriver sin verksamhet mot budget. En rullande prognos kan också identifiera tendenser. I Microsoft Dynamics 365 for Operations stöds rullande prognoser via ett budgetplandokument som första planeringsaktiviteter. Rullande prognoser kan utföras parallellt med planeringen för nästkommande budgetcykel.

-   [Grundläggande budgetering: Översikt och konfiguration](basic-budgeting-overview-configuration.md)
-   [Budgetkontroll: Översikt och konfiguration](budget-control-overview-configuration.md)
-   [Budgetplanering: Översikt och konfiguration](budget-planning-overview-configuration.md)
-   [Befattningsprognos](position-forecasting.md)
-   [Budget planering handlingar](budget-planning-justification-docs.md)
-   [Microsoft Excel-mallar för budgetplanering](budget-planning-excel-templates.md)

## <a name="budgeting-tools-in-dynamics-365-for-operations"></a>Budgeteringsverktyg i Dynamics 365 for Operations
[![Verktyg för budgetering](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

Ytterligare funktioner för planering och budgetering finns i Dynamics 365 for Operations och är integrerade i redovisningsbudgetarna.

-   **Personalbudgetar** – personalbudgeteringen innefattar detaljerad planering av budgetkostnadskomponenter för befattningar, lösengrupper osv.
-   **Budgetar för anläggningstillgångar** – Med utgångspunkt från information om anläggningstillgångar kan du beräkna avskrivningar och registrera andra planerade transaktioner som rör anläggningstillgångar.
-   **Projektbudgetar** – I projektmodulen kan du skapa detaljerade projektprognoser. Projektprognoserna ska inkludera information om planerade timmar, utgifter, avgifter och artiklar.
-   ** Kräver prognoser ** – baserade på historiska transaktionsdata du kan beräkna lager framtida efterfrågan och skapa efterfrågeprognoser.

Om du vill ha information om hur du hämtar planeringsdata från andra moduler till budgetplaner, se [Integrering av budgetplanering med andra moduler](budget-planning-integration-other-modules.md).

## <a name="user-interface-and-reporting-capabilities"></a>Användargränssnitt och rapporteringsfunktioner
I Dynamics 365 for Operations kan användarna skapa budgetplaner antingen direkt i Dynamics 365 for Operations-klienten (genom att använda en konfigurerbar sida i budgetplansdokumentet) eller via Excel. Excel innehåller flera ytterligare funktioner. Du kan till exempel använda externa uppgifter som källa till en budgetplan, göra egna beräkningar och använda Microsoft pivottabeller och diagram. De flesta variablerna i budgetplaneringsprocessen går att konfigurera. Du kan till exempel definiera vem som gör budgeten, vad som budgeteras och hur processen går till. Även om du använder Excel till budgetplanering, behålls Dynamics 365 for Operations som en enda sanningskälla som förhindrar budgetkontrollproblem. Periodiska processer kan användas för att införa startuppgifter för budgeteringen i budgetplanen. Till rapporteringen erbjuder Dynamics 365 for Operations en uppsättning standardförfrågningssidor som gör att du kan visa och analysera budgeteringsdata. Budgetplandata går att öppna via Management Reporter och enskilda budgetplansscenarier går att visa som kolumner i Management Reporter-rapporten.





