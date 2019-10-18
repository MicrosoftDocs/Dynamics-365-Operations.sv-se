---
title: Nyheter och ändringar i Dynamics 365 Talent (6 maj 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6a4571abdb0e104af0a0657c75bf5a6b5764345a
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023871"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-6-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (6 maj 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Välj valfria dokument när erbjudanden skapas

När du väljer en mall för erbjudandepaketet uppmanar nu Attract att välja tillämpliga, valfria dokument från den paketmallen. Du kan lägga till ytterligare valfria dokument när du förbereder erbjudandet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2282. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26-for-finance-and-operations"></a>Plattformsuppdatering 26 för Finance and Operations

Ytterligare information om plattformsuppdatering 26 för Finance and Operations finns i [Förhandsgranskningsfunktioner i Dynamics 365 Finance and Operations plattformsuppdatering 26 (maj 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Common Data Service enhetsstöd för anpassade fält

I den här veckans utgåva har följande enheter nu stöd för anpassade fält: Förmångsberäkningsfrekvens, förmångsberäkningstarriff, förmånstyp, arbetskalender, arbetskalendersemester, lönecykel och identifieringstyper för arbetare.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Lämna massregistreringar, ändra nivåbasen till "Datum för tjänsteålder" uppdaterar inte den ursprungliga periodiseringen (318526)

När du anger massregistrering för medarbetare och ändrar nivåunderlag, återspeglar den ursprungliga periodiseringen det nivåunderlag som du har valt.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Arbetsflöde som visar dubbla platshållare (313636)

Ändringar i den här versionen eliminerar dubblering av platshållare när arbetsflödesmeddelanden skickas.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>Dimensionsfält uppdateras inte när du använder "öppna i Excel" (176261)

Med den här versionen kan du nu uppdatera den ekonomiska dimensionen **Öppna i Excel** från sidan **arbetare**. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>Arbetaradress skapades i Common Data Service synkroniseras inte med Talent (317555)

Med den här ändringen uppdateras adresser som skapats i Common Data Service i Talent: Core HR.


## <a name="in-preview"></a>I förhandsgranskning

### <a name="new-page-to-validate-position-hierarchy-data"></a>Ny sida för validering av data för befattningshierarki

Personal (HR) och administratörer kan nu validera ledarskapshierarkin för att få cirkulära referenser som av misstag har importerats. Du kan komma åt den här nya sidan från **Organisationsadministration > Länkar > Befattningar > Validering av befattningshierarki**.

### <a name="specify-reason-codes-on-leave-types"></a>Ange orsakskoder för tjänstledighetstyper

Organisationer kanske behöver ytterligare information om ledighetsbegäranden. Du kan nu ange orsakskoder för tjänstledighetstyper och aktivera medarbetare att välja en orsakskod för deras ledighetsbegäranden.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Kräv orsakskoder för vissa tjänstledighetstyper på ledighetsbegäranden

Organisationer kan kräva orsakskoder för specifika tjänstledighetstyper när medarbetare skickar ledighetsansökningar. Det här kravet kan finnas på grund av företagets policy eller gällande krav. Du kan ange vilka tjänstledighetstyper som kräveren orsakskod och du kan kräva att anställda ger en orsakskod för deras tjänstledighetstypens ledighetsansökningar.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Ange transaktionslista för ledighet och frånvaro för personalavdelningen

Möjligheten att spåra arbetstiden och förstå hur tiden är beräknad hjälper inte bara HR till att svara på anställdas frågor, utan hjälper också till att säkerställa korrekt beviljande av ledighet för anställda. Personalavdelningen har nu en ny vy i transaktioner (anslag, periodiseringar, justeringar och begäranden) för att se skälen bakom saldon.

## <a name="coming-soon"></a>Kommer snart

### <a name="indicate-instance-type-when-provisioning-talent"></a>Ange instanstyp vid etablering av Talent

När du etablerar en ny instans av Talent kan du ange om instanstypen är **Produktion** eller **Begränsat läge**, vilket gör det möjligt att testa nya funktioner tidigt. Alla befintliga Talent-instanser kommer att uppdateras till produktionsinstanstypen. Om du vill uppdatera en av dina befintliga förekomster till instanstypen begränsat läge kontaktar du supporten för att initiera ändringsbegäran.
