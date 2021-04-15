---
title: Test av dataagnostisk med hjälp av Regression Suite Automation Tool
description: I det här avsnittet beskrivs rekommendationerna för test av dataagnostisk med Regression Suite Automation Tool.
author: kfend
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 120a88790b7cdb6a8cfcf97cbafeced4685384f2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744673"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Test av dataagnostisk med hjälp av Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Funktionsvalideringen av ett ERP-program kan inte vara fullständigt dataagnostisk men det finns flera faser och metoder för testning. Testfaserna omfattar:  

- SysTest-testramverk
- ATL-ramverk
- Regression Suite Automation Tool (RSAT)

[![Testklassificeringspyramid](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Översikt
-   **SysTest-ramverk** – SysTest-ramverket är pålitligt för skrivning av enhetstest. Eftersom enhetstest vanligtvis testar en metod eller funktion bör de alltid vara dataagnostik och endast beroende av indata som tillhandahålls som en del av testet.
-   **ATL-ramverk** – Microsoft har ett ATL-ramverk som är en abstraktion av SysTest-ramverket och som gör funktionellt testskrivning mycket enklare och pålitligt. Detta ramverk bör användas för att skriva komponenttest eller tester av enklare integrationstest.
-   **RSAT** – RSAT används för tester av integrationstest och affärscykel. Testerna av affärscykeln, som även kallas regressionsverifieringstest, är beroende av befintliga data. Dessa tester kan emellertid bli dataagnostik om du tar hänsyn till fler faktorer. 

    - o Där enhetstest och komponenttest är av låg nivå och kan vara fullt dataagnostik (inte beroende av befintlig datauppsättning), affärscykelns eller regressionens valideringstest beror på vissa befintliga data. Dessa data inkluderar inställningar, konfigurationsinställningar (parametrar) och huvuddata (kund, leverantörer, artiklar o.s.v.), men aldrig transaktionsdata. Se till att om något av dessa ändras under testen återställs de tillbaka som en del av det slutliga testet.
    - Välj huvuddata baserat på vissa kriterier istället för att välja en viss post. Om du till exempel vill välja en artikel med utgångspunkt i dimensionsvärden och lagertillgänglighet filtrerar du produktlistan med dessa värden, väljer den första artikeln och kopierar numret som ska användas för framtida tester. Om det är en enkel huvuddatarad, t.ex. kund, leverantör eller artikel, kan den skapas som en del av automatiseringen och användas i framtida tester genom att koppla samman. 
    - o Ange de unika identifierarna, t.ex. fakturanummer, via nummerserien eller genom att använda Microsoft Excel funktioner som t.ex. =TEXT(NOW(),"yyyymmddhhmm"). Funktionen anger ett unikt nummer varje minut, vilket gör att du kan spåra när åtgärden utförs. Den kan användas för variabler som t.ex. produktinleveransnummer och leverantörsfakturanummer. Dessa tester fortsätter att arbeta med samma databas igen och återigen, utan att det krävs någon återställning.
    - Ställ alltid in **Redigeringsläge** för miljön till **Läsa** eller **Redigera** som det första test fallet eftersom standardalternativet är **Auto**. Alternativet **Auto** använder alltid den föregående inställningen och kan orsaka otillförlitliga tester. 
 
    [![Sidan Alternativ, fliken Prestanda](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Validera endast när du filtrerar efter en viss transaktion i stället för en allmän validering. För antalet poster kan du t.ex. filtrera för transaktionsnumret eller transaktionsdatumet så att valideringen exkluderar alla andra transaktioner. 
    - Om du checkar in ett kundsaldo eller en budgetkontroll sparar du först värdet och lägger sedan till transaktionsvärdet för att validera det förväntade resultatet istället för att validera ett fast förväntat värde. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]