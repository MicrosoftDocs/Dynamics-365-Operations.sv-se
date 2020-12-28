---
title: Vad är nytt och ändrat i Dynamics 365 Talent (23 april 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 53faf972759c8f770017fcd3a87920410988e626
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527203"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Vad är nytt och ändrat i Dynamics 365 Talent (23 april 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2253. Siffror inom parenteser refererar till supportnummer i Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält
Med den här veckans version har följande entiteter stöd för anpassade fält: kompensationsnivå, förmånsalternativ, färdighetstyp och kompensationsregion.

### <a name="additional-odata-entities-302992"></a>Ytterligare OData-entiteter (302992)
Följande entiteter stöds nu i OData: arbetares professionella upplevelse och arbetares utbildning.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Bilagor med prestationsjournal för chefer och medarbetare (308248)
Med den här versionen kan du nu använda bilagor för både chefer och medarbetare när du skapar och uppdaterar prestationsjournalposter.

### <a name="employee-rehire-flag-always-available-310047"></a>Medarbetares återanställningsflagga är alltid tillgänglig (310047)
Alternativet medarbetarens återanställning är nu tillgängligt för uppdatering utanför uppsägningsprocessen. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>Det går inte att ändra **Min betalningsmetod** (308815)
Anpassning har aktiverats för att tillåta etiketten **min betalningsmetod** för att ändras i Självbetjäning för medarbetare.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Ekonomiska dimensioner för en befattning kan inte tas bort (293908)
Ekonomiska dimensioner kan nu tas bort när du begär en ändring av en befintlig befattning och de ekonomiska dimensionernas gränser för korsföretaget. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>Kunden kan inte publicera tillbaka data i Talent när data från Excel öppnas (302955)
Den här ändringen löser ett publiceringsproblem när du använder relaterade register.

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
## <a name="known-issues"></a>Kända problem

### <a name="email-support-for-alerts"></a>E-support för notifieringar
Med plattformsuppdatering 26 för Finance and Operations kan användare skapa notifieringsregler som automatiskt levererar e-postmeddelanden till kontakter när de utlöses av en händelse.
