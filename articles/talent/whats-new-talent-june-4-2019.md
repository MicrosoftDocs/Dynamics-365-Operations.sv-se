---
title: Nyheter och ändringar i Dynamics 365 Talent (4 juni 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97b44ee0d985755b33971c29c1f39561c4138fad
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896898"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-june-4-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (4 juni 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Kommer snart i Attract

### <a name="job-approvals-on-the-home-page"></a>Jobbgodkännanden på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännaren kan granska godkännandena under **tilldelade till dig**. I det här avsnittet visas jobb-ID, titel, andra godkännare och det datum då jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska deras jobb under **begärd av dig**. I det här avsnittet visas godkännarna som måste fortfarande godkänna det skickade jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Ny sida för validering av data för befattningshierarki

Personal (HR) och administratörer kan validera ledarskapshierarkin för att få cirkulära referenser som av misstag har importerats. Du kan komma åt den här nya sidan från **Organisationsadministration \> Länkar \> Befattningar \> Validering av befattningshierarki**.

### <a name="specify-reason-codes-on-leave-types"></a>Ange orsakskoder för tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Det här kravet kan finnas på grund av företagets policy eller gällande krav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Möjligheten att spåra arbetstiden och förstå hur tiden är beräknad hjälper inte bara HR till att svara på anställdas frågor, utan hjälper också till att säkerställa korrekt beviljande av ledighet för anställda. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom ledighetssaldon.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>Om du tar bort en post från Talent tas posten bort från Common Data Service

Poster som tas bort från Talent Core HR tas nu också bort från Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>Variabel kompensationsplan giltig från/till-datum uppfylls inte

I den här versionen kan du inte registrera en medarbetare i en variabel kompensationsplan om start datumet infaller före planens slutdatum. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>Resultatgranskningskommentarer tas bort när användaren väljer Avbryt

I den här versionen åtgärdar ett problem när granskningskommentarerna tas bort om en användare börjar ändra en kommentar men väljer **Avbryt**. 

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanser **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

## <a name="coming-soon-in-core-hr"></a>Kommer snart i Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visa utökad information för prestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner som deras anställda hanterar gemensamt. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda. 

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Medarbetare, chefer och personal kan skriva ut en medarbetares resultatöversyn.
