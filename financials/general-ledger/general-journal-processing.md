---
title: Hantering av redovisningsjournaler
description: "I den här artikeln beskrivs funktionerna i Microsoft Dynamics 365 för operationer som hjälper dig att skapa allmänna bearbetning enklare och som hjälper också garantera att korrekta data har tagits emot och intern kontroll inte äventyras."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 50cd203025be8857de943e458fc32315e494fb7a
ms.lasthandoff: 03/31/2017


---

# <a name="general-journal-processing"></a>Hantering av redovisningsjournaler

Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics AX som kan underlätta processen för allmänna journaler och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.  

Journalnamn

Ett av de viktigaste områdena som konfigurerar är journalnamn. Det är en god idé att definiera specifika journalnamn för respektive ändamål såsom koncerninterna påförs justering och felkorrigering. Du kan skräddarsy varje journalnamn för att datainmatning för varje ändamål lätt och är säkert. 

På **Journalnamn** sidan kan du ställa in följande element:

-   **Arbetsflödesgodkännande** – För att öka den interna kontrollen, definiera journalarbetsflöden som upprättar gränser för granskning och godkännande av åtgärder, på grundval av kriterier såsom totala debetbeloppet. Du ställer in arbetsflöden för redovisningsjournaler på den ** redovisningen arbetsflöden ** sida.
-   **Standardvärden** – Välj standardvärdena för kvittning, valuta och finansiella mått.
-   **Journalkontroll** – Du kan ställa in begränsningar för företaget och kontotyp och även segmentvärden. 

**Exempel**

Journalnamn kan endast användas för justeringar. I det här fallet kan du ange att endast **huvudbokskonton** är giltiga för alla företag. [![Journalen Kontrollera kontotyper](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Journalnamn kan användas endast för en viss sektor eller ett datumintervall för huvudbokskonton. [![Journalen kontrollen segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

**Automatisk återföring** alternativet finns tillgängligt i allmänna journaler. Du kan till exempel ha en periodiserad justering där det aktuella dokumentet har inte bearbetats, som visas i följande illustration.
[![Återföring av redovisningsjournal](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Microsoft Excel-tillägg för journalpost ger ytterligare automatisering och underlättar datainmatningen. **Öppna rader i Excel **åtgärden är tillgänglig i **Allmän journal** och **Journalverifikat** sidor. 

På **Periodiska journaler** sidan kan du ställa in återkommande journaler till automatisk journalbearbetning. 

Du kan använda verifikationsmallar när som helst. På den **redovisningsjournaler** sidan det **spara** och **Välj verifikationsmall** åtgärder finns på den **Bokföringsorder** sidan under **funktion** för verifikationsraderna.

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

Mer information finns i [planering: kontoplanen](plan-chart-of-accounts.md). 


