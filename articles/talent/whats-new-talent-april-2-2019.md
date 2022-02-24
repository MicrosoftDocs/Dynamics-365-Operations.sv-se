---
title: Vad är nytt och ändrat i Dynamics 365 Talent (2 april 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
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
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 04b5a006d4580fe419d81986a90851bc8d611722
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528229"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-2-2019"></a>Vad är nytt och ändrat i Dynamics 365 Talent (2 april 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="approval-emails-in-attract"></a>E-postmeddelanden för godkännande i Attract
Nya e-postmeddelanden för godkännande ger bättre insyn i godkännandeprocessen. E-postmeddelanden skickas till godkännare när något av följande inträffar:

- En begärande skickar ett jobb för godkännande.
- Ett jobb avvisas eller godkänns.
- En godkännare inte har agerat på en begäran om godkännande inom 24 timmar.

Du kan anpassa innehållet i e-postmeddelanden för godkännande med nya mallar.

### <a name="application-and-profile-attachments"></a>Bilagor till ansökan och profil
Förbättringar av fliken **dokument** för ansökningar och talangpoolprofiler visas nu både på dokumentnamnet och typen.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Kommer snart (Attract och Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Lifecycle Services (LCS)-integration med rapportera ett problem
I Attract och Onboard loggas problem av slutanvändare genom funktionen rapportera ett problem skapar nu automatiskt supportfrågor i kundens LCS-projekt. Administratörer kan sedan sortera problemen och skicka dem till Microsoft när det behövs. Detta stämmer överens med hur Core HR hanterar supportfrågor för slutanvändaren.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2216.

### <a name="platform-update-25-for-finance-and-operations"></a>Plattformsuppdatering 25 för Finance and Operations
Mer information om plattformsuppdatering 25 för Finance and Operations finns i [Förhandsgranskningsfunktioner i Dynamics 365 for Finance and Operations-plattformsuppdatering 25 (april 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Avancerad kompensationssäkerhet (fasta och rörliga)
I många organisationer kan kompensations- och förmånsansvariga endast ha tillgång till vissa kompensationsposter. Dessa kan inkludera poster för chefer eller nationella medarbetare. Denna ändring ger personalavdelningen möjlighet att hantera och underhålla kompensationsplaner för olika medarbetargrupper i organisationen. Du kan tilldela säkerhetsroller till fasta och variabla planer. Dessa säkerhetsroller avgör åtkomst till planer och relaterade medarbetardata, till exempel lön- eller bonusposter så att endast de rollerna kan bearbeta kompensation för medarbetargrupper.

### <a name="upgrade-to-common-data-service"></a>Uppgradera till Common Data Service
Tidsgränser för uppgradering till Common Data Service för appar närmar sig snabbt. Logga in på Microsoft Power Apps-administrationscenter för att avgöra om databasen måste uppgraderas. Mer information om deadlines och nödvändiga instruktioner för uppgradering finns i [uppgradera till Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>I förhandsgranskning

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Tillåt att orsakskoder anges på tjänstledighetstyper
Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden
Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Detta kan bero på företagspolicy eller regelkrav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

## <a name="coming-soon"></a>Kommer snart

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Kontrollera förbättringar av användargränssnittet för dubblettkontroll av medarbetare.
Med denna ändring detekteras dubbletter när du anger namnfält och status visar antalet dubbletter som hittades. Du kan välja den angivna länken för att öppna en ny sida för att bedöma om du ska använda de identifierade träffarna. Dublettformuläret öppnas inte automatiskt för att undvika att inmatningen avbryts.

###  <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 25 för Finance and Operations kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse. 
