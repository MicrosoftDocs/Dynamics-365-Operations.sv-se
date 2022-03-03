---
title: Regeluppdateringar
description: Det här avsnittet innehåller en lista med planerade och utgivna regleruppdateringar för Microsoft Dynamics 365 Finance.
author: VStamberg
ms.date: 01/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: vastrup
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10
ms.openlocfilehash: 663b7d3162af6d385bc9c445b1e98cf5f74a1471
ms.sourcegitcommit: f2a78e0d7d461ca843ac2f9abff7690275db9196
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2022
ms.locfileid: "8105574"
---
# <a name="regulatory-updates"></a>Regeluppdateringar

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de regeluppdateringar som planeras och ges ut i Dynamics 365 Finance lokaliseringar som stöds. Leveranstidslinjer kan ändras och planerade funktioner kan ändras eller kanske inte har frisläppts. Mer information finns i [Microsoft policy](https://go.microsoft.com/fwlink/p/?linkid=2007332). 

Regeluppdateringar är funktioner som har implementerats så att de stöder ny eller ändrad landsspecifik lagstiftning. För ytterligare information om andra planerade och släppta landsspecifika funktioner finns i [Dynamics 365 and Power Platform lanseringsplaner](/business-applications-release-notes/index).

Microsoft strävar efter att implementera nya regelkrav så tidigt som möjligt. Det faktiska leveransdatumet beror på rätt meddelandedatum, tillgänglighet av kravdetaljer från de lokala myndigheterna, tillgänglighet av valideringsverktyg och på storlek och komplexitet av ändringen.

Vi planerar att släppa andra tjänstuppdateringar för en version som ges ut i tid för kunderna att uppdatera och vara klar för genomförandedatumet (för transaktionsbaserade regeluppdateringar) eller för första obligatoriska rapporteringsdeadline (för regeluppdateringar relaterade till rapportering). Kunder och partners kan förhandsgranska regeluppdateringar i PEAP (Preview Early Adoption Program).

Vid sena meddelandedatum, sen tillgänglighet av kravdetaljer eller valideringsverktyg eller ovanligt stora och komplexa ändringar kanske det inte är möjligt att göra en andra regeluppdatering tillgänglig genom allmänna tillgänglighetsdatum av en månatlig uppdatering. I så fall måste regeluppdateringen levereras som snabbkorrigeringar för relevanta månatliga uppdateringar.

Regeluppdateringar som ingår i månadens uppdatering indikeras endast av en utgiven version. Regeluppdateringar som levereras antingen som snabbkorrigeringar eller som en del av en versions förhandsgranskning kan identifieras genom förkortningarna HF respektive PEAP. 

För de senaste kravuppdateringsplanerna, se följande tabell.   

|Land|Frisläppningsdatum|Slutversion|Regeluppdatering|
|--------------------|---------------|-------|-------| 
|      Österrike         |   Augusti 2021      | 10.0.22      |   Momsdeklarationen i XML förhandsgranska och Excel   |
|      Österrike         |   2021 september      | 10.0.22HF      |   Intrastat-format uppdateras från 2022 – Ursprungsland och partnermoms-ID blir obligatoriskt i utförsel   |
|      Belgien        |   2021 oktober      | 10.0.22HF     |   Intrastat-transaktionskoder ändras till 2 siffror från 2022  |
|      Brasilien         |   Augusti 2021      | 10.0.22      |   NF-e NT2020.006 – Identifiering av mellanhand för digital plattform (uppdatering av layout- och valideringsregler)   |
|      Brasilien         |   2021 december         | 10.0.22, 10.0.23, 10.0.24         |    SPED skattelayout 2022  |
|      Tjeckien         |   2021 oktober         | 10.0.23HF         |     Intrastat-format uppdateras från 2022 – Ursprungsland och partnermoms-ID blir obligatoriskt i utförsel  |
|      Danmark         |   2021 december         | 10.0.22HF         |    Intrastat-formatet uppdateras med början från 2022  |
|      Estland         |   2021 december      | 10.0.22HF      |   Intrastat-format uppdateras från 2022 – Ursprungsland och partnermoms-ID blir obligatoriskt i utförsel  |
|      Finland         |   November 2021         | 10.0.22HF         |    Intrastat-formatet uppdateras med början från 2022.  |
|      Tyskland        |   Augusti 2021       | 10.0.22HF      |   Intrastat-formatet INSTAT XML uppdateras med början från 2022. Intrastat-formatet TXT gäller inte från 01.07.2021  |
|      Tyskland        |   2021 oktober       | 10.0.23      |   Momsdeklaration i XML och förhandsgranskning i Excel (ny design med belopp i momskodsvaluta, som arbetar ur rutan med funktionen för återförd moms, kan utföras i juridiska personer som inte är DE och kan samla in momstransaktioner från flera juridiska personer)  |
|      Italien         |   November 2021         | 10.0.22HF, 10.0.23HF, 10.0.24         |    Elektronisk fakturering för gränsöverskridande transaktioner  |
|      Mexiko         |   November 2021      | 10.0.22      |   Carta de Porte-komplement i CFDI-dokument   |
|      Mexiko         |   2021 december      | 10.0.24      |   Carta de Porte komplement version 2.0  |
|      Nederländerna        |   2021 oktober      | 10.0.22HF      |   2-siffriga transaktionskoder i Intrastat-filformat från 2022  |
|      Nya Zeeland         |   Augusti 2021      | 10.0.22    |   GST deklarationsformulär GST101A  |
|      Norge        |   November 2021      | 10.0.24      |   Momsdeklarationsformat 2022 med direkt sändning - Dynamics 365 Finance |
|      Oman         |   Augusti 2021      | 10.0.22      |   Momsdeklaration - version 1 |
|      Polen          |   2021 oktober     | 10.0.23, 10.0.24     |   JPK_V7M - ny schemaversion från januari 2022 |
|      Polen          |   November 2021     | 10.0.24HF     |   Årsrapport om betalningsdatum i kommersiella transaktioner |
|      Polen          |   2021 oktober     | 10.0.24     |   Elektroniskt format för lista över försäljning inom EU (VAT-UE) |
|      Ryssland          |   2021 oktober     | 10.0.22HF, 10.0.23, 10.0.24    |   Ändringar i försäljning, försäljningsböcker och fakturajournaler|
|      Ryssland          |   2021 oktober     | 10.0.24HF    |   Ändra format på momsdeklarationer med redovisningsfiler|
|      Ryssland          |   November 2021     | 10.0.24    |   Federal Accounting Standards 6/2020 (anläggningstillgångar)|
|      Saudiarabien          |   November 2021     | 10.0.22HF, 10.0.23    |   Generering av elektronisk fakturering i Saudiarabien - fas 1|
|      Saudiarabien          |   November 2021     | 10.0.22HF, 10.0.23HF, 10.0.24    |   Butik - elektronisk fakturering i Saudiarabien - fas 1|
|      Spanien          |   2021 oktober     | 10.0.23    |    Momsdeklaration modell 303 i txt och förhandsgranska och Excel|
|      Spanien          |   2021 september     | 10.0.22    |    Intrastat-formatet kommer att uppdateras för rapportering 2022 - Partners momsregistreringsnummer och ursprungsland kommer att vara obligatoriska vid utskick|
|      Sverige          |   2021 oktober     | 10.0.22HF    |    Intrastat-format uppdateras från 2022 – Ursprungsland och partnermoms-ID blir obligatoriskt i utförsel. 2-siffriga transaktionskoder används.|
|      Storbritannien          |   Augusti 2021     | 10.0.22    |    Storbritannien – MTD-bedrägeriförebyggande 2021)|



## <a name="additional-resources"></a>Ytterligare resurser
- Mer information om alla planerade och frisläppta landsspecifika regeluppdateringar finns i [Sök efter landsspecifika lagstadgade uppdateringar](search-for-regulatory-updates.md). (Inloggning krävs.)
- För en lista över lokalisering som kan användas, se [Guide över internationell tillgänglighet](https://aka.ms/dynamics_365_international_availability_deck).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
