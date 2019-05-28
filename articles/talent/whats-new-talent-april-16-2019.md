---
title: Vad är nytt och ändrat i Dynamics 365 for Talent (16 april 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: adf8f470b00a565c62a27f857d490c6c000b21d8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519097"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-16-2019"></a>Vad är nytt och ändrat i Dynamics 365 for Talent (16 april 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="process-auditing"></a>Processgranskning

Du kan nu spåra de ändringar som har gjorts för kandidater, jobböppningar och jobbansökningar. Mer information finns i [spåra ändringar i rekryteringsdata](process-auditing.md)

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2239. Siffror inom parenteser refererar till supportnummer i Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Kompensationsregion, kompensationsnivå, förmånsalternativ och entiteter för färdighetstyper i Common Data Service uppdaterade för att inkludera kundfältstöd

Med den här versionen har Common Data Service-enheter uppdaterats med möjligheten att inkludera anpassade fält som läggs till genom Talent (Core HR).

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Nytt Common Data Service entitetsstöd för: överlåtelseregler för kompensation, kompensationsvariabelplan, variabel kompensation

I den här versionen har överlåtelseregler för kompensation, kompensationsvariabelplan och variabla kompensationsenheter lagts till i Common Data Service. Dessa entiteter stöder också anpassade fält som läggs till genom Talent (Core HR).

### <a name="powerbi-refresh-issues-314342"></a>PowerBI uppdateringsproblem (314342)

Den här ändringen åtgärdar ett problem med PowerBI-rapporter som uppdateras korrekt.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Det går inte att klicka direkt på övergångsaktiviteter i medarbetarsjälvbetjäning (303309)

Den här ändringen gör att användare med medarbetarrollen kan välja och uppdatera övergångsaktiviteter från att göra-listan i Talent.

### <a name="performance-feedback-email-message-updated-309615"></a>E-postmeddelande för prestandafeedback uppdaterad (309615)

Med den här ändringen visas ett bekräftelsemeddelande när återrapportering har skickats.

### <a name="missing-tables-in-word-template-308048"></a>Saknade tabeller i Word-mall (308048)

När du skapar en Word-mall med information om en medarbetare och kompetenser visas bara kompetenserna för den markerade medarbetaren i Word-dokumentet.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Vid användning av en offboard-checklista visas ett felmeddelande. (299877)

Den här ändringen åtgärdar ett problem när du använder en offboard-checklista direkt från medarbetarformuläret.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Tillåt att orsakskoder anges på tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Detta kan bero på företagspolicy eller regelkrav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Spåra medarbetares lediga tid och förstå hur ledig tid beräknas hjälper inte bara personalavdelningen att besvara frågor från medarbetare utan garanterar också korrekt beviljande av ledighet för medarbetare. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom saldon.

## <a name="coming-soon"></a>Kommer snart

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Kontrollera förbättringar av användargränssnittet för dubblettkontroll av medarbetare.

Med denna ändring detekteras dubbletter när du anger namnfält och status visar antalet dubbletter som hittades. Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna. Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.

### <a name="email-support-for-alerts"></a>E-support för notifieringar

Med plattformsuppdatering 25 kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse.


