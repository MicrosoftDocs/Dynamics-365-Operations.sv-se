---
title: Dataverse-register
description: Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8ddb74a2f0b6265c5be3c13a009211455ea862da
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893410"
---
# <a name="dataverse-tables"></a>Dataverse-register

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources använder Dataverse för att aktivera scenarier för utökning och integration.

> [!NOTE]
> Personal-entiteter motsvarar Dataverse-register. Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Följande Dataverse-register baseras på Personal-entiteter.

## <a name="benefit-tables"></a>Förmånsregister

| Namn | Register |
| --- | --- |
| Frekvens i förmånsberäkning | cdm_benefitcalculationfrequency |
| Löneperiod med frekvens i förmånsberäkning | cdm_benefitcalculationfrequencypayperiod |
| Tariff för förmånsberäkning | cdm_benefitcalculationrate |
| Uppgift om tariff för förmånsberäkning | cdm_benefitcalculationratedetail |
| Förmånsalternativ | cdm_benefitoption |
| Förmånsplan | cdm_benefitplan (inte aktiverat för stöd för anpassade fält) |
| Förmånstyp | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Uppgiftsentiteter för affärsprocesser

| Namn | Register |
| --- | --- |
| Affärsprocesskalender | cdm_businessprocesscalendar |
| Tilldelning av affärsprocessgrupp | cdm_businessprocessgroupassignment |
| Affärsprocessbibliotekets uppgiftsgrupp | cdm_businessprocesslibrarytaskgroup |
| Affärsprocessfas | cdm_businessprocessstage |
| Checklistemallens rubrik | cdm_businessprocesstemplateheader |
| Checklistemallens uppgift | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Kompensationsregister

| Namn | Register |
| --- | --- |
| Fast kompensationsplan | cdm_compensationfixedplan |
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
| Arbetarens fasta kompensation | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Organisationsregister

| Namn | Register |
| --- | --- |
| Avdelning | cdm_department |
| Anställning | cdm_employment |
| Företag | cdm_company |
| Befattning | cdm_job |
| Jobbfunktion | cdm_jobfunction |
| Befattning | cdm_jobposition |
| Befattningstyp | cdm_positiontype |
| Befattningstilldelning för arbetare | cdm_positionworkerassignmentmap |
| Befattningsdimension | cdm_jobpositiondimension|
| Jobbtyp | cdm_jobtype |
| Språk | cdm_language |
| Namn | cdm_title |

> [!NOTE]
> Ekonomiska dimensioner för **Befattningstyp**, **Befattningstilldelning för arbetare** och **Anställning** ger integration med Dataverse i en riktning. Uppdateringar av ekonomiska dimensioner kan för närvarande inte synkroniseras från Dataverse till personal. 

## <a name="leave-and-absence-tables"></a>Tjänstledighets- och frånvaroregister

| Namn | Register |
| --- | --- |
| Transaktion för tjänstledighetsbank | cdm_leavebanktransaction |
| Anmälning om tjänstledighet | cdm_leaveenrollment |
| Tjänstledighetsplan | cdm_leaveplan |
| Begäran om tjänstledighet | cdm_leaverequest |
| Information om att lämna begäran | cdm_leaverequestdetail |
| Tjänstledighetstyp | cdm_leavetype |
| Ledighetstypens orsakskod | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Löneregister

| Namn | Register |
| --- | --- |
| Lönecykel | cdm_paycycle |
| Löneperiod | cdm_payperiod |
| Inkomstkod | cdm_payrollearningcode |
| Bankkontoutbetalningar | cdm_bankaccountdisbursement |
| Skatteregion | cdm_taxregion |

## <a name="worker-tables"></a>Medarbetarregister

| Namn | Register |
| --- | --- |
| Arbetare | cdm_worker |
| Adress för arbetare | cdm_workeraddress |
| Arbetarens personuppgift | cdm_workerpersonaldetail |
| Arbetsidentifieringsnummer | cdm_workerpersonidentificationnumber |
| Arbetsidentifieringstyp | cdm_workerpersonidentificationtype |
| Arbetskalender | cdm_workcalendar |
| Arbetsdagar i kalendern | cdm_workcalendarday |
| Helgdag i arbetskalender |cdm_workcalendarholiday |
| Arbetskalenderns datumrad | cdm_workcalendarholidayline |
| Tidsintervall till arbetskalendern | cdm_workcalendartimeinterval (inte aktiverat för stöd för anpassade fält) |
| Bankkonto för arbetare | cdm_workerbankaccount |

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

[Välja en dataintegreringsteknik](hr-admin-integration-choose-technology.md)<br>
[Konfigurera Dataverse-integrering](hr-admin-integration-common-data-service.md)<br>
[Konfigurera virtuella Dataverse-register](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Vanliga frågeställningar och svar om virtuella register i Personal](hr-admin-virtual-entity-faq.md)<br>
[Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Terminologiuppdateringar](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]