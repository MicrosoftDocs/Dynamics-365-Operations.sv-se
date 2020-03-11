---
title: Common Data Service-entiteter
description: Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087356"
---
# <a name="common-data-service-entities"></a>Common Data Service-entiteter

Microsoft Dynamics 365 Human Resources använder Common Data Service för att aktivera scenarier för utökning och integration.

Mer information om Common Data Service, se [Vad är Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Följande personalentiteter är tillgängliga i Common Data Service.

## <a name="benefit-entities"></a>Förmånsentiteter

| Namn | Enhet |
| --- | --- |
| Frekvens i förmånsberäkning | cdm_benefitcalculationfrequency |
| Löneperiod med frekvens i förmånsberäkning | cdm_benefitcalculationfrequencypayperiod |
| Tariff för förmånsberäkning | cdm_benefitcalculationrate |
| Uppgift om tariff för förmånsberäkning | cdm_benefitcalculationratedetail |
| Förmånsalternativ | cdm_benefitoption |
| Förmånsplan | cdm_benefitplan (inte aktiverat för stöd för anpassade fält) |
| Förmånstyp | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Entiteter för affärsprocessuppgifter

| Namn | Enhet |
| --- | --- |
| Affärsprocesskalender | cdm_businessprocesscalendar |
| Tilldelning av affärsprocessgrupp | cdm_businessprocessgroupassignment |
| Affärsprocessbibliotekets uppgiftsgrupp | cdm_businessprocesslibrarytaskgroup |
| Affärsprocessfas | cdm_businessprocessstage |
| Checklistemallens rubrik | cdm_businessprocesstemplateheader |
| Checklistemallens uppgift | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Enheter för kompensation

| Namn | Enhet |
| --- | --- |
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
| Händelse för fast kompensation | cdm_fixedcompensationevent |
| Överlåtelseregel | cdm_vestingrule |
| Fast arbetarkompensation | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Organisationsenheter

| Namn | Enhet |
| --- | --- |
| Avdelning | cdm_department |
| Anställning | cdm_employment |
| Företag | cdm_company |
| Befattning | cdm_job |
| Jobbfunktion | cdm_jobfunction |
| Befattning | cdm_jobposition |
| Befattningstyp | cdm_positiontype |
| Befattningstilldelning för arbetare | cdm_positionworkerassignmentmap |
| Jobbtyp | cdm_jobtype |
| Språk | cdm_language |

## <a name="leave-and-absence-entities"></a>Enheter för tjänstledighet och frånvaro

| Namn | Enhet |
| --- | --- |
| Lämna banktransaktion | cdm_leavebanktransaction |
| Lämna anmälan | cdm_leaveenrollment |
| Tjänstledighetsplan | cdm_leaveplan |
| Begäran om tjänstledighet | cdm_leaverequest |
| Information om att lämna begäran | cdm_leaverequestdetail |
| Tjänstledighetstyp | cdm_leavetype |
| Ledighetstypens orsakskod | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Löneenheter

| Namn | Enhet |
| --- | --- |
| Lönecykel | cdm_paycycle |
| Löneperiod | cdm_payperiod |
| Inkomstkod för lön | cdm_payrollearningcode |
| Bankkontoutbetalningar | cdm_bankaccountdisbursement |
| Skatteregion | cdm_taxregion |

## <a name="worker-entities"></a>Entiteter för arbetare

| Namn | Enhet |
| --- | --- |
| Arbetare | cdm_worker |
| Arbetarens adress | cdm_workeraddress |
| Arbetarens personuppgift | cdm_workerpersonaldetail |
| Arbetsidentifieringsnummer | cdm_workerpersonidentificationnumber |
| Arbetsidentifieringstyp | cdm_workerpersonidentificationtype |
| Arbetskalender | cdm_workcalendar |
| Arbetsdagar i kalendern | cdm_workcalendarday |
| Helgdag i arbetskalender |cdm_workcalendarholiday |
| Arbetskalenderns datumrad | cdm_workcalendarholidayline |
| Tidsintervall till arbetskalendern | cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält) |
| Bankkonto för arbetare | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Enheter för arbetarkonfiguration

| Namn | Enhet |
| --- | --- |
| Veteranstatus | cdm_veteranstatus |
| Etniskt ursprung | cdm_ethnicorigin |
| Orsakskod | cdm_reasoncode |
| Utfärdande organ personidentifiering | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Kompetensenheter

| Namn | Enhet |
| --- | --- |
| Kompetenstyp | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modeller för enhetsrelation

### <a name="worker"></a>Arbetare

![Arbetare](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Jobb och jobbefattning

![Jobb och jobbefattning](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Fördelar

![Fördelar](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensation

![Kompensation](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Lämna

![Lämna](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Arbetskalender

![Arbetskalender](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Se även

[Välja en dataintegreringsteknik](hr-admin-integration-choose-technology.md)</br>
[Konfigurera Common Data Service-integrering](hr-admin-integration-common-data-service.md)