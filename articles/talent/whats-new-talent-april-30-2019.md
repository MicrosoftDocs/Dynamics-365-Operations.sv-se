---
title: Vad är nytt och ändrat i Dynamics 365 Talent (30 april 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 38158948dbcf8966edf49bcce5b1e5da7eddb8dc
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026054"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Vad är nytt och ändrat i Dynamics 365 Talent (30 april 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2270. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Lämna feedback

Alternativet att ge feedback finns på menyn **hjälp** (**?**) i Talent. På den här menyn får du till gång till följande resurser:

- Feedback
- Hjälp
- Kom igång
- Support
- Förslag
- Om

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Detektera förbättringar av användargränssnittet för dubblettkontroll av medarbetare.

På grund av den här ändringen upptäcktes dubbletter nu när du anger namnfält och en statusindikator visar antalet dubbletter som har upptäckts. En länk som ges öppnar en sida där du kan utvärdera om du ska använda en av dubbletterna. Dublettsidan öppnas inte automatiskt för att undvika att inmatningen avbryts. Du måste markera länken om du vill öppna sidan.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

I den här veckans version stöder nu följande enheter anpassade fält: anställning, förmånstyp och betalningscykel.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Ett fel uppstår när en offboard-kontrollista tilldelas (299877)

Den här ändringen korrigerar ett felmeddelande som visas när du tilldelar en offboard-kontrollista till en medarbetare utanför uppsägningsprocessen.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>Länken för uppsägda arbetare öppnar fel arbetare (309939)

Den här ändringen åtgärdar ett problem som uppstår när du återanställer en medarbetare från en annan juridisk person och försöker gå till medarbetaren från listan över uppsagda arbetare.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>Kompensationskortet för medarbetarens självbetjäning visar inte summeringsvärden när avancerad säkerhet är aktiverat (315231)

Den här ändringen åtgärdar ett problem som uppstår när du använder avancerad kompensationssäkerhet. När avancerad säkerhet är påslagen, visar anställdes självbetjäning nu sammanfattningsbeloppet för både anställda och chefer. Före ändringen visas sammanfattningsvärden som 0 (noll).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Om en position utan titel skapas i Common Data Service, skapas ingen position i Talent (314562)

Den här veckans ändringar åtgärdar ett problem som uppstår när du skapar befattningar i Common Data Service men inte anger någon titel.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Felmeddelanden i prestandajournalposter i medarbetarsjälvbetjäning (314134)

Den här ändringen åtgärdar ett problem som uppstår när du bifogar resultatmål till poster i en medarbetarjournal i medarbetarsjälvbetjäning.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Tillåt att orsakskoder anges på tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Det här kravet kan finnas på grund av företagets policy eller gällande krav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Möjligheten att spåra arbetstiden och förstå hur tiden är beräknad hjälper inte bara HR till att svara på anställdas frågor, utan hjälper också till att säkerställa korrekt beviljande av ledighet för anställda. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom saldon.

## <a name="coming-soon"></a>Kommer snart

### <a name="email-support-for-alerts"></a>E-support för notifieringar

I plattformsuppdatering 26 för Finance and Operations kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse.
