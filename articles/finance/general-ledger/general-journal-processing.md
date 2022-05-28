---
title: Hantering av redovisningsjournaler
description: Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 Finance som kan underlätta processen för allmänna journaler och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.
author: kweekley
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9cfe4af0c666fb2accb6737edb2de6e0b6e7cdf1
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720039"
---
# <a name="general-journal-processing"></a>Hantering av allmänna journaler

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av de funktioner som kan underlätta processen för allmänna journaler och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.  

## <a name="journal-names"></a>Journalnamn

Ett av de viktigaste områdena att konfigurera är journalnamn. Det är en god idé att definiera specifika journalnamn för respektive ändamål, till exempel koncerninterna, periodiseringsjustering och felkorrigering. Du kan skräddarsy varje journalnamn för att göra datainmatningen för varje ändamål lätt och säker. 

På **Journalnamn** sidan kan du ställa in följande element:

-   **Arbetsflödesgodkännande** – För att öka den interna kontrollen, definiera journalarbetsflöden som upprättar gränser för granskning och godkännande av åtgärder, på grundval av kriterier såsom totala debetbeloppet. Du ställer in arbetsflöden för allmänna journaler på **Redovisningsarbetsflöden** sidan.
-   **Standardvärden** – Välj standardvärdena för kvittning, valuta och finansiella mått.
-   **Journalkontroll** – Du kan ställa in begränsningar för företaget och kontotyp och även segmentvärden. 

**Exempel**

Journalnamn kan endast användas för justeringar. I det här fallet kan du ange att endast **huvudbokskonton** är giltiga för alla företag. 

[![Kontotyper för journalkontroll.](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Journalnamn kan användas endast för en viss sektor eller ett datumintervall för huvudbokskonton. 

[![Journalkontrollsegment.](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

**Automatisk återföring** alternativet finns tillgängligt i allmänna journaler. Du kan till exempel ha en periodiserad justering där det aktuella dokumentet har inte bearbetats, som visas i följande illustration.
[![Allmän journalåterföring.](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

Microsoft Excel-tillägget för poster i redovisningsjournal ger en extra nivå av automatisering och gör dataregistreringen lättare. **Öppna rader i Excel** åtgärden är tillgänglig i **Allmän journal** och **Journalverifikat** sidor. 

På **Periodiska journaler** sidan kan du ställa in återkommande journaler till automatisk journalbearbetning. 

Du kan använda verifikationsmallar när som helst. På sidan **Allmänna journaler** finns åtgärderna **Spara** och **Välj verifikationsmall** på sidan **Journalverifikation**, under **Funktioner** för verifikationsraderna.

## <a name="related-setup"></a>Relaterade inställningar
Följande inställningar är inte specifika för allmänna journaler, men kommer att garantera korrekt dataregistrering, enkelt.

### <a name="main-account"></a>Huvudkonto

Huvudkontoinställningen ger flera alternativ för allmän journal bearbetning:

-   **D/K-behov** – Använd det här alternativet om en huvud konto är begränsat till debet eller kredit transaktioner. Inställningen verifieras när en journal är validerad eller publiceras.

-   **Standardmotkonto**
-   **Uppskjutet** – Stoppa ett huvudkonto för inmatning av data över alla företag eller för ett specifikt företag/ juridisk person.
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
- [Planera kontoplanen](plan-chart-of-accounts.md) 
- [Skapa avancerade regler för journaler](tasks/create-advanced-rules-journals.md)
- [Skapa en journalpost med en mall](tasks/create-journal-entry-template.md)
- [Skapa och validera journaler](tasks/create-validate-journals.md)
- [Bokför periodiska journaler](tasks/post-periodic-journals.md)
- [Bearbeta journal för redovisningsallokering](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>Simulera bokföring
Du hittar **Simulera bokföring** på menyn **Validera** för de flesta journaler. När du validerar en journal med hjälp av funktionen **Validera** testar systemet journalen för specifika felförhållanden. Om du använder funktionen **Simulera bokföring**, kör systemet alla samma processer som körs utan att själva bokföringen av journalen vid bokföring. Du kan sedan granska bokföringsmeddelanden som visas, korrigera eventuella fel som kan du söka efter och öppna menyn **bokför** om du vill bokföra journalen. 

**Simulera bokföring** är inte tillgänglig för batchbearbetning. Det finns emellertid kod tillgänglig för att simulera bokföring i batch kod och utvecklare kan använda kod för att lägga till funktionen.  

## <a name="journal-unlock"></a>Lås upp journal
En knapp är tillgänglig på sidan Journal för att låsa upp en journal med status "låst av systemet" inställd på Ja. Den här upplåsningen kan utföras av en systemadministratör som har analyserat alla exekverande batchjobb och bekräftat att den här journalen inte längre aktivt bearbetas av ett batchjobb. Den här knappen aktiveras med funktionen **knappen lås upp journal** på sidan **funktionshantering**. 

## <a name="workflow-recall"></a>Arbetsflödet har återkallats 
Möjligheten att återkalla en journal i ett arbetsflöde med statusen "oåterkallelig" aktiveras genom att använda knappen **arbetsflöde** i en journal och på sidan **arbetsflödeshistorik**. Detta aktiveras med funktionen som kallas **återställning av arbetsflödesstatusen för journaler** på sidan **funktionshantering**.

## <a name="delete-journal-lines"></a>Radera journalrader
Möjligheten att snabbt ta bort alla journalrader är aktiverad i en journal under **funktioner** > **ta bort journalrader**. Om du vill aktivera den här funktionen väljer du **funktionshantering**, välj **ta bort optimeringar för journalprestanda**. Denna funktion påverkar tillägg i tabellen **LedgerJournalTrans** och dess **Ta bort**-metod, detta eftersom raduppsättningen tas bort utan att anropa respektive rads **Ta bort**-metod. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
