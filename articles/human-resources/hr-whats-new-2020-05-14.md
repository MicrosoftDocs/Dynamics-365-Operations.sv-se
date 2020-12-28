---
title: Nyheter och ändringar i Dynamics 365 Human Resources (14 maj 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 14 maj 2020.
author: Darinkramer
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 76ca497cc7fabf737c8a0ee71363f22fd4201ea8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528507"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (14 maj 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3244. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Lifecycle Services (LCS) för referens.

## <a name="platform-changes"></a>Plattformsändringar

Plattformsändringar ingår i den här veckans version. Mer information finns i [Plattformsuppdateringar för version 10.0.10 av Finance and Operations-appar (maj 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34). I den här versionen ingår felkorrigeringar och ändringar i sparade vyer.
 
## <a name="ensure-common-data-service-picklists-are-consistent-with-leave-enums-436343"></a>Kontrollera att Common Data Service-plocklistor är konsekventa med uppräkningar (enum) för tjänstledighet (436343)

Common Data Service-plocklistor är nu konsekventa med uppräkningar (enum) för tjänstledighet.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Tillåt användare att konfigurera arbetsflödet för ansökan om tjänstledighet baserat på kvantiteten för förfrågan (300044)

Användare kan konfigurera arbetsflödet för ansökan om tjänstledighet baserat på kvantiteten för förfrågan
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>Formuläret ny medarbetare visar data via Visa-menyn när avancerad säkerhet är aktiverad (403185)

Den här versionen korrigerar hur visning av medarbetare mellan olika juridiska personer fungerar när avancerad åtkomst är aktiverad och medarbetare i andra företag är tillgängliga.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Tillåt körning av ledighetsperiodiseringar för en enskild plan eller ett enskilt företag (318844)

Med den här ändringen kan du köra periodiseringar för ett företag eller en plan.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Visa befattningens heltidsmotsvarighet ("full time equivalent", FTE) i formuläret för anmälda arbetare (414658)

FTE-värdet tillhärande en medarbetares befattning avgör en medarbetares periodiseringspris när alternativet för heltid (FTE) är aktiverat för tjänstledighetstypen. Detta fält inkluderas nu i formuläret **Anmälda medarbetare** och i dialogrutan **Massregistrering**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Lägg till batchjobb för utgångsdatum för ledighetssaldo (431266)

Nu finns ett nytt batchjobb som körs dagligen. Detta minskar det återstående tjänstledighetssaldot när utgångsdatum inträffar.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>Export av personliga kontakter för en medarbetare som använder den personliga entiteten för en kontakt person för medarbetare exporterar inga personliga kontakter med den överordnade relationstypen (345893)

Dataentiteten **Personlig kontaktperson för medarbetare** (**HcmPersonalContactPersonEntity** i DMF och **PersonalContactPerson** i OData) kunde inte exportera personliga kontakter som har relationstypen **Överordnad**. Det här problemet åtgärdas för personliga kontakter som skapas efter denna ändring. Befintliga personliga kontakter av typen **Överordnad** kommer att korrigeras i senare versioner.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Orsakskoder visas mellan olika scenarier när de markeras som tjänstledighet och frånvaro och det strömlinjeformade medarbetarformuläret aktiveras (434163)

Denna ändring begränsar orsakskoderna till endast tjänstledighets- och frånvarokoder när du aktiverar strömlinjeformade medarbetarposter.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>Förhandsgranskningsfunktionen Tilldela en tjänstledighetsplan till anställda i framtiden uppvisar fel (433555)

Den här ändringen korrigerar ett fel när en tjänstledighetsplan har tilldelats två tjänstledighetstyper och du försöker tilldela en medarbetare.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>Komma igång-banderollen visas för alla användare (441731)

Med den här ändringen döljs Komma igång-banderollen för användare som inte är systemadministratörer eller datahanteringsadministratörer. 

## <a name="the-common-data-service-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>Common Data Service-entiteten för medarbetaradresser fungerar på annorlunda i fråga om giltighetsdatum i personal (425071)

Den här ändringen innehåller adressinformation som är justerad i vissa scenarier, baserat på adressens datum.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Det går inte att lägga till en bilaga till en godkänd tjänstledighetsansökan (425407)

Med den här veckans version kan du lägga till bilagor till godkända tjänstledighetsansökningar utan att ändra hela ansökan.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="leave-suspension"></a>Lämna uppehåll

Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Uppdatera användarupplevelsen att anger att periodiseringen är pausad (429550)

Användarupplevelsen anger nu att periodiseringen har avbrutits för en plan.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper (272447)

I den här versionen kan HR skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet. Obetald tjänstledighet kan vara en typ, men behöver inte vara det. Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF-enhet tillgänglig för periodiserade avstängningar (429549)

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Lägg till orsakskod för periodiserade avstängningar (429547)

Orsakskoder har lagts till den periodiserade avstängningen.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Påbörja övergång från Human Resources-parametrar till tjänstledighets- och frånvaroparametrar

Den här versionen börjar kombinera Human Resources-parametrar med parametrar för tjänstledighet och frånvaro.

## <a name="carry-forward-rules"></a>Överför regler

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)