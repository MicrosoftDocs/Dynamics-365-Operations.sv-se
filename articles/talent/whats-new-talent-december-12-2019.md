---
title: Nyheter och ändringar i Dynamics 365 Talent (10 december 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/10/2019
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
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b4bb599be27e7d97fed1c060f97627c7c6a868e6
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915520"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-10-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (10 december 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2660. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Arbetsytan Funktionshantering

Arbetsytan **Funktionshantering** ger en lista med funktioner som levereras i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem. Mer information om hur du aktiverar Funktionshantering finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan **Funktionshantering** kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.
 
I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan **funktionshantering**).
 
När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan **funktionshantering** anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

### <a name="streamlined-worker-form-has-moved-to-the-feature-management-workspace-390583"></a>Förenklat arbetarformulär har flyttats till arbetsytan funktionshantering (390583)

Med den här ändringen kan nu den strömlinjeformade arbetarformuläret aktiveras i arbetsytan **funktionshantering**. Den här funktionen har flyttats från formuläret **systemparametrar** i **systemadministration**.

### <a name="prevent-hcmworkerpayrollinfo-records-from-being-written-without-a-worker-value-394526"></a>Förhindra att HcmWorkerPayrollInfo-poster skrivs utan ett arbetarvärde (394526)

Med den här versionen **HcmWorkerPayrollInfo**-poster under utan arbetarreferens i det här scenariot. 

### <a name="message-log-associated-to-the-action-isnt-populated-when-the-action-fails-to-complete-374007"></a>Meddelandeloggen som är kopplad till åtgärden fylls inte när åtgärden inte slutförs (374007)

Den här utgåvan innehåller en ändring för att fylla i åtgärdsmeddelandeloggen när en åtgärd misslyckas i vissa scenarier. 

### <a name="common-data-service-integration-batch-job-creation-388030"></a>Common Data Service-integration batch-jobb skapas (388030)

Med den här ändringen skapas batchjobb Common Data Service-integration när tjänsten är aktiverad.

### <a name="additional-pick-list-values-to-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a>Ytterligare plocklistevärden till anpassade fält visas inte i Common Data Service när du klickar på tillämpa på anpassade fältformulär (379599)

Med denna ändring synkroniseras nu nya värden för plocklistor som anges i Talent till Common Data Service när du tillämpar ändringarna.

### <a name="update-to-common-data-service-for-then-leave-bank-transaction-entity-turns-into-an-insert-on-talent-side-352938"></a>Uppdatera till Common Data Service för sedan lämna banktransaktionen entiteten förvandlas till en infogning på Talent-sida (352938)

Den här ändringen korrigerar ett problem där en uppdatering av en lämna banktransaktion skapar en ny post i Talent.

## <a name="in-preview"></a>I förhandsgranskning

Funktionerna för förhandsgranskning är endast tillgängliga i **begränsade** miljöer

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.

