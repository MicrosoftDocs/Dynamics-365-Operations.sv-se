---
title: Vad är nytt och ändrat i Dynamics 365 Talent (9 april 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
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
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462645"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Vad är nytt och ändrat i Dynamics 365 Talent (9 april 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS)-integration med rapportera ett problem
I Attract och Onboard loggas problem av slutanvändare genom funktionen rapportera ett problem skapar nu automatiskt supportfrågor i kundens LCS-projekt. Administratörer kan sedan sortera problemen och skicka dem till Microsoft när det behövs. Detta stämmer överens med hur Core HR hanterar supportfrågor för slutanvändaren.

### <a name="relevance-search"></a>Relevanssökning
I talangpooler kan nu du söka efter särskilda kvalifikationer, namn eller utbildningsbakgrund i kandidatens hela databas. Du behöver inte längre ange vilken del av kandidatens profil som du vill genomsöka. Attract söker hela profilen och markerar alla matchningar som hittades. Attract söker även alla dokument som är tillgängliga för en kandidat och rangordnar intelligent sökresultaten. Dessutom kan du filtrera resultaten efter källa eller om de är en silvermedaljör. Mer information finns i [Sök och visa kandidatprofiler](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Rekommendation av potentiell kandidat
Attract kan hjälpa till att kickstarta källa för ett jobb när du aktiverar den genom att göra intelligenta kandidatrekommendationer från organisationens kandidatdatabas. Rekommendationerna omfattar de kompetenser och utbildningsinformation som identifierades vid sökning efter relevanta potentiella kandidater. Rekommendationerna visas på fliken **potentiella kandidater** under ett jobb om du aktiverar det under jobbets anställningsprocess. Mer information i [Rekommendation av potentiell kandidat](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Intervjuarens tillgänglighetstatus
Intervjuplaneraren kommer snart att kunna visa status **Ej på kontoret, arbetar någon annan stans** för intervjuare för att hjälpa tidsplanera tider som fungerar bättre för intervjuare.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Kandidatens erfarenhet av intervjuare: spara kalenderinbjudan
Kandidater kan nu hämta och spara deras intervjuhändelser till sina personliga kalendrar med hjälp av en .ics-fil som är kopplad till intervjuns sammanfattande e-postmeddelande som skickas till kandidaten.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS)-integration med rapportera ett problem
I Attract och Onboard loggas problem av slutanvändare genom funktionen rapportera ett problem skapar nu automatiskt supportfrågor i kundens LCS-projekt. Administratörer kan sedan sortera problemen och skicka dem till Microsoft när det behövs. Detta stämmer överens med hur Core HR hanterar supportfrågor för slutanvändaren.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>Procent av grundläggande variabla planer läser in felaktigt belopp
Den här veckans version korrigerar ett problem vid inläsning av variabel kompensation som använder procent av grundläggande planer.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>Datumväljare den sista arbetade dagen fungerar inte korrekt
Den här ändringen löser problemet: när användare redigerar **anställningens slutdatum** och väljer datum med hjälp av kalendern, läggs en dag till markeringen.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Begränsa personalåtgärdstyper genom den vidtagna åtgärden
Denna ändring begränsar de åtgärdstyper som visas när vissa åtgärder vidtas. Exempelvis när en ny befattning begärs visas endast nya befattningsåtgärder i listan med åtgärder som du väljer. Tidigare visades både nya och redigerade åtgärder. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Överför en anställd med kompensation i en andra juridisk person
Den här versionen tillåter att kompensation avslutas i en andra juridisk person om överföringen är för en överföring mellan företag.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Det går inte att välja kompensation för en framtida anställning under en överföring
Vid överföring av en anställd till en ny juridisk person kan du nu ställa in kompensation för den nya juridiska personen under överföringsprocessen.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>Användaren kan inte tilldela kompensation under befattningstilldelning
Lägga till en ny befattningstilldelning gör att du kan ställa in poster för fast kompensation. 

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

###  <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 25 för Finance and Operations kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]