---
title: Nyheter och ändringar i Dynamics 365 Talent (3 december 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528703"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (3 december 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2646. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Arbetsytan Funktionshantering

Arbetsytan **Funktionshantering** ger en lista med funktioner som levereras i varje utgåva. Nya funktionen är avstängda som standard. Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem. Mer information om hur du aktiverar Funktionshantering finns i [Översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Alla nya funktioner förblir i förhandsgranskning i minst 30 dagar, vanligtvis 30-60 dagar. Huvudfunktionerna är vanligtvis tillgängliga i oktober och april varje år efter förhandsgranskningsperioden. Så snart du ser nya funktioner på arbetsytan **Funktionshantering** kan du aktivera dem. Vissa funktioner kan vara aktiverade som standard.
 
I vissa situationer är en integrerad funktion som standard och kan inte inaktiveras (t.ex. arbetsytan **funktionshantering**).
 
När en funktion är allmänt är tillgänglig kan den aktiveras eller inaktiveras i produktionsmiljöer. Arbetsytan **funktionshantering** anger när en förhandsgranskningsfunktion blir obligatorisk. Detta datum är vanligtvis den 1 oktober eller 1 april för anpassning till halvårs frisläppningsplanerna. De kan inte inaktivera obligatoriska funktioner. Du kan aktivera och inaktivera en funktion i alla miljöer tills den blir obligatorisk.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Lägg till automatisk schemaläggning av rensning av batchjobbhistorik (332528)

Med den här ändringen körs **Historik över batchjobb** varje natt och tar bort historikobjekt för batchjobb som är äldre än 30 dagar.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>Talent svarar inte i arbetaråtgärder när identifieringsnummerlängden inte matchar identifieringstypen (390971)

Den här utgåvan korrigerar problemet dykt upp när ID-nummerlängden inte matchar definitionen inom identifieringstypen. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>Fast kompensation uppdaterar inte nivå med ändringar av befattningsinformation (348085)

I den här veckans version bestämmer **Startdatum för kompensation** bestämmer jobbet förknippat med positionen vid den tidpunkten när man skapar en ny fast ersättningsrekord för en anställd.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>Arbetstagare, anställda och entreprenörer listor visar arbetartyp som både när de ska endast vara arbetstagare eller entreprenör (384473)

Den här ändringen återspeglar exakt typen av arbetstagare som anges (entreprenör eller anställd).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>E-postaviseringar för nya anställningsåtgärder innehåller inte namninformation på grund av säkerhetsprinciper (383402)

Den här ändringen korrigerar informationen som visas i fälten förnamn eller efternamn i platshållarna för arbetsflödet när avancerad säkerhet är aktiverad.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>Systemet tillåter två heldags ledighetsförfrågningar för samma dag (379284)

Med den här ändringen kan du inte utfärda två tjänstledighetsbegäranden för samma dag. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>Adressändringar lista ska sorteras efter giltighetsdatum (352798)

Med den här ändringen är adress ändringslistan nu sorterad efter **giltighetsdatum**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>Ledighetsansökningar bör raderingar från Common Data Service till Talent (376999)

Med den här ändringen kan utkast och annullerade tjänstledighetsförfrågningar raderas från Common Data Service och sedan tas bort från Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>Ta bort inkomstkoder tillåts när samma inkomstkod tilldelas en medarbetare (371792)

I den här versionen måste du först ta bort inkomstkoden från medarbetaren innan du tar bort inkomstkoden från systemet.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>Arbetsflödena tjänstledighet och frånvaro med två godkännandefaser slutförs inte (391116)

Med den här ändringen fortsätter arbetsflödet ledighet och frånvaro genom alla steg när mer än en godkännandefas har konfigurerats för begäran.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>Utfärdandedatum synkroniseras inte till Common Data Service när uppdateras eller anges i Talent (397361)

Den här ändringen korrigerar ett problem där utleveransdatumet för posten **personidentifiering** inte synkroniserat till Common Data Service från Talent.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>Cirkulärt cirkelreferens felutfärdat när du tilldelar en chef till en befattning (386659)

Den här ändringen korrigerar ett unikt scenario där ett cirkelreferensfel visas när du tilldelar en ny chef till en befattning.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Common Data Service-entiteter som nu stöder anpassade fält

Följande Common Data Service entiteter nu stöder anpassade fält:

| Namn | Enhet |
| --- | --- |
| Bankkontoutbetalningar | cdm_bankaccountdisbursement |
| Frekvens i förmånsberäkning | cdm_benefitcalculationfrequency |
| Löneperiod med frekvens i förmånsberäkning | cdm_benefitcalculationfrequencypayperiod |
| Tariff för förmånsberäkning | cdm_benefitcalculationrate |
| Uppgift om tariff för förmånsberäkning | cdm_benefitcalculationratedetail |
| Förmånsalternativ | cdm_benefitoption |
| Förmånsplan | cdm_benefitplan (inte aktiverat för stöd för anpassade fält) |
| Förmånstyp | cdm_benefittype |
| Affärsprocesskalender | cdm_businessprocesscalendar |
| Tilldelning av affärsprocessgrupp | cdm_businessprocessgroupassignment |
| Affärsprocessbibliotekets uppgiftsgrupp | cdm_businessprocesslibrarytaskgroup |
| Affärsprocessfas | cdm_businessprocessstage |
| Checklistemallens rubrik | cdm_businessprocesstemplateheader |
| Checklistemallens uppgift | cdm_businessprocesstemplatetask |
| Företag | cdm_company |
| Plan för fast kompensation | cdm_compensationfixedplan |
| Kompensationsrutnät | cdm_compensationgrid |
| Kompensationsnivå | cdm_compensationlevel |
| Lönefrekvens för kompensation | cdm_compensationpayfrequency |
| Kompensationsreferenspunkt | cdm_compensationreferencepointsetup |
| Ställ in kompensationsreferenspunkt | cdm_compensationreferencepointsetupline |
| Kompensationsregion | cdm_compensationregion |
| Kompensationsstruktur | cdm_compensationstructure |
| Variabel kompensationsplan | cdm_compensationvariableplan |
| Variabel kompensationsplannivå | cdm_compensationvariableplanlevel |
| Typ av variabel kompensationsplan | cdm_compensationvariableplantype |
| Avdelning | cdm_department |
| Anställning | cdm_employment |
| Etniskt ursprung | cdm_ethnicorigin |
| Händelse för fast kompensation | cdm_fixedcompensationevent |
| Befattning | cdm_job |
| Jobbfunktion | cdm_jobfunction |
| Jobbefattning | cdm_jobposition |
| Jobbtyp | cdm_jobtype |
| Språk | cdm_language |
| Lämna banktransaktion | cdm_leavebanktransaction |
| Lämna anmälan | cdm_leaveenrollment |
| Tjänstledighetsplan | cdm_leaveplan |
| Begäran om tjänstledighet | cdm_leaverequest |
| Information om att lämna begäran | cdm_leaverequestdetail |
| Tjänstledighetstyp | cdm_leavetype |
| Ledighetstypens orsakskod | cdm_leavetypereasoncode |
| Lönecykel | cdm_paycycle |
| Löneperiod | cdm_payperiod |
| Inkomstkod för lön | cdm_payrollearningcode |
| Utfärdande organ personidentifiering | cdm_personidentificationissuingagency |
| Befattningstyp | cdm_positiontype |
| Befattningstilldelning för arbetare | cdm_positionworkerassignmentmap |
| Orsakskod | cdm_reasoncode |
| Kompetenstyp | cdm_skilltype |
| Skatteregion | cdm_taxregion |
| Överlåtelseregel | cdm_vestingrule |
| Veteranstatus | cdm_veteranstatus |
| Arbetskalender | cdm_workcalendar |
| Arbetsdagar i kalendern | cdm_workcalendarday |
| Helgdag i arbetskalender |cdm_workcalendarholiday |
| Arbetskalenderns datumrad | cdm_workcalendarholidayline |
| Tidsintervall till arbetskalendern | cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält) |
| Arbetare | cdm_worker |
| Arbetarens adress | cdm_workeraddress |
| Bankkonto för arbetare | cdm_workerbankaccount |
| Fast arbetarkompensation | cdm_workerfixedcompensation |
| Arbetarens personuppgift | cdm_workerpersonaldetail |
| Arbetsidentifieringsnummer | cdm_workerpersonidentificationnumber |
| Arbetsidentifieringstyp | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>I förhandsgranskning

Funktionerna för förhandsgranskning är endast tillgängliga i **begränsade** miljöer

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]