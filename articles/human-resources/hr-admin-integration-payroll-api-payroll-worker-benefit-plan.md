---
title: Förmånsplaner för lönearbetare
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för förmånsplaner för lönearbetare i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1805f7efaf2efc48d5996776f3aa27d75606886f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068444"
---
# <a name="payroll-worker-benefit-plan"></a>Förmånsplaner för lönearbetare


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för förmånsplaner för lönearbetare i Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>beskrivning

Den här enheten innehåller information om förmånsplanen för en viss arbetare.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd</br>Obligatoriskt | Medarbetarens unika personalnummer. |
| **ID för juridisk person**</br>mshr_legalentityID</br>*Sträng* | Skrivskydd | Anger den juridiska personen (företaget). |
| **Period-ID**</br>mshr_periodid</br>*Sträng* | Skrivskydd | Identifieraren för period. |
| **Plan-ID**</br>mshr_planid</br>*Sträng* | Skrivskydd | Identifieraren för planen. |
| **Omfattningsalternativ**</br>mshr_coverageoptionid</br>*Sträng* | Skrivskydd | Identifiering av disponeringsalternativ. |
| **Startdatum för avdrag**</br>mshr_deductionstartdatetime</br>*Datum Tid Offset* | Skrivskydd | Startdatum för avdrag. |
| **Slutdatum för avdrag**</br>mshr_deductionenddatetime</br>*Datum Tid Offset* | Skrivskydd | Slutdatum för avdrag. |
| **Status**</br>mshr_status</br>*[Alternativuppsättning för förmån medarbetarplanstatus](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Skrivskydd | Status för förmånsplanen. |
| **Giltig från**</br>mshr_validfrom</br>*Datum Tid Offset* | Skrivskydd | Tidpunkten från vilken posten är giltig. |
| **Giltig till**</br>mshr_validto</br>*Datum Tid Offset* |  Skrivskydd | Tidpunkten till vilken posten är giltig. |
| **Plantyp-ID**</br>mshr_plantypeid</br>*Sträng* | Skrivskydd | Identifieraren för plantyp. |
| **Kod för plantyp**</br>mshr_plantypecode</br>*[alternativ för täckning av förmånsplan](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Skrivskydd | Specifikationen av plantypen. |
| **Antal betalningsperioder**</br>mshr_payperiod</br>*Heltal* | Skrivskydd | Antalet löneperioder som anger hur ofta förmånsleverantören eller medarbetarna betalas. Detta belopp kommer att användas för att beräkna medarbetarens årliga förmånsbelopp. |
| **Medarbetarbelopp**</br>mshr_amountemployee</br>*Decimal* | Skrivskydd | Anställdas belopp eller procentsats. |
| **Arbetsgivarbelopp**</br>mshr_amountemployer</br>*Decimal* | Skrivskydd | Anställdas belopp eller procentsats. |
| **Primärt fält**</br>mshr_primaryfield</br>*Sträng* | Systemgenererad | Primärt fält. |
| **Värde för arbets-ID** </br>_mshr_fk_worker_id_value</br>*GUID* | Sekundärnyckel: mshr_hcmworkerbaseentityid tillhörande entiteten mshr_hcmworkerbaseentity. | Systemgenererad, unik identifierare för arbetaren. |
| **Periodvärde-ID**</br> _mshr_fk_period_id_value</br>*GUID* | Utländsk nyckel: mshr_benefitperiodentityid för mshr_benefitperiodentity enhet. | Systemgenererad, unik identifierare för perioden. |
| **Värde för plan-ID**</br> _mshr_fk_plan_id_value</br>*GUID* | Utländsk nyckel: mshr_benefitplanentityid för mshr_benefitplanentity enhet. | Systemgenererad, unik identifierare för planen. |
| **Plan typ-ID värde**</br> _mshr_fk_plantype_id_value</br>*GUID* | Utländsk nyckel: mshr_benefitplantypeentityid för mshr_benefitplantypeentity enhet. | Systemgenererad, unik identifierare för planen. |
| **ID-värde för disponeringsalternativ**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Utländsk nyckel: mshr_benefitcoverageoptionentityid av mshr_benefitcoverageoptionentity enhet. | Systemgenererad, unik identifierare för planen. |
| **Id-värde för lönearbetares förmånsplan**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Skrivskydd </br> Systemgenererad | Systemgenererad, unik identifierare för posten. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Exempelfråga för Löneförmånsplan

**Begäran**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Svar**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
