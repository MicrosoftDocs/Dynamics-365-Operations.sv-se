---
title: Nyheter och ändringar i Dynamics 365 Talent (13 maj 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
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
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 42feeb044d0a4cd25faf2d74863aa4e948c200fd
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008833"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-13-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (13 maj 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="coming-soon-in-attract"></a>Kommer snart i Attract

### <a name="job-approvals-on-home-page"></a>Jobbgodkännanden på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, titel, andra godkännare och tilldelat datum. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2297. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Ange instanstyp vid etablering av Talent

När du etablerar en ny instans av Talent kan du ange om instanstypen är **Produktion** eller **Begränsat läge**, vilket gör det möjligt att testa nya funktioner tidigt. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

I den här veckans utgåva har följande Common Data Service-enheter nu stöd för anpassade fält: Anställning, förmångsberäkningsfrekvens, förmångsberäkningstarriff, arbetskalendersemester, lönecykel och identifieringstyp.

### <a name="common-data-service-integration-page"></a>Common Data Service-integrationssida

Den här versionen innehåller ett nytt alternativ i **Systemadministration > Länkar > Integrationer > Common Data Service-konfiguration**. Med alternativet **Common Data Service-konfiguration** kan en administratör eller datahanteringsadministratör ha flexibilitet och insikt i Common Data Service. Med det här alternativet kan du aktivera eller inaktivera Common Data Service-integration med en Talent-instans och visa synkroniseringsinställningarna mellan Talent-instansen och Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importera resultatdata med slutgiltig medarbetarklassificering (316710)

I den här versionen kan du importera historiska medarbetarklassificeringsdata. Fältet **FinalEmployeeRatingId** har nu skrivbehörighet.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>Det går inte att skapa medarbetaradress i Common Data Service och synkronisera den med Talent (317555)

Den här ändringen gör att adressdata som skapades i Common Data Service synkroniseras med Talent.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="new-page-to-validate-position-hierarchy-data"></a>Ny sida för validering av data för befattningshierarki

Personal (HR) och administratörer kan validera ledarskapshierarkin för att få cirkulära referenser som av misstag har importerats. Du kan komma åt den här nya sidan från **Organisationsadministration > Länkar > Befattningar > Validering av befattningshierarki**.

### <a name="specify-reason-codes-on-leave-types"></a>Ange orsakskoder för tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Det här kravet kan finnas på grund av företagets policy eller gällande krav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Möjligheten att spåra arbetstiden och förstå hur tiden är beräknad hjälper inte bara HR till att svara på anställdas frågor, utan hjälper också till att säkerställa korrekt beviljande av ledighet för anställda. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom ledighetssaldon.
