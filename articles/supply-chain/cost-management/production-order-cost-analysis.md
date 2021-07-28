---
title: Analys av kostnad för produktionsorder
description: Den här artikeln innehåller information om den kostnadsanalys som du kan göra för slutförda och aktuella tillverkningsorder. Du kan analysera de uppskattade och faktiska kostnaderna med hjälp av prisberäkningssidan eller rapporten Kostnadsuppskattningar och kostnadsredovisningar. Information om uppskattade och faktiska kostnader (och kvantitet) visas för varje komponentartikel, flödesoperationen och den indirekta kostnaden.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage, ProdSetupHistoricalCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d0a298a8f782ae318971e99c03e864fa5a4ef88
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343660"
---
# <a name="production-order-cost-analysis"></a>Analys av kostnad för produktionsorder

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om den kostnadsanalys som du kan göra för slutförda och aktuella tillverkningsorder. Du kan analysera de uppskattade och faktiska kostnaderna med hjälp av prisberäkningssidan eller rapporten Kostnadsuppskattningar och kostnadsredovisningar. Information om uppskattade och faktiska kostnader (och kvantitet) visas för varje komponentartikel, flödesoperationen och den indirekta kostnaden.

De faktiska kostnaderna för en tillverkningsorder baseras på den rapporterade förbrukningen av material och flödesoperationerna. Du kan se detaljerade transaktioner om rapporterad förbrukning av material, flödesoperationer och indirekta kostnader för en tillverkningsorder på sidan **Produktionsbokföring**.

## <a name="variance-analysis-for-a-completed-production-order"></a>Avvikelseanalys för en slutförd tillverkningsorder
Avvikelserna återspeglar en jämförelse mellan de rapporterade produktionsaktiviteterna och standardkostnadsberäkningen för produktionsartikeln. Avvikelserna innebär ingen jämförelse med tillverkningsorderns uppskattade kostnader. De rapporterade produktionsavvikelserna omfattar förbrukning av material och flödesoperationer tillsammans med de associerade indirekta kostnaderna och den kvantitet som rapporteras som färdig. Följande fyra varianstyper beräknas:

-   Partistorleksavvikelse
-   Produktionskvantitetsavvikelse
-   Produktionsprisavvikelse
-   Produktionsersättningsavvikelse

I bilden nedan visas de fyra avvikelserna som står för skillnaden mellan en tillverkningsorders faktiska kostnader och de beräknade kostnaderna i artikelns kostnadspost när tillverkningsordern avslutas. 

![Avvikelser som förklarar skillnaderna i en avslutad produktionsorder.](./media/control.jpg) 

Du kan analysera produktionsavvikelser genom att använda sidan **avvikelse** rapporten **produktionsavvikelse**. Använd visningsalternativen om du vill visa detaljerade avvikelser per artikel och verksamhetsresurs eller per kostnadsgrupp. Principen för kostnadsuppdelning i lagerparametrarna bestämmer om avvikelser spåras efter kostnadsgrupp. Du kan också använda visningsalternativen **enstaka**, **flera** och **summa** för att visa sammanfattande avvikelser. Den detaljerade avvikelseinformationen ger dig en bättre förståelse för källan till respektive avvikelse. Om du vill kunna förutse avvikelserna innan tillverkningsordern avslutas, kan du analysera den detaljerade informationen som finns i rapporten **Kostnadsuppskattningar och kostnadsredovisningar**.

## <a name="cost-analysis-for-current-production-orders"></a>Kostnadsanalys för aktuella produktionsorder
Olika rapporter innehåller information om respektive transaktion. Använd dessa rapporter när du vill analysera kostnader för rapporterade produktionsaktiviteter. Information visas bara för aktuella tillverkningsorder med statusvärdet **Startat** eller **Rapporterat som färdigt**.

-   **Material i arbete** − den här rapporten innehåller de plocklistetransaktioner som rapporteras mot aktuella tillverkningsorder för ett angivet transaktionsdatum. Rapporten anger komponentens kvantitet som utlevereras och kostnadsbeloppet för varje transaktion. Använd urvalsvillkoret för en enstaka komponentartikel. Du kan till exempel skriva ut information om komponentens utlevererade kvantitet mot tillämpliga tillverkningsorder. Den utfärdade kvantiteten uppdateras inte av de kvantiteter som rapporteras som färdiga för den överordnade artikeln. Därför kan faktiska kvantiteten råmaterial i arbete överskattas.
-   **Produkter i arbete** − den här rapporten innehåller de flödestransaktioner (eller jobbtransaktioner) som rapporteras mot aktuella tillverkningsorder för ett angivet transaktionsdatum. I rapporten anges timmar, belopp och kvantitet (både godkänd kvantitet och antal fel) som har rapporterats för varje transaktion. Den innehåller också information som operationsnummer, operations-ID och verksamhetsresurs. Rapporten visar även total tid och totalt belopp för alla transaktioner gentemot tillverkningsordern och den kvantitet som har rapporterats som färdig.
-   **Pågående indirekta kostnader** − den här rapporten visar de indirekta kostnader som har uppstått för tillverkningsorder. Dessa data baseras på rapporterad förbrukning för flödesoperationer och komponenter för ett angivet transaktionsdatum. I rapporten visas typ av indirekt kostnad (tillägg eller tariff),kostnadsbladskod för indirekta kostnader samt kostnadsbeloppet för varje transaktion. Rapporten ger inte någon information om flödeskorts- eller plocklistetransaktionen som genererade den indirekta kostnaden.
-   **Kostnadsredovisning av produktion pågår** – den här rapporten visar den kombinerade förbrukningen av material, flödesoperationer och indirekta kostnader mot tillverkningsordern vid ett angivet transaktionsdatum.
-   **Färdiga artiklar i arbete** – den här rapporten visar aktuella tillverkningsorder och transaktioner för rapporterat som färdigt vid ett angivet transaktionsdatum.


## <a name="additional-resources"></a>Ytterligare resurser

[Gemensamma källor till produktionsavvikelser](common-sources-of-production-variances.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]