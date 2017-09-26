---
title: Hantering av redovisningsjournaler
description: "Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition som kan underlätta processen för allmänna journaler, och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: 68da281cb4793ed83f70c68d061d327aa8a8c772
ms.contentlocale: sv-se
ms.lasthandoff: 08/01/2017

---

# <a name="general-journal-processing"></a>Hantering av redovisningsjournaler

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition som kan underlätta processen för allmänna journaler, och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.  

Journalnamn

Ett av de viktigaste områdena att konfigurera är journalnamn. Det är en god idé att definiera specifika journalnamn för respektive ändamål, till exempel koncerninterna, periodiseringsjustering och felkorrigering. Du kan skräddarsy varje journalnamn för att göra datainmatningen för varje ändamål lätt och säker. 

På **Journalnamn** sidan kan du ställa in följande element:

-   **Arbetsflödesgodkännande** – För att öka den interna kontrollen, definiera journalarbetsflöden som upprättar gränser för granskning och godkännande av åtgärder, på grundval av kriterier såsom totala debetbeloppet. Du ställer in arbetsflöden för allmänna journaler på sidan **Arbetsflöden för redovisning**.
-   **Standardvärden** – Välj standardvärdena för kvittning, valuta och finansiella mått.
-   **Journalkontroll** – Du kan ställa in begränsningar för företaget och kontotyp och även segmentvärden. 

**Exempel**

Journalnamn kan endast användas för justeringar. I det här fallet kan du ange att endast **huvudbokskonton** är giltiga för alla företag. [![Kontotyper för journalkontroll](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Journalnamn kan användas endast för en viss sektor eller ett datumintervall för huvudbokskonton. [![Journalkontrollsegment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

**Automatisk återföring** alternativet finns tillgängligt i allmänna journaler. Du kan till exempel ha en periodiserad justering där det aktuella dokumentet har inte bearbetats, som visas i följande illustration.
[![Allmän journalåterföring](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Microsoft Excel-tillägget för poster i redovisningsjournal ger en extra nivå av automatisering och gör dataregistreringen lättare. **Öppna rader i Excel** åtgärden är tillgänglig i **Allmän journal** och **Journalverifikat** sidor. 

På **Periodiska journaler** sidan kan du ställa in återkommande journaler till automatisk journalbearbetning. 

Du kan använda verifikationsmallar när som helst. På sidan **Allmänna journaler** finns åtgärderna **Spara** och **Välj verifikationsmall** på sidan **Journalverifikation**, under **Funktioner** för verifikationsraderna.

## <a name="related-setup"></a>Relaterade inställningar
Följande inställningar är inte specifika för allmänna journaler, men kommer att garantera korrekt dataregistrering, enkelt.

### <a name="main-account"></a>Huvudkonto

Huvudkontoinställningen ger flera alternativ för allmän journal bearbetning:

-   **D/K-behov** – Använd det här alternativet om en huvud konto är begränsat till debet eller kredit transaktioner. Inställningen verifieras när en journal är validerad eller publiceras.
-   **Standardmotkonto**
-   **Uppskjutet** – Stoppa ett huvudkonto för inmatning av data över alla företag eller för ett specifikt företag/juridiska enheter.
-   **Tillåt inte manuell inmatning** – Förhindra användare från att manuellt ange ett värde för kontot i journaler.
-   **Standard/Validera valuta**
-   **Juridisk person åsidosätter** – Denna inställning är specifik för definierade företag/juridiska enhet:
    -   **Standard/Validera moms**
    -   **Standarddimension** – **Inte fast** eller **Fast värde**. **Fast värde** kommer att bidra till att garantera att alla konteringar för detta konto använder alltid något dimensionsvärde som är inställt som **fast**.
-   **Bokföringsvalidering**
    -   **Användarvalidering** – Det här alternativet styr vilka användare som tillåts bokföra på huvudkonto.
    -   **Konteringstypvalidering** – Med det här alternativet styr vilka konteringstyper som tillåts för huvudkonto.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Redovisningsstrukturer och avancerade regler strukturer

Redovisningsstrukturer och avancerade regler strukturer är oerhört viktiga för att garantera att de data som krävs för ekonomisk rapportering och uppföljning av prestationer är fångade under allmän journal bearbetning och all dokumentation. Redovisningsstrukturer och avancerade regler strukturer kan du skräddarsy data entry-upplevelse. Du kan registrera data endast för finansiella mått som är relevanta i varje situation, och kan också genomdriva kravet på att obligatorisk och korrekt data alltid finnas fångat.

Mer information finns i följande avsnitt:
- [Planering: Kontoplan](plan-chart-of-accounts.md) 
- [Skapa avancerade regler för journaler](tasks/create-advanced-rules-journals.md)
- [Skapa en post i en redovisningsjournal med hjälp av en mall](tasks/create-journal-entry-template.md)
- [Skapa och validera journaler](tasks/create-validate-journals.md)
- [Bokför periodiska journaler](tasks/post-periodic-journals.md)
- [Bearbeta journal för redovisningsallokering](tasks/process-ledger-allocation-journal.md)


