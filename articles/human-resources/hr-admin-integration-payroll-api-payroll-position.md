---
title: Löneuppgifter för Positioner
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för löneuppgifter för positioner i Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069817"
---
# <a name="payroll-position"></a>Lönebefattning


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för befattningar i Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollpositionentity.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller befattningsrelaterad information för en given medarbetare.

Fysiskt namn: mshr_payrollpositionentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | Beskrivning |
| --- | --- | --- |
| **Befattnings-ID**</br>mshr_positionid</br>*Sträng* | Skrivskydd | Befattningens ID. |
| **ID för lönecykel**</br>mshr_paycycleid</br>*Sträng* | Skrivskydd | Lönecykeln som definieras för befattningen. |
| **Ordinarie timmar per år**</br>annualregularhours</br>*Decimal* | Skrivskydd | Årligt antal regelbundna timmar som definierats för befattningen. |
| **Betalas av den juridiska personen**</br>paidbylegalentity</br>*Sträng* | Skrivskydd | Den juridiska person som definieras för den befattning som ansvarar för utfärdande av betalning. |
| **Giltig till**</br>validto</br>*Datum Tid Offset* | Skrivskydd | Det datum befattningsinformationen gäller till. |
| **Giltig från**</br>validfrom</br>*Datum Tid Offset* | Skrivskydd | Det datum befattningsinformationen gäller från. |
| **Primärt fält**</br>mshr_primaryfield</br>*Sträng* | Systemgenererad | Primärt fält. |
| **Entitets-ID för information om löneposition**</br>payrollpositiondetailsentityid</br>*Guid* | Obligatoriskt</br>Systemgenererat. | Ett systemgenererat globalt unikt ID (GUID) som identifierar befattningen unikt. |

## <a name="relations"></a>Relationer

| Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Inte tillämpligt |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Inte tillämpligt |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Svar**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
