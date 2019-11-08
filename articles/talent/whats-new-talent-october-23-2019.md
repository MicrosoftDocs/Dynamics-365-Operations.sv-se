---
title: Nyheter och ändringar i Dynamics 365 Talent (23 oktober 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
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
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 94243f83121a1306d8f9ae9be23d24e5c9b63a2d
ms.sourcegitcommit: 07e109dec176a93eff0df8a37ba5d875f212e9f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/25/2019
ms.locfileid: "2662675"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (23 oktober 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2569. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Plattformsuppdatering 30 för Finance and Operations-appar

Mer information finns i [Nyheter och ändringar i plattformsuppdatering 30 för Finance and Operations-appar (november 2019)](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Ta bort funktionen för öppna anmälan i förhandsversionen

I samverkan med vårt meddelande i blogginlägget Strategiska investeringar i Core HR-systemet för att effektivisera verksamheten tar Microsoft bort funktionen för öppna anmälan i den allmänna förhandsversionen 18 oktober 2019. I stället kommer nya funktioner att publiceras i framtiden. Produktionsanvändning av funktionen för öppna anmälan som för närvarande ingår i den allmänna förhandsgranskningen stöds inte.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Ett fel uppstod när landet/regionen i formuläret Arbetare skulle väljas en andra gång (350294)

Med den här veckans version har ärendet korrigerats när ett land eller en region väljs i formuläret **arbetare**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>Värden för ekonomiska dimensioner är som standard fältet för kombinationsvisning när Tillåt inte manuell inmatning är inställt på Sant (340097)

Med den här ändringen, när du ställer in ekonomiska dimensioner och använder alternativet att inte tillåta manuell inmatning, kommer systemet att korrekt standardisera dimensionsvärdet till fältet **kombinationsvisning**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>Nya relationstyper ska läggas till i Relationssökning i formuläret personliga kontakter (347691)

I den här versionen ingår nya funktioner för att lägga till nya **Relationstyper** i registret Relationstyper och återspegla ändringarna i Relationssökningen för personliga kontakter.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Ytterligare listvärden i anpassade fält visas inte i Common Data Service (379599)

Med den här veckans version kan du lägga till ett nytt listvärde i ett befintligt anpassat fält som redan Common Data Service är synkroniserat med de nya värdena för plocklistan visas nu när du har tillämpat ändringarna på enheten.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>På sidan anställningsvillkor visas alla medarbetarnas anställningsvillkor när du väljer Öppna i Excel (348073)

Med den här versionen öppnas bara de valda medarbetarnas anställningsvillkor i Excel. All företagssäkerhet används också.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service---324178"></a>Associationen mellan entiteten arbetskalendersemester och entiteten arbetskalender saknas i Common Data Service - (324178)

Den här relationen har lagts till med versionen. Den här ändringen gör att arbetsdagar för en medarbetare kan visas i PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Felmeddelande när arbetsflöden för medarbetarsjälvbetjäning med konfigurerbara hierarkier används (370132)

I den här versionen finns det bättre meddelanden om hur du konfigurerar arbetsflöden med konfigurerbara hierarkier. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>Systemet tillåter att nya positioner skapas där tillgängligheten för tilldelningsdatum infaller före aktiveringsdatumet (340103)

Den här ändringen visar en varning när datumet **tillgängliga för tilldelning** infaller före datumet **aktivering**.

## <a name="coming-soon"></a>Kommer snart

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.

### <a name="feature-management-workspace"></a>Arbetsytan Funktionshantering

Funktioner läggs till och uppdateras i alla versioner. Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.

Mer information om de ändringar som kommer från funktionshantering finns i [översikt över funktionshantering](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
