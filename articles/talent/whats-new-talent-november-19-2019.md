---
title: Nyheter och ändringar i Dynamics 365 Talent (19 november 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
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
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa984a01e9da30e6da07516fa2986833366a882b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527154"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (19 november 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2621. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Plattformsuppdatering 31 för Finance and Operations-appar

Mer information finns i [Förhandsgranskningsfunktioner i plattformsuppdatering 31 för Finance and Operations-appar (januari 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>Arbetsytan Funktionshantering (383856)

Arbetsytan **Funktionshantering** ger en lista med funktioner som levereras i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem. Mer information om hur du aktiverar Funktionshantering finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan **Funktionshantering** kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.
 
I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan **funktionshantering**).
 
När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan **funktionshantering** anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>Meddelandet visas när det finns en annullerad åtgärd för en befattning (382887)

Följande meddelande visas inte längre när du väljer en viss befattning och en annullerad åtgärd är allt som är tillgängligt för befattningen: **En oavslutad åtgärd pågår för befattningen xxxxxx**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>I Learning Analytics visar kurstypen och statusen felaktiga data (381151)

Denna veckas utgåva uppdaterade Learning Analytics för att visa **kurstyp** och **status** korrekt.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>Personnumret ska visas i den nya arbetarens formulär banderoll (383832)

I formuläret **ny arbetare** visas nu **personnumret** i banderollen för snabb referens.

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>Befattningens startdatum bestämmer vilken jobbpost som ska användas när en kompensationsnivå hämtas under anställning (350361)

I den här versionen bestämmer **Startdatum för kompensation** vilken nivå som har tilldelats det nya jobbet.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>Anpassade plocklistefält i befattningsregistret synkroniseras inte till Common Data Service (387503)

I den här versionen har du nu synkroniserat plocklisteartiklar med Common Data Service.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>Entiteten för arbetaradress synkroniseras inte med Common Data Service när nya data importeras (349673)

I den här veckans utgivning synkroniseras nu adressdata med Common Data Service medan nya data importeras.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.
