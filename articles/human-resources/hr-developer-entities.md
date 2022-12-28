---
title: Dataverse-register
description: Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838593"
---
# <a name="dataverse-tables"></a>Dataverse-register


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.

> [!NOTE]
> Personal-entiteter motsvarar Dataverse-register. Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Följande Dataverse-register baseras på Personal-entiteter.

För mer information om de kända problemen, se [Problemsökning i Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Förmånsregister

| Namn | Register | Kända problem  | Status |
| --- | --- |    --------|----------  |
| Frekvens i förmånsberäkning | cdm_benefitcalculationfrequency |     |     |
| Löneperiod med frekvens i förmånsberäkning | cdm_benefitcalculationfrequencypayperiod |     |     |
| Tariff för förmånsberäkning | cdm_benefitcalculationrate |    |     |
| Uppgift om tariff för förmånsberäkning | cdm_benefitcalculationratedetail |753225 | Löst  |
| Förmånsalternativ | cdm_benefitoption |    |     |
| Förmånsplan | cdm_benefitplan (inte aktiverat för stöd för anpassade fält) |    |     |
| Förmånstyp | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Uppgiftsentiteter för affärsprocesser

| Namn | Register |Kända problem  | Status |
| --- | --- |   --------|----------   |
| Affärsprocesskalender | cdm_businessprocesscalendar | 751867 | Löst |
| Tilldelning av affärsprocessgrupp | cdm_businessprocessgroupassignment | 751869  751863 | Aktiva|
| Affärsprocessbibliotekets uppgiftsgrupp | cdm_businessprocesslibrarytaskgroup |751866 | Stängd |
| Affärsprocessfas | cdm_businessprocessstage |      |     |
| Checklistemallens rubrik | cdm_businessprocesstemplateheader |     |     |
| Checklistemallens uppgift | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Kompensationsregister

| Namn | Register |Kända problem  | Status |
| --- | --- | ----------      | -------    |
| Fast kompensationsplan | cdm_compensationfixedplan |754453 | Stängd |
| Kompensationsrutnät | cdm_compensationgrid |             |     |
| Kompensationsnivå | cdm_compensationlevel |           |     |
| Lönefrekvens för kompensation | cdm_compensationpayfrequency |                  |     |
| Kompensationsreferenspunkt | cdm_compensationreferencepointsetup |               |     |
| Ställ in kompensationsreferenspunkt | cdm_compensationreferencepointsetupline |             |     |
| Kompensationsregion | cdm_compensationregion |                   |     |
| Kompensationsstruktur | cdm_compensationstructure |    754456        | Stängd    |
| Variabel kompensationsplan | cdm_compensationvariableplan |               |     |
| Variabel kompensationsplannivå | cdm_compensationvariableplanlevel |                |     |
| Typ av variabel kompensationsplan | cdm_compensationvariableplantype |               |     |
| Händelse för fast kompensation | cdm_fixedcompensationevent |               |     |
| Överlåtelseregel | cdm_vestingrule |              |     |
| Arbetarens fasta kompensation | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Organisationsregister

| Namn | Register |Kända problem  | Status |
| --- | --- | ----------      | -------    |
| Avdelning | cdm_department |  752194    | Stängd    |
| Anställning | cdm_employment | 762414  |  Stängd  |
| Företag | cdm_company |  |     |
| Befattning | cdm_job |  |     |
| Jobbfunktion | cdm_jobfunction |        |     |
| Befattning | cdm_jobposition | 752214      | Stängd    |
| Befattningstyp | cdm_positiontype |            |     |
| Befattningstilldelning för medarbetare | cdm_positionworkerassignmentmap | 752224    |  Stängd   |
| Befattningsdimension | cdm_jobpositiondimension|       |     |
| Jobbtyp | cdm_jobtype |      |     |
| Språk | cdm_language |        |     |
| Namn | cdm_title |       |     |

> [!NOTE]
> Ekonomiska dimensioner för **Befattningstyp**, **Befattningstilldelning för arbetare** och **Anställning** ger integration med Dataverse i en riktning. Uppdateringar av ekonomiska dimensioner kan för närvarande inte synkroniseras från Dataverse till personal. 

## <a name="leave-and-absence-tables"></a>Tjänstledighets- och frånvaroregister

| Namn | Register | Kända problem  | Status |
| --- | --- |   ----------      | -------    |
| Transaktion för tjänstledighetsbank | cdm_leavebanktransaction |  752252    |    Löst |
| Anmälning om tjänstledighet | cdm_leaveenrollment |  752934    |Stängd     |
| Tjänstledighetsplan | cdm_leaveplan |   752232   |   Stängd  |
| Begäran om tjänstledighet | cdm_leaverequest | 753207     | Stängd    |
| Information om att lämna begäran | cdm_leaverequestdetail | 753207     |   Stängd  |
| Tjänstledighetstyp | cdm_leavetype |      |     |
| Ledighetstypens orsakskod | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>Integreringen av dubbelriktad skrivning med Dataverse tabeller för ledighet och frånvaro är endast tillgänglig när funktionen **Konfigurera flera tjänstledighetstyper för en enskild tjänstledighetsplan** är aktiverad i Microsoft Dynamics 365 Finance med **Funktionshantering**. 

## <a name="payroll-tables"></a>Löneregister

| Namn | Register |Kända problem  | Status |
| --- | --- |  ----------      | -------    |
| Lönecykel | cdm_paycycle |    |     |
| Löneperiod | cdm_payperiod |          |     |
| Inkomstkod | cdm_payrollearningcode |   754458        |   Stängd  |
| Bankkontoutbetalningar | cdm_bankaccountdisbursement |    751904     |   Stängd  |
| Skatteregion | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Medarbetarregister

| Namn | Register |Kända problem  | Status |
| --- | --- |----------      | -------    |
| Arbetare | cdm_worker |    751906    |    Stängd |
| Adress för arbetare | cdm_workeraddress |   754465     |Stängd     |
| Arbetarens personuppgift | cdm_workerpersonaldetail |   751906     |   Stängd  |
| Arbetsidentifieringsnummer | cdm_workerpersonidentificationnumber |  766704      |   Stängd  |
| Arbetsidentifieringstyp | cdm_workerpersonidentificationtype |        |     |
| Arbetskalender | cdm_workcalendar |        |     |
| Arbetsdagar i kalendern | cdm_workcalendarday |        |     |
| Helgdag i arbetskalender |cdm_workcalendarholiday |        |     |
| Arbetskalenderns datumrad | cdm_workcalendarholidayline |        |     |
| Tidsintervall till arbetskalendern | cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält) |        |     |
| Bankkonto för arbetare | cdm_workerbankaccount |        |     |

## <a name="worker-setup-tables"></a>Inställningsregister för medarbetare

| Namn | Register |
| --- | --- |
| Veteranstatus | cdm_veteranstatus |
| Etniskt ursprung | cdm_ethnicorigin |
| Orsakskod | cdm_reasoncode |
| Utfärdande organ för personidentifiering | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Kompetensregister

| Namn | Register |
| --- | --- |
| Kompetenstyp | cdm_skilltype |

## <a name="table-relationship-models"></a>Relationsmodeller för register

### <a name="worker"></a>Arbetare

![Arbetare.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Jobb och jobbefattning

![Jobb och jobbefattning.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Förmåner

![Förmåner.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensation

![Kompensation.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Tjänstledighet

![Tjänstledighet.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Arbetskalender

![Arbetskalender.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Se även

[Välja en dataintegreringsteknik](hr-admin-integration-choose-technology.md)<br>
[Konfigurera Dataverse-integrering](hr-admin-integration-common-data-service.md)<br>
[Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Vanliga frågeställningar och svar om virtuella register i Personal](hr-admin-virtual-entity-faq.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Terminologiuppdateringar](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
