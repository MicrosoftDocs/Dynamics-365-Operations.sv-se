---
title: Nyheter och ändringar i Dynamics 365 for Talent (28 maj 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
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
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c99e0f3637a8d958e31a046eaad6faa57ce3e1e7
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856291"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-28-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (28 maj 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Kommer snart i Attract

### <a name="job-approvals-on-home-page"></a>Jobbgodkännanden på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, titel, andra godkännare och tilldelat datum. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

I den här versionen stöder följande Common Data Service-entiteter anpassade fält: information om förmånsberäkningstarriff, arbetskalendersemesterrad och anställning.

### <a name="copy-position-now-includes-payroll-details"></a>Kopiera befattning nu inkluderar nu löneinformation
När du använder **kopiera befattning** och väljer alla alternativ, inkluderas nu informationen om löneinformation i kopieringsinformationen. 

## <a name="in-preview-in-core-hr"></a>I förhandsgranskning i Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Vissa av tjänstledighetstyperna kanske inte är lämpliga för att medarbetare ska kunna skicka ledighet för och hanteras av personal (HR) i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Ny sida för validering av data för befattningshierarki

Personal (HR) och administratörer kan validera ledarskapshierarkin för att få cirkulära referenser som av misstag har importerats. Du kan komma åt den här nya sidan från **Organisationsadministration > Länkar > Befattningar > Validering av befattningshierarki**.

### <a name="specify-reason-codes-on-leave-types"></a>Ange orsakskoder för tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Det här kravet kan finnas på grund av företagets policy eller gällande krav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Möjligheten att spåra arbetstiden och förstå hur tiden är beräknad hjälper inte bara HR till att svara på anställdas frågor, utan hjälper också till att säkerställa korrekt beviljande av ledighet för anställda. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom ledighetssaldon.
